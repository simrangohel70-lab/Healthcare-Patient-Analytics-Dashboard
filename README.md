<div align="center">

# 🏥 Healthcare Patient Analytics Dashboard

**An interactive Power BI report that turns 55,500 raw patient records into clear insights on conditions, hospitals, insurance and billing.**

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Power Query](https://img.shields.io/badge/Data%20Prep-Power%20Query-217346?style=for-the-badge)
![DAX](https://img.shields.io/badge/Calculations-DAX-CC0000?style=for-the-badge)
![Records](https://img.shields.io/badge/Records-55%2C500-0078D4?style=for-the-badge)
![Status](https://img.shields.io/badge/Project-Completed-success?style=for-the-badge)

<br>

<img width="1321" height="737" alt="image" src="https://github.com/user-attachments/assets/2566961a-d844-48e9-a5b5-5198e87310d0" />



<br><br>


</div>

---

## 📑 Table of Contents

- [Project Overview](#-project-overview)
- [Video Demonstration](#-video-demonstration)
- [Dashboard Preview](#-dashboard-preview)
- [Key Features](#-key-features)
- [Data Preparation (Power Query)](#-data-preparation-power-query)
- [Data Model and Summary Tables](#-data-model-and-summary-tables)
- [Visuals Used](#-visuals-used)
- [Key Insights](#-key-insights)
- [Tools and Technologies](#️-tools-and-technologies)
- [Repository Structure](#-repository-structure)
- [How to Use](#-how-to-use)
- [Learning Outcomes](#-learning-outcomes)


---

## 📌 Project Overview

The **Healthcare Patient Analytics Dashboard** is a 4-page Power BI report built on a healthcare dataset of **55,500 patient records**. It helps a user answer questions such as:

- Which medical conditions have the most patients?
- Which hospitals bring in the most billing revenue?
- How do billing amounts differ by insurance provider and department?
- How do admissions change month by month and year by year?

The project covers the full analytics workflow: **loading data, cleaning and transforming it in Power Query, building summary tables, designing visuals, and adding interactive slicers and filters.**

---

## 🎥 Video Demonstration

Watch the full walkthrough of the dashboard and the Power Query steps:

<div align="center">

<!-- Tip: take a screenshot of your video's first frame, save it as images/video-thumbnail.png -->
[![Watch the project video] https://drive.google.com/file/d/1sC4ReI0DzASuTv7AGZe6cqkt99XRngmM/view?usp=sharing


</div>

> **Note:** In Google Drive, right-click the video, choose **Share**, and set access to **Anyone with the link → Viewer**, so everyone can open it.

---

## 📊 Dashboard Preview


### 📊 Dashboard Overview
KPI cards, patients by medical condition, top hospitals by revenue, monthly admissions trend and insurance mix, with slicers for Admission Type, Medical Condition and Admission Year.

<img width="1321" height="726" alt="image" src="https://github.com/user-attachments/assets/d948b593-0184-4f13-8613-10607bc54234" />

### 📋 Patient Detail
A detailed table of patient records with age category, department, stay category, billing and risk flag, filterable by medical condition and admission type.

<img width="1320" height="736" alt="image" src="https://github.com/user-attachments/assets/b5b282ad-c814-4bd7-ac19-95e06bda2857" />


### 💰 Billing Analysis
Average billing by department and billing tier, plus a matrix of total billing by medical condition and insurance provider.

<img width="1343" height="733" alt="image" src="https://github.com/user-attachments/assets/0628a6e2-1094-4613-8bda-c1a9a9e0c6c2" />

---

## ✨ Key Features

- **4-page report:** Home, Dashboard Overview, Patient Detail and Billing Analysis.
- **KPI cards:** Total Patients, Total Billing, Average Billing per Patient and Average Length of Stay.
- **Interactive slicers:** Admission Type (tiles), Medical Condition (dropdown) and Admission Year (range slider).
- **Cross-filtering:** clicking one condition or admission type updates the charts together.
- **Smart filters:** page-level filter on Age Category and visual-level filters on key charts.
- **Dynamic parameters:** `MinAge` and `AdmissionType` parameters for flexible filtering.
- **Consistent design:** red and white theme, aligned visuals, clear titles and subtitles.

---

## 🗂️ Dataset

| Item | Details |
|---|---|
| Main file | `healthcare_dataset.csv` |
| Lookup file | `Condition_Dept_Lookup.csv` (maps each Medical Condition to a Department) |
| Records | 55,500 patients |
| Source | Kaggle Healthcare Dataset (synthetic data) |

**Original columns (15):** Name, Age, Gender, Blood Type, Medical Condition, Date of Admission, Doctor, Hospital, Insurance Provider, Billing Amount, Room Number, Admission Type, Discharge Date, Medication, Test Results.

---

## 🧹 Data Preparation (Power Query)

All cleaning was done in **Power Query Editor** and every Applied Step was given a clear name.

### Data quality problems found

| Problem | How it was found | Fix |
|---|---|---|
| Negative values in Billing Amount | Column Profile (min value below zero) | New column `Billing_Amount_Fixed` using `Number.Abs`, then the original column was removed |
| Mixed capital letters in names (e.g. `Bobby JacksOn`) | Column Distribution on Name | Capitalize Each Word, Trim and Clean |
| Inconsistent hospital names | Column Distribution | Converted to UPPERCASE |

### Transformations

| Step | What was done |
|---|---|
| Text cleaning | Proper case for Name and Doctor, UPPERCASE for Hospital, Trim and Clean |
| Billing columns | Added `Billing_Amount_Fixed` and `Billing_Rounded`, removed original `Billing Amount` |
| Date columns | Changed to Date type, extracted `Admission_Year`, `Admission_Month` and `Admission_Month_Num` |
| Length of stay | Added `Length_of_Stay_Days` = Discharge Date − Date of Admission |
| Index | Added `Patient_ID` (unique ID for every patient) |
| Conditional columns | `Age_Category`, `Billing_Tier`, `Stay_Category`, `Risk_Flag` |
| Merge | Left Outer Join with `Condition_Dept_Lookup` to add the `Department` column |
| Parameters | `MinAge` (default 18) and `AdmissionType` (default All) used in filter steps |

### New columns and their rules

| Column | Rule |
|---|---|
| `Age_Category` | 65 and above = Senior, 18 and above = Adult, otherwise Minor |
| `Billing_Tier` | 40,000+ = Platinum, 25,000+ = Gold, 10,000+ = Silver, otherwise Standard |
| `Stay_Category` | 20+ days = Long Stay, 10+ = Medium Stay, 3+ = Short Stay, otherwise Day Case |
| `Risk_Flag` | Abnormal = High Risk, Inconclusive = Monitor, otherwise Low Risk |


---

## 🧩 Data Model and Summary Tables

| Query | Built using | Purpose |
|---|---|---|
| `healthcare_dataset` | Main query | Cleaned patient-level table |
| `Condition_Dept_Lookup` | CSV import | Condition to Department mapping |
| `Condition summary` | Reference + Group By | Patient count, average billing and average stay by condition |
| `Hospital Summary` | Reference + Group By | Patients and total revenue by hospital |
| `Insurance summary` | Reference + Group By | Covered patients and claims by insurance provider |
| `Monthly Admission` | Reference + Group By | Monthly admissions for the trend chart |
| `Condition pivot` | Pivot / Unpivot | Admission type counts per condition |
| `Admissions_Pre2022`, `Admissions_2022Plus`, `Admissions_Full` | Filter + Append | Splitting and re-combining data by year |

Power Query features practiced: **Import mode, column profiling, Reference, Group By, Merge, Pivot, Unpivot, Append, Folder connector, Data Source Settings and Parameters.**

---

## 📈 Visuals Used

| Visual | Shows |
|---|---|
| Card | Total Patients, Total Billing, Average Billing, Average Length of Stay |
| Clustered bar chart | Patients by Medical Condition |
| Clustered bar chart | Top 10 Hospitals by Total Billing Revenue |
| Line chart | Monthly Patient Admissions by Year |
| Donut chart | Patient distribution by Insurance Provider |
| Table | Patient detail records |
| Clustered column chart | Average billing by Department and Billing Tier |
| Matrix | Total billing by Medical Condition and Insurance Provider |
| Slicers | Admission Type, Medical Condition, Admission Year |

---

## 🔍 Key Insights

> Fill in the numbers from your own dashboard before publishing.

- 🏥 **Most common condition:** `<condition name>` with `<number>` patients.
- 💰 **Top hospital by revenue:** `<hospital name>` with `<amount>` in total billing.
- 🛡️ **Largest insurance group:** `<insurance provider>` covering `<percentage>` of patients.
- 📅 **Admission trend:** `<one line about the monthly or yearly pattern>`.
- ⚠️ **High-risk patients:** `<number or percentage>` flagged as High Risk based on test results.

---

## 🛠️ Tools and Technologies

| Tool | Used for |
|---|---|
| **Power BI Desktop** | Report design and visualization |
| **Power Query (M)** | Data cleaning and transformation |
| **DAX** | Measures and calculations, where applicable |
| **CSV files** | Source data and lookup data |

---

## 📁 Repository Structure

```text
Healthcare-Patient-Analytics-Dashboard/
│
├── Healthcare_Patient_Analytics_Dashboard.pbix
├── healthcare_dataset.csv
├── Condition_Dept_Lookup.csv
├── README.md
└── images/
    ├── 01-home.png
    ├── 02-dashboard-overview.png
    ├── 03-patient-detail.png
    ├── 04-billing-analysis.png
    ├── 05-power-query-applied-steps.png
    └── video-thumbnail.png
```

---

## 🚀 How to Use

1. Download or clone this repository.
2. Keep `healthcare_dataset.csv` and `Condition_Dept_Lookup.csv` in the same folder.
3. Open `Healthcare_Patient_Analytics_Dashboard.pbix` in **Power BI Desktop**.
4. If Power BI shows a data source error, go to **Home → Transform data → Data source settings → Change Source** and select your local CSV files.
5. Click **Refresh** to load the data.
6. Use the slicers and click on visuals to explore the four report pages.

---

## 📚 Learning Outcomes

Through this project I practiced:

- Loading CSV data in Import mode and profiling data quality.
- Cleaning text, number and date columns in Power Query.
- Creating index, conditional and custom columns.
- Using Group By, Merge, Pivot, Unpivot and Append.
- Building and using parameters.
- Designing KPI cards, charts, slicers and a multi-page report.
- Setting up filters and visual interactions in Power BI.

---

## 👩‍💻 Author

**Simran Gohel**

[![GitHub](https://img.shields.io/badge/GitHub-simrangohel70--lab-181717?style=flat-square&logo=github)](https://github.com/simrangohel70-lab)
[![Portfolio](https://img.shields.io/badge/Portfolio-Data%20%26%20Tech-CC0000?style=flat-square)](https://simrangohel70-lab.github.io/)

---

<div align="center">

⭐ If you found this project useful, please give the repository a star!

</div>
