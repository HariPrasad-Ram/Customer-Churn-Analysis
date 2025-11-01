# 📊 Customer Churn Analysis — Power BI | SQL | Python | Excel

### 🚀 Project Overview

This project analyzes **customer churn behavior** for a telecom company using **Python**, **SQL**, and **Power BI**.
It identifies the key factors driving customer churn, highlights high-risk customer segments, and provides actionable insights to improve retention and revenue growth.

---

## 🎯 Objectives

* Identify **why customers churn** and **which segments are most affected**.
* Perform **data cleaning, exploration, and visualization** using SQL, Python & Power BI.
* Develop an **interactive dashboard** for real-time decision-making.
* Support **data-driven strategies** for customer retention.

---

## 🧾 Dataset Overview

**File:** `Customer_Data1.csv`
**Rows:** ~7,000 | **Columns:** 30+

| Column                            | Description                   |
| --------------------------------- | ----------------------------- |
| `Customer_ID`                     | Unique customer identifier    |
| `Gender`, `Age`, `Married`        | Demographic details           |
| `State`                           | Customer location             |
| `Tenure_in_Months`                | Number of months with company |
| `Contract`, `Payment_Method`      | Subscription details          |
| `Monthly_Charge`, `Total_Revenue` | Financial data                |
| `Customer_Status`                 | Active / Churned / Joined     |
| `Churn_Category`, `Churn_Reason`  | Churn classification          |

---

## 🧹 Data Cleaning (SQL & Python)

### 🧩 SQL — Validation & Summary Queries

Files used:

* **`Data1.sql`** — Null value checks for all columns
* **`data.sql`** — Aggregations by Gender, Contract, Status, and State
* **`Churn analysis.sql`** — Database setup (`db_churn1`) and churn overview

Example:

```sql
SELECT Contract, COUNT(Contract) AS TotalCount,
COUNT(Contract) * 100.0 / (SELECT COUNT(*) FROM customer_data) AS Percentage
FROM customer_data
GROUP BY Contract;
```

---

### 🐍 Python — Data Cleaning & Visualization

**Libraries Used:**
`pandas`, `numpy`, `matplotlib`, `seaborn`, `pathlib`, `sklearn`

#### Key Steps:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load Data
df = pd.read_csv("Customer_Data1.csv")

# Basic Checks
print(df.info())
print(df.describe())

# Handle Nulls
df.fillna(method='ffill', inplace=True)

# Gender Distribution
sns.countplot(data=df, x='Gender')
plt.title("Customer Distribution by Gender")
plt.show()

# Churn by Contract Type
sns.barplot(data=df, x='Contract', y='Monthly_Charge', hue='Customer_Status')
plt.title("Churn by Contract Type")
plt.show()
```


## 📊 Power BI Dashboard

**File:** `prod_churn1.pbix`
Built an **interactive dashboard** connecting SQL/Python-cleaned data to Power BI.

### 📊 Key Visuals

* Churn Rate by Gender
* Revenue by Customer Status
* Churn by Contract Type
* State-wise Churn Distribution
* Monthly Charge vs Tenure Analysis
* Churn Category Breakdown

📸 *Preview:* <img width="1174" height="663" alt="Screenshot 2025-11-01 113114" src="https://github.com/user-attachments/assets/2d2b8e25-5015-4b1b-bec6-d9b6ae1f6f53" />


---

## 🔍 Insights & Findings

* **Month-to-Month** contracts have the **highest churn** rate.
* Customers using **Fiber Optic Internet** churn more than DSL users.
* **Electronic Check** payments correlate strongly with churn.
* **High tenure + long-term contracts** = **low churn probability**.
* **California and Texas** have the highest churn percentages.

---

## ⚙️ Tech Stack

| Tool                                     | Purpose                          |
| ---------------------------------------- | -------------------------------- |
| **MySQL**                                | Data extraction & transformation |
| **Python (pandas, matplotlib, seaborn)** | Data cleaning & EDA              |
| **Power BI**                             | Visualization & reporting        |
| **Excel**                                | Initial data audit               |
| **CSV**                                  | Data source                      |

---

## 🗂️ Folder Structure

```
📁 Customer Churn Analysis
├── Customer_Data1.csv          # Dataset
├── Data1.sql                   # Null count checks
├── data.sql                    # Aggregations
├── Churn analysis.sql          # Database setup
├── Python_Notebook.ipynb       # Data cleaning & visualization
├── prod_churn1.pbix            # Power BI dashboard
├── Screenshot 2025-11-01.png   # Dashboard preview
└── README.md                   # Documentation
```

---

## 💡 Business Impact

* Identified **15–20% churn-prone customers** for targeted offers.
* Supported **marketing & customer success teams** in designing retention strategies.
* Helped improve **retention rate** and **monthly recurring revenue (MRR)**.

---

## 🚀 Future Enhancements

* Add **automated ETL pipeline** using Python + SQL.
* Integrate **real-time data refresh** with MySQL.

---

## 👨‍💻 Author

**Hari Prasad Ram**
📍 Data Analyst | Power BI | SQL | Python | Excel
🔗 [LinkedIn](https://www.linkedin.com/in/hariprasad-ram-933152358/)
🖥️ [GitHub](https://github.com/HariPrasad-Ram)
