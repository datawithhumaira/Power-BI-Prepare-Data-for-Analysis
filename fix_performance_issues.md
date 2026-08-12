# Power BI Project: Fix Performance Issues

## Project Overview

This project demonstrates how to identify and resolve performance issues in Power BI using:

- Query Folding
- Query Diagnostics
- Performance Optimization Best Practices
- DirectQuery Optimization
- Data Source Optimization

Performance tuning is important because slow refreshes, delayed visuals, and inefficient queries can negatively impact the user experience.

This project is based on the Microsoft Learn PL-300 topic:

> Fix Performance Issues

---

# Learning Objectives

After completing this project, I was able to:

- Understand Power BI performance bottlenecks
- Understand Query Folding
- Use View Native Query
- Use Query Diagnostics
- Optimize Power Query transformations
- Apply performance best practices
- Improve DirectQuery performance

---

# Business Scenario

The Sales Department uses Power BI reports connected to SQL Server through:

```text
DirectQuery
```

Users report that:

- Some visuals load slowly
- Certain filters take longer to respond
- Reports refresh slowly

The objective is to identify bottlenecks and improve report performance.

---

# What Causes Performance Issues?

Performance issues can originate from:

## Data Sources

Examples:

```text
SQL Server
Oracle
MySQL
Azure SQL
```

---

## Power Query

Examples:

```text
Complex Transformations
Large Imports
Inefficient Queries
```

---

## Data Model

Examples:

```text
Too Many Relationships
Large Fact Tables
Poor Design
```

---

## Report Layer

Examples:

```text
Too Many Visuals
Complex DAX
Slow Filters
```

---

# Performance Optimization Areas

```text
Data Source
      ↓
Power Query
      ↓
Data Model
      ↓
Report Visuals
```

---

# Query Folding

## What is Query Folding?

Query Folding occurs when Power Query translates transformations into native queries that run on the source system instead of Power BI.

---

## Without Query Folding

```text
Database
      ↓
Power BI Import
      ↓
Transform Data
      ↓
Load
```

Power BI performs all transformations.

---

## With Query Folding

```text
Database
      ↓
Transform Data
      ↓
Return Results
      ↓
Power BI
```

The database performs transformations.

---

# Why Query Folding Matters

Benefits:

✅ Faster Refresh

✅ Reduced Memory Usage

✅ Better Incremental Refresh

✅ Improved DirectQuery Performance

✅ Reduced Power BI Processing

---

# Example

Suppose you perform:

```text
Filter Rows
Rename Columns
Sort Data
```

Power Query converts those transformations into:

```sql
SELECT
ColumnA,
ColumnB
FROM Sales
WHERE SalesAmount > 1000
ORDER BY ColumnA
```

The source database executes the query.

---

# Common Transformations That Fold

These usually support Query Folding:

```text
Filtering Rows
Selecting Columns
Sorting Data
Grouping Data
Joining Tables
Renaming Columns
```

---

# SQL Operations That Fold

Examples:

```sql
SELECT
WHERE
JOIN
GROUP BY
ORDER BY
UNION ALL
```

---

# Transformations That Usually Break Folding

## Adding Index Column

```text
Add Index Column
```

---

## Appending Different Sources

Example:

```text
Excel + SQL Server
```

---

## Merging Different Sources

Example:

```text
SharePoint + SQL Database
```

---

## Certain Data Type Changes

Some transformations prevent folding.

---

# Check Query Folding

## Navigation

```text
Transform Data
      ↓
Power Query Editor
      ↓
Applied Steps
```

---

# View Native Query

Right-click:

```text
Last Applied Step
```

Select:

```text
View Native Query
```

---

# Result

If available:

✅ Query Folding Exists

---

If disabled (greyed out):

❌ Query Folding is Broken

---

# How to Identify Broken Folding

Work backward through:

```text
Applied Steps
```

until:

```text
View Native Query
```

becomes available.

The step after that is often causing the issue.

---

# Query Diagnostics

## What is Query Diagnostics?

A Power Query tool used to analyze:

- Refresh duration
- Transformation duration
- Query execution times
- Bottlenecks

---

# Navigation

```text
Transform Data
      ↓
Tools
      ↓
Query Diagnostics
```

---

# Available Options

| Option | Purpose |
|----------|----------|
| Start Diagnostics | Begin recording |
| Stop Diagnostics | Stop recording |
| Diagnose Step | Measure a specific step |

---

# Start Diagnostics

```text
Tools
 └── Start Diagnostics
```

Perform transformations.

---

# Stop Diagnostics

```text
Tools
 └── Stop Diagnostics
```

Power Query returns diagnostic results.

---

# Diagnose Step

Select:

```text
Applied Step
```

Then:

```text
Diagnose Step
```

---

# Benefit

Shows:

```text
Duration
Resource Consumption
Execution Details
```

---

# Example

Results:

| Step | Duration |
|--------|----------|
| Source | 1 sec |
| Filter Rows | 2 sec |
| Merge Queries | 35 sec |

---

Analysis:

```text
Merge Queries
```

is the bottleneck.

---

# DirectQuery Performance

## Why DirectQuery Can Be Slow

Every visual generates source queries.

Example:

```text
Card
Chart
Matrix
Table
```

may each send separate queries.

---

# Performance Recommendations

### Filter Data Early

Apply filters in the source.

Good:

```sql
WHERE OrderDate >= '2024-01-01'
```

---

### Select Required Columns Only

Good:

```sql
SELECT
OrderID,
SalesAmount
```

Avoid:

```sql
SELECT *
```

---

### Use Indexed Columns

Databases query indexed fields faster.

---

### Avoid Unnecessary Visuals

More visuals:

```text
More Queries
```

---

# Query Folding + DirectQuery

Best combination:

```text
DirectQuery
+
Query Folding
```

Result:

✅ Faster reports

✅ Reduced latency

✅ Better source performance

---

# Other Performance Best Practices

## Process Data at the Source

Whenever possible:

```text
SQL Server
```

should perform calculations.

Instead of:

```text
Power Query
```

performing everything.

---

# Use Native SQL Queries

Good:

```sql
SELECT
ProductID,
SalesAmount
FROM Sales
WHERE SalesAmount > 1000
```

---

Avoid:

```text
Stored Procedures
Complex CTEs
```

when using DirectQuery.

---

# Separate Date and Time Columns

Bad:

```text
2025-01-01 14:35:22
```

Single column.

---

Good:

```text
Date
Time
```

Separate columns.

---

# Why?

Better:

- Compression
- Storage Efficiency
- Performance

---

# Practical Project

## Scenario

Build a Sales Dashboard using SQL Server and DirectQuery.

---

# Step 1

Connect:

```text
SQL Server
```

using:

```text
DirectQuery
```

---

# Step 2

Open:

```text
Power Query Editor
```

---

# Step 3

Apply Transformations:

```text
Filter Rows
Select Columns
Rename Columns
```

---

# Step 4

Verify Query Folding

```text
Applied Step
      ↓
Right Click
      ↓
View Native Query
```

---

# Step 5

Use Query Diagnostics

```text
Tools
      ↓
Start Diagnostics
```

Apply transformations.

```text
Stop Diagnostics
```

---

# Step 6

Review Diagnostic Results.

Identify:

```text
Slowest Step
```

---

# Step 7

Optimize Query.

Examples:

```text
Remove Unnecessary Columns
Filter Earlier
Improve SQL Query
```

---

# Screenshot Placeholders

## Query Folding

> Add View Native Query Screenshot Here

---

## Query Diagnostics

> Add Query Diagnostics Screenshot Here

---

## DirectQuery Configuration

> Add DirectQuery Screenshot Here

---

## Performance Analyzer Results

> Add Performance Analysis Screenshot Here

---

# PL-300 Exam Focus

## High Priority ✅

- Query Folding
- Query Diagnostics
- DirectQuery Performance
- View Native Query
- Source-Level Processing

---

## Medium Priority ✅

- Native SQL Queries
- Refresh Optimization
- Data Compression

---

## Low Priority ❌

- SQL Execution Plans
- Database Hardware Tuning
- DBA Administration Tasks

---

# Exam Questions & Answers - Fix Performance Issues (PL-300)

---

## Q1. What is Query Folding?

### Answer

Query Folding is the process where Power Query translates transformations into a native source query so that processing occurs in the source system rather than Power BI.

---

## Q2. Why is Query Folding Important?

### Answer

Query Folding improves performance because:

- Transformations run on the source system
- Less data is transferred to Power BI
- Refreshes complete faster
- DirectQuery performs better
- Power BI consumes fewer resources

---

## Q3. What is the main goal of Query Folding?

### Answer

To push transformations back to the original data source whenever possible.

---

## Q4. How can you verify if Query Folding is occurring?

### Answer

Use:

```text
Right-click Applied Step
    ↓
View Native Query
```

If available, Query Folding is occurring.

---

## Q5. What does "View Native Query" show?

### Answer

It shows the actual native query that Power Query sends to the source system.

Example:

```sql
SELECT ProductID,
       ProductName
FROM Products
WHERE Category = 'Electronics'
```

---

## Q6. What does it mean if "View Native Query" is disabled?

### Answer

Query Folding has been broken at that step.

---

## Q7. If Query Folding breaks, what should you do?

### Answer

Work backward through Applied Steps until:

```text
View Native Query
```

becomes available.

This helps identify the transformation causing the issue.

---

## Q8. Which storage modes rely heavily on Query Folding?

### Answer

✅ DirectQuery

✅ Dual (Composite)

---

## Q9. Why is Query Folding especially important for DirectQuery?

### Answer

Because every report interaction sends queries to the source database.

Efficient folding helps reduce execution time.

---

## Q10. What is Query Diagnostics?

### Answer

Query Diagnostics is a Power Query tool used to measure and analyze query performance.

---

## Q11. Where can Query Diagnostics be found?

### Answer

```text
Power Query Editor
    ↓
Tools
    ↓
Query Diagnostics
```

---

## Q12. What are the available Query Diagnostics options?

### Answer

```text
Start Diagnostics
Stop Diagnostics
Diagnose Step
```

---

## Q13. What does Start Diagnostics do?

### Answer

It begins tracking Power Query operations and performance metrics.

---

## Q14. What does Stop Diagnostics do?

### Answer

It stops tracking and generates diagnostic reports.

---

## Q15. What does Diagnose Step do?

### Answer

Measures how long a specific transformation step takes to execute.

---

## Q16. Why would you use Diagnose Step?

### Answer

To identify slow transformation steps and bottlenecks.

---

## Q17. Which types of issues can Query Diagnostics identify?

### Answer

- Slow refreshes
- Long-running transformations
- Expensive merges
- Resource-intensive queries
- Data source bottlenecks

---

# Query Folding Transformation Questions

## Q18. Which transformations usually support Query Folding?

### Answer

Examples include:

- Filter Rows
- Remove Columns
- Rename Columns
- Select Columns
- Sort Rows
- Join Tables
- Group Rows

---

## Q19. Which SQL clauses commonly support Query Folding?

### Answer

```sql
SELECT
WHERE
ORDER BY
GROUP BY
JOIN
UNION ALL
```

---

## Q20. Which transformations commonly break Query Folding?

### Answer

Examples include:

- Add Index Column
- Append Different Data Sources
- Merge Different Data Sources
- Certain Custom Transformations

---

## Q21. Does adding an Index Column usually support Query Folding?

### Answer

❌ No

It commonly breaks Query Folding.

---

## Q22. Can merging SQL Server and Excel tables break Query Folding?

### Answer

✅ Yes

Different source types often prevent native query generation.

---

## Q23. Can appending data from multiple source systems break Query Folding?

### Answer

✅ Yes

Query Folding often cannot be maintained across different data sources.

---

# DirectQuery Questions

## Q24. Why can DirectQuery reports become slow?

### Answer

Because every visual sends queries to the source database.

---

## Q25. How can DirectQuery performance be improved?

### Answer

- Maintain Query Folding
- Reduce columns
- Filter data early
- Optimize source database
- Reduce visual complexity

---

## Q26. Why should you avoid SELECT *?

### Answer

Because it retrieves unnecessary columns and increases processing time.

---

## Q27. Which query is better?

### Answer

✅ Better

```sql
SELECT ProductID,
       SalesAmount
FROM Sales
```

❌ Avoid

```sql
SELECT *
FROM Sales
```

---

## Q28. Why should filtering happen in the source system?

### Answer

The source database is optimized to process large volumes of data more efficiently than Power BI.

---

## Q29. What is a best practice when using DirectQuery?

### Answer

Process as much data as possible at the source.

---

## Q30. Should expensive calculations be performed in Power Query if they can be done in SQL?

### Answer

❌ No

Prefer source-side processing whenever possible.

---

# Data Model Optimization Questions

## Q31. Why separate Date and Time columns?

### Answer

Because separate columns improve:

- Compression
- Storage efficiency
- Query performance

---

## Q32. Which is preferred?

### Option A

```text
OrderDateTime
```

### Option B

```text
OrderDate
OrderTime
```

### Answer

✅ Option B

---

## Q33. Why does compression matter?

### Answer

Better compression reduces model size and improves performance.

---
