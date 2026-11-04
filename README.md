# 🏥 Insurance Company Complaint Pattern & Resolution Analysis Using Python

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green?logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-teal)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-yellow?logo=googlecolab)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 1. Project Overview

This project focuses on analyzing an **insurance company complaints dataset** using Python to extract meaningful insights. The analysis includes data cleaning, exploratory data analysis (EDA), statistical analysis, and visualization to understand complaint patterns, resolution trends, and recovery behavior.

The project aims to transform raw complaint data into useful information that supports better decision-making for insurance operations and customer service improvements.

The project follows a complete data analytics pipeline:

```
Data Loading → Initial EDA → Data Cleaning → Transformation →
Feature Engineering → Visualization → Key Insights → Conclusion
```

---

## 📂 2. Data Source

- **Dataset Name:** Insurance Company Complaints, Resolutions, Status, and Recoveries
- **Source:** U.S. Government Open Data Portal (data.gov)
- **Repository:** [Kumar S – GitHub](https://github.com/Kumarsakthi835/Kumarsakthi835-Insurance-Company-Complaints-Resolutions-Status-and-Recoveries)
- **File Type:** CSV
- **Number of Records:** 500 rows (sampled from 89,348 original records)
- **Number of Attributes:** 12 original columns

The dataset contains information related to insurance complaints filed between **2021 and 2026**, including complaint reasons, coverage types, resolution outcomes, and financial recovery amounts across the **United States of America**.

---

## ❓ 3. Problem Statement

Insurance companies receive thousands of complaints every year but often struggle to identify patterns in complaint types, resolution speed, and recovery rates. Without proper analysis, it is difficult to understand which complaint categories take longer to resolve and what factors influence recovery outcomes.

This project aims to analyze the insurance complaint dataset and identify key factors influencing complaint resolution patterns and business recovery performance.

---

## 🎯 4. Objectives

- To understand the dataset structure and complaint attributes
- To clean and prepare the data for analysis
- To handle missing values and duplicates
- To perform Exploratory Data Analysis (EDA)
- To engineer new features such as Resolution Days and Recovery Status
- To identify complaint patterns and resolution trends
- To create meaningful visualizations
- To generate actionable business insights

---

## 📋 5. Attribute (Column / Feature) Details

| # | Attribute Name | Data Type | Description |
|---|----------------|-----------|-------------|
| 1 | Company | Object | Name of the insurance company |
| 2 | File No. | Integer | Unique complaint file number |
| 3 | Opened | Date | Date complaint was opened |
| 4 | Closed | Date | Date complaint was closed |
| 5 | Coverage | Object | Type of insurance coverage |
| 6 | SubCoverage | Object | Sub-type of insurance coverage |
| 7 | Reason | Object | Primary reason for complaint |
| 8 | SubReason | Object | Detailed reason for complaint |
| 9 | Disposition | Object | How the complaint was handled |
| 10 | Conclusion | Object | Final conclusion of complaint |
| 11 | Recovery | Float | Amount recovered in USD |
| 12 | Status | Object | Current complaint status |

---

## 🛠️ 6. Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Google Colab

---

## ⚙️ 7. Data Pre-Processing and Feature Engineering

The dataset was prepared for analysis using data preprocessing techniques.

### Data Cleaning Steps

- Checked data types of all columns
- Identified missing values (513 null values across 6 columns)
- Handled null values using mode imputation and default value filling
- Confirmed 0 duplicate records — no rows dropped
- Converted date columns (Opened, Closed) to **datetime** format
- Cleaned Recovery column by removing `$` and `,` symbols → converted to numeric
- Renamed `File No.` → `File_No`

### Missing Value Treatment

| Column | Missing Count | Method Used |
|--------|--------------|-------------|
| SubCoverage | 90 (18.0%) | Filled with 'Not Specified' |
| Disposition | 207 (41.4%) | Filled with 'Unknown' |
| Conclusion | 137 (27.4%) | Filled with 'Unknown' |
| Coverage | 25 (5.0%) | Filled with Mode |
| Reason | 20 (4.0%) | Filled with Mode |
| SubReason | 20 (4.0%) | Filled with Mode |
| Closed | 14 (2.8%) | Filled with Opened date |

**After Handling:** Total missing values = **0**

### Feature Engineering

New features were created to improve analysis:

- **Resolution_Days** – Calculated from (Closed – Opened) date difference
- **Resolution_Category** – Fast (≤15 days), Medium (16–30 days), Slow (>30 days)
- **Recovery_Status** – 'Recovered' if Recovery > 0, else 'Not Recovered'
- **Year, Month, Quarter** – Extracted from Opened date for time-based analysis
- **Complaint_Age** – Old (2021–22), Recent (2023–24), Latest (2025–26)
- **Is_Recovered** – Binary flag (1 = Recovered, 0 = Not Recovered)

**Final Dataset Shape: (500 rows × 20 columns)**

---

## 📊 8. Analysis and Visualizations

The dataset was analyzed using Exploratory Data Analysis techniques to understand complaint patterns and relationships across coverage types, companies, and time periods.

---

## 🔍 9. Exploratory Data Analysis (EDA)

Initial inspection included:

- Data frame structure verification (shape, dtypes) — **Shape: (500, 12)**
- Statistical summary using `df.describe(include='all')`
- Null value verification — **513 missing values** across 6 columns
- Duplicate record validation — **0 duplicates** found
- Unique value counts using `df.nunique()`

EDA helped in understanding the distribution and characteristics of the complaint data.

### Stage 1 – Data Loading & Initial EDA Screenshots

| Screenshot | Description |

| Dataset loaded from GitHub — Shape: (500, 12) |

<img width="675" height="81" alt="image" src="https://github.com/user-attachments/assets/9e06cec7-edcc-4d65-af1e-47a1c05829b9" />


| First 5 rows using df.head() |

<img width="875" height="239" alt="image" src="https://github.com/user-attachments/assets/4d419995-a1f8-4978-ad72-eecf8cd67978" />


|Column names and data types using df.info() |

<img width="875" height="241" alt="image" src="https://github.com/user-attachments/assets/49d1f9c9-92b8-4d74-9f72-94adbfc78f84" />

|Missing values — 513 total across 6 columns |

<img width="713" height="299" alt="image" src="https://github.com/user-attachments/assets/c98955e3-fc12-4539-a225-f9c686712ad1" />


|Unique values per column using df.nunique() |

<img width="620" height="151" alt="image" src="https://github.com/user-attachments/assets/623d1004-5558-4784-b4d7-101a3a6de2e5" />

### Data Cleaning & Transformation Screenshots

| Screenshot | Description |

|Duplicate check — 0 duplicates found |

<img width="665" height="52" alt="image" src="https://github.com/user-attachments/assets/cf75f5fe-dcb6-46cf-94c4-481c817055ee" />

|Missing values before handling — 513 total |

<img width="706" height="165" alt="image" src="https://github.com/user-attachments/assets/d92772b6-baee-44c2-9d19-2269cbe3ae40" />

|Missing values after handling — 0 remaining |

<img width="494" height="186" alt="image" src="https://github.com/user-attachments/assets/16bc2752-8050-461b-8c9b-52ba91149c3e" />

|Data transformation — Shape updated to (500, 16) |

<img width="761" height="143" alt="image" src="https://github.com/user-attachments/assets/3aea26f8-6e45-4a18-bb8d-8e917ec67915" />

|Feature engineering — Final shape: (500, 20) |

<img width="896" height="271" alt="image" src="https://github.com/user-attachments/assets/f462698f-60a9-4fc5-ac76-27896b1439dc" />

|Final EDA — All columns and data types confirmed |

<img width="570" height="311" alt="image" src="https://github.com/user-attachments/assets/22968a7e-bf88-4c9a-abc7-7d2a4e8f0243" />
<img width="640" height="280" alt="image" src="https://github.com/user-attachments/assets/d7868bdd-7ea6-46eb-8d8b-cc388563ff2f" />

---

## 📐 10. Statistical Analysis

Statistical measures were used to summarize the dataset.

Measures included:

- Mean
- Median
- Mode
- Minimum value
- Maximum value
- Standard deviation

These measures helped understand the central tendency and variability of **Resolution Days** and **Recovery amounts**.

---

## 📈 11. Data Visualization

Visualization techniques were used to represent complaint data graphically and make patterns easier to understand.

---

### 1. Univariate Analysis

Univariate analysis was performed to analyze one variable at a time.

**Analysis Performed:**

**1. Top 10 Companies by Complaint Count** 

<img width="749" height="311" alt="image" src="https://github.com/user-attachments/assets/11ff4ac6-6ae1-428a-8b7d-7d4600889e62" />


- **Objective:** To identify which insurance companies received the highest number of complaints.
- **Visualization:** Horizontal bar chart showing top 10 companies sorted by complaint count.
- **Interpretation:** Anthem Health Plans, Inc leads with 121 complaints (24.2%), making it the single largest complaint contributor among 121 companies.
- **Key Insight:** One company alone accounts for nearly one-quarter of all complaints in the dataset.
- **Business Insight:** Anthem Health Plans should conduct an internal audit to identify root causes and implement targeted service improvements.

---

**2. Coverage Type Distribution** 

<img width="546" height="323" alt="image" src="https://github.com/user-attachments/assets/c2563360-4d0e-4182-b5f9-2573168aec97" />


- **Objective:** To understand which insurance coverage types receive the most complaints.
- **Visualization:** Pie chart showing complaint proportion by coverage type.
- **Interpretation:** A & H (Accident & Health) coverage dominates at 29.4% of complaints, followed by other coverage types.
- **Key Insight:** A & H coverage accounts for the highest complaint share among all coverage categories.
- **Business Insight:** Companies offering A & H coverage should invest in better claim handling procedures to reduce complaint volumes.

---

**3. Complaint Reasons Distribution** 

<img width="616" height="305" alt="image" src="https://github.com/user-attachments/assets/c7623708-bc4c-4efb-804a-5415466e6406" />


- **Objective:** To identify the most frequently occurring complaint reasons in insurance filings.
- **Visualization:** Vertical bar chart showing complaint counts by reason category.
- **Interpretation:** Claim Handling is the dominant complaint reason at 75.4% (377 out of 500), indicating widespread dissatisfaction with claims processing.
- **Key Insight:** Over 75% of all complaints are directly related to how claims are handled.
- **Business Insight:** Insurance companies must prioritize improving claim processing speed, transparency, and communication.

---

**4. Complaint Status Distribution** 

<img width="479" height="197" alt="image" src="https://github.com/user-attachments/assets/814931ac-ade8-4d3c-955c-da6f1e2a8c77" />
<img width="599" height="287" alt="image" src="https://github.com/user-attachments/assets/acc2e609-f125-4d28-9542-b6b819deae50" />



- **Objective:** To monitor how many complaints are currently open vs closed.
- **Visualization:** Pie chart showing proportion of Open vs Closed complaints.
- **Interpretation:** 97.2% of complaints (486 out of 500) are Closed, showing strong resolution performance.
- **Key Insight:** Nearly all complaints in the dataset have been successfully resolved.
- **Business Insight:** The remaining open complaints should be monitored and escalated to prevent aging.

---

### 2. Bivariate Analysis

Bivariate analysis was performed to study relationships between two variables.

**Analysis Performed:**

**5. Yearly Complaint Trend (2021–2026)** 

<img width="542" height="294" alt="image" src="https://github.com/user-attachments/assets/937ed43c-2dcf-4390-a27d-1b71362d9174" />


- **Objective:** To analyze how the number of complaints has changed from 2021 to 2026.
- **Visualization:** Line chart showing yearly complaint count trends over 6 years.
- **Interpretation:** Complaint volumes grew from 10 in 2021, reaching a peak of 131 complaints in 2025, reflecting increasing customer dissatisfaction.
- **Key Insight:** Complaints increased by over 1200% from 2021 to 2025.
- **Business Insight:** Proactive intervention during complaint-heavy periods can help reverse negative trends and improve customer retention.

---

**6. Resolution Days Distribution** 

<img width="590" height="305" alt="image" src="https://github.com/user-attachments/assets/8a235d54-cf10-4889-b96f-f502717f7f2a" />


- **Objective:** To understand the distribution of time taken to resolve complaints.
- **Visualization:** Histogram showing frequency of resolution day ranges.
- **Interpretation:** Most complaints are resolved within 0–60 days, but outliers exist up to 880 days, indicating systemic delays in certain cases.
- **Key Insight:** Average resolution time is 42.06 days; 47.4% fall in the Slow category (>30 days).
- **Business Insight:** Companies should aim to reduce average resolution days to below 30 by streamlining internal review processes.

---

**7. Complaint Status Count** 

<img width="647" height="320" alt="image" src="https://github.com/user-attachments/assets/5969d945-fdef-47bc-a503-0ae2d2473dc1" />


- **Objective:** To compare the exact count of Open vs Closed complaints visually.
- **Visualization:** Count plot showing bars for each complaint status category.
- **Interpretation:** 486 complaints are Closed vs only 14 remaining Open, confirming a high resolution rate of 97.2%.
- **Key Insight:** The dataset reflects strong complaint management performance with minimal pending cases.
- **Business Insight:** Focus should shift from volume closure to quality of resolution and customer satisfaction scores.

---

### 3. Multivariate Analysis

Multivariate analysis was used to analyze relationships among multiple variables.

**Analysis Performed:**

**8. Resolution Days by Coverage Type**

<img width="659" height="317" alt="image" src="https://github.com/user-attachments/assets/59780fad-f154-45e0-b1ff-7bf81eaaf86c" />


- **Objective:** To compare resolution speed across different insurance coverage types.
- **Visualization:** Box plot showing resolution day spread for each coverage category.
- **Interpretation:** Individual Private Passenger coverage shows the slowest average resolution at 49.43 days, with significant outliers indicating extreme delays in some cases.
- **Key Insight:** Coverage type significantly influences how quickly a complaint gets resolved.
- **Business Insight:** Coverage types with consistently high resolution times should have dedicated fast-track processing teams assigned.

---

**9. Correlation Matrix — Numerical Features** 

<img width="524" height="247" alt="image" src="https://github.com/user-attachments/assets/b6135add-2151-4cb7-9262-a6d309ae6860" />


- **Objective:** To identify statistical relationships between numerical variables in the dataset.
- **Visualization:** Heatmap showing correlation coefficients between Resolution_Days, Recovery, Is_Recovered, and other numeric features.
- **Interpretation:** Resolution_Days and Recovery show minimal correlation, indicating resolution speed does not directly affect financial recovery outcome.
- **Key Insight:** Recovery outcome depends more on complaint type and coverage than on resolution speed.
- **Business Insight:** Focusing on complaint category and coverage type can better predict financial recovery probability.

---

**10. Avg Resolution Days by Complaint Reason**

<img width="584" height="288" alt="image" src="https://github.com/user-attachments/assets/2052d086-fa1d-4d20-9303-8bc7082e318e" />


- **Objective:** To identify which complaint reasons take the longest average time to resolve.
- **Visualization:** Horizontal bar chart showing average resolution days per complaint reason category.
- **Interpretation:** Marketing & Sales complaints take the longest to resolve at an average of 50.50 days.
- **Key Insight:** Different complaint reasons have significantly different average resolution timelines.
- **Business Insight:** Insurers should create reason-specific SLAs and escalation paths for categories with above-average resolution times.

---

### Key Insights Screenshot

| Screenshot | Description |

<img width="611" height="332" alt="image" src="https://github.com/user-attachments/assets/8f1cc4ac-a9ac-477c-a55b-9f89f8b8449e" />

| Key insights summary — all 8 metrics printed in Colab output |

---

## 📊 12. Summary of Findings

- Majority of complaints are related to **Claim Handling** — 75.4% of all complaints
- **Accident & Health (A/H)** coverage has the highest complaint volume at 29.4%
- **97.2%** of complaints are successfully closed — strong resolution performance
- Average resolution time is **42.06 days**; 47.4% fall in the Slow category (>30 days)
- Complaint volumes grew significantly from **10 in 2021 to 131 in 2025**
- Total financial recovery achieved: **$878,358.86** across 97 complaints (19.4%)
- **Anthem Health Plans, Inc** is the top complaint company with 24.2% share
- Marketing & Sales complaints take the longest to resolve at **50.50 days** average

---

## 🧠 13. Types of Analysis

### 1. Descriptive Analysis

Descriptive analysis summarizes historical complaint data.

Examples:
- Total complaint count by year and quarter
- Average resolution days by coverage type
- Distribution of complaint reasons and coverage types

### 2. Diagnostic Analysis

Diagnostic analysis explains why certain patterns occur.

Examples:
- Reasons for higher complaint volumes in A/H coverage
- Factors contributing to slow resolution categories
- Why certain coverage types have lower recovery rates

### 3. Predictive Analysis

Predictive analysis helps forecast future outcomes.

Examples:
- Predicting complaint volume for upcoming quarters
- Estimating resolution time based on complaint type and coverage
- Forecasting financial recovery based on coverage category

### 4. Prescriptive Analysis

Prescriptive analysis suggests actions based on insights.

Examples:
- Offering faster resolution tracks for high-volume complaint categories
- Improving claim handling processes in A/H coverage
- Targeting coverage categories with lowest recovery rates for policy review

---

## 🚀 14. Future Enhancements and Suggestions

- Include more records from all U.S. states for better geographic accuracy
- Apply machine learning models to predict complaint resolution outcomes
- Build interactive dashboards using Power BI or Tableau
- Automate reporting process with scheduled Python scripts
- Integrate NLP analysis on complaint reason text for deeper insights

---

## ✅ 15. Conclusion

The project successfully analyzed the **Insurance Company Complaints** dataset using Python and extracted useful insights about complaint patterns, resolution trends, and recovery behavior.

Data preprocessing and feature engineering helped in transforming raw data into meaningful analytical features. Visualization techniques revealed important patterns across coverage types, time periods, and resolution categories.

The results of this project can help insurance companies make better business decisions by identifying complaint-prone areas, improving resolution speed, and maximizing financial recovery outcomes.

---

## 📁 Repository Structure

```
📦 Kumarsakthi835-Insurance-Company-Complaints-Resolutions-Status-and-Recoveries
 ┣ 📄 Insurance Company.csv          → Sampled dataset (500 rows)
 ┣ 📓 Insurance_Complaints.ipynb     → Google Colab Notebook
 ┣ 📁 screenshots/                   → All stage & visualization screenshots
 ┗ 📄 README.md                      → Project Documentation
```

---

## ▶️ How to Run

1. Open **Google Colab** at [colab.research.google.com](https://colab.research.google.com)
2. Upload the notebook file `Insurance_Complaints.ipynb`
3. Run all cells using **Runtime → Run All** or `Ctrl + F9`
4. All outputs, charts, and insights will be generated automatically

---

## 👨‍💻 Author

**Kumar S**  
Data Analytics — Entri Elevate  
📧 kumarsakthi835@gmail.com  
🔗 [GitHub Profile](https://github.com/kumarsakthi835)  
📍 Rasipuram, Tamil Nadu, India

---

## 📜 Data Source & License

- Data sourced from **U.S. Government Open Data Portal** (data.gov)
- Used for **educational and analytical purposes only**
- Original dataset: [Insurance Company Complaints, Resolutions, Status, and Recoveries](https://catalog.data.gov/dataset/insurance-company-complaints-resolutions-status-and-recoveries)

---

*Project by: Kumar S | Data Analytics – Entri Elevate | Dataset Period: 2021–2026 | Records: 500 | Tools: Python, Pandas, NumPy, Matplotlib, Seaborn, Google Colab*
