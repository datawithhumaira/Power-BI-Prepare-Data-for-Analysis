# 📊 Power BI Service - Complete Study Notes

> Comprehensive notes for learning, revision, interviews, and PL-300 certification preparation.

---

# 📚 Table of Contents

- #-power-bi-service-overview
- #-power-bi-architecture
- #-workspaces
- #-workspace-types
- #-workspace-roles
- #-reports
- #-semantic-models
- #-dashboards
- #-apps
- #-publish-to-power-bi-service
- [Uploadd-pbix-files
- #-workspace-folders
- #-exam-revision-notes
- [Memory Trickss

---

# 🌐 Power BI Service Overview

## What is Power BI Service?

Power BI Service is the cloud-based (SaaS) platform of Microsoft Power BI that allows users to:

- Publish reports
- Share reports
- Create dashboards
- Collaborate with teams
- Manage workspaces
- Distribute apps
- Access reports through a web browser

**URL:** https://app.powerbi.com

---

## Power BI Workflow

```text
Data Sources
      ↓
Power Query
      ↓
Data Model
      ↓
Power BI Desktop
      ↓
Publish
      ↓
Power BI Service
      ↓
Share & Collaborate
```

---

# 🏗️ Power BI Architecture

```text
Workspace
    │
    ├── Semantic Model
    │
    ├── Report
    │
    ├── Dashboard
    │
    └── App
```

---

# 🏢 Workspaces

## What is a Workspace?

A Workspace is a collaborative environment where Power BI content is stored, managed, and shared.

A workspace can contain:

- Reports
- Semantic Models
- Dashboards
- Dataflows
- Apps

### Example

```text
Finance Workspace
│
├── Budget Report
├── Revenue Dashboard
├── Finance Dataset
└── Finance App
```

---

# 👥 Workspace Types

There are two main types of workspaces.

## 1. My Workspace

Personal workspace for individual users.

### Features

✅ Private

✅ Personal reports

✅ Testing area

✅ Not intended for collaboration

---

## 2. Shared Workspace

Collaboration workspace for teams.

### Features

✅ Multiple users

✅ Shared reports

✅ Shared datasets

✅ App publishing

✅ Team collaboration

### Example

```text
Sales Workspace
├── Sales Report
├── KPI Dashboard
└── Sales Dataset
```

---

# 🎫 Workspace Capacity Types

## Power BI Pro

Suitable for small and medium-sized teams.

### Features

✅ Collaboration

✅ Sharing

✅ Workspace access

### Requirements

All workspace users must have:

- Power BI Pro License
OR
- Premium Per User License

### Limitations

❌ No advanced AI features

❌ Smaller model sizes

---

## Premium Per User (PPU)

Includes all Pro capabilities plus advanced Premium features.

### Features

✅ AI features

✅ Large semantic models

✅ 48 refreshes per day

✅ Advanced analytics

### Limitation

Only PPU users can access PPU workspaces.

---

## Fabric Capacity

Enterprise-grade capacity with dedicated resources.

### Features

✅ Dedicated cloud resources

✅ Real-time analytics

✅ AI capabilities

✅ Data warehouses

✅ Data pipelines

✅ Large-scale semantic models

---

# 🔐 Workspace Roles

Roles control what users can do inside a workspace.

---

## Viewer

### Permissions

✅ View reports

✅ View dashboards

✅ Use filters

✅ Interact with visuals

### Restrictions

❌ Cannot edit content

❌ Cannot create reports

---

## Contributor

### Permissions

✅ Create content

✅ Edit content

✅ Delete content

### Restrictions

❌ Cannot publish apps

❌ Cannot manage workspace settings

---

## Member

### Permissions

✅ Publish apps

✅ Share content

✅ Manage reports

✅ Modify dataset settings

### Restrictions

❌ Cannot delete workspace

❌ Cannot manage Admin roles

---

## Admin

### Permissions

✅ Full workspace control

✅ Add/remove users

✅ Change settings

✅ Delete workspace

✅ Manage permissions

✅ Publish apps

---

## Easy Role Memory Trick

```text
Viewer      → View
Contributor → Create
Member      → Manage
Admin       → All Access
```

---

# 📄 Reports

## What is a Report?

A Report is a collection of visualizations built from a single semantic model.

### Features

✅ Multiple pages

✅ Interactive

✅ Filtering

✅ Drill-down

✅ Drill-through

✅ Cross-highlighting

---

## Example

```text
Sales Report
│
├── Overview
├── Product Analysis
├── Regional Sales
└── Customer Insights
```

---

## Report Characteristics

| Feature | Report |
|----------|----------|
| Multiple Pages | ✅ |
| Interactive | ✅ |
| Uses One Semantic Model | ✅ |
| Filtering | ✅ |
| Drill Down | ✅ |

---

# 🗄️ Semantic Models

## What is a Semantic Model?

A Semantic Model represents structured business data used by reports and dashboards.

Contains:

- Tables
- Relationships
- Measures
- Calculations

---

## Example

```text
Customers
     │
     ▼
Sales
     ▲
     │
Products
```

---

## Benefits

✅ Reusability

✅ Consistency

✅ Single source of truth

✅ Faster report development

---

## Example Measures

```DAX
Total Sales =
SUM(Sales[Amount])

Total Profit =
SUM(Sales[Profit])
```

---

# 📊 Dashboards

## What is a Dashboard?

A Dashboard is a single-page summary of important insights.

---

## Characteristics

✅ Single page

✅ Quick overview

✅ Executive-focused

✅ Multiple reports supported

✅ Supports alerts

---

## Dashboard Tiles

When a report visual is pinned to a dashboard, it becomes a:

```text
Tile
```

---

## Example Dashboard

```text
Revenue        $5,000,000
Profit         $1,000,000
Customers      10,000
Growth         15%
```

---

# Dashboard vs Report

| Dashboard | Report |
|------------|----------|
| Single Page | Multiple Pages |
| Summary | Detailed Analysis |
| Multiple Sources | One Semantic Model |
| Supports Alerts | No Alerts |
| Service Only | Desktop + Service |

---

## Memory Trick

```text
Dashboard = Summary
Report = Details
```

---

# 📱 Apps

## What is a Power BI App?

Apps allow designers to package and distribute Power BI content.

Apps can contain:

- Reports
- Dashboards
- Semantic Models

---

## Example

```text
Finance App
│
├── Revenue Dashboard
├── Budget Report
├── Expense Report
└── Finance Dataset
```

---

## Benefits

### For Users

✅ Easy navigation

✅ Single access point

✅ Organized content

---

### For Designers

✅ Controlled distribution

✅ Version management

✅ Audience targeting

✅ Centralized updates

---

# 🚀 Publish to Power BI Service

## Why Publish?

Instead of emailing `.pbix` files:

```text
Sales.pbix
```

Publish them to:

```text
Power BI Service
```

for centralized access.

---

## Publish Steps

### Option 1

```text
Home
 ↓
Publish
```

### Option 2

```text
File
 ↓
Publish
 ↓
Publish to Power BI
```

---

## Publishing Process

```text
Power BI Desktop
       ↓
Sign In
       ↓
Select Workspace
       ↓
Publish
       ↓
Power BI Service
```

---

## What Gets Published?

When publishing a PBIX file:

```text
Sales.pbix
```

Power BI publishes:

```text
Report
+
Semantic Model
```

---

## Republishing

When changes are made:

```text
Update Report
       ↓
Republish
       ↓
Replace Existing Version
```

Power BI displays the impact on:

- Reports
- Dashboards
- Workspaces

before updating.

---

# 📤 Upload PBIX Files

An alternative to publishing directly from Desktop.

---

## Upload Sources

### Local Computer

```text
Browse
↓
Select PBIX File
```

---

### OneDrive for Work or School

```text
OneDrive
↓
Select File
```

---

### SharePoint

```text
SharePoint
↓
Select File
```

---

# 🔄 OneDrive & SharePoint Synchronization

When PBIX files are stored in:

- OneDrive
- SharePoint

Power BI creates a connection.

```text
PBIX File Updated
        ↓
OneDrive / SharePoint
        ↓
Power BI Service
        ↓
Automatic Sync (~1 Hour)
```

### Benefits

✅ Automatic updates

✅ Version control

✅ Centralized storage

---

# 📁 Workspace Folders

Folders help organize Power BI content.

---

## Create Folder Structure

Example:

```text
Finance Workspace
│
├── Reports
│   ├── Monthly
│   ├── Quarterly
│   └── Annual
│
├── Dashboards
│
└── Datasets
```

---

## Nested Folders

Power BI supports:

```text
Up to 10 Folder Levels
```

Example:

```text
Reports
└── Regional
    └── UAE
        └── Abu Dhabi
            └── 2025
```

---

# ✅ Exam Revision Notes

## Workspace

✅ Content container

✅ Collaboration area

✅ Supports role-based access

---

## Roles

✅ Viewer

✅ Contributor

✅ Member

✅ Admin

---

## Reports

✅ Multiple pages

✅ Interactive

✅ One semantic model

---

## Semantic Models

✅ Tables

✅ Relationships

✅ Measures

✅ Reusable

---

## Dashboards

✅ Single page

✅ Summary view

✅ Supports alerts

---

## Apps

✅ Package content

✅ Controlled distribution

✅ Easy user experience

---

## Publishing

✅ Publish from Desktop

✅ Report + Semantic Model published together

✅ Supports republishing

---

## Uploading

✅ Computer

✅ OneDrive

✅ SharePoint

✅ Automatic synchronization available

---

# 🧠 Ultimate Memory Map

```text
Workspace
│
├── Semantic Model
│
├── Report
│
├── Dashboard
│
└── App
```

---

# 🎯 Golden Interview Answer

> A Power BI Workspace is a collaborative container that stores semantic models, reports, dashboards, and apps. Reports are created in Power BI Desktop and published to Power BI Service, where they can be secured, organized, shared, and distributed across an organization using role-based access control and Power BI apps.

---

# 📸 Screenshots

Create an `/images` folder in the repository.

```text
images/
│
├── powerbi-service-home.png
├── workspace-list.png
├── create-workspace.png
├── manage-access.png
├── publish-report.png
├── semantic-model.png
├── dashboard-tiles.png
├── app-view.png
├── upload-pbix.png
└── folder-structure.png
```

---

# 📖 Quick Recall Formula

```text
Workspace
      ↓
Semantic Model
      ↓
Report
      ↓
Dashboard
      ↓
App
```

**Workspace stores everything.  
Semantic Model powers the data.  
Report analyzes the data.  
Dashboard summarizes the data.  
App distributes the content.**
