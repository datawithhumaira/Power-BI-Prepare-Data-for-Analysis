# Power BI - Create Dynamic Reports with Parameters

## What are Dynamic Reports?

A **Dynamic Report** allows users or developers to change the data displayed without creating multiple reports.

### Benefits

| Benefit | Description |
|----------|-------------|
| Reusable | One report serves multiple users |
| Flexible | Data changes dynamically |
| Less Maintenance | Fewer reports to manage |
| Better User Experience | Users control displayed data |

---

# What is a Parameter?

A **Parameter** is a variable that allows users to change the data returned in a report.

### Example

Instead of creating:

- Sales Report for John
- Sales Report for Sarah
- Sales Report for Ahmed

You create:

✅ One Sales Report

Then change the parameter value:

```text
SalesPerson = John
SalesPerson = Sarah
SalesPerson = Ahmed
```

The report updates automatically.

---

# Dynamic Report Workflow

```text
Create SQL Query
        ↓
Connect to Database
        ↓
Create Parameter
        ↓
Link Parameter to Query
        ↓
Apply Changes
        ↓
Report Updates Dynamically
```

---

# Scenario

Sales team wants:

- One report
- Ability to view individual salesperson data
- Ability to switch between salespeople

Solution:

✅ Use Parameters

---

# Create Dynamic Reports for Individual Values

## Step 1: Connect to SQL Server

```text
Home
 └── Get Data
      └── SQL Server
```

---

## Step 2: Open Advanced Options

In SQL Server connection window:

```text
Server Name
Database Name
Advanced Options ▼
```

---

## Step 3: Paste SQL Query

Paste your SQL query into:

```text
SQL Statement
```

Then:

```text
OK
```

---

## Step 4: Open Power Query

When preview appears:

```text
Edit
```

Power Query Editor opens.

---

# Create Parameter

## Navigation

```text
Power Query Editor
 └── Home
      └── Manage Parameters
           └── New Parameter
```

---

# New Parameter Settings

## Example

| Setting | Value |
|-----------|---------|
| Name | SalesPerson |
| Type | Text |
| Suggested Values | Any Value |

---

## Parameter Configuration

| Property | Value |
|------------|---------|
| Parameter Name | SalesPerson |
| Data Type | Text |
| Suggested Value | Any Value |

---

# Result

Power BI creates a new query called:

```text
SalesPerson
```

Visible in:

```text
Queries Panel (Left Side)
```

---

# Modify SQL Query to Use Parameter

## Open Advanced Editor

```text
Right Click Query1
    └── Advanced Editor
```

---

## Purpose

Replace hardcoded values with parameter values.

---

### Before

```sql
EXEC GetSales 'John'
```

### After

```sql
EXEC GetSales " & SalesPerson
```

*(Conceptually showing parameter usage)*

---

# Save Query

After editing:

```text
Done
```

---

# Test the Parameter

Select:

```text
SalesPerson Parameter
```

Change:

```text
Current Value
```

Example:

```text
Ahmed
```

or

```text
Sarah
```

---

# Native Query Warning

Sometimes Power BI shows:

```text
Native Database Query Warning
```

---

### Fix

```text
Edit Permission
    ↓
Run
```

---

# Apply Changes

```text
Close and Apply
```

---

# Change Parameter Later

## Navigation

```text
Home
 └── Transform Data ▼
      └── Edit Parameters
```

---

## Steps

| Step | Action |
|--------|--------|
| 1 | Open Edit Parameters |
| 2 | Enter new value |
| 3 | Select OK |
| 4 | Apply Changes |
| 5 | Run Query |

---

# Result

Changing:

```text
SalesPerson = Ahmed
```

shows Ahmed's data.

Changing:

```text
SalesPerson = Sarah
```

shows Sarah's data.

---

# Dynamic Reports for Multiple Values

## Problem

A single parameter only handles:

```text
One Value
```

Example:

```text
SalesPerson = Ahmed
```

But what if users want:

```text
Ahmed
Sarah
John
All Together
```

---

# Solution

Create an Excel file containing a list of values.

---

# Excel Table Example

| SalesPersonID |
|--------------|
| 1001 |
| 1002 |
| 1003 |
| 1004 |

---

# Load Excel into Power BI

```text
Home
 └── Get Data
      └── Excel
```

Open:

```text
Navigator
    ↓
Edit
```

---

# Configure New Query

## Step 1: Rename Column

### Before

```text
Column1
```

### After

```text
SalesPersonID
```

---

## Step 2: Change Data Type

| Setting | Value |
|----------|--------|
| Data Type | Text |

---

## Why?

Avoid data conversion errors.

---

# Rename Query

In Query Properties:

### Before

```text
Sheet1
```

### After

```text
SalesPersonID
```

---

# Create Function

## Navigation

```text
Right Click Query1
     └── Create Function
```

---

# Function Purpose

Pass every SalesPersonID value into Query1.

---

## Example

```text
1001 → Query1

1002 → Query1

1003 → Query1

1004 → Query1
```

---

# Name the Function

Example:

```text
GetSalesFromSalesPerson
```

---

# Disable Original Query

## Navigation

```text
Right Click Query1
      └── Enable Load
```

Uncheck it.

---

## Why?

Prevents Query1 from appearing in report fields.

### Benefit

Cleaner experience for users.

---

# Invoke Custom Function

## Navigation

```text
Select SalesPersonID Query
        ↓
Add Column
        ↓
Invoke Custom Function
```

---

# Function Settings

| Setting | Value |
|-----------|--------|
| Function Query | GetSalesFromSalesPerson |

---

# Result

A new column appears.

Example:

| SalesPersonID | GetSalesFromSalesPerson |
|--------------|-------------------------|
| 1001 | Data |
| 1002 | Data |
| 1003 | Data |

---

# Expand Results

Click:

```text
⬍ Two-Arrows Icon
```

in the new column header.

---

# Select Columns to Keep

Choose required fields.

Example:

| Available Columns |
|-------------------|
| Sales Amount |
| Sales Date |
| Customer Name |
| Product Name |

---

# Remove Prefix

Uncheck:

```text
Use Original Column Name as Prefix
```

---

## Why?

Cleaner field names.

### Example

Instead of:

```text
GetSalesFromSalesPerson.SalesAmount
```

You get:

```text
SalesAmount
```

---

# Add More Salespeople

Update the Excel table.

Example:

| SalesPersonID |
|--------------|
| 1001 |
| 1002 |
| 1003 |
| 1004 |
| 1005 |
| 1006 |

---

# Refresh Data

## Navigation

```text
Power Query
 └── Home
      └── Refresh Preview
```

---

# Result

New salesperson records load automatically.

---

# Finish

```text
Close and Apply
```

---

# Final Workflow (Multiple Values)

```text
Excel List of IDs
        ↓
Load Excel
        ↓
Create Function
        ↓
Invoke Function
        ↓
Expand Results
        ↓
Refresh Data
        ↓
Close & Apply
        ↓
Build Report
```

---

# Where to Find Everything in Power BI

## Create Parameter

```text
Transform Data
     ↓
Power Query Editor
     ↓
Home
     ↓
Manage Parameters
     ↓
New Parameter
```

---

## Edit Parameter Later

```text
Power Query Editor
     ↓
Home
     ↓
Manage Parameters
     ↓
Edit Parameters
```

---

## Create Function

```text
Queries Pane
     ↓
Right Click Query
     ↓
Create Function
```

---

## Advanced Editor

```text
Power Query Editor
     ↓
Home
     ↓
Advanced Editor
```

Or

```text
Right Click Query
     ↓
Advanced Editor
```

---

## Invoke Custom Function

```text
Power Query Editor
     ↓
Add Column
     ↓
Invoke Custom Function
```

---

# Key Terms

| Term | Meaning |
|---------|----------|
| Dynamic Report | Report changes based on parameter values |
| Parameter | Variable used to filter data |
| Current Value | Parameter's selected value |
| Function | Reusable query logic |
| Invoke Function | Execute a function on each row |
| Query1 | Original SQL query |
| Advanced Editor | Edit M code manually |
| Native Query | SQL query executed on database |
| Refresh Preview | Reload data preview |

---

# Exam Notes

✅ Dynamic Reports = One report, many users

✅ Parameter = User-controlled value

✅ Create Parameter:

```text
Home
 └── Manage Parameters
      └── New Parameter
```

✅ Multiple Values:

```text
Excel List
   ↓
Function
   ↓
Invoke Function
```

✅ After changes:

```text
Refresh Preview
    ↓
Close and Apply
```

---

# Quick Memorization

### P-F-I-R

| Letter | Meaning |
|----------|---------|
| P | Parameter |
| F | Function |
| I | Invoke Function |
| R | Refresh |

**PFIR = Dynamic Reporting Process**
