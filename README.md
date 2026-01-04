# Personal Finance Tracker | Working Professional

### Create a personal finance tracker to help working professionals manage their finances using Excel.

## 📌 Table of Contents

<h2><a class="anchor" id="overview"></a>📝 Overview</h2>

This project aims to create a simple yet effective personal finance planner and tracker to help working professionals manage their monthly expenses by answering three primary questions.
- Design a fact table to capture daily or weekly expenses using Excel
- Automate the generation of Budget and Actual report using Pivot Tables
- Generate a simple variance view with surplus amount

[<image>](https://github.com/gaurav-patil-git/10_Finance_Tracker/blob/main/images/2026-01-04_post.jpg)

<h2><a class="anchor" id="tools-technologies"></a>🛠️ Tools & Technologies</h2>

| Tool | Purpose |
| :--- | :--- |
| Excel | Data model and report |
| ChatGPT | Dummy Data |

<h2><a class="anchor" id="tools-technologies"></a>⚙️ Designing Process</h2>

### Step 1: Design the data model

#### Dimension Table
| Category | SubCategory | Type |
| :--- | :--- | :---: |
| **Income** | Salary | Fixed |
| **Income** | Freelance | Variable |
| **Needs** | House Rent / EMI | Fixed |
| **Needs** | Electricity Bill | Variable |
| **Needs** | Gas / Cylinder | Variable |
| **Needs** | Groceries | Variable |
| **Needs** | Mobile / Internet | Fixed |
| **Needs** | Health Insurance | Fixed |
| **Needs** | Medical Expenses | Variable |
| **Needs** | Transport – Public / Pass | Fixed |
| **Savings** | Emergency Fund | Fixed |
| **Savings** | SIP – Mutual Funds | Fixed |
| **Savings** | Stock Investments | Variable |
| **Wants** | OTT Subscriptions | Fixed |
| **Wants** | Dining Out | Variable |
| **Wants** | Shopping | Variable |
| **Wants** | Travel / Vacations | Variable |
| **Wants** | Movies / Events | Variable |
| **Wants** | Hobbies | Variable |
| **Wants** | Courses | Variable |

#### Fact Table
| Field | Description |
| :--- | :--- |
| **Date** | Date of transaction (DD-MM-YYYY) | 
| **Category** | Dropdown of categories (Income, Needs, Wants, Savings) |
| **SubCategory** | Subcategories for each main category (dependent dropdown) |
| **FixedVar** | Expense type (Fixed, Variable) | 
| **Amount** | Value to expense (INR ₹) |

<image>

### Step 2: Generate Report

#### Budget Allocation & Income Statement

```
# DAX to automate budget calculation
=IF(
    HASONEVALUE(fact_table[Category]),
    SWITCH(
        VALUES(fact_table[Category]),
        "Income", [total_income] * 1.0,
        "Needs",   [total_income] * 0.5,
        "Wants",   [total_income] * 0.3,
        "Savings", [total_income]* 0.2,
        BLANK()
    )
)
```

[<image>](https://github.com/gaurav-patil-git/10_Finance_Tracker/blob/main/images/2026-01-04_data%20model.png)

<h2><a class="anchor" id="author-contact"></a>🧑🏽‍🦱 Author & Contact</h2>

**Gaurav Patil** (Data Analyst) 
- 🔗 [LinkedIn](https://www.linkedin.com/in/gaurav-patil-in/)
