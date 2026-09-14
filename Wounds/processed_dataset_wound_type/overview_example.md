### Dataset Overview

# processed_dataset_wound_type

### Data Description

These two files are sequential stages of the same wound image metadata export: a merged wound-details table (July 2022), and a follow-on version that adds standardized/reorganized file path fields and batch-name tracking for each record. Together they cover wound images across 25 distinct capture batches, with full image + wound annotation metadata (wound type, depth, location, area-of-interest coordinates).

- **What the dataset contains**: Wound images with patient/image metadata, wound type, anatomical location, wound depth, area-of-interest bounding boxes, original and (in one file) reorganized file paths, and batch name.
- **Key entities or metrics included**: Patients, images, individual wound annotations, wound type, wound depth, anatomical location, batch name, raw/overlay file paths (original and updated).

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | Wound |
| **Dataset Owner** | AITIS |
| **Status** | Active |
| **Version** | N/A |
| **Classification** |Internal |
| **Licences** | N/A |
| **Created** | N/A |
| **Last Updated** | July 2022 |
| **Refresh Frequency** | N/A |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 2 CSVs (metadata only; source images referenced by path, not included) |
| Formats | CSV (metadata); JPG (referenced images) |
| extension | .csv |
| Storage Size | N/A |
| Primary Key(s) | ImageDetail.ImageFilename (join key across both files) |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 2 |
| Number of Columns | 48 (merged_wound_details_july_2022); 51 (wound_type_new_path_metadata) |
| Number of Rows | 2,751 (merged_wound_details_july_2022); 2,738 (wound_type_new_path_metadata) |
| Number of Observations | 1 per wound annotation (an image with multiple wounds has multiple rows) |
| Total Records | 5,489 |
| Data Stucture | Structured (flat tabular CSV) |
| Data Orientation | Row-per-wound-annotation |
| Partition Strategy | N/A |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | N/A |
| **Platform** | N/A |
| **Storage Location** | `https://github.com/AITI-Solutions/Wound-Project/tree/main/Processed%20Dataset/Wound_type` |
| **Storage Format** | CSV |
| **Region** | N/A  |
| **Database** | N/A |
| **Schema** | N/A |
| **Table Name** | N/A |
| **Environment** | N/A |
| **Compression** | None |
---

<br><br>

## Documentation

- **merged_wound_details_july_2022.csv** (2,751 rows, 48 cols) — base merged wound-details export.
- **wound_type_new_path_metadata.csv** (2,738 rows, 51 cols) — same schema plus `Batch Name`, `changed_raw_directory`, `changed_ov_directory`, recording a file-path reorganization/migration step.

<br><br>

## External Links

- N/A
