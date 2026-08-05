# Power BI - Get Data from Files

## What is a Flat File?

A **flat file** is a file that contains:

- Only **one data table**
- Same structure in every row
- No relationships or hierarchies

### Common Flat File Types

| File Type | Extension |
|------------|-----------|
| Comma-Separated Values | .csv |
| Delimited Text File | .txt |
| Fixed Width File | Various |
| Excel Workbook | .xlsx |

**Remember:** Flat File = One Table + No Hierarchy

---

# Scenario

The HR team at XYZ Traders provides an Excel file containing:

- Employee Name
- Hire Date
- Position
- Manager

The goal is to import this data into Power BI and create reports.

---

# File Storage Locations

## Comparison of File Locations

| Location | Description | Updates Reflected in Power BI? | Best Use Case |
|-----------|-------------|-------------------------------|---------------|
| Local Computer | Data is copied into Power BI | ❌ No | Static data |
| OneDrive for Business | Power BI stays connected to file | ✅ Yes | Frequently updated data |
| OneDrive Personal | Similar to OneDrive Business | ✅ Yes | Personal account usage |
| SharePoint Team Sites | Connected cloud storage for teams | ✅ Yes | Team collaboration |

---

## Local Storage

### Characteristics

| Feature | Value |
|----------|--------|
| File moved into Power BI | No |
| Data copied into model | Yes |
| Automatic updates | No |
| Suitable for | Data that rarely changes |

### Key Point

Changes made to the original Excel file are **not automatically reflected** in Power BI.

---

## OneDrive for Business

### Characteristics

| Feature | Value |
|----------|--------|
| Cloud connected | Yes |
| Automatic synchronization | Yes |
| Reports updated automatically | Yes |
| Suitable for | Frequently changing data |

### Key Point

Power BI regularly checks the file and updates:

- Semantic Models
- Reports
- Dashboards

---

## OneDrive Personal

### Characteristics

| Feature | Value |
|----------|--------|
| Uses personal account | Yes |
| Auto synchronization | Yes |
| Requires sign-in | Yes |
| Keep Me Signed In option | Required |

### Key Point

Check organizational policies before using personal OneDrive.

---

## SharePoint Team Sites

### Characteristics

| Feature | Value |
|----------|--------|
| Cloud storage | Yes |
| Auto synchronization | Yes |
| Team collaboration | Yes |
| Connect via URL | Yes |

### Key Point

Very similar to OneDrive for Business but uses SharePoint connections.

---

# Recommended Storage Choice

| Option | Recommendation |
|----------|--------------|
| OneDrive for Business | ⭐ Best |
| SharePoint Team Sites | ⭐ Best |
| Local Computer | Good for static data |

### Reason

Cloud storage keeps:

- Files
- Semantic Models
- Reports
- Dashboards

automatically synchronized.

---

# Connecting to a File

## Steps

| Step | Action |
|--------|--------|
| 1 | Open Power BI Desktop |
| 2 | Go to Home Tab |
| 3 | Select Get Data |
| 4 | Choose file type (Excel, CSV, XML, etc.) |
| 5 | Browse and locate file |
| 6 | Open file |

---

# Available File Source Options

| Option | Purpose |
|----------|---------|
| Excel | Import Excel workbooks |
| Text/CSV | Import CSV files |
| XML | Import XML files |
| Other File Types | Based on supported connectors |

---

# Quick Access

The Home tab provides shortcuts for frequently used sources.

| Shortcut | Purpose |
|-----------|----------|
| Excel | Direct connection to Excel files |
| Get Data | Full list of available sources |

---

# Authentication

Some sources require authentication.

| Source Type | Authentication Needed |
|------------|----------------------|
| Local File | Usually No |
| OneDrive | Yes |
| SharePoint | Yes |

---

# Navigator Window

After connecting to a file, Power BI opens the **Navigator Window**.

## Purpose

| Function | Description |
|----------|-------------|
| Display available tables | Shows sheets/tables |
| Preview data | Allows review before import |
| Select data | Choose which tables to load |

---

# Importing Tables

## Steps

| Step | Action |
|--------|--------|
| 1 | Select desired table(s) |
| 2 | Preview contents |
| 3 | Confirm selection |
| 4 | Choose Load or Transform Data |

---

# Available Actions

| Button | Purpose |
|----------|---------|
| Load | Import data directly |
| Transform Data | Open Power Query Editor |

---

# Load vs Transform Data

| Feature | Load | Transform Data |
|----------|------|---------------|
| Immediate Import | ✅ | ❌ |
| Data Cleaning | ❌ | ✅ |
| Power Query Opens | ❌ | ✅ |
| Best Practice | ⚠️ Sometimes | ✅ Recommended |

---

# Power Query Editor

## Purpose

Power Query Editor allows you to:

- Clean data
- Modify columns
- Remove errors
- Change data types
- Prepare data before loading

### Recommendation

Use **Transform Data** whenever possible before loading data.

---

# Changing the Source File

Sometimes:

- File location changes
- Folder changes
- Development environment changes

Power BI allows updating the source path.

---

## Methods to Change Source

| Method | Description |
|----------|------------|
| Data Source Settings | Most common method |
| Query Settings | Modify query properties |
| Advanced Editor | Edit source code manually |

---

# Change Source Using Data Source Settings

## Steps

| Step | Action |
|----------|---------|
| 1 | Open Power Query |
| 2 | Select Data Source Settings |
| 3 | Select existing file |
| 4 | Click Change Source |
| 5 | Update file path |
| 6 | Click OK |
| 7 | Click Close |

---

# Warning: File Structure Must Remain the Same

When changing the source file:

✅ Allowed:
- New file location
- Different folder path

❌ Not Allowed:
- Deleting columns
- Renaming columns
- Changing table structure

---

## Why?

Power BI reports depend on the existing data model.

Structural changes can cause:

| Change | Possible Result |
|----------|---------------|
| Delete Column | Report breaks |
| Rename Column | Visual errors |
| Change Table Structure | Query failures |

---

# Key Terms

| Term | Definition |
|---------|-----------|
| Flat File | Single table file with no hierarchy |
| Semantic Model | Data model created in Power BI |
| Navigator | Window for selecting imported data |
| Power Query Editor | Tool for cleaning and transforming data |
| Load | Import data directly |
| Transform Data | Clean data before loading |
| Data Source Settings | Location to change file paths |

---

# Exam Notes

## Storage Types

| Storage | Auto Sync |
|----------|----------|
| Local | ❌ |
| OneDrive Business | ✅ |
| OneDrive Personal | ✅ |
| SharePoint Team Sites | ✅ |

---

## Import Process

```text
Home
 └── Get Data
      └── Excel
           └── Select File
                └── Navigator
                     ├── Load
                     └── Transform Data
```

---

## Quick Memorization

### FLITC

| Letter | Meaning |
|----------|---------|
| F | Flat File |
| L | Locations |
| I | Import Data |
| T | Transform Data |
| C | Change Source |

**FLITC = Entire "Get Data from Files" Process**
