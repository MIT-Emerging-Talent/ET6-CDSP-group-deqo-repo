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
