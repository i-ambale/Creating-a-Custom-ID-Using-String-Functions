# 🆔 Creating a Custom Country ID Using SQL String Functions

This notebook guides you through creating customized country IDs in a relational database using SQL string functions. It demonstrates how to combine values like country name, year, and population size into a single, consistent identifier in the Access_to_Basic_Services table of the united_nations MySQL database.

⚠️ Important: This notebook is intended for use on a local machine and will not run on Google Colab due to the database connection requirements.
---
# 🎯 Learning Objectives
By the end of this notebook, you will be able to:

- Use string functions to generate a custom `country_id` column.

- Format and standardize custom IDs for consistent use across datasets.

- Combine multiple fields (e.g., `Country_name`, `Time_period`, `Est_population_in_millions`) into a single string identifier.
---
# 🧰 Tools & Setup
- Database Engine: MySQL

- Interface: MySQL Workbench or Jupyter Notebook using SQLAlchemy and PyMySQL

- Table Used: `Access_to_Basic_Services`
---
# 🔨 Example: Custom Country ID
Imagine a record like this:
```sql
Country_name: Kenya  
Time_period: 2015  
Est_population_in_millions: 45.3
```
We want to create a `country_id` that looks like:
```
KEN-2015-45M
```
To do this, we apply SQL functions like:
```
CONCAT(UCASE(LEFT(Country_name, 3)), '-', Time_period, '-', ROUND(Est_population_in_millions), 'M')
```
---
# 🧪 What You'll Practice
- `CONCAT()` – for joining strings together

- `IFNULL()` – for replacing null values

- `SUBSTRING()` - for slicing strings

- `UCASE()` or `UPPER()` – for capitalization
---
# 🔌 Connecting to the Database
Make sure your notebook is running locally and connected using something like:
```
'mysql+pymysql://root:yourpassword@localhost:3306/united_nations'
```
---
# ✅ Expected Outcomes
A new, formatted country_id column that helps uniquely identify each record in a human-readable and consistent format, which is helpful in reporting, analysis, or integration with other systems.
---
# 📦 Requirements
- Python ≥ 3.8

- `sqlalchemy`

- `pymysql`

- MySQL Workbench or equivalent

- `united_nations` database with the `Access_to_Basic_Services` table
---
# 👨‍🏫 Developed By
ExploreAI Academy

Adapted for real-world usage by **Ibrahim Ambale**
---

