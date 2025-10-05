💳 Financial Transactions Analysis Dashboard
📊 Overview

This project focuses on analyzing financial transactions data to uncover insights related to spending behavior, fraud detection, and card performance.
The workflow integrates SQL, Python, and Power BI to form an end-to-end data analysis pipeline — from data extraction to visualization.

⚙️ Step 1 — Data Extraction (SQL Server)

The project begins by connecting to SQL Server to retrieve data from three main tables:

Financial_Transaction — contains transaction details (amount, merchant info, MCC description, etc.)

Cards_Data — contains card metadata (brand, type, chip status, credit limit, etc.)

Users_Data — includes customer demographic and income information

Key tasks performed:

Established connection to SQL Server using pyodbc

Verified and previewed datasets before loading

Selected relevant columns for analysis (e.g., transaction amount, merchant category, card brand, user income)

🧹 Step 2 — Data Cleaning and Preparation (Python - Pandas)

Data cleaning was performed in Python to ensure data consistency and prepare it for analysis.

Main operations:

Merged multiple tables into a unified DataFrame

Handled missing values and formatting inconsistencies

Corrected misaligned columns (e.g., MCC description spilling into the fraud column)

Converted dates to proper datetime format

Removed duplicates and ensured correct data types

Sampled the top 800,000 rows from the financial dataset for performance efficiency

New derived fields:

Transaction year (for time series analysis)

Fraud flag normalization (is_fraud = 0 or 1)

Grouped MCC categories and card types

📈 Step 3 — Data Modeling (Power BI)

In Power BI, the cleaned data was loaded and related using a data model:

Tables used:

users_data

cards_data

Financial_Transaction

(Optionally a merged dataset for dashboard performance)

Relationships built:

users_data[user_id] → Financial_Transaction[user_id]

cards_data[card_id] → Financial_Transaction[card_id]

This model enables dynamic filtering and cross-table insights.

🎨 Step 4 — Dashboard Design (Power BI)

A multi-page Power BI Dashboard was created to display key financial insights.

Page 1 — Financial Overview Dashboard

KPIs and Cards

Total Yearly Income

Total Transaction Amount

Average Credit Limit

Total Number of Transactions

Visuals

📉 Line Chart: Total transaction amount over the years

📊 Bar Chart: Top 5 merchant categories by transaction amount

🥧 Pie Chart: Transaction amount by card brand

🗺️ Map Visual: Geographic distribution of merchant states

🎚️ Slicers: Card Type, Chip Usage Type (Vertical layout)

Page 2 — Users & Cards Insights

(Optional second page if added)

Age group distribution

Income vs. credit limit analysis

Number of cards per user

Fraud ratio by card type or brand

💡 Step 5 — Insights and Findings

Wholesale Clubs and Utility Services are the top spending categories.

Mastercard dominates total transaction volume.

The majority of cards use chip-based transactions, reflecting modern security adoption.

High income groups correlate with higher credit limits and lower fraud rates.

🛠️ Tools & Technologies
Tool	Purpose
SQL Server	Data extraction and storage
Python (Pandas, NumPy)	Data cleaning and preprocessing
Power BI	Data modeling and visualization
GitHub	Version control and documentation
