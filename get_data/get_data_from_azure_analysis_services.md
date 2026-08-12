# Power BI Project: Get Data from Azure Analysis Services

## Project Overview

This project demonstrates how to connect Power BI Desktop to **Azure Analysis Services (AAS)** and use enterprise-grade semantic models for reporting and analytics.

Azure Analysis Services provides:

- Centralized business logic
- Pre-built calculations
- Enterprise semantic models
- Advanced security
- Cloud-based tabular models

Instead of rebuilding DAX calculations in Power BI, reports can directly connect to models already created in Azure Analysis Services.

This project is based on the Microsoft Learn PL-300 topic:

> Get Data from Azure Analysis Services

---

# Learning Objectives

After completing this project, I was able to:

- Understand Azure Analysis Services
- Connect Power BI to Azure Analysis Services
- Understand Import vs Connect Live
- Reuse existing semantic models
- Understand MDX and DAX querying concepts
- Build reports using centralized business models

---

# What is Azure Analysis Services?

Azure Analysis Services (AAS) is a cloud-based Platform as a Service (PaaS) that hosts enterprise semantic models.

It allows organizations to:

- Combine multiple data sources
- Define business calculations
- Create reusable semantic models
- Apply centralized security
- Share business logic across reports

---

# Business Scenario

XYZ Traders stores:

```text
Financial Forecasts
Budget Projections
Revenue Estimates
```

inside Azure Analysis Services.

Actual sales data exists in another source.

The goal is to:

```text
Compare

Forecast Sales

vs

Actual Sales
```

using Power BI.

---

# Why Use Azure Analysis Services?

Without AAS:

```text
SQL Server
Excel
SharePoint
```

must all be transformed in Power BI.

---

With AAS:

```text
Azure Analysis Services
      ↓
Power BI
```

Most modeling work is already done.

---

# Key Features

## Enterprise Semantic Models

Data is already:

- Cleaned
- Modeled
- Related

before reaching Power BI.

---

## Pre-Built Calculations

Unlike SQL tables:

Azure Analysis Services models already contain:

```text
Measures
KPIs
Business Calculations
```

Examples:

```DAX
Total Sales

Profit Margin

Year-to-Date Sales
```

---

## Security

Data security can be managed centrally.

This means:

```text
One Model
Multiple Reports
Central Security
```

---

# Azure Analysis Services vs SQL Server

| Feature | SQL Server | Azure Analysis Services |
|-----------|------------|------------------------|
| Raw Data Storage | ✅ | ❌ |
| Semantic Models | ❌ | ✅ |
| Relationships Predefined | ❌ | ✅ |
| Measures Prebuilt | ❌ | ✅ |
| DAX Calculations | Usually in Power BI | Already Available |
| Centralized Business Logic | ❌ | ✅ |

---

# Connection Process

## Navigation

```text
Home
 └── Get Data
      └── Analysis Services
```

---

# Connection Window

Power BI requests:

```text
Server Address
```

and optionally:

```text
Database Name
```

---

# Example Server

```text
asazure://uaenorth.asazure.windows.net/SalesModel
```

*(Example only)*

---

# Storage Options

Power BI offers:

```text
Import
```

or

```text
Connect Live
```

---

# Option 1: Import

## Description

Data is copied into Power BI.

```text
Azure Analysis Services
          ↓
Import
          ↓
Power BI Dataset
```

---

## Advantages

✅ Faster report performance

✅ Offline reporting

✅ Supports full Power BI functionality

---

## Disadvantages

❌ Duplicate data

❌ Requires refreshes

❌ Existing calculations may be duplicated

---

# Option 2: Connect Live

## Description

Power BI stays connected directly to Azure Analysis Services.

```text
Power BI
      ↓
Live Connection
      ↓
Azure Analysis Services
```

---

## Advantages

✅ One source of truth

✅ No duplicate data

✅ Latest calculations

✅ Immediate updates

✅ Centralized model management

---

## Disadvantages

❌ Dependent on AAS performance

❌ Less flexibility compared to imported datasets

---

# Why Connect Live is Recommended

Azure Analysis Services already stores:

- Relationships
- Measures
- KPIs
- Business Rules

Therefore:

```text
Connect Live
```

allows Power BI to reuse everything.

---

# Live Connection Benefits

If Azure Analysis Services refreshes:

```text
8:00 AM
```

Power BI immediately displays new values.

No Power BI dataset refresh is required.

---

# Selecting Tables

After authentication:

```text
Navigator
```

opens.

Available models are displayed.

Example:

```text
Finance Model
Sales Model
Inventory Model
```

---

Select:

```text
Sales Model
```

or

```text
Finance Model
```

depending on reporting needs.

---

# Querying Azure Analysis Services

Unlike SQL Server:

```sql
SELECT *
FROM Sales
```

Azure Analysis Services supports:

## DAX

```DAX
SUM(Sales[SalesAmount])
```

---

## MDX

```text
MDX
(Multi-Dimensional Expressions)
```

---

# DAX vs MDX

| Feature | DAX | MDX |
|-----------|------|------|
| Tabular Models | ✅ | Limited |
| Power BI | ✅ | ❌ |
| Analysis Services | ✅ | ✅ |
| Most Common Today | ✅ | ❌ |

---

# Recommended Architecture

Microsoft often recommends:

```text
SQL Server
Excel
SharePoint
        ↓
Azure Analysis Services
        ↓
Power BI Live Connection
```

Benefits:

- Single semantic model
- One location for business logic
- Reduced maintenance

---

# Practical Project

## Scenario

Finance Team maintains forecasts in Azure Analysis Services.

Sales Team maintains actual sales in SQL Server.

Goal:

```text
Forecast vs Actual Dashboard
```

---

# Connection Steps

## Step 1

```text
Home
 └── Get Data
      └── Analysis Services
```

---

## Step 2

Enter:

```text
Server Name
```

---

## Step 3

Choose:

```text
Connect Live
```

---

## Step 4

Authenticate.

---

## Step 5

Select:

```text
Finance Forecast Model
```

---

## Step 6

Load model.

---

## Step 7

Build visuals.

---

# Example Visuals

## KPI Card

```text
Forecast Sales
```

---

## KPI Card

```text
Actual Sales
```

---

## KPI Card

```text
Forecast Accuracy %
```

---

## Line Chart

```text
Forecast Trend
vs
Actual Trend
```

---

## Matrix

```text
Product
Forecast
Actual
Variance
```

---

# Example DAX

## Variance

```DAX
Variance =
[Actual Sales] - [Forecast Sales]
```

---

## Accuracy %

```DAX
Forecast Accuracy % =
DIVIDE(
    [Actual Sales],
    [Forecast Sales],
    0
)
```

---

# Screenshot Placeholders

## Azure Analysis Services Connection

> Add Connection Screenshot Here

---

## Navigator Window

> Add Navigator Screenshot Here

---

## Live Connection Settings

> Add Live Connection Screenshot Here

---

## Forecast vs Actual Dashboard

> Add Dashboard Screenshot Here

---

# PL-300 Exam Focus

## High Priority ✅

- Understand Azure Analysis Services
- Connect to Analysis Services
- Import vs Connect Live
- Benefits of Live Connections
- Pre-built Semantic Models

---

## Medium Priority ✅

- DAX vs MDX
- Enterprise Modeling
- Refresh Benefits

---

## Low Priority ❌

- Azure Administration
- Deploying AAS Models
- MDX Syntax

---

# Exam Questions & Answers

## Q1. What is Azure Analysis Services?

### Answer

A cloud-based service that provides enterprise semantic models and business calculations.

---

## Q2. What type of models does Azure Analysis Services provide?

### Answer

✅ Tabular Semantic Models

---

## Q3. Which Power BI connector is used?

### Answer

```text
Get Data
 └── Analysis Services
```

---

## Q4. Which two connection modes are available?

### Answer

```text
Import
Connect Live
```

---

## Q5. Which mode is commonly recommended?

### Answer

✅ Connect Live

Reason:

Business logic and calculations remain in Azure Analysis Services.

---

## Q6. What is the biggest advantage of Connect Live?

### Answer

Power BI uses:

- Existing Measures
- Existing KPIs
- Existing Relationships

without importing them.

---

## Q7. Does Connect Live require Power BI dataset refreshes?

### Answer

❌ No

When Azure Analysis Services refreshes, Power BI reflects updated data automatically.

---

## Q8. Which language is most commonly used with tabular models?

### Answer

✅ DAX

---

## Q9. Which language is traditionally used with multidimensional models?

### Answer

✅ MDX

---

## Q10. What already exists in Azure Analysis Services models?

### Answer

- Measures
- KPIs
- Calculations
- Relationships

---

## Q11. Why use Azure Analysis Services?

### Answer

To centralize business logic and semantic modeling.

---

## Q12. Which architecture is recommended?

### Answer

```text
Data Sources
      ↓
Azure Analysis Services
      ↓
Power BI Live Connection
```

---

# Scenario-Based Questions

## Q13.

A company has already created hundreds of DAX measures in Azure Analysis Services.

Should the measures be recreated in Power BI?

### Answer

❌ No

Use:

```text
Connect Live
```

and reuse existing measures.

---

## Q14.

A company requires a single source of truth for KPIs.

What should be used?

### Answer

✅ Azure Analysis Services

---

## Q15.

A company wants immediate report updates whenever the semantic model refreshes.

Which option should be selected?

### Answer

✅ Connect Live

---

# One-Minute Revision

## Connection Flow

```text
Get Data
      ↓
Analysis Services
      ↓
Server Name
      ↓
Connect Live
      ↓
Authenticate
      ↓
Select Model
      ↓
Build Report
```

---

# PL-300 Cheat Sheet

## Azure Analysis Services

```text
Enterprise Semantic Model
```

---

## Main Benefits

```text
Prebuilt DAX
Prebuilt KPIs
Security
Centralized Logic
```

---

## Connection Options

```text
Import
Connect Live
```

---

## Recommended Option

```text
Connect Live
```

---

## DAX

```text
Tabular Models
```

---

## MDX

```text
Multidimensional Models
```

---

# Memory Trick

### A-L-D-K

| Letter | Meaning |
|----------|----------|
| A | Azure Analysis Services |
| L | Live Connection |
| D | DAX |
| K | KPIs |

Remember:

```text
Azure Analysis Services
+
Live Connection
+
DAX
+
KPIs
=
Enterprise Reporting
```

---

# Key Takeaway

Azure Analysis Services allows organizations to build and maintain a centralized semantic model.

Power BI can connect using:

```text
Connect Live
```

to reuse existing:

- Measures
- Calculations
- KPIs
- Security Rules

without recreating them in Power BI.
