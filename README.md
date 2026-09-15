# Ecommerce-Data-Analyst-Project
**Project Overview**
E-Commerce Data Analytics: Automated ETL Pipeline
This project demonstrates a complete end-to-end ETL (Extract, Transform, Load) pipeline built with Python. It takes raw, unstructured e-commerce sales data, performs rigorous data cleaning and feature engineering, and seamlessly loads the optimized dataset into a MySQL relational database for downstream visualization and reporting in Power BI.

**Data Loading:** You successfully imported the raw Ecommerce_Unclean_Project.xlsx file.  
**Data Cleaning:** You removed duplicate records, handled invalid values like 'N/A' and 'NULL', stripped extra spaces, and formatted text columns (like City and State) into Title Case. You also filtered out invalid email addresses.  
**Data Formatting:** You converted dates into the correct datetime format and smartly filled in missing values, like putting 0 for Discount and 'Unknown' for Phone. You also dropped orders with negative or zero quantities.  
**Feature Engineering**: You created new, highly useful columns from the existing data, such as Sales, Net_Amount, Profit, month, Year, and Weekday.  
**Data Export (Pipeline):** Finally, you saved this clean data into a CSV file (Clean_Ecommerce_data.csv) and pushed it directly to a MySQL database table named orders using SQLAlchemy and the replace method.  


 **Tech Stack & Libraries**
Language: Python (Jupyter Notebook)

Data Manipulation: Pandas, NumPy

Database Integration: SQLAlchemy, PyMySQL (MySQL)

File Handling: Openpyxl (Excel)

** Key Data Processing Steps (The ETL Process)**
1. **Data Extraction**
Imported raw sales data from an uncleaned Excel file (Ecommerce_Unclean_Project.xlsx) containing 551 initial records.

**2. Data Transformation & Cleaning**
Deduplication: Identified and removed duplicate records.

Handling Null & Invalid Values: Standardized invalid entries (e.g., 'N/A', 'NULL') to NaN and dynamically filled missing values (e.g., setting missing discounts to 0 and empty phone numbers to 'Unknown').

Text Standardization: Stripped leading and trailing whitespaces and converted categorical columns (Customer_Name, City, State) into proper Title Case.

Data Quality Checks: Filtered out logically incorrect data, such as orders with negative or zero quantities, and ensured all email addresses contained a valid @ symbol.

Type Casting: Converted Order_Date and Delivery_Date to proper Datetime formats, and cast operational columns (Qty, Unit_Price, Discount) to numeric data types.

**3. Feature Engineering**
Created crucial business metrics directly within the pipeline for faster Business Intelligence (BI) dashboard rendering:

Calculated Sales (Qty * Unit_Price).

Derived Net_Amount by factoring in discounts.

Estimated Profit margins based on the net amount.

Extracted temporal features like Month, Year, and Weekday for time-series analysis.

**4. Data Loading (Database Integration)**
Exported the finalized, analytics-ready dataset (reduced to a clean 401 records) into a Clean_Ecommerce_data.csv file.

Established a direct connection to a local MySQL database using SQLAlchemy.

Automated the data ingestion process to a table named orders using the if_exists='replace' methodology to prevent data duplication.

**Impact**
By automating the cleaning and database insertion process, this Python script eliminates manual Excel formatting and ensures that downstream business intelligence tools (like Power BI) are always connected to a reliable, accurate, and single source of truth.

This description tells recruiters that you didn't just build a visual dashboard, but you also handled the complex backend data engineering using Python and SQL.
