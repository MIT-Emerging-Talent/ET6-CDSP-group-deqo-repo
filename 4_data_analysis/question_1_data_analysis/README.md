# Data Analysis: Under-Five Mortality and Morbidity Hotspot Detection

## 1) Research Context

Child mortality under the age of five remains a critical public health concern.
This analysis investigates whether geographic hotspots of child mortality exist in
Somalia, and explores how socio-demographic, morbidity, and healthcare factors  
contribute to survival outcomes.  

The study combines **exploratory data analysis**, **spatial clustering tests  
(Moran’s I)**, and **predictive modeling (logistic regression, XGBoost)** to  
assess risk patterns and determinants.  

---

## 2) Research Question

Are there geographic hotspots for children under five with respect to  
**mortality** and **morbidity**?  

---

## 3) Data & Sample

- **Population:** Children under five years of age.  
- **Exclusions:** Older children were dropped.  
- **Unit of analysis:** Individual child records.  
- **Aggregation level for spatial analysis:** Administrative regions.  

### Key variables used

| Category              | Variable(s)           | Description                   |
|-----------------------|---------------------|---------------------------------------------|
| **Mortality**         | B5                  | Child survival status(Alive / Dead).|
| **Age**               | Age_months          | Age of child at survey or death.|
| **Morbidity**         | Diarrhea, Fever, ARI| Past-two-week reported symptoms.|
| **Composite**         | sickness            | Binary = 1 if any of diarrhea,|
|                       |                     | fever, or ARI. |
| **Socio-demographic** | Education (V106),   | Mother’s background: education,|
|                       | Wealth (V190),      | wealth, and maternal age (V012).|
|                       | Maternal age (V012) |                               |
| **Healthcare**        | ANC, Place of birth | Care-seeking and service use.|
|                       | (M15), Response     |                               |
| **Spatial**           | Region (V024),      | Regional and urban/rural setting.|
|                       | Residence (V102)    |                               |
| **Derived**           | spatial_lag_mortality| Neighboring mortality rate|
|                       |                     | (queen contiguity).          |

---

## 4) Data Preparation & Cleaning

- Restricted dataset to children under five.  
- Constructed composite **sickness variable** (any morbidity).  
- Recoded uncertain ANC responses (“don’t remember/know”) as missing.  
- Aggregated mortality and morbidity to the **regional level** for mapping and  
  clustering.  
- Created **spatial lag variable** for mortality using queen contiguity.  

---

## 5) Statistical Methods

- **Exploratory descriptive summaries**: mortality by socio-demographic,  
  morbidity, and healthcare variables.  
- **Visualization**: choropleth maps of mortality and morbidity by region.  
- **Spatial autocorrelation**: Moran’s I for mortality and morbidity.  
- **Predictive models**:  
  - Logistic regression (baseline and weighted for class imbalance).  
  - XGBoost classifier (to capture nonlinearities).  
  - Regional logistic regression for hotspot areas.  

---

## 6) Results

### 6.1 Mortality by Socio-Demographic Variables

- Education showed **no clear relationship** with mortality.  
  - No education: 0.950  
  - Primary: 0.953  
  - Secondary: 0.965  
  - Higher: 0.963  
- Child age: majority of deaths occurred **before 20 months** of age.  

---

### 6.2 Morbidity and Composite Sickness

- Mortality correlated with reports of **diarrhea, fever, and ARI**.  
- Children marked as **sick** had higher mortality overall.  
- Composite *sickness* variable improved detection of associations.  

**Figure 1: Distribution of Age at Death**  
![Distribution of Age at Death B7](https://i.postimg.cc/KY6VkbW9/1.webp)

**Figure 2: Diarrhea vs Mortality**  
![Diarrhea vs Mortality](https://i.postimg.cc/76SRSc8q/2.webp)

**Figure 3: Fever vs Mortality**  
![Fever vs Mortality](https://i.postimg.cc/kG9pscqK/3.webp)

**Figure 4: ARI vs Mortality**  
![ARI vs Mortality](https://i.postimg.cc/PJ4FRw5c/4.webp)

**Figure 5: Sickness symptoms vs Mortality**  
![Sickness symptoms vs Mortality](https://i.postimg.cc/kMFZ4kvc/5.webp)

---

### 6.3 Health-Seeking and ANC Behaviors

- **Diarrhea treatment:** associated with higher survival.  
- **Fever and cough treatment:** paradoxically associated with higher mortality.
- **ANC timing:** inconsistent due to many missing or uncertain responses.  

---

### 6.4 Spatial Analysis

- **Mortality (Under 5):**  
  - Moran’s I = 0.303, p = 0.042 → **statistically significant clustering**.  
  - Interpretation: mortality is spatially clustered (hotspot regions).  

**Figure 6: Choropleth Map of Mortality Rates**  
![Morbidity map](https://i.postimg.cc/fT8r7mFS/6.webp)

- **Morbidity (Under 5):**  
  - Moran’s I = 0.110, p = 0.194 → **not significant**.  
  - Interpretation: morbidity is spatially random.  

**Figure 7: Choropleth Map of Morbidity Rates**  
![Mortality map](https://i.postimg.cc/fT8r7mFS/6.webp)

---

### 6.5 Logistic Regression (Baseline)

- Severe class imbalance: deaths ≈ 5%.  
- Standard logistic regression predicted mostly survival → poor recall.  
- Balanced logistic regression:  
  - Precision = 0.18  
  - Recall = 0.68  
  - Accuracy = 0.81  

**Coefficient insights:**  

- **Response:** Positive association with mortality (likely severity bias).  
- **Sickness:** Negative association with mortality (likely recall/timing).  
- **ANC:** Showed moderate influence.  
- **Spatial lag:** Strong predictor, consistent with clustering.  

---

### 6.6 XGBoost

- Improved slightly over logistic regression, but imbalance issue persisted.  
- Precision and recall remained low for deaths.  

---

### 6.7 Regional Model

- Focused on hotspot regions (e.g., Togdheer, Sool).  
- Same coefficient patterns as global model:  
  - Response positively linked to mortality.  
  - Sickness negatively linked.  
  - ANC retained influence.  

---

## 7) Interpretation of Counterintuitive Findings

- **Severity bias:** Children most sick are those taken for care → higher death
  risk.  
- **Survivorship bias:** Sickness recorded only for survivors → sickness appears
  protective.  
- **Late care-seeking:** Treatment may occur only when death is imminent.  
- **Access confounding:** Urban areas with facilities report both more care and
  more deaths.  

---

## 8) Limitations

- Mortality is rare, making estimates unstable.  
- Morbidity recall window (2 weeks) introduces noise.  
- Self-reported measures (ANC, sickness) are subject to bias.  
- Imbalanced data reduces predictive model performance.  

---

## 9) Policy & Practice Implications

- **Target mortality hotspots** (e.g., Togdheer, Sool) with intensive  
  interventions.  
- **Improve timely care-seeking** through community education.  
- **Strengthen neonatal and maternal services** (ANC, skilled birth attendance).
- **Use severity indicators** to better understand health-seeking dynamics.  
- **Invest in rural healthcare access** to address geographic disparities.  

---
