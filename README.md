PROJECT TITLE
🏥 Insurance Company Complaint Pattern & Resolution Analysis Using Python
Python 3.x
Pandas
NumPy
Matplotlib
Seaborn
Google Colab
Status: Completed ✅
📌 1. Project Overview

This project focuses on analyzing an insurance company complaints dataset using Python to extract meaningful insights. The analysis includes data cleaning, exploratory data analysis (EDA), statistical analysis, and visualization to understand complaint patterns, resolution trends, and recovery behavior.

The project aims to transform raw complaint data into useful information that supports better decision-making for insurance operations and customer service improvements.

The project follows a complete data analytics pipeline:

Data Loading → Initial EDA → Data Cleaning → Transformation → Feature Engineering → Visualization → Key Insights → Conclusion
📂 2. Data Source
Dataset Name: Insurance Company Complaints, Resolutions, Status, and Recoveries
Source: U.S. Government Open Data Portal (data.gov)
Repository: Kumar S – GitHub
File Type: CSV
Number of Records: 500 rows (sampled from 89,348 original records)
Number of Attributes: 12 original columns

The dataset contains information related to insurance complaints filed between 2021 and 2026, including complaint reasons, coverage types, resolution outcomes, and financial recovery amounts across the United States of America.

❓ 3. Problem Statement

Insurance companies receive thousands of complaints every year but often struggle to identify patterns in complaint types, resolution speed, and recovery rates. Without proper analysis, it is difficult to understand which complaint categories take longer to resolve and what factors influence recovery outcomes.

This project aims to analyze the insurance complaint dataset and identify key factors influencing complaint resolution patterns and business recovery performance.

🎯 4. Objectives
To understand the dataset structure and complaint attributes
To clean and prepare the data for analysis
To handle missing values and duplicates
To perform Exploratory Data Analysis (EDA)
To engineer new features such as Resolution Days and Recovery Status
To identify complaint patterns and resolution trends
To create meaningful visualizations
To generate actionable business insights
📋 5. Attribute (Column / Feature) Details
#	Attribute Name	Data Type	Description
1	Company	Object	Name of the insurance company
2	File No.	Integer	Unique complaint file number
3	Opened	Date	Date complaint was opened
4	Closed	Date	Date complaint was closed
5	Coverage	Object	Type of insurance coverage
6	SubCoverage	Object	Sub-type of insurance coverage
7	Reason	Object	Primary reason for complaint
8	SubReason	Object	Detailed reason for complaint
9	Disposition	Object	How the complaint was handled
10	Conclusion	Object	Final conclusion of complaint
11	Recovery	Float	Amount recovered in USD
12	Status	Object	Current complaint status
🛠️ 6. Tools & Technologies
Python
Pandas
NumPy
Matplotlib
Seaborn
Google Colab
⚙️ 7. Data Pre-Processing and Feature Engineering

The dataset was prepared for analysis using data preprocessing techniques.

Data Cleaning Steps
Checked data types of all columns
Identified missing values (513 null values across 6 columns)
Handled null values using mode imputation and default value filling
Confirmed 0 duplicate records — no rows dropped
Converted date columns (Opened, Closed) to datetime format
Cleaned Recovery column by removing $ and , symbols → converted to numeric
Renamed File No. → File_No
Missing Value Treatment
Column	Missing Count	Method Used
SubCoverage	90 (18.0%)	Filled with 'Not Specified'
Disposition	207 (41.4%)	Filled with 'Unknown'
Conclusion	137 (27.4%)	Filled with 'Unknown'
Coverage	25 (5.0%)	Filled with Mode
Reason	20 (4.0%)	Filled with Mode
SubReason	20 (4.0%)	Filled with Mode
Closed	14 (2.8%)	Filled with Opened date

After Handling: Total missing values = 0

Feature Engineering

New features were created to improve analysis:

Resolution_Days – Calculated from (Closed – Opened) date difference
Resolution_Category – Fast (≤15 days), Medium (16–30 days), Slow (>30 days)
Recovery_Status – 'Recovered' if Recovery > 0, else 'Not Recovered'
Year, Month, Quarter – Extracted from Opened date for time-based analysis
Complaint_Age – Old (2021–22), Recent (2023–24), Latest (2025–26)
Is_Recovered – Binary flag (1 = Recovered, 0 = Not Recovered)

Final Dataset Shape: (500 rows × 20 columns)

📊 8. Analysis and Visualizations

The dataset was analyzed using Exploratory Data Analysis techniques to understand complaint patterns and relationships across coverage types, companies, and time periods.

🔍 9. Exploratory Data Analysis (EDA)

Initial inspection included:

Data frame structure verification (shape, dtypes) — Shape: (500, 12)
Statistical summary using df.describe(include='all')
Null value verification — 513 missing values across 6 columns
Duplicate record validation — 0 duplicates found
Unique value counts using df.nunique()

EDA helped in understanding the distribution and characteristics of the complaint data.

📸 EDA Screenshots
Screenshot	Description

📸 screenshots/s1_load.png
	Dataset loaded from GitHub — Shape: (500, 12)

📸 screenshots/s2_head.png
	First 5 rows using df.head()

📸 screenshots/s3_info.png
	Column names and data types using df.info()

📸 screenshots/s4_missing.png
	Missing values — 513 total across 6 columns

📸 screenshots/s5_unique.png
	Unique values per column using df.nunique()

📸 screenshots/s6_duplicate.png
	Duplicate check — 0 duplicates found

📸 screenshots/s7_missing_before.png
	Missing values before handling — 513 total

📸 screenshots/s8_missing_after.png
	Missing values after handling — 0 remaining

📸 screenshots/s9_transform.png
	Data transformation — Shape updated to (500, 16)

📸 screenshots/s10_feature.png
	Feature engineering — Final shape: (500, 20)

📸 screenshots/s11_final_eda.png
	Final EDA — All columns and data types confirmed
📐 10. Statistical Analysis

Statistical measures were used to summarize the dataset.

Measures included:

Mean
Median
Mode
Minimum value
Maximum value
Standard deviation

These measures helped understand the central tendency and variability of Resolution Days and Recovery amounts.

📈 11. Data Visualization

Visualization techniques were used to represent complaint data graphically and make patterns easier to understand.

1. Univariate Analysis

Univariate analysis was performed to analyze one variable at a time.

Analysis Performed:
1. Top 10 Companies by Complaint Count (with image)
📸 screenshots/v1_top_companies.png — Bar Chart | Matplotlib
Objective: To identify which insurance companies received the highest number of complaints.
Visualization: Horizontal bar chart showing top 10 companies sorted by complaint count.
Interpretation: Anthem Health Plans, Inc leads with 121 complaints (24.2%), making it the single largest complaint contributor among 121 companies.
Key Insight: One company alone accounts for nearly one-quarter of all complaints in the dataset.
Business Insight: Anthem Health Plans should conduct an internal audit to identify root causes of high complaint volumes and implement targeted service improvements.
2. Coverage Type Distribution (with image)
📸 screenshots/v2_coverage_pie.png — Pie Chart | Matplotlib
Objective: To understand which insurance coverage types receive the most complaints.
Visualization: Pie chart showing complaint proportion by coverage type.
Interpretation: A & H (Accident & Health) coverage dominates at 29.4% of complaints, followed by other coverage types.
Key Insight: A & H coverage accounts for the highest complaint share among all coverage categories.
Business Insight: Insurance companies offering A & H coverage should invest in better claim handling procedures to reduce complaint volumes in this category.
3. Complaint Reasons Distribution (with image)
📸 screenshots/v3_reasons.png — Bar Chart | Matplotlib
Objective: To identify the most frequently occurring complaint reasons in insurance filings.
Visualization: Vertical bar chart showing complaint counts by reason category.
Interpretation: Claim Handling is the dominant complaint reason at 75.4% (377 out of 500), indicating widespread dissatisfaction with claims processing.
Key Insight: Over 75% of all complaints are directly related to how claims are handled.
Business Insight: Insurance companies must prioritize improving claim processing speed, transparency, and communication to reduce the highest complaint category.
4. Complaint Status Distribution (with image)
📸 screenshots/v4_status_pie.png — Pie Chart | Matplotlib
Objective: To monitor how many complaints are currently open vs closed.
Visualization: Pie chart showing proportion of Open vs Closed complaints.
Interpretation: 97.2% of complaints (486 out of 500) are Closed, showing strong resolution performance across the dataset.
Key Insight: Nearly all complaints in the dataset have been successfully resolved.
Business Insight: While closure rates are high, the remaining 1.4% open complaints should be monitored and escalated to prevent aging complaints.
2. Bivariate Analysis

Bivariate analysis was performed to study relationships between two variables.

Analysis Performed:
5. Yearly Complaint Trend (2021–2026) (with image)
📸 screenshots/v5_yearly_trend.png — Line Chart | Matplotlib
Objective: To analyze how the number of complaints has changed from 2021 to 2026.
Visualization: Line chart showing yearly complaint count trends over 6 years.
Interpretation: Complaint volumes show a rising trend from 10 in 2021, reaching a peak of 131 complaints in 2025, reflecting increasing customer dissatisfaction over time.
Key Insight: Complaints increased by over 1200% from 2021 to 2025, signaling a significant growth in dissatisfaction.
Business Insight: Proactive intervention in complaint-heavy periods can help companies reverse negative trends and improve customer retention.
6. Resolution Days Distribution (with image)
📸 screenshots/v6_resolution_hist.png — Histogram | Matplotlib
Objective: To understand the distribution of time taken to resolve complaints.
Visualization: Histogram showing frequency of resolution day ranges.
Interpretation: Most complaints are resolved within 0–60 days. However, outliers exist with resolution times up to 880 days, indicating systemic delays in certain cases.
Key Insight: Average resolution time is 42.06 days; 47.4% of complaints fall in the Slow category (>30 days).
Business Insight: Companies should aim to reduce average resolution days to below 30 by streamlining internal review and escalation processes.
7. Complaint Status Count (with image)
📸 screenshots/v7_status_count.png — Count Plot | Seaborn
Objective: To compare the exact count of Open vs Closed complaints visually.
Visualization: Count plot showing bars for each complaint status category.
Interpretation: 486 complaints are Closed vs only 14 remaining Open, confirming a high resolution rate of 97.2%.
Key Insight: The dataset reflects strong complaint management performance with minimal pending complaints.
Business Insight: Focus should now shift from volume closure to quality of resolution and customer satisfaction scores.
3. Multivariate Analysis

Multivariate analysis was used to analyze relationships among multiple variables.

Analysis Performed:
8. Resolution Days by Coverage Type (with image)
📸 screenshots/v8_boxplot.png — Box Plot | Seaborn
Objective: To compare resolution speed across different insurance coverage types.
Visualization: Box plot showing resolution day spread for each coverage category.
Interpretation: Individual Private Passenger coverage shows the slowest average resolution at 49.43 days. Significant outliers indicate extreme delays in some cases.
Key Insight: Coverage type significantly influences how quickly a complaint gets resolved.
Business Insight: Coverage types with consistently high resolution times should have dedicated fast-track processing teams assigned.
9. Correlation Matrix — Numerical Features (with image)
📸 screenshots/v9_heatmap.png — Heatmap | Seaborn
Objective: To identify statistical relationships between numerical variables in the dataset.
Visualization: Heatmap showing correlation coefficients between Resolution_Days, Recovery, Is_Recovered, and other numeric features.
Interpretation: Resolution_Days and Recovery show minimal correlation, indicating resolution speed does not directly affect financial recovery outcome.
Key Insight: Recovery outcome is more dependent on complaint type and coverage than on how fast it is resolved.
Business Insight: Focusing on complaint category and coverage type rather than resolution speed alone can better predict financial recovery probability.
10. Avg Resolution Days by Complaint Reason (with image)
📸 screenshots/v10_avg_days.png — Bar Chart | Matplotlib
Objective: To identify which complaint reasons take the longest average time to resolve.
Visualization: Horizontal bar chart showing average resolution days for each complaint reason category.
Interpretation: Marketing & Sales complaints take the longest to resolve at an average of 50.50 days, while some other categories resolve faster.
Key Insight: Different complaint reasons have significantly different average resolution timelines.
Business Insight: Insurers should create reason-specific SLAs and escalation paths to address categories with above-average resolution times.
📸 Key Insights Screenshot
Screenshot	Description

📸 screenshots/s12_insights.png
	Key insights summary — all 8 metrics printed in Colab output
📊 12. Summary of Findings
Majority of complaints are related to Claim Handling — 75.4% of all complaints
Accident & Health (A/H) coverage has the highest complaint volume at 29.4%
97.2% of complaints are successfully closed — strong resolution performance
Average resolution time is 42.06 days; 47.4% fall in the Slow category (>30 days)
Complaint volumes grew significantly from 10 in 2021 to 131 in 2025
Total financial recovery achieved: $878,358.86 across 97 complaints (19.4%)
Anthem Health Plans, Inc is the top complaint company with 24.2% share
Marketing & Sales complaints take the longest to resolve at 50.50 days average
🧠 13. Types of Analysis
1. Descriptive Analysis

Descriptive analysis summarizes historical complaint data.

Examples:

Total complaint count by year and quarter
Average resolution days by coverage type
Distribution of complaint reasons and coverage types
2. Diagnostic Analysis

Diagnostic analysis explains why certain patterns occur.

Examples:

Reasons for higher complaint volumes in A/H coverage
Factors contributing to slow resolution categories
Why certain coverage types have lower recovery rates
3. Predictive Analysis

Predictive analysis helps forecast future outcomes.

Examples:

Predicting complaint volume for upcoming quarters
Estimating resolution time based on complaint type and coverage
Forecasting financial recovery based on coverage category
4. Prescriptive Analysis

Prescriptive analysis suggests actions based on insights.

Examples:

Offering faster resolution tracks for high-volume complaint categories
Improving claim handling processes in A/H coverage
Targeting coverage categories with lowest recovery rates for policy review
🚀 14. Future Enhancements and Suggestions
Include more records from all U.S. states for better geographic accuracy
Apply machine learning models to predict complaint resolution outcomes
Build interactive dashboards using Power BI or Tableau
Automate reporting process with scheduled Python scripts
Integrate NLP analysis on complaint reason text for deeper insights
✅ 15. Conclusion

The project successfully analyzed the Insurance Company Complaints dataset using Python and extracted useful insights about complaint patterns, resolution trends, and recovery behavior.

Data preprocessing and feature engineering helped in transforming raw data into meaningful analytical features. Visualization techniques revealed important patterns across coverage types, time periods, and resolution categories.

The results of this project can help insurance companies make better business decisions by identifying complaint-prone areas, improving resolution speed, and maximizing financial recovery outcomes.

📁 Repository Structure
📦 Kumarsakthi835-Insurance-Company-Complaints-Resolutions-Status-and-Recoveries
┣ 📄 Insurance Company.csv       → Sampled dataset (500 rows)
┣ 📓 Insurance_Complaints.ipynb   → Google Colab Notebook
┣ 📁 screenshots/                 → All stage & visualization screenshots
┗ 📄 README.md                    → Project Documentation
▶️ How to Run
Open Google Colab at colab.research.google.com
Upload the notebook file Insurance_Complaints.ipynb
Run all cells using Runtime → Run All or Ctrl + F9
All outputs, charts, and insights will be generated automatically
👨‍💻 Author
Kumar S

Data Analytics — Entri Elevate

📧 kumarsakthi835@gmail.com

🔗 github.com/kumarsakthi835

📍 Rasipuram, Tamil Nadu, India

📜 Data Source & License
Data sourced from U.S. Government Open Data Portal (data.gov)
Used for educational and analytical purposes only
Original dataset: Insurance Company Complaints, Resolutions, Status, and Recoveries
Project by: Kumar S  |  Data Analytics – Entri Elevate  |  Dataset Period: 2021–2026  |  Records: 500  |  Tools: Python, Pandas, NumPy, Matplotlib, Seaborn, Google Colab
