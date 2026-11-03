# 🏥 Insurance Company Complaint Pattern & Resolution Analysis using Python

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green?logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-teal)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-yellow?logo=googlecolab)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Project Overview

This project analyzes **500 insurance complaint records** from the **United States (2021–2026)**
sourced from the U.S. Government Open Data Portal (data.gov). The analysis covers complaint
patterns, resolution timelines, coverage types, company-wise distribution, and financial
recovery trends using Python data analytics libraries.

The project follows a complete data analytics pipeline:

```
Data Loading → Initial EDA → Data Cleaning → Transformation →
Feature Engineering → Visualization → Key Insights → Conclusion
```

---

## 🎯 Objectives

1. Analyze complaint patterns across different insurance companies
2. Identify the most common complaint reasons and coverage types
3. Monitor complaint resolution status (Open vs Closed)
4. Analyze complaint resolution time (days taken to close)
5. Evaluate recovery amounts by company and coverage type
6. Identify yearly complaint trends from 2021 to 2026
7. Generate descriptive, diagnostic, and prescriptive business insights

---

## 📂 Dataset Information

| Item | Details |
|------|---------|
| **Dataset Name** | Insurance Company Complaints, Resolutions, Status, and Recoveries |
| **Source** | [U.S. Government Open Data Portal](https://catalog.data.gov/dataset/insurance-company-complaints-resolutions-status-and-recoveries) |
| **Repository** | [Kumar S – GitHub](https://github.com/Kumarsakthi835/Kumarsakthi835-Insurance-Company-Complaints-Resolutions-Status-and-Recoveries) |
| **Domain** | Finance / Insurance / Consumer Protection |
| **Location** | United States of America (USA) |
| **Timeline** | 2021 – 2026 |
| **Original Records** | 89,348 rows |
| **Sampled Records** | 500 rows × 12 columns |
| **File Format** | CSV |

---

## 📁 Original Dataset Columns (12)

| # | Column | Data Type | Description |
|---|--------|-----------|-------------|
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

## 🆕 New Columns After Feature Engineering (8)

| # | New Column | Description | Values |
|---|------------|-------------|--------|
| 1 | Resolution_Days | Days to close complaint | Numeric |
| 2 | Resolution_Category | Speed of resolution | Fast / Medium / Slow |
| 3 | Recovery_Status | Financial recovery flag | Recovered / Not Recovered |
| 4 | Complaint_Age | Time period group | Old / Recent / Latest |
| 5 | Quarter | Quarter of complaint | Q1 / Q2 / Q3 / Q4 |
| 6 | Year | Year of complaint | 2021–2026 |
| 7 | Month | Month of complaint | January–December |
| 8 | Is_Recovered | Binary recovery flag | 1 = Yes / 0 = No |

**Final Dataset Shape: (500 rows × 20 columns)**

---

## 🛠️ Tools & Technologies

| Tool / Library | Version | Purpose |
|----------------|---------|---------|
| Python | 3.x | Core programming language |
| Pandas | Latest | Data loading, cleaning, manipulation |
| NumPy | Latest | Numerical operations |
| Matplotlib | Latest | Basic charts and plots |
| Seaborn | Latest | Statistical visualizations |
| Google Colab | — | Cloud-based development environment |

---

## 📝 Project Stages

### ✅Data Loading & Initial EDA

- Imported all required libraries (Pandas, NumPy, Matplotlib, Seaborn)
- Loaded dataset from GitHub using `pd.read_csv()`
- Checked shape: **(500, 12)**
- Verified column names, data types using `df.info()` and `df.dtypes`
- Generated statistical summary using `df.describe(include='all')`
- Identified missing values across 6 columns (513 total missing)
- Checked unique values per column using `df.nunique()`

---

### ✅Data Cleaning

- **Duplicates:** Confirmed 0 duplicate rows — no rows dropped
- **Missing Values Handled (513 total):**

| Column | Missing Count | Strategy Used |
|--------|--------------|---------------|
| SubCoverage | 90 (18.0%) | Filled with 'Not Specified' |
| Disposition | 207 (41.4%) | Filled with 'Unknown' |
| Conclusion | 137 (27.4%) | Filled with 'Unknown' |
| Coverage | 25 (5.0%) | Filled with Mode |
| Reason | 20 (4.0%) | Filled with Mode |
| SubReason | 20 (4.0%) | Filled with Mode |
| Closed | 14 (2.8%) | Filled with Opened date |

- **After Handling:** Total missing values = **0**

---

### ✅Data Transformation & Feature Engineering

- Converted `Opened` and `Closed` columns to **datetime** format
- Calculated `Resolution_Days` = Closed date − Opened date
- Extracted `Year`, `Month`, `Quarter` from Opened date
- Cleaned `Recovery` column — removed `$` and `,` symbols → converted to numeric
- Renamed `File No.` → `File_No`
- Created 4 new feature columns using business logic
- **Final shape: (500, 20)**

---

### ✅Data Visualization (10 Charts)

| # | Chart Type | Library | Topic |
|---|------------|---------|-------|
| 1 | Bar Chart | Matplotlib | Top 10 Companies by Complaint Count |
| 2 | Pie Chart | Matplotlib | Coverage Type Distribution |
| 3 | Bar Chart | Matplotlib | Complaint Reasons Distribution |
| 4 | Pie Chart | Matplotlib | Complaint Status Distribution |
| 5 | Line Chart | Matplotlib | Yearly Complaint Trend (2021–2026) |
| 6 | Histogram | Matplotlib | Resolution Days Distribution |
| 7 | Count Plot | Seaborn | Complaint Status Count |
| 8 | Box Plot | Seaborn | Resolution Days by Coverage Type |
| 9 | Heatmap | Seaborn | Correlation Matrix |
| 10 | Bar Chart | Matplotlib | Avg Resolution Days by Complaint Reason |

---

### ✅Key Insights & Conclusion

- Generated 8 business insights from visualizations
- Identified key complaint drivers and resolution patterns
- Provided actionable business recommendations

---

## 📊 Key Findings

| Metric | Value |
|--------|-------|
| **Total Complaints Analyzed** | 500 |
| **Total Companies** | 121 |
| **Top Complaint Company** | Anthem Health Plans, Inc — 121 complaints (24.2%) |
| **Most Common Reason** | Claim Handling — 377 complaints (75.4%) |
| **Most Common Coverage** | A & H (Accident & Health) — 147 complaints (29.4%) |
| **Complaint Closure Rate** | 97.2% (486 out of 500 Closed) |
| **Average Resolution Time** | 42.06 days |
| **Median Resolution Time** | 28.5 days |
| **Maximum Resolution Time** | 880 days |
| **Fast Resolutions (≤15 days)** | 103 complaints (20.6%) |
| **Slow Resolutions (>30 days)** | 237 complaints (47.4%) |
| **Total Recovery Amount** | $878,358.86 |
| **Complaints with Recovery** | 97 out of 500 (19.4%) |
| **Peak Complaint Year** | 2025 — 131 complaints |

---

## 📸 Screenshots

### Data Loading & Initial EDA

| Screenshot | Description |


| Dataset loaded from GitHub — Shape: (500, 12) |

<img width="675" height="81" alt="image" src="https://github.com/user-attachments/assets/3a0ee5fa-94dc-428d-9439-9e49e0965662" />


| First 5 rows using df.head() |

<img width="875" height="239" alt="image" src="https://github.com/user-attachments/assets/f07ad8cd-ac59-47c3-9717-3c636ca126e6" />


| Column names, data types using df.info() |

<img width="875" height="241" alt="image" src="https://github.com/user-attachments/assets/3de0b765-98c3-4f48-aa40-b7ab8dff6598" />

| Missing values — 513 total across 6 columns |

<img width="713" height="299" alt="image" src="https://github.com/user-attachments/assets/fd1f5126-e770-4b6c-a418-aef28c824d25" />

| Unique values per column using df.nunique() |

<img width="620" height="151" alt="image" src="https://github.com/user-attachments/assets/57967618-99ed-4575-b425-c7f20b63a3c9" />


---

### Data Cleaning & Transformation

| Screenshot | Description |


| Duplicate check — 0 duplicates found |

<img width="665" height="52" alt="image" src="https://github.com/user-attachments/assets/d963595a-fb12-4a01-99e4-2ec398a06f12" />


| Missing values before handling — 513 total |

<img width="706" height="165" alt="image" src="https://github.com/user-attachments/assets/8583e9ca-bd34-44e7-81cf-2e0256e24084" />


| Missing values after handling — 0 remaining |

<img width="494" height="186" alt="image" src="https://github.com/user-attachments/assets/e4a2d13b-449b-41a9-812e-5c8a821faf18" />

| Data transformation — Shape updated to (500, 16) |

<img width="677" height="137" alt="image" src="https://github.com/user-attachments/assets/cdc50682-768c-42ad-a21f-bd90e7b1ce8e" />


| Feature engineering — Final shape: (500, 20) |

<img width="896" height="271" alt="image" src="https://github.com/user-attachments/assets/36c7b8ff-1301-49e8-b77b-ea16e57fc160" />

| Final EDA — All columns, data types confirmed |

<img width="570" height="311" alt="image" src="https://github.com/user-attachments/assets/87d4f62d-6ee6-4501-bfb2-8c3c57fc0c5d" />

---

### Visualizations

| Screenshot | Chart | Key Finding |

|Bar – Top 10 Companies | Anthem Health Plans leads with 121 complaints (24.2%) |

<img width="749" height="311" alt="image" src="https://github.com/user-attachments/assets/25412225-2f96-4885-8e30-5926f3702a75" />


|Pie – Coverage Types | A & H dominates at 29.4% of complaints |

<img width="546" height="323" alt="image" src="https://github.com/user-attachments/assets/aee17ec2-8eca-4157-8725-8a9b62a4b092" />


|Bar – Complaint Reasons | Claim Handling = 75.4% of all complaints |

<img width="616" height="305" alt="image" src="https://github.com/user-attachments/assets/d66494db-4094-4698-8190-a05b075c8e1d" />

|Pie – Status | 97.2% complaints are Closed |

<img width="479" height="197" alt="image" src="https://github.com/user-attachments/assets/725a1abb-b1ac-480a-b32b-1c91333bfbbe" />
<img width="599" height="287" alt="image" src="https://github.com/user-attachments/assets/add3e0ca-227c-4659-93ee-c0e81f2842ad" />


|Line – Yearly Trend | Complaints grew from 10 (2021) to 131 (2025) |

<img width="542" height="294" alt="image" src="https://github.com/user-attachments/assets/bcff00bf-da1e-4ba9-8bc5-4496baa923db" />

|Histogram – Resolution Days | Mean 42.06 days; max 880 days |

<img width="590" height="305" alt="image" src="https://github.com/user-attachments/assets/acd9b639-bcac-4e40-8858-9626ff2a5321" />

|Count Plot – Status | 486 Closed vs 3 Open complaints |

<img width="647" height="320" alt="image" src="https://github.com/user-attachments/assets/41cfd2cf-452d-4d89-964c-b270b05f7324" />


|Box Plot – Coverage | Individual Private Passenger slowest at 49.43 days |

<img width="659" height="317" alt="image" src="https://github.com/user-attachments/assets/38543c19-9279-49be-b7f2-ed460603f026" />

|Heatmap – Correlation | Resolution Days and Recovery are independent |

<img width="524" height="247" alt="image" src="https://github.com/user-attachments/assets/0a089c01-4cf9-4435-b259-112d911c591f" />

|Bar – Avg Days by Reason | Marketing & Sales slowest at 50.50 days avg |

<img width="584" height="288" alt="image" src="https://github.com/user-attachments/assets/acdb98ae-50ac-459a-906d-565725d35d62" />

---

###  Key Insights

| Screenshot | Description |


| Key insights summary — all 8 metrics printed |

<img width="611" height="332" alt="image" src="https://github.com/user-attachments/assets/443a3590-9d7b-4854-b383-a11acf671366" />

---

## 💡 Conclusion

- **Anthem Health Plans, Inc** accounts for **24.2%** of all complaints
  — the single largest contributor among 121 companies
- **Claim Handling** drives **75.4%** of complaints, indicating a
  critical failure point in insurance operations
- **97.2%** of complaints are successfully closed, showing strong
  resolution performance overall
- Average resolution takes **42.06 days**; however, **47.4%** of
  complaints fall in the Slow category (>30 days)
- Total financial recovery of **$878,358.86** was achieved across
  97 complaints (19.4% recovery rate)
- Complaint volume grew significantly from **10 in 2021 to 131 in 2025**,
  signaling increasing customer dissatisfaction over the years
- This analysis provides actionable insights to help insurance companies
  improve claim handling processes, reduce resolution time, and enhance
  overall customer satisfaction

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
- Original dataset:
  [Insurance Company Complaints, Resolutions, Status, and Recoveries](https://catalog.data.gov/dataset/insurance-company-complaints-resolutions-status-and-recoveries)
