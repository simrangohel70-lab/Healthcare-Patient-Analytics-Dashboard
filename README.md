# 🏥 Healthcare Patient Analytics Dashboard | Power BI

<p align="center">
  <img src="https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black" />
  <img src="https://img.shields.io/badge/Power%20Query-Data%20Transformation-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white" />
  <img src="https://img.shields.io/badge/Dataset-Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white" />
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge" />
</p>

<p align="center">
  <b>Turning Healthcare Data into Meaningful Insights 📊</b>
</p>

---

## 🎥 Video Demonstration

click here to watch video:-https://drive.google.com/file/d/1sC4ReI0DzASuTv7AGZe6cqkt99XRngmM/view?usp=sharing


- 📂 Dataset import and data source connection
- 🧹 Data cleaning and transformation using Power Query
- 🔄 Merge, Append, Pivot, and Unpivot operations
- 📊 Interactive dashboard and KPI cards
- 🎛️ Slicers, filters, and report navigation

**Project:** Healthcare Patient Analytics Dashboard  
**Tool:** Microsoft Power BI Desktop


## 📌 Table of Contents

- [🎥 Video Demonstration](#-video-demonstration)
- [📖 Project Overview](#-project-overview)
- [🎯 Project Objectives](#-project-objectives)
- [🛠️ Tools and Technologies](#️-tools-and-technologies)
- [📂 Dataset Information](#-dataset-information)
- [🧹 Data Preparation](#-data-preparation)
- [📊 Dashboard Pages](#-dashboard-pages)
- [⚙️ Key Features](#️-key-features)
- [💡 Key Insights](#-key-insights)
- [🖼️ Dashboard Preview](#️-dashboard-preview)
- [🚀 How to Run the Project](#-how-to-run-the-project)
- [🎥 Video Demonstration](#-video-demonstration)
- [📚 Learning Outcomes](#-learning-outcomes)
- [👩‍💻 Author](#-author)

---

## 📖 Project Overview

The **Healthcare Patient Analytics Dashboard** is an interactive Power BI project designed to analyze hospital patient records, medical conditions, admission patterns, billing amounts, and insurance provider information.

The project uses Power Query for data cleaning, transformation, grouping, merging, pivoting, unpivoting, and appending. The prepared data is then used to build an interactive, multi-page Power BI report.

The goal is to transform raw healthcare data into meaningful visual insights that support data exploration and reporting.

## 🎯 Project Objectives

- 🏥 Analyze patient demographics and medical conditions.
- 💰 Understand hospital billing and revenue distribution.
- 📅 Explore patient admission trends by year and month.
- 🩺 Compare patient counts across medical conditions.
- 🛡️ Analyze insurance provider distribution and claims.
- 🔄 Apply essential Power Query data transformation techniques.
- 📊 Build an interactive dashboard using charts, KPI cards, tables, and slicers.

## 🛠️ Tools and Technologies

| Tool | Purpose |
|---|---|
| 📊 Microsoft Power BI Desktop | Dashboard development and visualization |
| 🔄 Power Query Editor | Data cleaning and transformation |
| 📁 CSV Files | Source data and lookup tables |
| 📈 Power BI Visuals | KPI cards, charts, slicers, and matrix |
| 🧮 Power Query M | Data transformation logic |

## 📂 Dataset Information

**Dataset:** Healthcare Dataset — Patient Hospital Records

**Source:** Kaggle

**Author:** Prasad Patil (`pras ad22` on Kaggle)

🔗 **Dataset Link:** https://www.kaggle.com/datasets/prasad22/healthcare-dataset

The main dataset contains approximately **55,500 patient records** and 15 columns.

### 📋 Main Dataset Columns

| Category | Fields |
|---|---|
| Patient Details | Name, Age, Gender, Blood Type |
| Medical Information | Medical Condition, Doctor, Hospital |
| Admission Details | Date of Admission, Discharge Date, Admission Type |
| Financial Information | Billing Amount, Insurance Provider |
| Additional Information | Room Number, Medication, Test Results |

### 📄 Additional Lookup File

`Condition_Dept_Lookup.csv`

This manually created lookup file maps medical conditions to hospital departments.

| Medical Condition | Department |
|---|---|
| Cancer | Oncology |
| Diabetes | Endocrinology |
| Hypertension | Cardiology |
| Obesity | Bariatrics |
| Asthma | Pulmonology |
| Arthritis | Rheumatology |

*Note: The department mapping is created for this project and is used to enrich the main patient dataset.*

## 🧹 Data Preparation

The following Power Query techniques are included in the project:

- 🧼 **Data Profiling:** Column quality, distribution, validity, errors, and empty values.
- 🔤 **Text Transformations:** Proper Case, UPPERCASE, Trim, and Clean.
- 🔢 **Numeric Transformations:** Correcting negative billing values and rounding billing amounts.
- 📅 **Date Transformations:** Extracting admission year and month.
- 🧮 **Custom Columns:** Patient ID, Age Category, Billing Tier, Stay Category, and Risk Flag.
- 📊 **Grouping & Aggregation:** Summarizing patients, billing, claims, and monthly admissions.
- 🔀 **Merge Queries:** Combining the department lookup with patient records.
- ↔️ **Pivot & Unpivot:** Reshaping admission-type data for analysis.
- 📚 **Append Queries:** Combining data from different admission-year queries.
- 📁 **Folder Connector:** Demonstrating folder-based data combination.
- ⚙️ **Parameters:** Creating dynamic filters for patient age and admission type.

## 📊 Dashboard Pages

### 🏠 Page 1: Home Page

The Home Page serves as the landing page of the Healthcare Patient Analytics Dashboard. It features a clean and professional design with a healthcare-related visual to introduce the project. It provides an overview of the dashboard and helps users navigate to other pages for exploring patient data, healthcare trends, and key insights.

### 🏠 Page 2 — Hospital Patient Analysis Dashboard

- Total Patients
- Total Billing Revenue
- Average Billing per Patient
- Average Length of Stay
- Monthly Patient Admission Trends
- Top 10 Hospitals by Billing Revenue
- Patient Count by Medical Condition
- Patient Distribution by Insurance Provider

### 👥 Page 3 — Patient Detail

- Detailed patient records in a table
- Medical Condition slicer
- Admission Type slicer
- Patient demographics and billing details
- Department, length of stay, and risk classification

### 💰 Page 4— Billing Analysis

- Average Billing Amount by Department and Billing Tier
- Billing Matrix by Medical Condition and Insurance Provider
- Admission Year slicer
- Comparison of billing distribution across departments

## ⚙️ Key Features

- 🎛️ Interactive slicers and filters
- 📈 Dynamic charts and KPI cards
- 🔍 Cross-filtering between visuals
- 🗂️ Multiple report pages
- 🧹 Structured data-cleaning workflow
- 🔗 Merged lookup data for department analysis
- 📊 Patient, billing, and insurance summaries
- 🎨 Consistent dashboard theme and formatting

## 💡 Key Insights

The dashboard is designed to help explore questions such as:

- Which medical conditions account for the highest patient counts?
- Which hospitals generate the highest total billing revenue?
- How do patient admissions change over time?
- How is billing distributed across departments and insurance providers?
- How do admission type and patient age affect the displayed results?
- Which billing tiers contribute most to department-level averages?

*Actual findings should be documented after validating the final charts, measures, and filters.*

## 🖼️ Dashboard Preview

Add screenshots of your completed report here.

```markdown
![Hospital Patient Analysis Dashboard](screenshots/page1.png)

![Patient Detail](screenshots/page2.png)

![Billing Analysis](screenshots/page3.png)
```

📌 Create a folder named `screenshots` in your repository and add the three dashboard screenshots using the filenames shown above.

## 🚀 How to Run the Project

1. 📥 Download the healthcare dataset from Kaggle.
2. 📄 Create the `Condition_Dept_Lookup.csv` file.
3. 📊 Open Microsoft Power BI Desktop.
4. 📂 Import both CSV files.
5. 🔄 Complete the Power Query transformations and create the summary queries.
6. 🔗 Apply the merge, pivot, unpivot, and append operations.
7. ✅ Click **Close & Apply** to load the prepared data.
8. 📈 Build the three report pages and configure the visuals.
9. 🎛️ Test the slicers, filters, and visual interactions.
10. 💾 Save the final report as `Healthcare_Patient_Analytics.pbix`.

## 🎥 Video Demonstration

📹 **Project Walkthrough:** [Add your video link here]

The demonstration can cover:

- Dataset introduction and data source connection
- Power Query transformations
- Grouping, merging, pivoting, and appending
- KPI cards and dashboard visualizations
- Slicers, filters, and report navigation

## 📚 Learning Outcomes

Through this project, I practiced:

- Importing and managing CSV data sources
- Cleaning and profiling datasets using Power Query
- Creating conditional and custom columns
- Applying grouping and aggregation
- Merging and appending queries
- Pivoting and unpivoting data
- Building interactive reports in Power BI
- Designing multi-page dashboards for analytical reporting

## 👩‍💻 Author

**Simran Gohel**

🎓 Aspiring Data Analyst | Power BI | SQL | Excel | Python

🔗 **GitHub:** https://github.com/simrangohel70-lab


---

<p align="center">
  ⭐ If you find this project interesting, consider starring the repository!
</p>

<p align="center">
  <b>Made with 📊 Power BI and 💙 a passion for data analytics</b>
</p>
