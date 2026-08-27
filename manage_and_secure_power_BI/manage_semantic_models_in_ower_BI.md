# 🚀 Power BI Administration & Semantic Model Management
### PL-300 Revision Notes | Complete Study Guide

> A complete guide covering:
>
> - Power BI Gateway
> - Scheduled Refresh
> - Incremental Refresh
> - Semantic Model Promotion & Certification
> - Query Caching
> - Lineage View & Impact Analysis

---

# 📚 Table of Contents

- #-1-power-bi-gateway
- #-2-scheduled-refresh
- [Incrementaltal-refresh
- [Manageage--promote-semantic-models
- [-5-query-caching
- [Lineage View & --impact-analysis
- [PL-300 Exam Cheat Sheet](#-7-pl-vision Mind Map](#-
---

# 🔹 1. Power BI Gateway

## What is a Power BI Gateway?

A Power BI Gateway is a secure bridge that allows Microsoft cloud services to communicate with on-premises data sources.

```text
On-Premises Data Source
          │
          ▼
   Power BI Gateway
          │
          ▼
    Power BI Service
```

### Why is it Needed?

Without a gateway:

- Power BI Service cannot access local databases.
- Scheduled refreshes cannot work for on-premises sources.
- Secure communication cannot be established through corporate firewalls.

---

## Gateway Types

### Standard Mode (Enterprise Gateway)

✅ Recommended for organizations

**Features**

- Multiple users
- Multiple data sources
- Shareable
- Supports:
  - Power BI
  - Power Apps
  - Power Automate
  - Azure Services

```text
Many Users
     │
     ▼
Enterprise Gateway
     │
     ▼
Multiple Data Sources
```

---

### Personal Mode

✅ Designed for one user

**Features**

- Single user only
- Cannot be shared
- Power BI only
- Local PC must remain ON

```text
Local Computer
      │
      ▼
Personal Gateway
      │
      ▼
 Power BI Service
```

---

## Gateway Communication Flow

```text
1. Power BI creates query
             │
             ▼
2. Gateway Cloud Service
             │
             ▼
3. Azure Service Bus
             │
             ▼
4. Gateway receives request
             │
             ▼
5. Connects to Data Source
             │
             ▼
6. Results returned to Power BI
```

---

## Gateway Required?

### ✅ Gateway Required

- SQL Server
- Oracle
- SAP
- Local Files
- On-Premises Databases

### ❌ Gateway Not Required

- SharePoint Online
- OneDrive
- Azure SQL Database
- Dataverse

---

## PL-300 Exam Notes

✅ Gateway = Secure Bridge

✅ Standard Mode = Multiple Users

✅ Personal Mode = Single User

✅ Required for on-premises scheduled refresh

---

# 🔹 2. Scheduled Refresh

## What is Scheduled Refresh?

Scheduled Refresh automatically updates semantic models at predefined times.

```text
Source Data Updated
          │
          ▼
Scheduled Refresh
          │
          ▼
Semantic Model Updated
          │
          ▼
Reports Updated
```

---

## Benefits

✅ No manual refresh

✅ Latest data available

✅ Better user experience

✅ Saves time

---

## Configure Scheduled Refresh

### Step 1

Open Workspace

```text
Workspace
   ▼
Semantic Model
```

### Step 2

Select:

```text
Schedule Refresh
```

### Step 3

Enable:

```text
Scheduled Refresh = ON
```

### Step 4

Choose:

- Frequency
- Time Zone

### Step 5

Add Refresh Times

Example:

```text
08:00 AM
11:00 AM
01:00 PM
04:00 PM
```

### Step 6

Select:

```text
Apply
```

---

## Refresh Limits

### Shared Capacity

```text
Maximum = 8 refreshes/day
```

### Premium Capacity

```text
Maximum = 48 refreshes/day
```

---

## Refresh Now

Immediate refresh.

```text
Refresh Now
```

Does NOT change future scheduled refreshes.

---

## Refresh History

Provides:

- Success/Failure Status
- Refresh Time
- Error Details

Navigation:

```text
Dataset
   ▼
Settings
   ▼
Refresh History
```

---

## PL-300 Exam Notes

✅ Scheduled Refresh = Automatic

✅ Refresh Now = Manual

✅ Shared Capacity = 8/day

✅ Premium = 48/day

✅ Disabled after 2 months inactivity

✅ Disabled after 4 consecutive failures

---

# 🔹 3. Incremental Refresh

## What is Incremental Refresh?

Refresh only recent or changed data instead of all historical data.

---

### Traditional Refresh

```text
5 Years Data
      ▼
Refresh All Data
```

---

### Incremental Refresh

```text
5 Years Data
      ▼
Refresh Last 10 Days Only
```

---

## Benefits

### Faster Refreshes

```text
10 Days Refreshed
Instead of
5 Years Refreshed
```

### More Reliable

- Smaller operations
- Fewer failures

### Lower Resource Consumption

- Less CPU
- Less Memory
- Less Network Usage

---

## Query Folding Requirement

⚠ Incremental Refresh should be used on data sources that support Query Folding.

Examples:

✅ SQL Server

✅ Oracle

✅ Azure SQL

---

## Configuration Steps

### Step 1: Create Parameters

Create:

```text
RangeStart
RangeEnd
```

Type:

```text
Date/Time
```

---

### Step 2: Apply Filter

```text
Date >= RangeStart

Date < RangeEnd
```

⚠ Do NOT use:

```text
Date <= RangeEnd
```

---

### Step 3: Configure Policy

Example:

```text
Store Data = 5 Years

Refresh Data = Last 10 Days
```

---

### Step 4: Publish

```text
Power BI Desktop
        ▼
Publish
        ▼
Power BI Service
```

---

## How It Works

### First Refresh

```text
Load Complete Historical Data
```

### Future Refreshes

```text
Refresh Changed Data Only
```

---

## Remember

```text
RRPP

RangeStart
RangeEnd
Policy
Publish
```

---

## PL-300 Exam Notes

✅ Requires RangeStart

✅ Requires RangeEnd

✅ Parameters must be DateTime

✅ Defined in Desktop

✅ Executed in Service

✅ Query Folding Recommended

---

# 🔹 4. Manage & Promote Semantic Models

## Why Endorse Semantic Models?

Many organizations have:

```text
Sales Dataset
Sales Dataset V2
Sales Dataset Test
Sales Dataset Final
```

Users may not know which dataset is trusted.

---

## Endorsement Types

### Promotion

Meaning:

```text
Recommended for Use
```

Used to encourage adoption.

---

### Certification

Meaning:

```text
Officially Approved Dataset
```

Highest trust level.

Usually requires administrator approval.

---

### Master Data

Microsoft Fabric feature.

Examples:

- Customer Master
- Product Master
- Employee Master

---

## Promote a Semantic Model

```text
Workspace
    ▼
Semantic Model
    ▼
Settings
    ▼
Endorsement
    ▼
Promoted
```

---

## Certify a Semantic Model

```text
Workspace
    ▼
Semantic Model
    ▼
Settings
    ▼
Endorsement
    ▼
Certified
```

---

## Promotion vs Certification

### Promotion

✅ Recommended

✅ Useful

✅ Team-Endorsed

### Certification

✅ Official

✅ Trusted

✅ Single Source of Truth

---

## PL-300 Exam Notes

✅ Promotion = Recommended

✅ Certification = Official Approval

✅ Certified = Highest Trust Level

✅ Certification often requires admin rights

---

# 🔹 5. Query Caching

> Available only in:
>
> - Microsoft Fabric
> - Power BI Premium
> - Power BI Embedded

---

## What is Query Caching?

Stores query results to improve report performance.

---

### Without Query Caching

```text
Open Report
      ▼
Run Queries
      ▼
Calculate Results
      ▼
Display Report
```

---

### With Query Caching

```text
Open Report
      ▼
Use Cached Results
      ▼
Display Report Faster
```

---

## Benefits

✅ Faster reports

✅ Faster dashboards

✅ Reduced semantic model load

✅ Better user experience

✅ User-specific caching

✅ Security respected

✅ Works with RLS

---

## Important Note

Query Caching only caches:

```text
Initial Landing Page
```

Not every report interaction.

---

## Enable Query Caching

```text
Workspace
    ▼
Semantic Model
    ▼
Settings
    ▼
Query Caching
    ▼
ON
```

---

## Warning

Turning off Query Caching:

```text
Clears all cache entries
```

---

## PL-300 Exam Notes

✅ Stores query results

✅ Premium/Fabric feature

✅ Improves report performance

✅ Reduces dataset workload

✅ User-specific cache

---

# 🔹 6. Lineage View & Impact Analysis

## What is Lineage View?

Lineage View visually displays the flow of data across Power BI artifacts.

---

### Example

```text
SQL Server
     ▼
Sales Dataset
     ▼
Sales Report
     ▼
Executive Dashboard
```

---

## Requirements

Minimum Workspace Permission:

```text
Contributor
```

---

## Information Available

### Data Sources

- SQL Server
- Azure SQL
- SharePoint
- Dataverse

### Gateway Information

```text
Data Source
     ▼
Gateway
     ▼
Dataset
```

### Semantic Model Information

- Last Refresh
- Certified Status
- Promoted Status

---

# Impact Analysis

## Purpose

Determine:

```text
What breaks if I change something?
```

---

## Semantic Model Impact Analysis

Example:

```text
Sales Dataset
       ▼
Sales Report
       ▼
Executive Dashboard
```

Changing the dataset may impact:

- Reports
- Dashboards
- Other Workspaces

---

## Data Source Impact Analysis

Example:

```text
SQL Server
      ▼
Sales Dataset
      ▼
Sales Dashboard
```

If SQL Server fails:

```text
Dashboard Impacted
```

---

## Benefits

✅ Understand Dependencies

✅ Safer Change Management

✅ Prevent Outages

✅ Identify Affected Users

---

## PL-300 Exam Notes

✅ Lineage View = Data Flow

✅ Impact Analysis = Dependency Analysis

✅ Useful before modifying datasets

✅ Useful before changing data sources

---

# 🔹 7. PL-300 Exam Cheat Sheet

## Gateway

```text
Gateway = Bridge
```

Enterprise = Multiple Users

Personal = Single User

---

## Scheduled Refresh

```text
Shared = 8/day

Premium = 48/day
```

---

## Incremental Refresh

```text
RangeStart
RangeEnd

Date >= Start
Date < End
```

Store Historical Data

Refresh Recent Data

---

## Endorsement

```text
Promotion = Recommended

Certification = Official
```

---

## Query Caching

```text
Stores Query Results
```

Premium/Fabric Only

---

## Lineage View

```text
Shows Data Flow
```

---

## Impact Analysis

```text
Shows What Breaks
```

---

# 🔹 8. Revision Mind Map

```text
                    POWER BI ADMINISTRATION

                              │
      ┌───────────────────────┼───────────────────────┐
      │                       │                       │
   Gateway               Refreshing             Governance
      │                       │                       │
      │                       │                       │
 Standard              Scheduled Refresh      Promotion
 Personal              Incremental Refresh    Certification

                              │
                         Performance
                              │
                        Query Caching

                              │
                         Monitoring
                              │
                 Lineage & Impact Analysis
```

---

# 📂 Repository Structure

```text
📦 power-bi-pl300-notes
│
├── README.md
│
├── images
│   ├── gateway-architecture.png
│   ├── scheduled-refresh-settings.png
│   ├── refresh-history.png
│   ├── rangestart-rangeend.png
│   ├── incremental-refresh-policy.png
│   ├── promote-dataset.png
│   ├── certify-dataset.png
│   ├── query-caching-settings.png
│   ├── lineage-view.png
│   └── impact-analysis.png
│
└── assets
    └── exam-cheat-sheet.pdf
```

---

# ✅ Quick Revision Formula

```text
Gateway
→ Connect On-Prem Data

Scheduled Refresh
→ Keep Data Updated

Incremental Refresh
→ Refresh Recent Data Only

Promotion
→ Recommended Dataset

Certification
→ Official Dataset

Query Caching
→ Faster Reports

Lineage
→ See Data Flow

Impact Analysis
→ See What Breaks
```

**If you remember these 8 concepts, you'll cover most PL-300 questions related to semantic model management, refresh, governance, and performance optimization.**
