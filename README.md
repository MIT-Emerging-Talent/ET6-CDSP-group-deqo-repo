<!-- markdownlint-disable MD033 -->
<!-- markdownlint-disable MD013 -->
# Deqo’s Project: Real-Time Health Data in Somalia

## **Emerging Talent 6 - Collaborative Data Science Project (CDSP)**

[![temp-Imagex-Nbboo.avif](https://i.postimg.cc/d0vP6cqs/temp-Imagex-Nbboo.avif)](https://postimg.cc/TKk42SLF)

This project is part of a collaborative data science initiative where we aim to create meaningful solutions aligned with pressing health needs in Somalia.

We are a team of aspiring data scientists designing a real-time health data platform that enables Somali health workers to input daily patient information, transforming it into live dashboards and maps. The system supports early outbreak detection, monitoring of chronic conditions, and informed resource allocation to underserved areas.

---

## 🌍 Project Overview

**Title:** Real-Time Health Data Platform for Somalia: Maternal and Child health (0–5 years)

**Summary:**
This project will investigate the status of maternal and child health (0–5 years) with a focus on neonatal health in Somalia. The study is divided into two main parts: the first examines maternal health in Somalia, while the second focuses on the health of children under five years of age. Together, these two components aim to provide a comprehensive understanding of the current challenges and opportunities for improving health outcomes for mothers and young children in Somalia.

## 🎯 Problem Identification

### Design Thinking Process

We began by exploring the state of healthcare in Somalia through statistical data and academic research, which revealed several critical areas of concern.

#### 🔹 Divergence (Exploration phase)

We began by exploring the available data on Somalia’s health status. Our initial challenge was Somalia’s long-standing data drought, where for nearly three decades little to no nationally representative health data was available. This gap was addressed by the Somalia Health and Demographic Survey (SHDS) 2020, which became a cornerstone resource, effectively ending this 30-year data drought.

Using the SHDS dataset, we carried out broad exploratory research into multiple dimensions of Somalia’s health, including:

- Maternal health and reproductive health outcomes

- Child health, particularly children under five

- Gender-based violence (GBV)

- Chronic diseases and non-communicable conditions

- Nutritional status and malnutrition patterns

Through this exploratory (divergent) process, we gained a wide understanding of Somalia’s key health burdens and identified major knowledge gaps.

#### 🔹 Convergence (Focusing phase)

After systematically reviewing these domains, we narrowed our focus to maternal and under 5 children health, given their persistently high mortality rates and the critical impact of practices such as female genital mutilation (FGM) on outcomes.
Hence we came up with these questions

---

#### 🔍 Research Focus

This research aims to:

- Assess the impact of FGM on maternal and neonatal outcomes in Somalia.
- Map and analyze national patterns and geographic hotspots of children under 5 mortality and morbidity throughout Somalia.

> 🔎 Check the [0_domain_study](./0_domain_study/) for more information
>

---

## Non-Technical Explanation of the Domain Model

The SHDS dataset includes real-world constructs represented in data variables. The main concepts relevant to our research include:

- Maternal health: Includes caesarean section history, fertility indicators such as number of children born, and number of children deceased. It also records healthcare access and utilization measures such as antenatal care (ANC) visits, skilled birth attendance, and postnatal care.

- Female Genital Mutilation (FGM): Covers prevalence, type (e.g., Type I–III), age at which the procedure was performed, and the person who performed it (e.g., traditional circumciser, healthcare worker)
Children under 5 health outcomes:Includes mortality data, vaccination birth weight, and morbidity indicators such as fever, acute respiratory infection (ARI) symptoms, and diarrhea.

- Geographic location: regional data enabling analysis of subnational disparities and identification of hotspots.

- Health service access: metrics such as facility births, ANC visits, postnatal care (PNC), which act as mediating factors in outcomes.

- Treatment Pathways – whether care was sought, from where (government hospital, pharmacy, traditional healer, etc.), and what treatments were given (e.g., antibiotics, rehydration therapy, antimalarials).

> 🔎 Check the [2_data_preparation/](./2_data_preparation/non-technical-domain-modeling.md) for more information
>

---

## 🏗️ Repository Structure

| File/Folder | Description |
|-------------|-------------|
| `README.md` | Overview and instructions |
| `guide.md` | Collaboration and development tips |
| `collaboration/` | Team norms, retrospectives, communication plans |
| `notes/` | Tutorials, tools, learning materials |
| `0_domain_study/` | Research on Somalia’s health context |
| `1_datasets/` | Raw and cleaned data |
| `2_data_preparation/` | Data cleaning/transformation scripts |
| `3_data_exploration/` | Initial summary statistics and plots |
| `4_data_analysis/` | Research question-focused analyses |
| `5_communication_strategy/` |  Message design, visuals, and strategy |
| `6_final_presentation/` | Slide decks, scripts, video demo |

---

## Team Introduction

Welcome! We are a large team of aspiring data scientists participating in the **ET6 CDSP**.

<table>
  <thead>
    <tr>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center;">
        <img src="https://github.com/abdoalsir.png" width="65" alt="Abdulrahman Alsir"><br>
        <strong>Abdulrahman Alsir</strong><br>
        <a href="https://github.com/abdoalsir">abdoalsir</a>
      </td>
      <td style="text-align: center;">
        <img src="https://github.com/AnaiMurillo.png" width="65" alt="Ana Isabel Murillo"><br>
        <strong>Ana Isabel Murillo</strong><br>
        <a href="https://github.com/AnaiMurillo">AnaiMurillo</a>
      </td>
      <td style="text-align: center;">
        <img src="https://github.com/aabukmail.png" width="65" alt="Aseel Abutair"><br>
        <strong>Aseel AbuKmail</strong><br>
        <a href="https://github.com/aabukmail">Aseel-AbuKmail</a>
      </td>
    </tr>
    <tr>
      <td style="text-align: center;">
        <img src="https://github.com/ciiyaa.png" width="65" alt="Ava Abdullah"><br>
        <strong>Ava Abdullah</strong><br>
        <a href="https://github.com/ciiyaa">ciiyaa</a>
      </td>
      <td style="text-align: center;">
        <img src="https://github.com/hectordacb.png" width="65" alt="Hector Colmenares"><br>
        <strong>Hector Colmenares</strong><br>
        <a href="https://github.com/hectordacb">hectordacb</a>
      </td>
      <td style="text-align: center;">
        <img src="https://github.com/MarthaNyekanga.png" width="65" alt="Martha Nyekanga"><br>
        <strong>Martha Nyekanga</strong><br>
        <a href="https://github.com/MarthaNyekanga">MarthaNyekanga</a>
      </td>
    </tr>
    <tr>
      <td style="text-align: center;">
        <img  src="https://github.com/mohd-makki.png" width="65" alt="Mohamed Makki"><br>
        <strong>Mohamed Makki</strong><br>
        <a href="https://github.com/mohd-makki">mohd-makki</a>
      </td>
      <td style="text-align: center;">
        <img src="https://github.com/misik-eng.png" width="65" alt="Muhammet Isik"><br>
        <strong>Muhammet Isik</strong><br>
        <a href="https://github.com/misik-eng">misik-eng</a>
      </td>
      <td style="text-align: center;">
        <img src="https://github.com/reunicorn1.png" width="65" alt="Reem Osama"><br>
        <strong>Reem Osama</strong><br>
        <a href="https://github.com/reunicorn1">reunicorn1</a>
      </td>
    </tr>
    <tr>
      <td style="text-align: center;">
        <img src="https://github.com/RafaaAli.png" width="65" alt="Rafaa Ali"><br>
        <strong>Rafaa Ali</strong><br>
        <a href="https://github.com/RafaaAli">RafaaAli</a>
      </td>
      <td style="text-align: center;">
        <img src="https://github.com/safaabuzaid.png" width="65" alt="Safaa Osman"><br>
        <strong>Safaa Osman</strong><br>
        <a href="https://github.com/safaabuzaid">safaabuzaid</a>
      </td>
      <td style="text-align: center;">
        <img src="https://github.com/Safi222.png" width="65" alt="Safia Adalla"><br>
        <strong>Safia Abdalla</strong><br>
        <a href="https://github.com/Safi222">Safi222</a>
      </td>
    </tr>
    <tr>
      <td style="text-align: center;">
        <img src="https://github.com/Solarahamza.png" width="65" alt="Solara Hamza"><br>
        <strong>Solara Hamza</strong><br>
        <a href="https://github.com/Solarahamza">Solarahamza</a>
      </td>
      <td style="text-align: center;"> <!-- Empty cell --> </td>
      <td style="text-align: center;"> <!-- Empty cell --> </td>
    </tr>
  </tbody>
</table>

<!-- markdownlint-disable MD013 -->
<!-- markdownlint-disable MD033 -->
