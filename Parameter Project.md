# Power BI - Dynamic Reports with Parameters (PL-300 Notes)

## Exam Focus

For the **PL-300 Exam**, Microsoft expects you to understand:

✅ What parameters are

✅ How to create parameters

✅ How to edit parameters

✅ How to use parameters in Power Query

✅ Common business scenarios for parameters

You are **NOT expected** to build complex Power Query functions or write advanced M code.

---

# What is a Parameter?

A parameter is a variable that allows Power BI users or developers to change the data being imported or filtered without modifying the query itself.

### Example

```text
EmployeeParameter = Ahmed Ali
```

Result:

```text
Only Ahmed Ali's data loads
```

Change parameter:

```text
EmployeeParameter = Sarah Khan
```

Result:

```text
Only Sarah Khan's data loads
```

---

# Benefits of Parameters

| Benefit | Description |
|----------|------------|
| Dynamic Reports | Change report output without rebuilding |
| Reusability | One report serves multiple purposes |
| Easier Maintenance | Fewer reports to create |
| Environment Switching | Switch between Dev, Test, and Production |
| Flexible Data Sources | Change file paths and database connections |

---

# Parameter Types

Common parameter types:

```text
Text
Decimal Number
Date
Date/Time
True/False
Any
```

---

# Where to Create Parameters

```text
Home
 └── Transform Data
      └── Manage Parameters
           └── New Parameter
```

---

# Project 1 - Employee Parameter

## Parameter Settings

```text
Name: EmployeeParameter
Type: Text
Current Value: Ahmed Ali
```

---

## Apply Filter

Filter:

```text
Employees Table
    └── EmployeeName
```

Condition:

```text
EmployeeName = EmployeeParameter
```

---

## Result

Change:

```text
Ahmed Ali
```

to

```text
Sarah Khan
```

and refresh.

Report shows Sarah's records.

---

# Project 2 - Department Parameter

## Parameter Settings

```text
Name: DepartmentParameter
Type: Text
Current Value: Sales
```

---

## Apply Filter

Filter:

```text
DepartmentName
```

Condition:

```text
DepartmentName = DepartmentParameter
```

---

## Example

Current Parameter:

```text
Sales
```

Returns:

```text
Sales Department Data
```

Change to:

```text
IT
```

Returns:

```text
IT Department Data
```

---

# Project 3 - EmployeeID Parameter

## Parameter Settings

```text
Name: EmployeeIDParameter
Type: Decimal Number
Current Value: 101
```

---

## Apply Filter

Filter:

```text
Sales Table
    └── EmployeeID
```

Condition:

```text
EmployeeID = EmployeeIDParameter
```

---

## Example

```text
EmployeeIDParameter = 101
```

Returns:

```text
Employee 101 Sales
```

Change to:

```text
105
```

Returns:

```text
Employee 105 Sales
```

---

# Editing Existing Parameters

## Navigation

```text
Transform Data
 └── Manage Parameters
      └── Edit Parameters
```

---

## Process

```text
Change Value
    ↓
OK
    ↓
Close & Apply
```

Report refreshes automatically.

---

# Common PL-300 Uses of Parameters

## Change File Path

Example:

```text
C:\Sales\Data.xlsx
```

can be changed to:

```text
D:\Reports\Data.xlsx
```

without editing queries.

---

## Change Database Server

Example:

```text
DEV-SQL01
```

switch to:

```text
PROD-SQL01
```

using a parameter.

---

## Change Database Name

Example:

```text
Sales_Dev
```

switch to:

```text
Sales_Prod
```

through a parameter.

---

## Filter Imported Data

Example:

```text
Department = Sales
```

loads only Sales department data.

---

# Advanced Scenario (Microsoft Learn)

## Multiple Value Parameters

Instead of:

```text
EmployeeIDParameter = 101
```

Microsoft Learn demonstrates:

```text
Excel File
       ↓
List of Employee IDs
       ↓
Power Query Function
       ↓
Invoke Custom Function
       ↓
Load Multiple Employees
```

Example Excel file:

| EmployeeID |
|------------|
| 101 |
| 102 |
| 105 |

Result:

```text
101
102
105
```

employees load simultaneously.

---

# Do You Need This for PL-300?

## Required

✅ Create Parameters

✅ Edit Parameters

✅ Use Parameters in Power Query

✅ Understand Dynamic Reports

✅ Understand File/Server Switching

---

## Nice to Know

✅ Excel as Parameter Source

✅ Invoke Custom Function

✅ Functions in Power Query

---

## Not Usually Tested Deeply

❌ Writing custom M functions

❌ Advanced Power Query function development

❌ Complex Invoke Custom Function workflows

---

# Best Practice for PL-300

Focus on:

### EmployeeParameter

```text
Text Parameter
```

### DepartmentParameter

```text
Text Parameter
```

### EmployeeIDParameter

```text
Numeric Parameter
```

These are sufficient to understand the exam objective.

---

# Exam Questions You Might See

## Why Use Parameters?

✅ Make reports dynamic

✅ Reduce maintenance

✅ Change data sources without editing queries

✅ Support development and production environments

---

## Where Are Parameters Created?

```text
Transform Data
 └── Manage Parameters
      └── New Parameter
```

---

## Can Parameters Be Used in Power Query?

✅ Yes

Examples:

```text
Filter Rows
File Paths
Server Names
Database Names
Database Connections
```

---

# Quick Revision

## Create Parameter

```text
Transform Data
    ↓
Manage Parameters
    ↓
New Parameter
```

---

## Edit Parameter

```text
Transform Data
    ↓
Manage Parameters
    ↓
Edit Parameters
```

---

## Common Uses

```text
Server Name
Database Name
File Path
Department Filter
Employee Filter
```

---

# PL-300 Exam Cheat Sheet

### P-F-S-D

| Letter | Meaning |
|----------|----------|
| P | Parameters |
| F | Filter Data |
| S | Switch Data Sources |
| D | Dynamic Reports |

Remember:

```text
Parameters make reports dynamic
by filtering data or switching data sources.
```

This is the key takeaway for the PL-300 exam.
