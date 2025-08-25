<!-- markdownlint-disable MD013 -->
# Data Preparation

> **Note:**  Data is confidential, therefore the notebooks aren’t fully reproducable as the data files are not provided within the repository.

## Question 1

> Are there  **geographic hotspots**  where  **neonatal mortality**  and  **morbidity**  cluster?

</aside>

To answer the research question, Variables were selected and categorized into these four categories:

1. Geographical location
2. Outcomes -> mortality & morbidity
3. Care Seeking Behavior
    1. Preventive dimensions -> Vaccinations
    2. Responsive dimensions -> Treatment and seeking help
    3. Exposure dimensions -> birth weight + ANC/PNC
4. Contextual/ Environmental Risk Factors

The data consists of **82 selected variables**  that are related to the previous categories.
Out of 83 total columns (82 selected variables + ID), **77 variables contained missing values**.

To manage missingness, variables were categorized by the percentage of missing data.

- **Low Missingness (≤5%)**: Considered negligible, generally left as-is or imputed minimally.
- **Moderate Missingness (5–10%)**: Evaluated for safe imputation strategies.
- **High Missingness (>10%)**: Required case-by-case assessment; often contextual or structural (e.g., skip patterns in survey).

### (5–10% Missingness)

#### Example: Variable **B5 (Child Alive or Dead at Time of Interview)**

- **Missingness:** 8%
- **Assessment:**
  - Records with missing B5 values also tended to be missing in other critical columns (e.g., sickness symptoms, ANC/PNC details, mother’s reported number of deceased children).
  - No geographic pattern or correlation with district was found.
- **Decision:**
  - Dropped rows with missing B5 values, as these cases were largely incomplete across multiple outcome-related variables.

> After dropping rows with missing values in **B5 (Child Alive/Dead)**, the total dataset size decreased, which reduced the relative proportion of missingness in other variables. Variables therefore were reassessed again for missingness

- **B8 (Current Age of Child, if alive)**
  - **Missingness:** ~5%
  - **Treatment:**
    - If child is **alive**: Imputed using the **mode** (most frequently reported current age).
    - If child is **dead**: Assigned value **“-1”** to explicitly indicate that current age is not applicable.
- **M18 (Size of Child at Birth)**
  - **Missingness:** ~6.7%
  - **Treatment:**
    - Imputed missing values with **“Don’t Know”**, which is a valid categorical response already present in the dataset.
    - This preserves interpretability and prevents introducing artificial bias by forcing numeric or derived imputations.

#### Consistency Checks on Mortality Variables

Before addressing variables with 10–30% missingness, I performed **consistency checks** on the mortality-related variables **B6 (Age at Death in Months)** and **B7 (Age at Death in Days)**.

- **Logic Applied:**
  - If **B5 = 1 (Child Alive)**, then **B6** and **B7** should not contain valid values.
- **Finding:**
  - For alive children (B5 = 1), both B6 and B7 were filled with `NaN`.
- **Action Taken:**
  - Assigned **“-1”** to both B6 and B7 whenever B5 = 1, to explicitly indicate “Not Applicable.”

This ensured consistency across survival and age-at-death variables.

> Following this step, **no variables with <10% missingness remain untreated**.

### Missingness Between 10–30% (Child Morbidity and Care-Seeking)

The next set of variables with moderate missingness (10–30%) were primarily related to **child morbidity (diarrhea, fever, respiratory symptoms)** and their associated **care-seeking and treatment** variables.

#### Diarrhea-Related Variables

- **H11 (Child had diarrhea in the last 2 weeks):**
  - Missing values replaced with **“8 = Don’t Know”**, to avoid assumptions of presence/absence.
- **Seeking Help & Treatment Variables (linked to diarrhea):**
  - If **H11 = NaN (child not reported for diarrhea)**, all associated help-seeking and treatment variables were encoded as **0 (Not Selected)** for consistency.

#### Fever-Related Variables

- **H22 (Child had fever in the last 2 weeks):**
  - Missing values replaced with **“8 = Don’t Know.”**
- **Help-Seeking & Treatment Variables (linked to fever):**
  - If H22 is missing, all related variables were encoded as **0 (Not Selected).**

#### Respiratory Symptoms (Cough, Short Rapid Breaths)

- **H31B (Short/Rapid Breathing) & H31C (Chest Problems/Blocked Nose):**
  - Missing values replaced with **“8 = Don’t Know.”**
- **Associated Care-Seeking Variables:**
  - If symptom variable was missing, treatment and care-seeking responses were set to **0 (Not Selected).**

> After this step, **all variables with missingness <30% were resolved.**

### Variables with >30% Missingness

Finally, I addressed 13 variables with **high missingness (54–90%)**, including:

- Child **vaccination records**
- Maternal **ANC/PNC care details**
- **Birth weight (in kg)**
- Maternal report of **number of sons/daughters deceased**

#### Decision

- Given their extremely high missingness, retaining these variables risked introducing noise, unreliable imputation, or loss of interpretability.
- Since alternative variables capturing **care-seeking behavior, birth conditions, and outcomes** were already included, dropping these variables would not jeopardize the analytic strategy.
- **Action:** All variables with >30% missingness were **dropped**.

> The final dataset is now **consistent, complete, and analysis-ready** for modeling geographic hotspots of neonatal mortality and morbidity.

______________________________________________________________________________________________

## Question 2

Female Genital Mutilation (FGM) and Neonatal Health Outcomes in Somalia  

## Research Context

This notebook documents the **data cleaning and preparation process** for analyzing the impact of Female Genital Mutilation (FGM) severity on neonatal health outcomes among Somali women.  

FGM remains a critical public health issue in Somalia, and understanding its relationship with neonatal outcomes provides valuable evidence for maternal and child health interventions.  

## Research Question  

**How does the severity at which FGM (Female Genital Mutilation) is performed influence neonatal health outcomes?**  

## Dataset Information  

- **Source:** Somalia Demographic and Health Survey (SHDS) 2020  
- **Population:** Ever-married women aged 12–49 years  
- **Record Type:** Individual Recode (IR) — one record per eligible woman  
- **Original Format:** SPSS (.sav) → Converted to CSV  

### Key Data Characteristics  

- **Survey Design:** Multi-stage cluster sampling with stratification  
- **Weighting:** Population-representative weights included (V005)  
- **Geographic Coverage:** National coverage across Somali regions  
- **Temporal Coverage:** Births and health events in the 5 years preceding the survey  

The dataset contains both:  

- **Single variables:** Demographics (age, education, wealth)  
- **Multiple variables:** Birth history, child health, contraceptive knowledge  

**Suffix notation**: `$01, $02, $03…` → multiple children/events per woman  
Example: `M70$01 = postnatal care for 1st birth`, `M70$02 = 2nd birth`  

## Variables of Interest  

- **FGM Practices:** Type, severity/extent, age at circumcision, performer  
- **Neonatal Health:** Child survival, age at death, delivery outcomes  
- **Maternal Factors:** C-section, parity, education, wealth  

## Data Cleaning Workflow  

### Step 1: Initial Data Inspection  

- Used **questionnaires** to identify variables relevant to FGM and neonatal health  
- Conducted **manual sorting** of raw SHDS variable lists  
- Applied **questioning and cross-checking** against the SHDS **data dictionary** to validate coding, variable meaning, and categorical responses  
- Loaded a sample (500–1000 rows) to inspect:  
  - Data types (categorical, numeric, datetime)  
  - Missing values and null-heavy columns  
  - Consistency with survey design (weights, stratification)  

### Step 2: Schema Definition & Selective Loading  

- Defined memory-efficient data types (`Int64`, `category`, `string`)  
- Loaded only relevant columns (FGM, neonatal outcomes, demographics)  
- Applied error handling for malformed rows during CSV conversion  

### Step 3: Cleaning & Standardization  

- Dropped irrelevant or unused categories (e.g., missing codes not in SHDS)  
- Normalized categorical values for consistency (e.g., standardizing FGM severity levels)  
- Converted date strings (births, child deaths) to `datetime64[ns]`  
- Applied **table-specific filtering** to include only:  
  - Women with valid FGM data  
  - Birth records with neonatal outcomes reported  

### Step 4: Output  
  
- Each cleaned dataset corresponds to one processing notebook in this repo
