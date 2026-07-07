# Sales Analytics Dashboard (Power BI)

An interactive Power BI report analyzing retail sales performance across customers, products, and employees, with full time-intelligence support for trend and growth analysis.

## 📊 Overview

This project models sales transaction data in a classic **star schema** and surfaces key business metrics such as revenue, profit, margins, and month-over-month / year-over-year growth.

## 🗂️ Data Model

**Fact table**
- `Sales` — one row per sales transaction (linked to customer, product, employee, and date)

**Dimension tables**
- `Customers` — customer details, including signup date
- `Products` — product catalog
- `Employees` — salesperson details, including hire date
- `Calendar` — dedicated date dimension for time intelligence

**Relationships** (all one-to-many, single direction):

| From (many) | To (one) |
|---|---|
| Sales[CustomerID] | Customers[CustomerID] |
| Sales[ProductID] | Products[ProductID] |
| Sales[EmployeeID] | Employees[EmployeeID] |
| Sales[Date] | Calendar[Date] |

## 🧮 DAX Measures (23 total)

Measures are organized into display folders:

**Revenue**
- Total Revenue, Total Quantity, Total Transactions
- Customer Count, Average Order Value
- Revenue per Customer, Revenue per Employee

**Profitability**
- Total Profit, Total Cost, Profit Margin, Average Discount %

**Time Intelligence**
- YTD / QTD Revenue and Profit
- Previous Month Revenue & Profit, MoM Growth % (revenue and profit)
- Previous Year Revenue & Profit, YoY Growth % (revenue and profit)

## 🛠️ Built With

- **Power BI Desktop**
- **DAX** for measures and time intelligence
- **Power Query (M)** for data transformation
- Star schema data modeling

## 🚀 Getting Started

1. Clone this repository
2. Open the `.pbip` project (or `.pbix` file) in Power BI Desktop
3. Refresh the data if needed

## 📁 Repository Structure

```
├── SalesAnalytics.pbip          # Power BI project file
├── SalesAnalytics.Report/       # Report definition
├── SalesAnalytics.SemanticModel/# Data model (TMDL)
└── README.md
```

## 📄 License

This project is for portfolio/learning purposes.
