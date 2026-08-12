# Power BI Project: Get Data from a NoSQL Database (Azure Cosmos DB)

## Project Overview

This project demonstrates how to connect Power BI to a **NoSQL database (Azure Cosmos DB)** and transform JSON data into a tabular format suitable for reporting and analysis.

Unlike relational databases such as SQL Server, NoSQL databases store data in flexible document structures, often using JSON.

This project is based on the Microsoft Learn PL-300 topic:

> Get Data from a NoSQL Database

---

# Learning Objectives

After completing this project, I was able to:

- Understand what a NoSQL database is
- Understand Azure Cosmos DB basics
- Connect Power BI to Azure Cosmos DB
- Import JSON documents
- Expand and normalize nested data
- Transform JSON into a tabular model
- Load Cosmos DB data into Power BI

---

# What is a NoSQL Database?

A NoSQL database is a non-relational database that stores data without using traditional tables and relationships.

Unlike SQL databases, NoSQL databases often store data in:

- JSON Documents
- Key-Value Pairs
- Graph Structures
- Wide-Column Structures

---

# Relational vs NoSQL Databases

| Relational Database | NoSQL Database |
|--------------------|----------------|
| Uses Tables | Uses Documents |
| Fixed Schema | Flexible Schema |
| SQL Language | Various Query Methods |
| Structured Data | Semi-Structured Data |
| Example: SQL Server | Example: Azure Cosmos DB |

---

# Business Scenario

XYZ Traders developed a Shipping & Tracking Application.

The application stores data in:

```text
Azure Cosmos DB
```

instead of SQL Server.

Data is stored as:

```json
{
  "ProductID": 1001,
  "ProductName": "Laptop",
  "Category": "Electronics",
  "Warehouse": "Dubai"
}
```

The goal is to import this data into Power BI and create reports.

---

# What is Azure Cosmos DB?

Azure Cosmos DB is Microsoft's cloud-based NoSQL database service.

### Features

- Globally distributed
- High performance
- Flexible schema
- JSON document storage
- Cloud-native database

---

# JSON Data Example

Data in Cosmos DB is usually stored as JSON documents.

Example:

```json
{
  "ProductID": 1001,
  "ProductName": "Laptop",
  "Category": "Electronics",
  "Price": 2000
}
```

Unlike SQL tables, JSON documents may contain nested structures.

---

# Connecting Power BI to Azure Cosmos DB

## Navigation

```text
Home
 └── Get Data
      └── More
```

---

# Select Data Source

Choose:

```text
Azure
 └── Azure Cosmos DB
```

Then:

```text
Connect
```

---

# Preview Connector

Power BI displays:

```text
Preview Connector
```

Select:

```text
Continue
```

---

# Cosmos DB Connection Details

Power BI requests:

```text
Account Endpoint URL
```

and

```text
Account Key
```

---

# Where to Find Endpoint URL?

In Azure Portal:

```text
Cosmos DB Account
 └── Keys
      └── URI
```

Example:

```text
https://mycosmosdb.documents.azure.com:443/
```

---

# Where to Find Account Key?

In Azure Portal:

```text
Cosmos DB Account
 └── Keys
      └── Primary Key
```

Example:

```text
3Fh8xK2...abcxyz
```

---

# Important Note

For this project, Azure Cosmos DB was not available.

Therefore, the connection process was studied conceptually.

The practical connection requires:

```text
Cosmos DB Endpoint URL
```

and

```text
Primary Key
```

which are generated inside an Azure subscription.

---

# Alternative Connection Options

Instead of selecting:

```text
Endpoint URL
```

users can browse available:

- Databases
- Collections
- Containers

through Navigator.

---

# Navigator Window

After connecting successfully:

```text
Navigator
```

shows available Cosmos DB collections.

Example:

```text
Products
Orders
Customers
Shipments
```

---

# Loading JSON Data

Selecting:

```text
Products
```

typically displays:

```text
Record
Record
Record
Record
```

instead of traditional columns.

---

# Why Does This Happen?

Power BI recognizes each JSON document as:

```text
Record
```

instead of rows and columns.

---

# Open Power Query

Instead of Load:

```text
Edit
```

Select:

```text
Edit
```

to transform the JSON structure.

---

# Expanding JSON Records

Inside Power Query:

Find:

```text
Column1
```

containing:

```text
Record
```

values.

Click:

```text
Expand Icon
```

(two arrows).

---

# Select Fields

Choose fields to extract.

Example:

```text
ProductID
ProductName
Category
Warehouse
Price
```

---

# Remove Prefix

Uncheck:

```text
Use Original Column Name As Prefix
```

---

# Example

Before:

| Column1 |
|---------|
| Record |
| Record |
| Record |

---

After Expansion

| ProductID | ProductName | Category |
|------------|--------------|------------|
| 1001 | Laptop | Electronics |
| 1002 | Mouse | Accessories |
| 1003 | Monitor | Electronics |

---

# Data Transformation

Common cleanup actions:

- Rename Columns
- Remove Columns
- Change Data Types
- Filter Rows
- Expand Nested Records

---

# Load Data

After reviewing the transformed data:

```text
Home
 └── Close & Apply
```

---

# Result

Power BI loads normalized data into:

```text
Rows
Columns
```

format.

The data can now:

- Participate in relationships
- Be used in DAX calculations
- Be visualized in reports

---

# Practical Simulation Project

Since Azure Cosmos DB was not available, the same concept can be practiced using a local JSON file.

---

## Sample JSON File

Create:

```json
[
 {
   "ProductID":1001,
   "ProductName":"Laptop",
   "Category":"Electronics",
   "Price":2000
 },
 {
   "ProductID":1002,
   "ProductName":"Mouse",
   "Category":"Accessories",
   "Price":50
 }
]
```

Save as:

```text
Products.json
```

---

## Import JSON into Power BI

```text
Home
 └── Get Data
      └── JSON
```

Select:

```text
Products.json
```

---

## Expand Records

Click:

```text
Expand
```

Select:

```text
ProductID
ProductName
Category
Price
```

---

## Close & Apply

Power BI converts JSON into a structured table.

This simulates the same transformation process used with Cosmos DB.

---

# PL-300 Exam Focus

## High Priority

✅ Understand NoSQL Databases

✅ Understand Azure Cosmos DB

✅ Understand JSON Data

✅ Connect using Get Data

✅ Expand Records

✅ Transform JSON into Tables

---

## Medium Priority

✅ Endpoint URL

✅ Account Key

✅ Navigator

✅ Expander Button

---

## Low Priority

❌ Memorizing Azure Portal screens

❌ Real Azure administration

❌ Cosmos DB configuration

---

# Exam Questions and Answers

## Q1. What is a NoSQL Database?

### Answer

A NoSQL database is a non-relational database that stores data without traditional tables.

Example:

```text
Azure Cosmos DB
```

---

## Q2. What type of data is commonly stored in Azure Cosmos DB?

### Answer

✅ JSON Documents

---

## Q3. Which Azure service is Microsoft's NoSQL database?

### Answer

✅ Azure Cosmos DB

---

## Q4. Which Power BI connector is used to connect to Cosmos DB?

### Answer

```text
Get Data
 └── Azure Cosmos DB
```

---

## Q5. What information is required to connect to Cosmos DB?

### Answer

- Endpoint URL
- Primary Key

---

## Q6. Where is the Endpoint URL located?

### Answer

```text
Azure Portal
 └── Cosmos DB
      └── Keys
```

---

## Q7. Why does Power BI show "Record" instead of columns?

### Answer

Because JSON documents are imported as Record objects.

---

## Q8. How do you convert Record values into columns?

### Answer

Use the:

```text
Expand
```

button.

---

## Q9. Why is JSON often transformed before loading?

### Answer

Because JSON data is commonly:

- Nested
- Semi-structured
- Difficult to analyze directly

---

## Q10. After expanding JSON data, what should be selected?

### Answer

```text
Close & Apply
```

to load the transformed data model.

---

# PL-300 Revision Sheet

## NoSQL Database

```text
Flexible Schema
JSON Documents
Non-Relational
```

---

## Azure Cosmos DB

```text
Microsoft NoSQL Database
```

---

## Connection Flow

```text
Get Data
 ↓
More
 ↓
Azure Cosmos DB
 ↓
Endpoint URL
 ↓
Primary Key
 ↓
Navigator
 ↓
Edit
 ↓
Expand Records
 ↓
Close & Apply
```

---

## Exam Keyword Memory Trick

### C-J-E-L

| Letter | Meaning |
|----------|----------|
| C | Cosmos DB |
| J | JSON Documents |
| E | Expand Records |
| L | Load Data |

Remember:

```text
Cosmos DB stores JSON.
JSON must be Expanded before Loading.
```
