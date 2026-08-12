# PL-300 Exam Prep: Parameters & Dynamic Reports

## Q1. What is a Parameter in Power BI?

### Answer

A Parameter is a variable that allows a developer or user to change a query without manually modifying its code.

### Example

```text
EmployeeParameter = Ahmed Ali
```

Result:

```text
Only Ahmed Ali's data loads.
```

---

## Q2. Why are Parameters Used?

### Answer

Parameters are used to:

- Create dynamic reports
- Filter imported data
- Change data sources
- Reduce report maintenance
- Switch between environments (Dev/Test/Prod)

---

## Q3. Where are Parameters Created?

### Answer

```text
Home
 └── Transform Data
      └── Manage Parameters
           └── New Parameter
```

---

## Q4. What Types of Parameters Can Be Created?

### Answer

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

## Q5. What is the Difference Between a Parameter and a Filter?

### Answer

### Filter

Applied after data is loaded into Power BI.

### Parameter

Applied before or during data loading in Power Query.

### Key Difference

Parameters can reduce the amount of data imported.

---

## Q6. Which Power BI Feature Allows You to Create Parameters?

### Answer

```text
Power Query
 └── Manage Parameters
```

---

## Q7. Can Parameters Be Edited After Creation?

### Answer

Yes.

### Navigation

```text
Transform Data
 └── Manage Parameters
      └── Edit Parameters
```

---

## Q8. What Happens When a Parameter Value Changes?

### Answer

Power BI refreshes the query and retrieves data based on the new parameter value.

### Example

Before:

```text
DepartmentParameter = Sales
```

After:

```text
DepartmentParameter = IT
```

Result:

```text
IT department data is loaded.
```

---

# Scenario-Based Questions

## Q9. Your company has Development and Production SQL Servers.

Which Power BI feature lets you switch between servers without editing queries?

### Answer

✅ Parameter

### Example

```text
DEV-SQL01
```

switches to

```text
PROD-SQL01
```

through a parameter.

---

## Q10. Your Excel file location changes regularly.

How can you avoid changing the query each time?

### Answer

✅ Use a File Path Parameter

Example:

```text
C:\Data\Sales.xlsx
```

can become

```text
D:\Reports\Sales.xlsx
```

without modifying Power Query steps.

---

## Q11. What Parameter Type Should Be Used for Employee Name?

### Answer

✅ Text

Example:

```text
Ahmed Ali
Sarah Khan
John Smith
```

---

## Q12. What Parameter Type Should Be Used for Employee ID?

### Answer

✅ Decimal Number (or Whole Number if available)

Example:

```text
101
102
105
```

---

## Q13. Which Parameter Type Should Be Used for Department Name?

### Answer

✅ Text

Example:

```text
Sales
Finance
IT
```

---

# Dynamic Report Questions

## Q14. What is a Dynamic Report?

### Answer

A Dynamic Report changes its data based on user-selected values or parameter values.

### Benefits

- Reusable reports
- Less maintenance
- Better user experience

---

## Q15. How Do Parameters Help Dynamic Reports?

### Answer

Parameters allow reports to display different results without creating multiple report versions.

### Example

Instead of creating:

```text
Sales Report - Ahmed
Sales Report - Sarah
Sales Report - John
```

Create one report:

```text
EmployeeParameter
```

and change the parameter value.

---

## Q16. Which is More Efficient?

### Option A

```text
10 Separate Reports
```

### Option B

```text
1 Report + Parameter
```

### Answer

✅ Option B

Reason:

- Easier maintenance
- Less duplication
- More scalable

---

# Power Query Questions

## Q17. Can Parameters Be Used in Power Query?

### Answer

✅ Yes

Common uses:

```text
Filter Rows
File Paths
Server Names
Database Names
```

---

## Q18. Can Parameters Be Used to Filter Imported Rows?

### Answer

✅ Yes

Example:

```text
EmployeeID = EmployeeIDParameter
```

Only matching rows are imported.

---

## Q19. Which Loads Less Data?

### Option A

Import all rows then filter.

### Option B

Use a parameter in Power Query.

### Answer

✅ Option B

Reason:

Data is filtered before loading.

---

# Advanced Scenario Questions

## Q20. What is the Purpose of an Excel Control Table?

### Answer

It stores multiple values that Power BI can use dynamically.

Example:

| EmployeeID |
|------------|
| 101 |
| 102 |
| 105 |

---

## Q21. What Feature Executes a Function for Every Row in a Table?

### Answer

✅ Invoke Custom Function

---

## Q22. What is a Power Query Function?

### Answer

A reusable query that accepts input values and returns results.

---

## Q23. Is Create Function + Invoke Custom Function a High-Priority PL-300 Topic?

### Answer

❌ No

It is an advanced Power Query topic.

You should understand the concept but focus more on standard parameters.

---

# True/False Questions

## Q24.

Parameters can be used to switch between databases.

### Answer

✅ True

---

## Q25.

Parameters are created in the Report View.

### Answer

❌ False

They are created in Power Query.

---

## Q26.

Parameters help create dynamic reports.

### Answer

✅ True

---

## Q27.

A parameter can only be text.

### Answer

❌ False

It can be:

- Text
- Number
- Date
- Date/Time
- True/False

---

## Q28.

Parameters can reduce the amount of imported data.

### Answer

✅ True

---

## Q29.

Changing a parameter value requires rebuilding the report.

### Answer

❌ False

Simply edit the parameter and refresh.

---

# Most Important PL-300 Exam Question

## Q30.

You need users to switch between Development and Production environments without modifying queries.

What should you use?

### Answer

✅ Parameter

Reason:

Parameters can dynamically change:

```text
Server Name
Database Name
File Path
```

without editing query logic.

---

# Final Exam Cheat Sheet

## Parameters

Purpose:

```text
Make reports dynamic
```

Used For:

```text
Filtering Data
File Paths
Server Names
Database Names
Environment Switching
```

Create Parameter:

```text
Transform Data
 └── Manage Parameters
      └── New Parameter
```

Edit Parameter:

```text
Transform Data
 └── Manage Parameters
      └── Edit Parameters
```

Remember:

```text
Parameters = Dynamic Reports + Flexible Data Sources
```
