# Data Analysis: Female Genital Mutilation (FGM) and Neonatal Health

## 1) Research Context

Female Genital Mutilation (FGM) remains highly prevalent in Somalia and is
suspected to contribute to adverse maternal and neonatal outcomes. This
analysis uses nationally representative survey data to quantify associations
between FGM severity and early-life outcomes, with a focus on delivery mode
and first‑month child mortality.

## 2) Research Question

How does the severity at which FGM is performed influence neonatal health
outcomes?

## 3) Data & Sample

● Source: Somalia Health & Demographic Survey (SHDS) 2020.
● File: Individual Recode (IR) — one record per ever‑married woman aged 12–49.
● Original format: SPSS (.sav), converted to CSV for analysis.
● Analytic sample: Ever‑married women with non‑missing FGM indicators and
  birth histories needed for outcomes.

### Key columns used

| Category | Code / Variable | Description |
|----------|----------------|-------------|
| **FGM Indicators** | G102A | FGM type (Sunn / Intermediate / |
| | | Pharaonic; "Don't know/Other" |
| | | dropped). |
| | G103 | Flesh removal (No / Yes). |
| | G104 | Genital nicking (No / Yes). |
| | G105 | Genital sewing / infibulation |
| | | (No / Yes). |
| **Delivery Mode** | M17$01 | Caesarean section at first birth |
| | | (1 = Vaginal, 2 = Caesarean). |
| **Child Survival /** | B5$01 – B5$05 | Birth status for first five births |
| **Mortality** | | (1 = Alive, 2 = Died). |
| | B7$01 – B7$05 | Age at death for first five births |
| | | (in months). |
| **Sociodemographic** | Residence | Urban / Rural / Nomadic. |
| **Covariates** | Wealth_quintile | Household economic status |
| | | quintiles. |
| | Place_category | Place of delivery (Health facility |
| | | vs Non-health facility). |
| | Age_first_birth | Age of mother at first birth. |

## 4) Data Preparation & Cleaning

● Dropped G102A categories "Don't know" and "Other".
● Constructed neonatal death proxy:
  ○ For each of the first five births, retained status as Died only if B5==2
    and corresponding B7<=1 month; otherwise recoded to Alive.
  ○ Aggregated to woman‑level variable any_child_died_first_month = 1 if
    any of the first five children died within 1 month.
● Built any_child_dead (0/1) for models that use the survey's first‑five
  births death indicator without restricting to ≤1 month (for
  robustness/secondary models).
● Excluded rows with missing values in variables required for each specific
  analysis.

## 5) Statistical Methods

● Descriptive cross‑tabs and visualizations (stacked bars, heatmaps) to
  examine distributions by FGM type and procedure.
● Chi‑square tests of independence for associations between categorical FGM
  indicators and outcomes:
  ○ (a) FGM type (G102A) × Caesarean at first birth (M17$01).
  ○ (b) Procedural indicators (G103, G104, G105) × neonatal death
    (woman‑level any_child_died_first_month).
● Logistic regression to estimate adjusted odds:
  ○ Model A: any_child_dead ~ C(G102A) (unadjusted for sociodemographics;
    establishes baseline association by FGM type).
  ○ Model B: any_child_dead ~ C(G105) + C(Wealth_quintile) + C(Residence)
    + C(Place_category) + Age_first_birth (adjusted for key covariates;
    isolates infibulation effect).

## 6) Results

### 6.1 FGM Type × Caesarean at First Birth

The chi-square test reveals a statistically significant association between
the type of Female Genital Mutilation (FGM) a woman experienced and the
likelihood of undergoing a caesarean section at her first birth. Women who
reported Pharaonic FGM exhibited a higher frequency of caesarean delivery
relative to other types, while those with Sunn or Intermediate forms showed
comparatively lower frequencies. This finding suggests that more severe forms
of FGM may contribute to obstructed or complicated deliveries that increase
the need for surgical intervention.

[![FGM Type vs Caesarean at First Birth](https://i.postimg.cc/zXJ6KhZs/1.png)

[![HeatMap FGM Type vs Caesarean at First Birth](https://i.postimg.cc/7P1j5Vc1/2.png)

**Key statistics:**

● Contingency table (FGM Type × Delivery Mode):
  ○ Intermediate: Vaginal = 1, Caesarean = 12
  ○ Pharaonic: Vaginal = 2, Caesarean = 82
  ○ Sunn: Vaginal = 6, Caesarean = 30
● Chi-square statistic: 8.17
● Degrees of freedom (df): 2
● p-value: 0.017 → statistically significant at the 5% level.
● Expected frequencies: distribution differs from expected under independence.
● Interpretation: We reject the null hypothesis — there is a significant
  association.

### 6.2 FGM Procedural Indicators × Neonatal Death ≤1 Month (Chi‑square)

We assessed whether specific procedural aspects of Female Genital Mutilation
(FGM) were associated with neonatal mortality (death within the first month
of life) across the first five births. Three procedural indicators were
tested: flesh removal (G103), genital nicking (G104), and genital sewing
(G105). Chi-square tests revealed significant associations for two of the
three indicators. Flesh removal (G103) showed a modest but significant link
with higher neonatal mortality, while genital sewing (G105) demonstrated a
strong and highly significant association. In contrast, genital nicking
(G104) did not appear to influence early child death. These results suggest
that the severity and invasiveness of the FGM procedure play a critical role
in newborn survival outcomes.

[![Grouped-Bar-Chart-Neonatal-Death](https://i.postimg.cc/wMkrnqJ4/3.png)

[![Flesh Removal vs Child Death](https://i.postimg.cc/d3FXWk7T/4.png)

[![Genital Nicking vs Child Death](https://i.postimg.cc/vmpCVSbh/5.png)

[![Genital Sewing vs Child Death](https://i.postimg.cc/d3FXWk7T/4.png)
*Heatmaps showing proportions of child death vs. procedure type.*

**Key statistics:**
● G103 (Flesh Removal):
  ○ χ² = 4.008, p = 0.045 → statistically significant.
  ○ Slightly higher neonatal deaths among children of mothers who underwent
    flesh removal.
● G104 (Genital Nicking):
  ○ χ² = 0.025, p = 0.873 → no significant association.
  ○ Rates of neonatal death similar regardless of exposure.
● G105 (Genital Sewing):
  ○ χ² = 9.788, p = 0.0018 → highly significant association.
  ○ Strongly elevated rates of neonatal death among children of mothers
    subjected to sewing.

**Inference:**

● Both flesh removal (G103) and especially genital sewing (G105) are linked
  to increased risk of early child mortality.
● Genital nicking (G104) has no detectable effect.
● The findings highlight that more invasive forms of FGM are particularly
  harmful for neonatal survival.

### 6.3 Logistic Regression Models Predicting Child Death

#### 1. Model with FGM Type (G102A)

**Objective:** To examine whether the type of FGM is associated with child
mortality (any of the first five children having died).

● Outcome: Any child death (binary).
● Predictors: FGM type (Pharaonic vs Sunn).
● Key results:
  ○ Overall model fit was statistically significant (LLR p = 0.0098, Pseudo
    R² = 0.027).
  ○ Sunn type FGM was significantly associated with lower odds of child
    death (OR = 0.30, 95% CI: 0.10–0.87, p = 0.026).
  ○ Pharaonic type FGM was not significantly different from the reference
    group.

**Interpretation:**
This model indicates that women who reported Sunn circumcision had
significantly lower odds of reporting child mortality compared to women with
other forms of FGM, suggesting that the less invasive Sunn practice may
carry fewer intergenerational health risks. However, the effect of Pharaonic
type was not statistically significant, though the direction of effect
suggested slightly lower odds of child death.

[![Predicted-Probability-FGM-Type](https://i.postimg.cc/VkZxYkh3/8.png))

[![Odds-Ratios-Forest-Plot](https://i.postimg.cc/MTVNbbGS/7.png)

#### 2. Model with Infibulation (G105) and Socio-Demographics

**Objective:** To assess whether infibulation (genital sewing, G105) is
linked to child mortality after adjusting for maternal and socio-economic
factors.

● Outcome: Any child death (binary).
● Predictors: G105 (infibulation), wealth quintile, residence, place of
  delivery, and maternal age at first birth.
● Key results:
  ○ Overall model was highly significant (LLR p = 0.00068, Pseudo R² =
    0.082).
  ○ Infibulation (G105): Strong and significant predictor → women with
    infibulation had 3.0 times higher odds of reporting child death (OR =
    2.99, 95% CI: 1.65–5.41, p < 0.001).
  ○ Residence: Rural women had significantly higher odds of child death
    compared to nomadic/urban groups (OR = 3.16, 95% CI: 1.13–8.86, p =
    0.028).
  ○ Wealth quintile, place of delivery, and age at first birth were not
    statistically significant.

**Interpretation :**
Infibulation (genital sewing) emerged as a major risk factor for child
mortality, even after adjusting for socio-economic and demographic variables.
The nearly threefold increase in odds underscores the severe reproductive
health consequences associated with this practice. Rural residence also
significantly heightened the risk of child death, reflecting disparities in
healthcare access and delivery. Other factors such as wealth and place of
delivery followed expected trends but were not statistically significant in
this model.

[![ROC-Curve-Model](https://i.postimg.cc/jSjV07MH/9.png)
*ROC curve of the model (showing AUC ≈ 0.70–0.75, depending on
calculation).*

## 9) Limitations

● Outcome construction relies on first five births and a derived ≤1 month
  criterion; true neonatal deaths beyond five births (or minor dating error)
  may be missed.
● Cross‑sectional associations cannot establish causality; unobserved
  confounding remains possible.
● Potential misclassification in self‑reported FGM type/procedure.
● Survey design effects may bias standard errors if not fully accounted for.

## 10) Policy & Practice Implications

The analysis indicates that infibulation (G105) is consistently associated
with higher odds of early child death and a higher need for caesarean
delivery, underscoring the severe obstetric burden of the most extreme FGM
form. The compounded risk for rural women highlights structural barriers to
timely, quality obstetric care.

**Action‑oriented bullets:**
● Prioritize elimination of infibulation within FGM abandonment programs.
● Expand skilled birth attendance and emergency obstetric care in rural
  settings.
● Strengthen antenatal screening for FGM complications and referral pathways
  for high‑risk pregnancies.
● Promote community education on obstetric risks of severe FGM forms.
