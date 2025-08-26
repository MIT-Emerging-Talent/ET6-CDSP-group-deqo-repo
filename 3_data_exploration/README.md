<!-- markdownlint-disable MD013 -->
# Data Exploration

## Question 1
>
> Are there geographic hotspots where childs mortality and morbidity cluster?
>
### Data Overview

The dataset was loaded and inspected. It contains demographic, health, and outcome information about children and their families across multiple regions of Somalia. The inspection process confirmed the dataset’s size, completeness, and variable distribution.

### Exploration & Analysis

#### 2. Demographic & Background Exploration

The dataset includes children from multiple regions, with the distribution across regions showing noticeable variation.

- **Banadir**  (region 22) had the highest number of children, with 2,119 (≈10.9% of the total).
- **Bay**  (region 24) had the lowest number, with 429 children (≈2.2%).

This indicates some regions are more represented in the dataset than others.
[![Screenshot-2025-08-25-at-2-56-11-PM.png](https://i.postimg.cc/HkWnWSbp/Screenshot-2025-08-25-at-2-56-11-PM.png)](https://postimg.cc/bsMp396M)

##### Mother’s Education

- The majority of mothers had  **no formal education (83.5%)**.
- Mothers with primary education represented 12.3%.
- Secondary education: 3.1%.
- Higher education: 1.1%.

This distribution highlights a  **low overall education level**  among mothers in the sampled population, which may influence health-seeking behavior and child outcomes.

> **Conclusion:**  The dataset shows regional variation in the number of children, with Banadir most represented, and a low educational level among mothers, which could be important for interpreting neonatal mortality and morbidity patterns.

[![Screenshot-2025-08-25-at-2-56-36-PM.png](https://i.postimg.cc/L5Z47wdT/Screenshot-2025-08-25-at-2-56-36-PM.png)](https://postimg.cc/ct0NtDLg)

#### 3. Child Characteristics

##### Summary Results

**1. Current Age:**

- Mean age: 2.3 years (min: 0, max: 6).
- Most common age: 2 years (~3,500 children).
- Next most common: 3 and 4 years.

**2. Age at Death (for deceased children):**

- Mean age at death: 4.9 months.
- Minimum: 0 months, Maximum: 96 months.

**3. Size at Birth:**

- Average: 57.8%
- Smaller than average: 5.5%
- Very small: 5.8%
- Larger than average: 3.95%
- Don’t know: 21.8%

**4. Gestational Age at First ANC Visit:**

- No antenatal care: ~6,000 women.
- After 8th month: 281 women.

----------

#### 4. Mortality Exploration

##### Mortality Results

- Alive: 18,542 children (95.1%).
- Dead: 949 children (4.9%).

**Among deceased:**

- Neonatal (<1 month): 4.3%
- Infant (1–11 months): 79.35%
- Child (1–5 years): 15.7%
- Above 5 years: 0.6%

----------

#### 5. Illness Symptoms Exploration

- Diarrhea: 4.8% of children in the last 2 weeks.
- Fever: 5.6%.
- Cough: 6.5%.
- Breathing problem:
  - 2.3% chest only problems.
  - 1.4% nose only.
  - 1.05% both.
  - 0.02% other problems.

----------

#### 6. Health-Seeking Behaviour

The dataset also tracked how families responded when children showed symptoms of illness. Health-seeking behavior included whether care was sought from health facilities, traditional healers, or not at all. Although details are better illustrated with figures, preliminary exploration shows  **low formal healthcare utilization**  relative to symptom prevalence, suggesting access or awareness challenges.

[![Screenshot-2025-08-25-at-2-57-46-PM.png](https://i.postimg.cc/mDPFLdfc/Screenshot-2025-08-25-at-2-57-46-PM.png)](https://postimg.cc/HcCL39LH)

#### 7. Counts and Rates by Region/District

Exploration by region and district revealed disparities in mortality and morbidity counts. Some districts exhibited higher-than-average rates, potentially linked to socioeconomic or healthcare access differences.

#### 8. Urban vs Rural Differences

Urban children had slightly better outcomes compared to rural children, reflecting disparities in healthcare access, maternal education, and infrastructure availability.

#### 9. Morbidity Hotspots

Certain geographic clusters emerged as morbidity hotspots, particularly where diarrheal and fever cases were concentrated. These may warrant further investigation into environmental or infrastructural causes.

[![Screenshot-2025-08-25-at-3-00-14-PM.png](https://i.postimg.cc/ZR4DXy1D/Screenshot-2025-08-25-at-3-00-14-PM.png)](https://postimg.cc/qtDL3gB8)

#### 10. Treatment vs Mortality

Preliminary analysis suggested no evident relationship between treatment-seeking behavior and survival. But there might be a relationship between ANC coverage and mortality.

[![Screenshot-2025-08-25-at-3-02-57-PM.png](https://i.postimg.cc/rF3ZMHB4/Screenshot-2025-08-25-at-3-02-57-PM.png)](https://postimg.cc/1f0rKv5R)
[![Screenshot-2025-08-25-at-3-01-56-PM.png](https://i.postimg.cc/6QLMVpyV/Screenshot-2025-08-25-at-3-01-56-PM.png)](https://postimg.cc/mck3BR3h)

#### 11. Education vs Mortality

Here doesn’t seem to be a simple, clear-cut relationship you can extract directly from this chart. Any analysis would need to account for **regional context** and possibly other covariates before concluding anything about education’s effect.

[![Screenshot-2025-08-25-at-3-04-37-PM.png](https://i.postimg.cc/FFnDVqs6/Screenshot-2025-08-25-at-3-04-37-PM.png)](https://postimg.cc/7b03xKz1)

## Question 2
>
>**How does the severity at which FGM (Female Genital Mutilation) is performed influence neonatal health outcomes?
>
### Key Variables Explored

#### 1. Neonatal Health Outcomes

##### Child Survival Status (B5$01 - B5$20)

Indicates whether each child was alive or dead at interview time> 
Encoding: 1 = "Alive", 2 = "Dead"> 
Observations: Data becomes sparse for higher birth orders (B5$15+). 
[![1-alive-or-dead.png](https://i.postimg.cc/L5h8TPr2/1-alive-or-dead.png)](https://postimg.cc/zHZNDyzc)

##### Age at Death (B6$01 - B6$20, B7$01 - B7$20)

B6: Age at death with coded units (1=days, 2=months, 3=years). 
B7: Age at death in completed months. 
Data Processing: Converted B6 values to days for consistency. 
Issues: Some unrealistic values (>3 years) treated as outliers. 
[![3-age-distribution.png](https://i.postimg.cc/9fnmf0Dk/3-age-distribution.png)](https://postimg.cc/XZ9SHVcK)

[![2-age-correlation.png](https://i.postimg.cc/MKVvr7np/2-age-correlation.png)](https://postimg.cc/gnczx6yC)

#### 2. Delivery Characteristics

##### Caesarean Section Delivery (M17$01 - M17$20)

Indicates C-section delivery for each birth. 
Encoding: 1 = "Yes", 2 = "No". 
Purpose: Proxy indicator for delivery complications. 
[![4-caesarean-vs-non-cs.png](https://i.postimg.cc/bJmQrQxh/4-caesarean-vs-non-cs.png)](https://postimg.cc/mzFc61pX)

#### 3. FGM Severity Measures

##### Circumcision Status (G102)

Whether respondent has been circumcised. 
Encoding: 1 = "Yes", 2 = "No". 
Finding: High prevalence of FGM among respondents. 
[![5-respondent-cirumcisin.png](https://i.postimg.cc/sxBZ2bfY/5-respondent-cirumcisin.png)](https://postimg.cc/jnbjgg72)

##### Type of Circumcision (G102A) - Primary Severity Indicator

Classification of FGM type
Categories:

1 = Sunni
2 = Intermediate
3 = Pharaonic
4 = Don't Know
5 = Other

Key Observation: Pharaonic type appears common in the dataset. 
[![6-types-of-circumstion.png](https://i.postimg.cc/pTm62Xjq/6-types-of-circumstion.png)](https://postimg.cc/zb1j7N0g)

##### Procedure Details (G103 - G105)

G103: Flesh removed from genital area (1 = "Yes"). 
G104: Genital area just nicked without removing flesh (1 = "Yes"). 
G105: Genital area sewn closed (1 = "Yes"). 
Purpose: Provides specific procedure information to assess severity. 
[![7-disterbution-of-circ.png](https://i.postimg.cc/Zqt89bXw/7-disterbution-of-circ.png)](https://postimg.cc/pmCh4HWj)

##### Age at Circumcision (G106)

Age when FGM was performed. 
Special Codes: 95 = "Baby", 98 = "Don't Know". 
Format: Years for numeric values. 
[![8-age-of-circum.png](https://i.postimg.cc/jjbfx8J9/8-age-of-circum.png)](https://postimg.cc/75KhXn9M)

##### Practitioner Type (G107)

Who performed the circumcision procedure. 
Categories: Traditional vs. medical practitioners (specific mapping needed). 
[![10-who-preformed-circumcision.png](https://i.postimg.cc/0Nhy5j3N/10-who-preformed-circumcision.png)](https://postimg.cc/gwqWNzG9)

#### 4. Maternal Demographics

##### Number of Living Children (V218)

Total living children at time of interview. 
Purpose: Provides context on maternal parity. 
[![9-no-of-living-children.png](https://i.postimg.cc/MTGvHgZs/9-no-of-living-children.png)](https://postimg.cc/jWGskg7N)

Data Quality Assessment
Missing Data Patterns

[![11-heatmap.png](https://i.postimg.cc/TYkGYh5X/11-heatmap.png)](https://postimg.cc/1fNbvmKW)

Higher birth orders (15+ children) show expected sparsity. 
Some respondents have incomplete FGM procedure details. 
Age at death variables show missing values for surviving children (expected). 
[![12-disturbition-of-no-of-living-children.png](https://i.postimg.cc/1587wzYS/12-disturbition-of-no-of-living-children.png)](https://postimg.cc/RNzTzvBp)

Data Integrity Issues

Some unrealistic age at death values identified
Inconsistencies between different FGM severity measures require investigation
Special codes (95, 98) need proper handling in analysis

#### Key Findings from Exploration

- High FGM Prevalence: Majority of respondents report being circumcised
- Severity Distribution: Pharaonic type appears to be commonly reported
- Neonatal Mortality Present: Deaths recorded across different birth orders
- Data Structure: Birth history data shows expected pattern with decreasing completeness for higher parities
