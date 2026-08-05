# Power BI - Get Data from Relational Data Sources

## What is a Relational Database?

A **relational database** stores data in multiple related tables.

### Examples

| Database | Type |
|-----------|------|
| SQL Server | Relational Database |
| MySQL | Relational Database |
| Oracle | Relational Database |
| PostgreSQL | Relational Database |

### Benefits

| Benefit | Description |
|----------|-------------|
| Real-time access | Connect directly to source data |
| Trend analysis | Monitor business performance |
| Forecasting | Predict future sales |
| Reporting | Build dashboards and reports |

---

# Scenario

The Sales team at XYZ Traders wants to:

- Connect to SQL Server
- Import sales data
- Create Power BI reports

---

# Connecting to SQL Server

## Steps

| Step | Action |
|--------|--------|
| 1 | Open Power BI Desktop |
| 2 | Home → Get Data |
| 3 | Select SQL Server |
| 4 | Enter Server Name |
| 5 | Enter Database Name |
| 6 | Select Connectivity Mode (Import/Direct Query) |
| 7 | Sign In |
| 8 | Connect |

---

# Data Connectivity Modes

## Comparison

| Mode | Description | Recommended |
|---------|------------|-------------|
| Import | Copies data into Power BI model | ✅ Yes |
| DirectQuery | Queries database directly when needed | ⚠️ Advanced |

---

## Import Mode

| Feature | Value |
|----------|--------|
| Data stored in Power BI | Yes |
| Faster reporting | Yes |
| Default option | Yes |
| Recommended | Yes |

### Remember

**Import = Best choice for most situations**

---

## DirectQuery Mode

| Feature | Value |
|----------|--------|
| Data stored in Power BI | No |
| Queries database live | Yes |
| Requires database access | Yes |
| More advanced | Yes |

### Remember

**DirectQuery = Live Connection**

---

# Authentication Methods

After entering server details, Power BI asks for credentials.

## Sign-In Options

| Authentication Type | Description |
|---------------------|-------------|
| Windows | Uses Windows / Azure AD account |
| Database | Uses database-specific login |
| Microsoft Account | Uses Microsoft account credentials |

---

## Windows Authentication

| Feature | Details |
|----------|---------|
| Uses Windows credentials | Yes |
| Uses Azure AD account | Yes |
| Common in organizations | Yes |

---

## Database Authentication

| Feature | Details |
|----------|---------|
| Uses SQL username/password | Yes |
| Separate from Windows login | Yes |
| Provided by DBA | Usually |

---

## Microsoft Account Authentication

| Feature | Details |
|----------|---------|
| Uses Microsoft credentials | Yes |
| Common for Azure services | Yes |

---

# Navigator Window

After a successful connection, Power BI opens the Navigator.

## Functions

| Function | Purpose |
|----------|----------|
| Display tables | Show available database tables |
| Preview data | Verify correct data |
| Select tables | Choose data to import |

---

# Loading Data

After selecting tables, choose one option.

| Option | Purpose |
|----------|---------|
| Load | Import data directly |
| Transform Data | Open Power Query |

---

# Load vs Transform Data

| Feature | Load | Transform Data |
|----------|------|---------------|
| Immediate Import | ✅ | ❌ |
| Data Cleansing | ❌ | ✅ |
| Power Query Opens | ❌ | ✅ |
| Best Practice | Sometimes | ✅ Recommended |

---

# Power Query Transformations

## Common Tasks

| Task | Purpose |
|--------|---------|
| Remove Columns | Delete unnecessary fields |
| Remove Rows | Exclude unwanted records |
| Group Data | Summarize information |
| Fix Errors | Improve quality |
| Change Data Types | Ensure accurate analysis |

---

# Import Data Using SQL Query

Instead of importing full tables, you can write an SQL query.

### Benefits

| Benefit | Description |
|-----------|------------|
| Faster performance | Loads less data |
| Smaller model | Reduced memory usage |
| Better control | Select only needed data |
| Easier filtering | Apply conditions before import |

---

# Writing an SQL Query

## Basic Structure

```sql
SELECT column_names
FROM table_name
```

---

# Example 1: Select Specific Columns

```sql
SELECT
    ID,
    NAME,
    SALESAMOUNT
FROM SALES
```

---

## Query Breakdown

| Clause | Purpose |
|----------|---------|
| SELECT | Choose columns |
| FROM | Specify source table |

---

# SELECT Statement

### Purpose

Specifies which columns to retrieve.

Example:

```sql
SELECT
    ID,
    NAME,
    SALESAMOUNT
```

### Result

Only these columns are imported:

| Imported Columns |
|------------------|
| ID |
| NAME |
| SALESAMOUNT |

---

# FROM Statement

### Purpose

Specifies the table containing the data.

Example:

```sql
FROM SALES
```

### Meaning

Retrieve data from the SALES table.

---

# Avoid Using Wildcard (*)

## Not Recommended

```sql
SELECT *
FROM SALES
```

---

## Why Avoid It?

| Problem | Impact |
|-----------|--------|
| Loads all columns | More data than needed |
| Slower refresh | Reduced performance |
| Larger semantic model | Increased memory usage |
| More cleanup work | Extra transformations |

---

## Recommended Approach

```sql
SELECT
    ID,
    NAME,
    SALESAMOUNT
FROM SALES
```

### Remember

✅ Select only needed columns.

❌ Avoid `SELECT *`.

---

# WHERE Clause

## Purpose

Filters rows before importing.

### Syntax

```sql
SELECT columns
FROM table
WHERE condition
```

---

# Example: Recent Sales Only

```sql
SELECT
    ID,
    NAME,
    SALESAMOUNT
FROM SALES
WHERE OrderDate >= '2026-01-01'
```

---

## Query Breakdown

| Clause | Purpose |
|----------|---------|
| SELECT | Columns to import |
| FROM | Source table |
| WHERE | Filter records |

---

## Benefits of WHERE Clause

| Benefit | Description |
|----------|------------|
| Smaller dataset | Fewer records imported |
| Better performance | Faster refresh |
| Easier reporting | Relevant data only |

---

# Data Source Settings

After loading data, connection settings can be modified.

### Common Reasons

| Reason | Example |
|----------|---------|
| Password Change | Security policy |
| Server Change | New database server |
| Database Change | New environment |
| Permission Change | Updated access requirements |

---

# Open Data Source Settings

## Method 1

```text
Home
 └── Transform Data
      └── Data Source Settings
```

---

## Method 2

```text
Power Query
 └── Data Source Settings
```

---

## Method 3

```text
Query Settings
 └── Source
      └── Edit Settings
```

---

# Available Data Source Actions

| Action | Purpose |
|----------|---------|
| Change Source | Update server/database |
| Edit Permissions | Modify access |
| Clear Permissions | Remove stored credentials |

---

# Applying Changes

After editing settings:

```text
Close and Apply
```

### Purpose

Apply updates to Power BI model.

---

# SQL Capabilities

SQL can do much more than selecting data.

| Capability | Description |
|------------|------------|
| Select Columns | Choose fields |
| Filter Rows | WHERE clause |
| Join Tables | Combine tables |
| Calculations | Perform calculations |
| Logical Conditions | Apply business rules |
| Aggregations | Summarize data |

---

# Why SQL is Useful

## Example Scenario

Sales table contains:

| Year Range |
|------------|
| 2023 |
| 2024 |
| 2025 |
| ... |
| Current Year |

Suppose your report only needs data from 2026 onward.

Instead of importing everything:

✅ Filter using SQL.

```sql
WHERE OrderDate >= '2026-01-01'
```

Result:

- Smaller model
- Faster refresh
- Better performance

---

# Views in SQL

## What is a View?

A **View** is a virtual table created from an SQL query.

### Characteristics

| Feature | Description |
|----------|-------------|
| Contains rows and columns | Yes |
| Stores query logic | Yes |
| Acts like a table | Yes |
| Reusable | Yes |

---

# Why Use Views Instead of Complex SQL in Power BI?

| Benefit | Description |
|----------|------------|
| Cleaner Power BI model | Less complexity |
| Easier maintenance | SQL managed in database |
| Better performance | Optimized by database |
| Supports Query Folding | Yes |

---

# Query Folding

## Definition

Query Folding occurs when Power Query pushes transformations back to the database.

### Benefits

| Benefit | Result |
|----------|--------|
| Less data transferred | Faster |
| Better performance | Faster refresh |
| Uses database engine | More efficient |

---

# Key Terms

| Term | Definition |
|---------|------------|
| Relational Database | Database with related tables |
| SQL Server | Microsoft's relational database |
| Import Mode | Copy data into Power BI |
| DirectQuery | Live connection to database |
| Authentication | User login verification |
| Navigator | Table selection screen |
| SQL | Structured Query Language |
| SELECT | Choose columns |
| FROM | Specify table |
| WHERE | Filter rows |
| View | Saved SQL query acting like a table |
| Query Folding | Processing done by source database |
| Data Source Settings | Connection management area |

---

# Exam Notes

## Connectivity Modes

| Mode | Stores Data in Power BI |
|--------|------------------------|
| Import | ✅ Yes |
| DirectQuery | ❌ No |

---

## SQL Best Practices

✅ Select only required columns

```sql
SELECT ID, NAME, SALESAMOUNT
FROM SALES
```

❌ Avoid

```sql
SELECT *
FROM SALES
```

✅ Use WHERE clause

```sql
WHERE OrderDate >= '2026-01-01'
```

✅ Prefer Views for complex queries

✅ Encourage Query Folding

---

# One-Minute Revision

## Connection Flow

```text
Home
 └── Get Data
      └── SQL Server
           └── Server Name
                └── Database Name
                     └── Authentication
                          └── Navigator
                               ├── Load
                               └── Transform Data
```

---

## SQL Query Structure

```sql
SELECT columns
FROM table
WHERE condition
```

---

## Quick Memorization

### SIDNV

| Letter | Meaning |
|----------|---------|
| S | SQL Server |
| I | Import Mode |
| D | DirectQuery |
| N | Navigator |
| V | Views & Query Folding |

**SIDNV = Complete Relational Database Workflow**
