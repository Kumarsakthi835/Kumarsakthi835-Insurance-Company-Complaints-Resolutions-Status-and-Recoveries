📁 Project Title
🛡️ Insurance Company Complaint Pattern & Resolution Analysis Using Python

📌 1. Project Overview

This project focuses on analyzing an insurance company complaints dataset using Python to extract meaningful insights. The analysis includes data cleaning, exploratory data analysis (EDA), statistical analysis, and visualization to understand complaint patterns, resolution trends, and recovery behavior across the United States.

The project aims to transform raw complaint data into useful information that supports better decision-making for insurance operations and customer service improvements.

🗂️ 2. Data Source

📄 Dataset Name: Insurance Company Complaints, Resolutions, Status, and Recoveries

🌐 Source: U.S. Government / Open Data Portal

📋 File Type: CSV

🔢 Number of Records: 500

📊 Number of Attributes: 12


The dataset contains information related to insurance complaints filed between 2021 and 2026, including complaint reasons, coverage types, resolution outcomes, and financial recovery amounts across the United States.

❓ 3. Problem Statement

Insurance companies receive thousands of complaints every year but often struggle to identify patterns in complaint types, resolution speed, and recovery rates. Without proper analysis, it is difficult to understand which complaint categories take longer to resolve and what factors influence recovery outcomes.

This project aims to analyze the insurance complaint dataset and identify key factors influencing complaint resolution patterns and business recovery performance.

🎯 4. Objectives

✅ To understand the dataset structure and complaint attributes
✅ To clean and prepare the data for analysis
✅ To handle missing values and duplicates
✅ To perform Exploratory Data Analysis (EDA)
✅ To engineer new features such as Resolution Days and Recovery Status
✅ To identify complaint patterns and resolution trends
✅ To create meaningful visualizations
✅ To generate actionable business insights

🧾 5. Attribute (Column / Feature) Details

Attribute Name	Description
File No.	Unique identifier for each complaint
Opened	Date when the complaint was filed
Closed	Date when the complaint was resolved
Company	Name of the insurance company
Coverage	Type of insurance coverage (e.g., A/H, Auto, Property)
SubCoverage	Sub-category of the coverage type
Reason	Primary reason for the complaint
SubReason	Detailed sub-reason for the complaint
Disposition	How the complaint was handled
Conclusion	Final resolution outcome
Status	Current status of the complaint
Recovery	Financial recovery amount (in USD)

🛠️ 6. Tools & Technologies

🐍 Python
🐼 Pandas
🔢 NumPy
📊 Matplotlib
🎨 Seaborn
☁️ Google Colab

🧹 7. Data Pre-Processing and Feature Engineering

The dataset was prepared for analysis using data preprocessing techniques.

🔍 Data Cleaning Steps

🔎 Checked data types of all columns
⚠️ Identified missing values (513 null values across 6 columns)
🛠️ Handled null values using mode imputation and default value filling
🗑️ Removed duplicate records
✏️ Corrected inconsistent data formats
📅 Converted date columns (Opened, Closed) to datetime format
💰 Cleaned Recovery column by removing $ and , symbols and converting to numeric

🔧 Missing Value Treatment:

Column	Method Used
SubCoverage	Filled with 'Not Specified'
Coverage	Filled with mode value
Reason	Filled with mode value
SubReason	Filled with mode value
Disposition	Filled with 'Unknown'
Conclusion	Filled with 'Unknown'
Closed	Filled with Opened date

⚙️ Feature Engineering

New features were created to improve analysis:

📆 Resolution_Days – Calculated from (Closed – Opened) date difference
🏷️ Resolution_Category – Fast (≤15 days), Medium (16–30 days), Slow (>30 days)
💸 Recovery_Status – 'Recovered' if Recovery > 0, else 'Not Recovered'
🗓️ Year, Month, Quarter – Extracted from Opened date for time-based analysis
🕰️ Complaint_Age – Old (2021–22), Recent (2023–24), Latest (2025–26)
🔢 Is_Recovered – Binary flag (1 = Recovered, 0 = Not Recovered)

📈 8. Analysis and Visualizations

The dataset was analyzed using Exploratory Data Analysis techniques to understand complaint patterns and relationships.

🔬 9. Exploratory Data Analysis (EDA)

Initial inspection included:

📐 Data frame structure verification (shape, dtypes)
📊 Statistical summary of numerical columns
🔍 Null value verification
🔄 Duplicate record validation
🗃️ Unique value counts for categorical columns

EDA helped in understanding the distribution and characteristics of the complaint data.

📐 10. Statistical Analysis

Statistical measures were used to summarize the dataset.

Measures included:

➕ Mean
📍 Median
🔁 Mode
⬇️ Minimum value
⬆️ Maximum value
📉 Standard deviation

These measures helped understand the central tendency and variability of Resolution Days and Recovery amounts.

📊 11. Data Visualization

Visualization techniques were used to represent complaint data graphically and make patterns easier to understand.

📌 1. Univariate Analysis

Univariate analysis was performed to analyze one variable at a time.

Analysis Performed:

📊 Visualization 1 – Top 10 Insurance Complaint Reasons
📷
[Screenshot: Bar Chart – Top 10 Insurance Complaint Reasons]
🎯 Objective: To identify the most frequently occurring complaint reasons in insurance filings.
📊 Visualization: Horizontal bar chart showing top 10 complaint reasons sorted by frequency count.
🔍 Interpretation: "Claim Handling" and "Delays" are the most common complaint reasons, indicating customers are most dissatisfied with how their claims are processed.
💡 Key Insight: Over 35% of complaints are related to claim handling issues alone.
💼 Business Insight: Insurance companies should prioritize improving claim processing speed and communication to reduce the highest complaint categories.
🛡️ Visualization 2 – Coverage Type Distribution
📷
[Screenshot: Bar Chart – Insurance Coverage Type Distribution]
🎯 Objective: To understand which insurance coverage types receive the most complaints.
📊 Visualization: Vertical bar chart showing complaint counts by coverage type.
🔍 Interpretation: Accident and Health (A/H) coverage generates the highest number of complaints, followed by Auto and Property insurance.
💡 Key Insight: A/H coverage accounts for the majority of total complaints in the dataset.
💼 Business Insight: Companies offering A/H coverage should invest in better claim handling procedures to reduce complaint volumes.
⏱️ Visualization 3 – Complaint Resolution Category Distribution
📷
[Screenshot: Pie Chart – Complaint Resolution Speed Distribution]
🎯 Objective: To understand how quickly complaints are being resolved across the dataset.
📊 Visualization: Pie chart showing proportion of Fast, Medium, and Slow resolution categories.
🔍 Interpretation: A significant portion of complaints fall under the "Slow" category, indicating many complaints take more than 30 days to close.
💡 Key Insight: Less than 30% of complaints are resolved within 15 days (Fast category).
💼 Business Insight: Companies should target reducing slow resolutions by setting internal SLAs and escalation procedures.

📌 2. Bivariate Analysis

Bivariate analysis was performed to study relationships between two variables.

Analysis Performed:

📅 Visualization 4 – Complaint Volume by Year
📷
[Screenshot: Line Chart – Complaint Volume Trend by Year (2021–2026)]
🎯 Objective: To analyze how the number of complaints has changed over the years.
📊 Visualization: Line chart showing yearly complaint count trends from 2021 to 2026.
🔍 Interpretation: Complaint volumes show a rising trend from 2021 to 2024 with a peak in recent years, reflecting increasing customer dissatisfaction over time.
💡 Key Insight: Complaints increased year-over-year between 2021 and 2024.
💼 Business Insight: Proactive intervention in complaint-heavy years can help companies reverse negative trends and improve customer retention.
📉 Visualization 5 – Resolution Days Distribution
📷
[Screenshot: Histogram – Distribution of Resolution Days]
🎯 Objective: To understand the distribution of time taken to resolve complaints.
📊 Visualization: Histogram showing the frequency of resolution day ranges.
🔍 Interpretation: Most complaints are resolved within 30–60 days. However, outliers exceeding 180 days indicate systemic delays in certain cases.
💡 Key Insight: The average resolution time is approximately 45–60 days, which is above the ideal target.
💼 Business Insight: Companies should aim to reduce average resolution days to below 30 by streamlining internal review processes.
💰 Visualization 6 – Recovery Amount by Coverage Type
📷
[Screenshot: Box Plot – Recovery Amount by Coverage Type]
🎯 Objective: To compare financial recovery amounts across different coverage types.
📊 Visualization: Box plot showing recovery amount spread for each coverage category.
🔍 Interpretation: Auto and Property coverage show higher median recovery amounts compared to A/H. Significant outliers indicate some cases with very large recoveries.
💡 Key Insight: Property-related complaints tend to yield the highest recovery amounts.
💼 Business Insight: Higher recovery amounts in certain coverage types suggest greater financial risk and should be monitored closely.

📌 3. Multivariate Analysis

Multivariate analysis was used to analyze relationships among multiple variables.

Analysis Performed:

⚖️ Visualization 7 – Complaint Disposition vs Resolution Speed
📷
[Screenshot: Grouped Bar Chart – Complaint Disposition vs Resolution Category]
🎯 Objective: To understand how the complaint handling method affects resolution speed.
📊 Visualization: Grouped bar chart comparing disposition types (Upheld, Denied, Withdrawn) against resolution categories.
🔍 Interpretation: Complaints that were "Upheld" tend to have longer resolution times compared to "Withdrawn" complaints. "Denied" cases are resolved faster on average.
💡 Key Insight: Upheld complaints require more review time, contributing to slow resolution rates.
💼 Business Insight: Insurers should create fast-track processes for cases likely to be upheld to improve customer satisfaction.
💹 Visualization 8 – Recovery Status by Coverage Type
📷
[Screenshot: Stacked Bar Chart – Recovery Status by Coverage Type]
🎯 Objective: To analyze which coverage types have higher financial recovery rates.
📊 Visualization: Stacked bar chart showing Recovered vs Not Recovered counts for each coverage type.
🔍 Interpretation: Property and Auto coverage types show relatively higher recovery rates, while Life and A/H coverage show lower recovery percentages.
💡 Key Insight: Only about 40% of complaints across all coverage types result in financial recovery.
💼 Business Insight: Improving recovery rates in low-performing coverage categories can significantly reduce financial losses for insurance companies.
🗓️ Visualization 9 – Complaint Count by Quarter
📷
[Screenshot: Bar Chart – Complaint Count by Quarter (Q1–Q4)]
🎯 Objective: To identify seasonal patterns in complaint filing behavior.
📊 Visualization: Bar chart showing total complaints filed in Q1, Q2, Q3, and Q4.
🔍 Interpretation: Q1 and Q3 show the highest complaint volumes, suggesting seasonal peaks in customer dissatisfaction. Q4 has relatively fewer complaints.
💡 Key Insight: Complaint volumes peak in Q1 (January–March) and Q3 (July–September).
💼 Business Insight: Companies should increase support staff and response capacity during Q1 and Q3 to handle peak complaint periods effectively.
🔥 Visualization 10 – Correlation Heatmap
📷
[Screenshot: Heatmap – Correlation Between Numerical Features]
🎯 Objective: To identify statistical relationships between numerical variables in the dataset.
📊 Visualization: Heatmap showing correlation coefficients between Resolution_Days, Recovery, Is_Recovered, and other numeric features.
🔍 Interpretation: Recovery amount shows moderate positive correlation with Is_Recovered. Resolution_Days shows minimal correlation with recovery, indicating resolution speed does not directly affect recovery outcome.
💡 Key Insight: Recovery amount and recovery status are strongly correlated, as expected.
💼 Business Insight: Focusing on complaint type and coverage rather than speed alone can better predict whether a financial recovery will occur.

📝 12. Summary of Findings

🔴 Majority of complaints are related to Claim Handling and Delays
🏥 Accident & Health (A/H) coverage has the highest complaint volume
⏳ Most complaints take more than 30 days to resolve (Slow category)
📈 Complaint volumes have increased year-over-year from 2021 to 2024
💰 Property and Auto coverage types yield the highest recovery amounts
📉 Only about 40% of complaints result in any financial recovery
📅 Q1 and Q3 are peak periods for complaint filings
⚖️ Upheld complaints take significantly longer to resolve than denied ones

🔎 13. Types of Analysis

📋 1. Descriptive Analysis

Descriptive analysis summarizes historical complaint data.

Examples:

📊 Total complaint count by year and quarter
⏱️ Average resolution days by coverage type
🗃️ Distribution of complaint reasons and coverage types

🔍 2. Diagnostic Analysis

Diagnostic analysis explains why certain patterns occur.

Examples:

❓ Reasons for higher complaint volumes in A/H coverage
⚠️ Factors contributing to slow resolution categories
📉 Why certain coverage types have lower recovery rates

🔮 3. Predictive Analysis

Predictive analysis helps forecast future outcomes.

Examples:

📈 Predicting complaint volume for upcoming quarters
⏳ Estimating resolution time based on complaint type
💰 Forecasting financial recovery based on coverage category

💡 4. Prescriptive Analysis

Prescriptive analysis suggests actions based on insights.

Examples:

🚀 Offering faster resolution tracks for high-value complaints
🛠️ Improving claim handling processes in A/H coverage
🎯 Targeting complaint categories with lowest recovery rates for policy review

🚀 14. Future Enhancements and Suggestions

🗺️ Include more records from all U.S. states for better geographic accuracy
🤖 Apply machine learning models to predict complaint resolution outcomes
📊 Build interactive dashboards using Power BI or Tableau
⚙️ Automate reporting process with scheduled Python scripts
💬 Integrate NLP analysis on complaint reason text for deeper insights

✅ 15. Conclusion

The project successfully analyzed the Insurance Company Complaints dataset using Python and extracted useful insights about complaint patterns, resolution trends, and recovery behavior.

Data preprocessing and feature engineering helped in transforming raw data into meaningful analytical features. Visualization techniques revealed important patterns across coverage types, time periods, and resolution categories.

The results of this project can help insurance companies make better business decisions by identifying complaint-prone areas, improving resolution speed, and maximizing financial recovery outcomes.

👨‍💻 Project by: Kumar S  |  🎓 Data Analytics – Entri Elevate  |  📅 Dataset Period: 2021–2026  |  🔢 Records: 500  |  🛠️ Tools: Python, Pandas, NumPy, Matplotlib, Seaborn, Google Colab
