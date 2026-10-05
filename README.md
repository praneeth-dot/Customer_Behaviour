
👨🏻‍💻Customer Behavior Data Analyst Portfolio Project

📌 Project Overview

This project demonstrates an **end-to-end Data Analyst workflow** for analyzing e-commerce sales and customer behavior.

The project starts with raw customer and sales data, performs **data loading and exploratory data analysis (EDA) using Python**, stores the cleaned dataset in **PostgreSQL**, performs business analysis using **SQL queries**, and finally connects the analyzed data to **Power BI** to create an interactive dashboard.

A **Gamma presentation** is also created to communicate the project findings, business insights, and recommendations in a professional format.

🎯 Project Objective

The main objective is to:

* Understand customer purchasing behavior
* Identify important sales and revenue patterns
* Analyze customer segments
* Find high-performing categories
* Identify trends and business opportunities
* Build an interactive business dashboard
* Present data-driven insights to stakeholders

---

 🔄 Project Workflow

```text
Raw Dataset
     ↓
Python
     ↓
Data Loading & Cleaning
     ↓
Exploratory Data Analysis (EDA)
     ↓
PostgreSQL
     ↓
SQL Queries & Business Analysis
     ↓
Power BI
     ↓
Interactive Dashboard
     ↓
Gamma
     ↓
Business Presentation & Insights
```

---

# 🛠️ Tools & Technologies

| Tool                | Purpose                        |
| ------------------- | ------------------------------ |
| 🐍 Python           | Data loading, cleaning and EDA |
| 🐼 Pandas           | Data manipulation and analysis |
| 📊 Matplotlib       | Data visualization             |
| 🎨 Seaborn          | Statistical visualization      |
| 🐘 PostgreSQL       | Database storage               |
| 🗄️ SQL             | Business analysis and querying |
| 📈 Power BI         | Dashboard and reporting        |
| 🖥️ Gamma           | Business presentation          |
| 📓 Jupyter Notebook | Python analysis environment    |

---

# 📂 Project Structure

```text
AI-Ecommerce-Sales-Customer-Analytics/
│
├── 📁 data/
│   └── ecommerce_dataset.csv
│
├── 📁 python/
│   └── ecommerce_eda.ipynb
│
├── 📁 sql/
│   └── ecommerce_analysis.sql
│
├── 📁 powerbi/
│   └── ecommerce_dashboard.pbix
│
├── 📁 presentation/
│   └── ecommerce_analysis_presentation.pdf
│
├── 📁 images/
│   ├── dashboard.png
│   ├── revenue_analysis.png
│   └── customer_analysis.png
│
└── README.md
```

---

# 1️⃣ Data Loading Using Python

The raw e-commerce dataset is initially loaded into **Python using Pandas**.

### Key activities

* Import dataset
* Read CSV file
* Understand dataset structure
* Check rows and columns
* Inspect data types
* Identify missing values
* Identify duplicate records
* Check unique values
* Understand numerical and categorical columns

### Example

```python
import pandas as pd

df = pd.read_csv("ecommerce_dataset.csv")

df.head()
```

### Dataset Inspection

```python
df.shape
df.info()
df.describe()
df.isnull().sum()
df.duplicated().sum()
```

---

# 2️⃣ Data Cleaning & Preparation

The dataset is cleaned and prepared before performing analysis.

### Cleaning activities

* Handling missing values
* Removing duplicate records
* Correcting data types
* Renaming columns
* Handling inconsistent values
* Creating required columns
* Sorting data
* Preparing categorical and numerical fields

Example:

```python
df = df.drop_duplicates()

df.columns = df.columns.str.lower().str.replace(" ", "_")
```

The cleaned dataset is then used for further exploratory analysis.

---

# 3️⃣ Exploratory Data Analysis (EDA)

EDA is performed using **Pandas, Matplotlib, and Seaborn** to understand customer behavior and sales patterns.

### 🔍 EDA Areas

#### Customer Analysis

* Customer demographics
* Age groups
* Customer segments
* Purchase frequency
* Average purchase amount
* Customer spending behavior

#### Sales Analysis

* Total sales
* Total revenue
* Average purchase amount
* Number of transactions
* Revenue by category
* Revenue by customer segment

#### Behavioral Analysis

* Purchase patterns
* Discount usage
* Customer preferences
* High-value customers
* Category preferences
* Spending trends

### Example Analysis

```python
df.groupby("category")["purchase_amount"].sum()
```

### Visualization Examples

* Revenue by Category
* Revenue by Age Group
* Customer Spending Distribution
* Purchase Trends
* Category Performance
* Customer Segment Analysis

---

# 4️⃣ Loading Data into PostgreSQL

After Python-based analysis and preparation, the dataset is loaded into a **PostgreSQL database**.

### Database Workflow

```text
Python Dataset
      ↓
PostgreSQL Database
      ↓
E-commerce Table
      ↓
SQL Analysis
```

The database provides a structured environment for performing business queries.

### Example Table

```text
ecommerce_sales
```

Possible fields include:

```text
customer_id
age
gender
category
purchase_amount
discount
subscription_status
purchase_date
payment_method
```

---

# 5️⃣ SQL Business Analysis

SQL is used to answer important business questions from the PostgreSQL database.

### 📌 Key Business Questions

#### 1. What is the total revenue?

```sql
SELECT SUM(purchase_amount) AS total_revenue
FROM ecommerce_sales;
```

#### 2. What is the average purchase amount?

```sql
SELECT AVG(purchase_amount) AS average_purchase
FROM ecommerce_sales;
```

#### 3. Which category generates the highest revenue?

```sql
SELECT
    category,
    SUM(purchase_amount) AS revenue
FROM ecommerce_sales
GROUP BY category
ORDER BY revenue DESC;
```

#### 4. What is the revenue by gender?

```sql
SELECT
    gender,
    SUM(purchase_amount) AS revenue
FROM ecommerce_sales
GROUP BY gender;
```

#### 5. Which customers spent more than the average purchase amount?

```sql
SELECT
    customer_id,
    purchase_amount
FROM ecommerce_sales
WHERE purchase_amount >
      (SELECT AVG(purchase_amount)
       FROM ecommerce_sales);
```

#### 6. What is the number of purchases by category?

```sql
SELECT
    category,
    COUNT(*) AS purchase_count
FROM ecommerce_sales
GROUP BY category
ORDER BY purchase_count DESC;
```

---

# 6️⃣ Connecting PostgreSQL to Power BI

The analyzed data is connected from **PostgreSQL to Power BI**.

### Power BI workflow

```text
PostgreSQL
     ↓
Power BI
     ↓
Data Transformation
     ↓
Data Modeling
     ↓
DAX Measures
     ↓
Visualizations
     ↓
Interactive Dashboard
```

### Power BI activities

* Connect PostgreSQL to Power BI
* Load required tables
* Verify data types
* Perform required transformations
* Create relationships
* Create DAX measures
* Add filters and slicers
* Design dashboard
* Validate KPIs and visuals

---

# 7️⃣ Power BI Dashboard

The final dashboard provides an interactive view of **sales performance and customer behavior**.

### 📊 KPI Cards

The dashboard includes important KPIs such as:

* 💰 Total Revenue
* 🛒 Total Purchases
* 👥 Total Customers
* 💵 Average Purchase Amount
* 📈 Customer/Revenue Performance

### 📈 Dashboard Visuals

Possible dashboard visuals include:

* Revenue by Category
* Revenue by Age Group
* Revenue by Gender
* Customer Segment Analysis
* Purchase Trends
* Subscription Status
* Top Categories
* Customer Behavior Patterns

### 🎛️ Interactive Filters

Users can analyze the dashboard using slicers such as:

* Age Group
* Gender
* Category
* Subscription Status
* Country
* Date

---

# 8️⃣ Customer Behavior Analysis

A major focus of the project is understanding **customer behavior patterns**.

The analysis helps identify:

* High-value customers
* Frequently purchased categories
* Customer spending patterns
* Age-group purchasing behavior
* Subscription-based purchasing behavior
* Discount usage patterns
* Revenue contribution by customer segment

These insights can help businesses improve **customer targeting, marketing strategies, and revenue growth**.

---

# 9️⃣ Business Insights

The project converts raw data into meaningful business insights.

### Example insights

* Identify the highest-revenue product categories
* Understand which customer segments contribute most to revenue
* Identify high-spending customers
* Compare purchasing behavior across age groups
* Analyze the impact of discounts
* Understand subscription customer behavior
* Identify sales trends and opportunities

> **Note:** Final insights should be updated based on the actual results obtained from the dataset.

---

# 🔟 Gamma Presentation

A professional presentation is created using **Gamma** to communicate the project to stakeholders or recruiters.

### Presentation Structure

```text
1. Project Introduction
2. Business Problem
3. Dataset Overview
4. Tools & Technologies
5. Python Data Analysis
6. EDA Findings
7. SQL Business Analysis
8. Power BI Dashboard
9. Customer Behavior Insights
10. Business Recommendations
11. Conclusion
```

The presentation focuses on **business storytelling rather than only showing technical work**.

---

# 📊 End-to-End Skills Demonstrated

This project demonstrates practical knowledge of:

### Python

* Pandas
* Data Cleaning
* Data Manipulation
* EDA
* Matplotlib
* Seaborn

### SQL

* SELECT
* WHERE
* GROUP BY
* ORDER BY
* Aggregate Functions
* Subqueries
* CASE statements
* JOINs
* Business Queries

### PostgreSQL

* Database creation
* Table creation
* Data loading
* Query execution
* Data retrieval

### Power BI

* Data connection
* Data transformation
* Data modeling
* DAX
* KPI creation
* Slicers
* Interactive visualizations
* Dashboard design

### Business Analytics

* Customer behavior analysis
* Sales analysis
* Revenue analysis
* Trend analysis
* Business insights
* Data-driven recommendations

### Presentation

* Data storytelling
* Business insights
* Stakeholder communication
* Gamma presentation design

---

# 🎯 Key Outcome

The project demonstrates a complete **Data Analyst workflow**, starting from raw data and ending with an interactive business dashboard and presentation.

```text
DATA
 ↓
PYTHON
 ↓
EDA
 ↓
POSTGRESQL
 ↓
SQL
 ↓
POWER BI
 ↓
DASHBOARD
 ↓
BUSINESS INSIGHTS
 ↓
GAMMA PRESENTATION
```

This project showcases the ability to **collect, clean, analyze, query, visualize, and communicate data-driven insights** using industry-relevant Data Analytics tools.

---

# 👨‍💻 Author

**Praneeth Pani**

**Data Analyst | Python | SQL | Power BI | Excel**

---

## ⭐ Project Highlights

> **Python** → Data Cleaning & EDA
> **PostgreSQL** → Data Storage
> **SQL** → Business Analysis
> **Power BI** → Interactive Dashboard
> **Gamma** → Business Presentation

**From Raw Data → Business Insights 🚀**
