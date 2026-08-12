# Power BI Project: Select a Storage Mode

## Project Overview

This project demonstrates how Power BI uses different **Storage Modes** to retrieve and manage data.

Storage Mode determines:

- Where data is stored
- How data is refreshed
- How queries are executed
- Overall report performance
- Data security compliance

Understanding Storage Modes is important for designing efficient Power BI solutions and is a common topic in the **PL-300 certification exam**.

---

# Learning Objectives

After completing this project, I was able to:

- Understand Storage Modes in Power BI
- Differentiate between Import and DirectQuery
- Understand Composite (Dual) Models
- Select appropriate storage modes based on business requirements
- Identify performance and security considerations

---

# Business Scenario

The Sales Department at XYZ Traders needs Power BI reports.

However:

- Sales data is very large
- Security policies prevent data copies
- Users need the latest information

Because of these requirements:

```text
Import Mode
```

is not the best option.

Instead:

```text
DirectQuery Mode
```

is used to connect directly to the source database.

---

# What is a Storage Mode?

Storage Mode defines how Power BI accesses and stores data.

It controls:

```text
Where data is stored
How data is refreshed
How queries are executed
```

---

# Available Storage Modes

Power BI supports three storage modes:

| Mode | Description |
|--------|------------|
| Import | Data copied into Power BI |
| DirectQuery | Data remains in source system |
| Dual (Composite) | Combination of Import and DirectQuery |

---

# Where to Find Storage Modes

## Navigation

```text
Model View
    ↓
Select Table
    ↓
Properties Pane
    ↓
Storage Mode
```

---

# Import Mode

## What is Import Mode?

Import Mode creates a copy of the data inside Power BI.

```text
Data Source
      ↓
Power BI Model
      ↓
Report
```

Data is loaded into the Power BI dataset.

---

# Import Mode Features

| Feature | Supported |
|----------|------------|
| Local Data Storage | ✅ |
| Fast Performance | ✅ |
| Scheduled Refresh | ✅ |
| Q&A Visual | ✅ |
| Quick Insights | ✅ |
| Offline Analysis | ✅ |

---

# How Import Mode Works

```text
Database
      ↓
Import Data
      ↓
Power BI Dataset
      ↓
Reports
```

---

# Advantages

✅ Fastest report performance

✅ Full Power BI functionality

✅ Supports advanced DAX

✅ Works well for small and medium datasets

✅ Supports Q&A and Quick Insights

---

# Disadvantages

❌ Stores a copy of data

❌ Data can become outdated

❌ Not ideal for huge datasets

❌ May violate security policies

---

# Best Use Cases

- Small datasets
- Medium datasets
- Daily reporting
- Historical reporting
- Data without strict security restrictions

---

# Example

```text
Sales Table
100,000 rows
```

Import into Power BI.

Result:

```text
Fast report performance
```

---

# DirectQuery Mode

## What is DirectQuery?

DirectQuery does not store data inside Power BI.

Instead:

```text
Power BI
      ↓
Sends Query
      ↓
Data Source
      ↓
Returns Results
```

---

# How DirectQuery Works

```text
Report Visual
      ↓
Power BI Query
      ↓
Database
      ↓
Results
      ↓
Report
```

---

# DirectQuery Features

| Feature | Supported |
|----------|------------|
| Data Stored in Source | ✅ |
| Real-Time Data | ✅ |
| Latest Data Available | ✅ |
| Large Datasets | ✅ |
| No Local Data Copy | ✅ |

---

# Advantages

✅ Always shows latest data

✅ No duplicate data storage

✅ Handles large datasets

✅ Meets strict security requirements

✅ Reduced memory usage

---

# Disadvantages

❌ Slower than Import

❌ Depends on database performance

❌ Limited DAX functionality in some cases

❌ Requires active connection

---

# Best Use Cases

- Enterprise databases
- Large semantic models
- Real-time reporting
- Highly secure environments
- Frequently changing data

---

# Example

```text
Sales Database
500 Million Records
```

Instead of importing:

```text
DirectQuery
```

retrieves only required data.

---

# Dual Mode (Composite Model)

## What is Dual Mode?

Dual Mode combines:

```text
Import
+
DirectQuery
```

in a single model.

---

# How Dual Mode Works

Some tables are:

```text
Imported
```

while other tables are:

```text
Queried Directly
```

---

# Example

## Import Tables

```text
Departments
Products
Calendar
```

---

## DirectQuery Tables

```text
Sales Transactions
Orders
Inventory
```

---

# Benefits

✅ Improved performance

✅ Flexible architecture

✅ Efficient storage

✅ Best of both modes

---

# How Power BI Uses Dual Mode

Power BI automatically determines the most efficient retrieval method.

Example:

```text
Dimension Tables
→ Import

Fact Tables
→ DirectQuery
```

---

# Storage Mode Comparison

| Feature | Import | DirectQuery | Dual |
|----------|---------|-------------|---------|
| Data Stored in Power BI | ✅ | ❌ | Partial |
| Fastest Performance | ✅ | ❌ | ✅ |
| Real-Time Data | ❌ | ✅ | ✅ |
| Large Dataset Support | Limited | ✅ | ✅ |
| Security Friendly | ❌ | ✅ | ✅ |
| Supports Q&A | ✅ | Limited | ✅ |

---

# Practical Project

## Scenario

Tailwind Traders needs a Sales Dashboard.

Requirements:

- Live sales data
- Secure data access
- Millions of records

---

# Solution Candidates

## Option 1

```text
Import Mode
```

Result:

```text
Large model
Slow refresh
Security concerns
```

---

## Option 2

```text
DirectQuery
```

Result:

```text
Live data
No copies stored
```

✅ Best Option

---

## Option 3

```text
Dual Mode
```

Result:

```text
Fast dimensions
Live transactions
```

✅ Enterprise Option

---

# Storage Mode Selection Steps

## Open Model View

```text
Model View
```

---

## Select Table

Example:

```text
Sales Table
```

---

## Open Properties

```text
Properties Pane
```

---

## Choose Storage Mode

```text
Import
DirectQuery
Dual
```

---

# Sample Project

## Imported Tables

```text
Departments
Products
Calendar
```

Storage Mode:

```text
Import
```

---

## Fact Table

```text
Sales
```

Storage Mode:

```text
DirectQuery
```

---

## Composite Model

```text
Departments
Products
Calendar

→ Import

Sales

→ DirectQuery
```

---

# Screenshot Placeholders

## Storage Mode Settings

> Add Model View Screenshot Here

---

## Import Mode Example

> Add Import Mode Screenshot Here

---

## DirectQuery Example

> Add DirectQuery Screenshot Here

---

## Composite Model Example

> Add Composite Model Screenshot Here

---

# PL-300 Exam Focus

## High Priority ✅

- Import Mode
- DirectQuery Mode
- Dual Mode
- Storage Mode Selection
- Import vs DirectQuery

---

## Medium Priority ✅

- Performance Impact
- Security Considerations
- Real-Time Reporting

---

## Low Priority ❌

- Internal Query Optimization
- Advanced Composite Modeling

---

# Exam Questions & Answers

## Q1. What is a Storage Mode?

### Answer

A Storage Mode determines how Power BI stores and retrieves data.

---

## Q2. How many Storage Modes are available in Power BI?

### Answer

Three:

```text
Import
DirectQuery
Dual
```

---

## Q3. Which Storage Mode stores data inside Power BI?

### Answer

✅ Import Mode

---

## Q4. Which Storage Mode keeps data in the source system?

### Answer

✅ DirectQuery

---

## Q5. Which Storage Mode provides the fastest report performance?

### Answer

✅ Import Mode

---

## Q6. Which Storage Mode always shows the latest data?

### Answer

✅ DirectQuery

---

## Q7. Which mode is best for very large datasets?

### Answer

✅ DirectQuery

---

## Q8. Which mode combines Import and DirectQuery?

### Answer

✅ Dual Mode

---

## Q9. When should DirectQuery be used?

### Answer

When:

- Data is very large
- Live data is required
- Security prevents importing data

---

## Q10. What is the default Storage Mode in Power BI?

### Answer

✅ Import Mode

---

## Q11. Which mode supports Q&A and Quick Insights best?

### Answer

✅ Import Mode

---

## Q12. Which mode reduces data duplication?

### Answer

✅ DirectQuery

---

## Q13. Where can Storage Mode be changed?

### Answer

```text
Model View
    ↓
Select Table
    ↓
Properties Pane
    ↓
Storage Mode
```

---

# Scenario-Based Questions

## Q14.

A company has 500 million sales records and requires real-time reporting.

Which Storage Mode should be used?

### Answer

✅ DirectQuery

---

## Q15.

A company wants the fastest report performance and data volume is small.

Which Storage Mode should be used?

### Answer

✅ Import

---

## Q16.

A company wants some tables imported and some queried live.

Which mode should be used?

### Answer

✅ Dual (Composite)

---

# PL-300 Cheat Sheet

## Import

```text
Fast
Local Copy
Default Mode
```

---

## DirectQuery

```text
Live Data
No Copy
Large Datasets
```

---

## Dual

```text
Import + DirectQuery
```

---

# Memory Trick

### I-D-D

| Letter | Meaning |
|----------|----------|
| I | Import |
| D | DirectQuery |
| D | Dual |

Remember:

```text
Import = Fast

DirectQuery = Live

Dual = Both
```

---

# Key Takeaway

Choose the storage mode based on:

```text
Performance
Security
Data Size
Refresh Requirements
```

Most organizations use:

```text
Import
```

for performance,

```text
DirectQuery
```

for large or secure datasets,

and

```text
Dual
```

for enterprise-scale solutions.
