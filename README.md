# 🏥 Healthcare Claim Denial Analysis

## Project Overview

This is an end-to-end healthcare business analytics project that investigates outpatient claim denials and identifies operational opportunities to reduce preventable revenue loss.

The project combines Python-based data auditing, data cleaning, exploratory data analysis (EDA), business analytics, and Tableau visualization to transform simulated healthcare operational data into actionable business insights.

The analysis focuses specifically on insurance eligibility and front-end registration issues, with additional drill-down analysis by department, payer group, denial reason, and financial impact.

The final deliverable includes an interactive Tableau dashboard designed to support operational monitoring and denial-reduction decision-making.

---

## Business Problem

Claim denials are a major challenge in healthcare revenue cycle management. They delay reimbursement, increase administrative rework, and negatively affect financial performance.

Many denials can originate before a claim is submitted. Front-end issues such as incorrect primary insurance selection, inactive coverage, incomplete eligibility verification, member identification errors, and subscriber information mismatches may result in claims that require correction or rework.

The central business question for this project is:

> **Which front-end insurance and registration issues create the greatest denial exposure, where are those issues concentrated, and which operational interventions should be prioritized?**

Rather than evaluating denial rate alone, the analysis considers denial frequency, department-level variation, payer differences, and financial exposure to identify the highest-impact improvement opportunities.

---

## Project Objectives

The objectives of this project are to:

- Audit and clean simulated healthcare operational data.
- Measure overall claim denial performance.
- Identify the most common preventable front-end denial drivers.
- Evaluate denial patterns across clinical departments.
- Examine payer-specific denial differences.
- Quantify the financial impact of different front-end issues.
- Distinguish high-rate problems from high-volume problems.
- Translate analytical findings into targeted operational recommendations.
- Develop an interactive Tableau dashboard for denial monitoring and investigation.

---

## Dataset

This project uses a simulated outpatient healthcare dataset containing **2,500 patient encounters** from **July 2025 through June 2026** across five clinical departments:

- Cardiology
- Primary Care
- Orthopedics
- Imaging
- OB/GYN

The dataset contains operational fields including:

- Encounter ID and encounter date
- Clinical department
- Visit type
- Insurance payer group
- Front-end registration issue
- Real-time eligibility (RTE) status
- Coordination of Benefits (COB) review status
- Pre-registration completion
- Coverage status
- Claim denial status
- Denial reason
- Denied amount

All data used in this project is simulated for portfolio demonstration purposes. No real patient information or protected health information (PHI) is included.

---

## Project Workflow

```text
Business Problem
      ↓
Data Audit
      ↓
Data Cleaning
      ↓
Exploratory Data Analysis
      ↓
Denial Driver Analysis
      ↓
Department & Payer Drill-Down
      ↓
Financial Impact Analysis
      ↓
Business Insights
      ↓
Operational Recommendations
      ↓
Tableau Dashboard
```

---

# Key Findings

## 1. Most denials were linked to preventable front-end issues

Out of 2,500 encounters, 298 claims were denied, giving an overall denial rate of **11.9%** and a total denied amount of **$112,807**.

What stood out most was that **83.9% of denied claims were associated with preventable front-end issues**.

The two largest issues were:

- **Incorrect Primary Insurance:** 87 denials
- **Inactive Coverage:** 80 denials

Together, they accounted for **56.0% of all denied claims** and about **55.2% of total denied dollars**.

This was the clearest finding in the project. More than half of the denial problem was concentrated in just two insurance-related front-end issues.

---

## 2. The department with the highest denial rate was not the department with the most denials

Cardiology had the highest denial rate at **14.7%**, while OB/GYN had the lowest at **9.0%**.

However, Primary Care had the largest number of denied claims, with **108 denials**.

This matters because looking only at denial rate can be misleading.

Cardiology appears to be the highest-risk department by rate, while Primary Care may offer a larger opportunity to reduce the total number of denials because of its higher encounter volume.

---

## 3. The main denial drivers were different across departments

The department drill-down showed that the same front-end issues did not affect every department in exactly the same way.

For example:

- In **Cardiology**, Incorrect Primary Insurance and Inactive Coverage together accounted for **34 of 60 denials**.
- In **Orthopedics**, those same two issues accounted for **29 of 44 denials**.
- In **Imaging**, Incorrect Primary Insurance alone accounted for **16 of 38 denials** and about **$8,053 in denied amount**.

This means the overall dashboard is useful for identifying the biggest problems, but department-level analysis is still needed before deciding what kind of process improvement would be most useful.

---

## 4. Denial count and financial impact do not always tell the same story

The most common denial issues generally also created the largest total denied amounts.

However, some lower-volume issues still had meaningful financial impact.

For example, Subscriber Demographic Mismatch occurred less often than the major denial categories, but its average denied amount was approximately **$441 per claim**.

Because of this, I would not prioritize denial problems based only on how often they occur. Denial count and denied dollars should be reviewed together.

---

# Business Recommendations

## 1. Focus first on primary insurance and active coverage

Incorrect Primary Insurance and Inactive Coverage were responsible for more than half of both denied claims and denied dollars.

These two issues would be my first priority for process improvement.

Possible actions include:

- confirming primary and secondary insurance order during registration,
- verifying active coverage before the visit,
- and creating a clear follow-up process for coverage that cannot be verified.

The goal would be to catch these problems before the claim reaches billing.

---

## 2. Use both denial rate and denial volume when deciding where to intervene

Cardiology had the highest denial rate, but Primary Care had the largest number of denied claims.

For that reason, I would not rank departments using denial rate alone.

A department-level review should consider:

- denial rate,
- number of denied claims,
- and denied amount.

This gives a more complete picture of where improvement could have the largest effect.

---

## 3. Use department-specific follow-up instead of one general training approach

The department analysis showed different denial patterns across departments.

For example, Imaging had a particularly strong concentration of Incorrect Primary Insurance denials.

Rather than giving the same training to every department, I would use the dashboard to identify the dominant issue in each department and then review that specific part of the registration workflow.

For Imaging, that would mean looking closely at how primary insurance is selected and confirmed during scheduling or registration.

---

## 4. Track financial impact together with denial frequency

High-frequency problems deserve attention, but lower-frequency problems should not automatically be ignored.

I would include both claim count and denied dollars in ongoing denial monitoring so that a smaller category with relatively high financial impact is still visible.

This would make the dashboard more useful for deciding which problems are worth investigating first.

---

# Tableau Dashboard

The Tableau workbook was designed to support both executive-level monitoring and detailed operational investigation.

## Overview Dashboard

The Overview dashboard summarizes:

- Total denied amount
- Overall denial rate
- Preventable denial percentage
- Monthly denial-rate trend
- Denial rate by department
- Denial rate by front-end issue
- Financial impact by front-end issue

![Overview Dashboard](images/Overview.png)

---

## Department Analysis

The Department Analysis dashboard allows users to select a clinical department and investigate:

- Department denial rate
- Department denied claims
- Department denied amount
- Denial rate by front-end issue
- Denied claims by denial reason
- Financial impact by front-end issue
- Denial rate by payer group

This drill-down view helps distinguish organization-wide patterns from department-specific operational risks.

![Department Analysis](images/Primary_care_Analysis.png)

---

## Raw Data Investigation

The Raw Data dashboard provides encounter-level records and interactive filters for:

- Front-end issue
- Denial reason
- Department
- Month

This allows analysts or operational users to move from aggregated dashboard findings to the underlying encounter records for further investigation.

![Raw Data](images/Rawdata.png)

---

## Data Dictionary / Glossary

The Tableau workbook also includes a glossary describing report parameters, field definitions, metrics, and report navigation.

![Glossary](images/Glossary.png)

---

# Repository Structure

```text
healthcare-claim-denial-analysis/
│
├── data/
│   ├── raw_encounters.csv
│   └── cleaned_encounters.csv
│
├── notebooks/
│   ├── 01_Data_Audit_Cleaning.ipynb
│   └── 02_EDA.ipynb
│
├── images/
│   ├── Overview.png
│   ├── Department Analysis.png
│   ├── Rawdata.png
│   └── Glossary.png
│
├── tableau/
│   └── insurance_eligibility_denial_analysis.twbx
│
└── README.md
```

---

# Tools Used

- **Python** — data preparation and analysis
- **Pandas** — data cleaning, transformation, and aggregation
- **NumPy** — numerical operations
- **Matplotlib** — exploratory visualization
- **Jupyter Notebook** — data audit, cleaning, and EDA documentation
- **Tableau** — interactive business intelligence dashboard
- **GitHub** — project documentation and version control

---

## Limitations

This project uses simulated data designed for portfolio demonstration and does not represent the performance of any real healthcare organization.

The analysis identifies associations and operational patterns within the simulated dataset but does not establish causal relationships between specific workflows and claim denials.

Recommendations should therefore be interpreted as areas for operational investigation and process improvement rather than confirmed causal interventions.

---

## Conclusion

The analysis shows that denial exposure is not evenly distributed across front-end issues, departments, or payer groups.

More than half of all denied claims and denied dollars are concentrated in just two front-end issues: **Incorrect Primary Insurance and Inactive Coverage**.

At the same time, department-level analysis demonstrates that operational priorities differ depending on whether the objective is to reduce denial rate, denial volume, or financial exposure.

The findings support a targeted denial-management strategy that combines organization-wide prioritization of major front-end issues with department- and payer-specific workflow investigation.
