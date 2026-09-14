### Dataset Overview

# Preprocessed_dataset Segmentation Level 02

### Data Description

This dataset comprises 9 sequential capture/export batch files of clinical wound images and their annotation metadata (image detail + wound detail), covering four+ wound aetiology types (Neuro-Ischemic, Pressure, Surgical Site Infection, Venous Leg Ulcer, plus an "Other" category). 8 of the 9 files share an identical schema; `batch_24` has a reduced schema (5 fewer populated fields, 2 blank unlabeled columns).


<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | Wound |
| **Dataset Owner** | AITIS |
| **Status** | Active |
| **Version** | |
| **Classification** | Internal |
| **Licences** | N/A |
| **Created** | N/A |
| **Last Updated** | N/A |
| **Refresh Frequency** | N/A |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 9 CSVs |
| Formats | CSV (metadata); JPEG (referenced wound images, inferred from filenames) |
| extension | .csv |
| Storage Size | N/A |
| Primary Key(s) | WoundDetail.Id (row-level); ImageDetail.ImageFilename (image-level join key) |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 9 (one per batch file) |
| Number of Columns | 40 (batch_01–06, batch_17, batch_23); 37 (batch_24) |
| Number of Rows | batch_01: 19, batch_02: 279, batch_03: 132, batch_04: 142, batch_05: 157, batch_06: 198, batch_17: 123, batch_23: 123, batch_24: 46 |
| Number of Observations | 1 per wound annotation (an image with multiple wounds has multiple rows) |
| Total Records | 1,219 across all 9 files |
| Data Stucture | Structured (flat tabular CSV) |
| Data Orientation | Row-per-wound-annotation |
| Partition Strategy | N/A |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | N/A |
| **Platform** | N/A |
| **Storage Location** | `https://github.com/AITI-Solutions/Wound-Project/tree/main/Processed%20Dataset/Segmentation/level_02`  |
| **Storage Format** | CSV |
| **Region** | N/A |
| **Database** | N/A |
| **Schema** | Flat metadata table, 2 schema variants|
| **Table Name** | N/A |
| **Environment** | N/A |
| **Compression** | None |
---


<br><br>


