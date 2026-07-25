# myportfolio
**CREDIT CARD FRAUD DETECTION ANALYSIS**

**Credit Card Fraud Detection Analysis**
Power BI Dashboard Project

Project Overview

Analysis of 500,000 real credit card transactions covering January to August 2019, taken from a 1.3 million row dataset. The project identifies fraud patterns across merchants, categories, geography and customer behaviour to support financial institutions in fraud prevention decision making.

Built following the structured data analytics workflow:
Ask, Prepare, Process, Analyze, Share, Act

Objectives

Determine the overall fraud rate. Identify who is most affected by age, gender and location. Analyze when fraud occurs and identify time patterns. Highlight high risk categories, merchants and transaction sizes.

Dataset

Source: Credit Card Transaction Fraud Detection, Kaggle, Kartik Shenoy
Original size: 1.3 million transactions
Working sample: 500,000 transactions, January to August 2019
Total columns: 23

Key fields: trans_date_trans_time, amt, category, merchant, gender, state, city, is_fraud

**Tools and Technologies**

Power BI Desktop for data modelling and visualisation. Power Query for data cleaning and transformation. DAX for calculated measures and columns. SQL for querying logic understanding.

**Data Preparation in Power Query**

Removed unnecessary columns. Filtered dataset to 500,000 rows for performance optimisation. Split trans_date_trans_time into separate Date and Time columns. Fixed data types including scientific notation issues. Created derived columns including Hour, Day of Week, Month, Age and Amount Band. Set correct data categories for Latitude and Longitude columns. Removed duplicates and ensured data consistency.

**Data Modelling**

Implemented Star Schema. Created Date Table for time intelligence. Built relationships with correct cardinality. Hidden foreign key columns for clean model view.

**KEY DAX MEASURES**

Total Transactions = COUNT(TRANSACTIONS[trans_num])

Total Fraud Cases = CALCULATE(COUNT(TRANSACTIONS[is_fraud]), TRANSACTIONS[is_fraud] = 1)

Total Fraud Loss = CALCULATE(SUM(TRANSACTIONS[amt]), TRANSACTIONS[is_fraud] = 1)

Fraud Rate = DIVIDE([Total Fraud Cases], [Total Transactions])

Avg Loss per Fraud = DIVIDE([Total Fraud Loss], [Total Fraud Cases])

Amount Band = SWITCH(TRUE(), TRANSACTIONS[amt] <= 50, "1. $0 to $50", TRANSACTIONS[amt] <= 100, "2. $51 to $100", TRANSACTIONS[amt] <= 200, "3. $101 to $200", TRANSACTIONS[amt] <= 500, "4. $201 to $500", "5. $500 plus")

**Dashboard Pages**

**Page 1 Fraud Overview**
**KPIs:** Total Transactions, Fraud Cases, Non-Fraud Cases, Total Fraud Loss, Fraud Rate, Average Loss per Fraud.
**Visuals**: Multi-line fraud rate by age group and month, fraud vs non-fraud donut, fraud amount by month, monthly fraud table, top 5 categories by fraud amount.

**Page 2 Merchant and Category Risk**
**KPIs:** Total Fraud Loss, Fraud Rate, Fraud Transactions, Average Loss per Fraud.
**Visuals:** Top 5 merchants by fraud rate, top 5 categories by fraud loss, fraud rate by amount band, category distribution donut, insight text box.

**Page 3 Geographical Fraud Analysis**
**KPIs:** Total Amount, Total Fraud Loss, Non-Fraud Cases, Fraud Transactions, Average Transaction Amount. 
**Visuals:** Regional fraud matrix by month, fraud by age group, geographic bubble map by merchant location, regional fraud distribution donut.

**Page 4 Time and Customer Behaviour**
**KPIs:** Total Amount, Total Transactions, Total Fraud Loss, Fraud Transactions, Non-Fraud Cases. 
**Visuals:** Fraud rate by age group, fraud transactions by hour, top 10 jobs by fraud loss, gender fraud trend by month, fraud by weekday and time of day.

**KEY INSIGHTS**

Fraud rate is 0.61% but causes $1.58M in total losses. Shopping Net is the highest risk category at 30% of fraud losses. Transactions above $500 show disproportionately high fraud rates. Evening hours consistently record the highest fraud activity. Age 65 plus is the most targeted demographic across all regions. North East region records highest fraud concentration at 31%. Monday and Tuesday are highest fraud risk weekdays. TEFL Teachers recorded highest fraud losses by profession.

Dashboard Design

Theme: Dark Mode. Primary background: Navy Blue. Accent colour: Gold and Yellow. Supporting: Dark Charcoal. Focus: Clean, professional and easy to read visuals.

Business Impact

This dashboard helps financial institutions detect high risk behaviour patterns, improve targeted fraud prevention strategies and enable data driven decision making across risk teams.

Future Improvements

Add real time fraud detection integration. Incorporate machine learning fraud prediction models. Expand dataset for long term trend analysis. Add customer segmentation analysis.

**Author**

Paul Letam
Data Analyst | Power BI | DAX | Power Query | SQL
GitHub: github.com/bpanalyticsinsight
Email: letambariledumpaul@gmail.com
