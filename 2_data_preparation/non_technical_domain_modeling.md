<!-- markdownlint-disable MD013 -->
# Non-Technical Domain Modeling

## Context & Purpose

The Somali Health and Demographic Survey (SHDS) 2020 is the premier nationally representative source of health and demographic data in Somalia, collected between 2018 and early 2020 from over 100,000 households. It offers critical insights into maternal and neonatal health, reproductive health, nutrition, family planning, and child health outcomes across urban, rural, and nomadic communities in Somalia.

Our research leverages SHDS 2020 to address two key questions:

- How does FGM affect maternal and neonatal outcomes?
- What are the geographic hotspots of mortality and morbidity in Somalia, particularly among mothers and children under 5?

By using this dataset, we aim to quantify the associations between FGM and adverse maternal and newborn outcomes, and to map the health burdens of children under 5 across regions to inform targeted policy interventions.

## Main Concepts

The SHDS dataset includes real-world constructs represented in data variables. The main concepts relevant to our research include:

- **Maternal health:** Includes caesarean section history, fertility indicators such as number of children born, and number of children deceased. It also records healthcare access and utilization measures such as antenatal care (ANC) visits, skilled birth attendance, and postnatal care.

- **Female Genital Mutilation (FGM):** Covers prevalence, type (e.g., Type I–III), age at which the procedure was performed, and the person who performed it (e.g., traditional circumciser, healthcare worker).

- **Children under 5 health outcomes:** Includes mortality data, vaccination birth weight, and morbidity indicators such as fever, acute respiratory infection (ARI) symptoms, and diarrhea.

- **Geographic location:** regional data enabling analysis of subnational disparities and identification of hotspots.

- **Health service access:** metrics such as facility births, ANC visits, postnatal care (PNC), which act as mediating factors in outcomes.

- **Treatment Pathways** – whether care was sought, from where (government hospital, pharmacy, traditional healer, etc.), and what treatments were given (e.g., antibiotics, rehydration therapy, antimalarials).

## Relationships

- **Geographic variation:** Patterns of neonatal mortality and morbidity likely vary across regions, reflecting differences in healthcare access, socioeconomic conditions, and prevalence of FGM.

- **FGM → Maternal outcomes:** The practice of FGM, especially high-risk forms like Type III, is hypothesized to increase the likelihood of obstetric complications (e.g., obstructed labor, prolonged labour), which in turn elevate maternal mortality and increase caesarean section rates.

- **FGM → Neonatal outcomes:** Mothers with FGM may be more likely to have complications such as birth asphyxia or stillbirth, resulting in adverse neonatal outcomes including low APGAR scores and NICU admissions.

## Data Story

### Data Story 1 — FGM & Maternal/Neonatal Outcomes

In the SHDS, variables on FGM type, age at which it was performed, and who performed it can be linked with maternal health outcomes such as delivery method, birth complications, and neonatal health status.

Imagine Hodan, who was cut at age 3 (FGM Type III, performed by a traditional circumciser). Years later, during her first pregnancy, she experienced obstructed labor and required a C-section. Her baby girl was born with low birth weight (2.4 kg) but survived (recorded as “alive” in the dataset).
This individual case, when combined with hundreds of others in SHDS, allows researchers to examine whether severe forms of FGM are systematically associated with obstructed labor, C-sections, prolonged labor, stillbirths, or neonatal morbidity. The patterns that emerge can help highlight how FGM contributes to maternal and neonatal health risks in Somalia.

### Data Story 2 — The Morbidity & Mortality of Children Under 5

Somalia has one of the highest under-5 mortality rates globally, with 115 deaths per 1,000 live births. Most of these deaths are preventable and stem from conditions such as respiratory infections, diarrhea, measles, and complications from low birth weight and malnutrition. The Somali Health and Demographic Survey (SHDS) includes detailed child health indicators and geographic identifiers, making it possible to map where the risks are greatest.
Imagine Amina, a mother in a displaced settlement in southern Somalia. She gave birth to a baby boy, who was small at birth (reported as “smaller than average”). Two weeks later, the child developed diarrhea and a fever.
Amina sought help at a local pharmacy (recorded in H12K for diarrhea and H32K for fever/cough). She was advised to give oral rehydration solution (H13) but could not afford zinc supplements (H15E). For the fever, she received paracetamol (H37L) but no antimalarials or antibiotics.
Sadly, the child died at 20 days old (recorded in B6/B7). This case contributes to the dataset as:

- Morbidity symptoms present (diarrhea, fever)
- Treatment sought but incomplete
- Outcome: neonatal death (<1 month)
- Geographic context: IDP camp in southern region

When we combine many such stories, we begin to see patterns: for example, higher neonatal mortality in IDP camps, clusters of fever cases without proper treatment, or regions where children with diarrhea rarely receive zinc.
