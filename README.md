# 🗃️ Inventory Data Pipeline and Analysis

This project demonstrates a complete data pipeline for inventory management using Python for ETL (Extract, Transform, Load) and SQL for analysis. It was designed to complete quarterly Inventory data analysis of all technology assets at the school site that I manage.  Insights gathered from this analysis is used to determine which Chromebooks are outside of their 5 year warranty, how many additional Chromebooks need to be purchased and how many Chromebooks need to be updated.

## 📁 Project Structure

- `inventory_etl.ipynb`: A Jupyter notebook that performs the full ETL process.
  - Reads raw inventory data from a CSV.
  - Cleans and standardizes data (column names, data types, date formats).
  - Removes duplicates and handles missing values.
  - Outputs a cleaned dataset for downstream analysis.

- `inventory_sql_analysis.sql`: A SQL script that runs several analytical queries.
  - Calculates total inventory by product and category.
  - Identifies low-stock or out-of-stock items.
  - Analyzes inventory trends over time.

## 📊 Use Case

This project can be used by warehouse managers, retail analysts, or data engineers who need to:

- Prepare inventory data for reporting or dashboarding.
- Monitor stock levels and optimize restocking.
- Derive insights from historical inventory trends.

## 🚀 Getting Started

1. **Run the ETL notebook** to clean and export inventory data.
2. **Load the cleaned CSV** into a SQL database.
3. **Execute the SQL script** to generate insights and reports.

## 🛠️ Requirements

- Python (pandas, datetime)
- Jupyter Notebook
- SQL database (e.g., SQLite, PostgreSQL)

## 📌 Author

Benjamin Flynn  
