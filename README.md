# SQL_DATA_WAREHOUSE_PROJECT
BUILDING A MODERN DATA WAREHOUSE WITH SQL SERVER,INCLUDING ETLPROCESSES,DATA MODELING AND ANALYTICS
SQL Data Warehouse Project: Medallion Architecture
📌 Project Overview
This project demonstrates the end-to-end design and implementation of a modern Data Warehouse using SQL Server and T-SQL. Following the Medallion Architecture, I transformed raw, unstructured data into a business-ready "Gold" layer optimized for reporting and analytics.

The project simulates a real-world scenario where a retail business needs to centralize data from various sources (CRM, ERP) to analyze sales performance and customer demographics.

🏗️ Architecture: The Medallion Approach
The data flows through three distinct stages to ensure quality and integrity:

Bronze (Raw): Direct ingestion of source CSV files. No transformations are applied here to maintain a "source of truth."

Silver (Standardized): Data is cleaned, deduplicated, and cast into correct data types. Standardized formats are applied to dates, currency, and strings.

Gold (Analytics): Business logic is applied. Data is modeled into a Star Schema consisting of Fact and Dimension tables, optimized for Power BI/Tableau.

🛠️ Tech Stack & Tools
Language: T-SQL (Transact-SQL)

Database: Microsoft SQL Server

IDE: SQL Server Management Studio (SSMS)

Modeling: Dimensional Modeling (Star Schema)

🚀 Key Features & Workflow
1. Data Ingestion (Bronze)
Created a dedicated bronze schema.

Developed stored procedures to automate the loading of CSV files using the BULK INSERT command.

Implemented "Truncate and Load" logic for full data refreshes.

2. Data Cleaning & Transformation (Silver)
Identified and handled missing values and outliers.

Standardized text data (e.g., converting 'M'/'F' to 'Male'/'Female').

Removed duplicates using ROW_NUMBER() and CTE methods.

Enforced data integrity by ensuring primary keys and foreign keys align.

3. Dimensional Modeling (Gold)
Designed a Star Schema to reduce join complexity and improve query performance.

Fact Tables: Centralized quantitative data (Sales, Quantity, Price).

Dimension Tables: Descriptive attributes (Customer details, Product categories, Geography).

📂 Project Structure
Plaintext
├── Scripts/
│   ├── 01_Bronze_Layer/     # Scripts for table creation and data loading
│   ├── 02_Silver_Layer/     # Data cleaning and standardization scripts
│   ├── 03_Gold_Layer/       # Transformation into Fact and Dimension tables
│   └── 04_Analytics/        # Sample business queries and views
├── Data/                    # Source CSV files (or links to datasets)
└── README.md                # Project documentation
📈 Sample Business Insights
Using the final Gold layer, the warehouse can answer critical business questions such as:

What is the total revenue per product category over time?

Which geographic regions have the highest customer churn?

What is the average order value (AOV) per customer segment?

📝 How to Use
Clone this repository.

Run the init_database.sql script to create the environment.

Execute scripts in the Scripts/ folder in numerical order.

(Optional) Connect the gold views to a BI tool of your choice.
