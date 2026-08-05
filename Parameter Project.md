

## Departments Table
DepartmentID,DepartmentName
1,Sales
2,HR
3,Finance
4,IT
5,Marketing

## Employees Table
EmployeeID,EmployeeName,Email,PersonalEmail,Salary,DepartmentID
101,Ahmed Ali,ahmed@company.com,ahmed@gmail.com,12000,1
102,Sarah Khan,sarah@company.com,sarah@gmail.com,11000,1
103,Omar Hassan,omar@company.com,omar@gmail.com,15000,2
104,Lina George,lina@company.com,lina@gmail.com,13000,3
105,Mohammed Noor,mohammed@company.com,mohammed@gmail.com,16000,4
106,Aisha Rahman,aisha@company.com,aisha@gmail.com,12500,5
107,John Smith,john@company.com,john@gmail.com,14000,1
108,Fatima Ali,fatima@company.com,fatima@gmail.com,11800,2
109,David Lee,david@company.com,david@gmail.com,13500,4
110,Mary Thomas,mary@company.com,mary@gmail.com,12200,5

## Products Table
ProductID,ProductName,Category
1001,Laptop,Electronics
1002,Keyboard,Accessories
1003,Monitor,Electronics
1004,Mouse,Accessories
1005,Printer,Office Equipment
1006,Headset,Accessories

##Sales Table
SaleID,EmployeeID,DepartmentID,ProductID,Quantity,SalesAmount,SaleDate
1,101,1,1001,2,4000,2024-01-15
2,101,1,1002,5,500,2024-02-20
3,102,1,1003,1,1200,2024-01-18
4,102,1,1004,10,350,2024-03-01
5,103,2,1005,2,800,2024-02-10
6,104,3,1001,1,2000,2024-02-11
7,105,4,1006,4,600,2024-03-05
8,106,5,1002,8,800,2024-03-15
9,107,1,1003,3,3600,2024-04-01
10,108,2,1004,6,210,2024-04-10
11,109,4,1005,1,400,2024-04-20
12,110,5,1001,2,4000,2024-05-01
13,101,1,1003,2,2400,2024-05-08
14,102,1,1006,5,750,2024-05-12
15,103,2,1002,10,1000,2024-05-20
16,104,3,1004,12,420,2024-06-02
17,105,4,1001,2,4000,2024-06-15
18,106,5,1005,1,400,2024-06-25
19,107,1,1002,15,1500,2024-07-01
20,108,2,1006,3,450,2024-07-10
21,109,4,1003,2,2400,2024-07-15
22,110,5,1004,7,245,2024-07-20
25,101,1,1001,1,2000,2024-08-02
26,102,1,1005,2,800,2024-08-05
27,105,4,1003,4,4800,2024-08-10
28,107,1,1001,3,6000,2024-08-12
29,109,4,1006,6,900,2024-08-15
30,110,5,1002,10,1000,2024-08-18

##Security Mapping Table
DepartmentID,UserEmail
1,sales.manager@company.com
2,hr.manager@company.com
3,finance.manager@company.com
4,it.manager@company.com
5,marketing.manager@company.com

*This table matches your model for Row Level Security practice later.*

## Relationships to Create
Departments[DepartmentID]
    1 ------ * Sales[DepartmentID]

Departments[DepartmentID]
    1 ------ * Employees[DepartmentID]

Products[ProductID]
    1 ------ * Sales[ProductID]

Employees[EmployeeID]
    1 ------ * Sales[EmployeeID]

Departments[DepartmentID]
    1 ------ * SecurityMapping[DepartmentID]

## DAX Measures for the Project
Total Sales = sum('Sales Table'[SalesAmount])
Total Quantity = SUM('Sales Table'[Quantity])
Average Sale = AVERAGE('Sales Table'[SalesAmount])
Total Employee = DISTINCTCOUNT('Employees Table'[EmployeeID])

## Parameter
### Project 1 (Easiest) - Employee Parameter
Open Power Query
Home
└─ Transform Data
Create Parameter
Home
└─ Manage Parameters
  └─ New Parameter
Open Employees Table
└─ Employees Table
Filter EmployeeName Using Parameter
└─ EmployeeName

Text Filters
└─ Equals
Select
└─ EmployeeParameter
Choose 
└─ Parameter
It should look like:
EmployeeName = EmployeeParameter
Verify Applied Steps
Query Settings
 └─ Applied Steps
      ├─ Source
      ├─ Navigation
      └─ Filtered Rows
Close and Apply
Home
 └─ Close & Apply

 

Parameter ✅
Relationships ✅
Star Schema ✅
DAX Measures ✅
Row-Level Security ✅
Sales Dashboard ✅
Filtering & Slicers ✅
