### Dataset Overview

# Wisconsin Wound Data (raw data)

### Data Description

This dataset is a raw-image inventory of Wisconsin-sourced wound photographs, split into two files by wound aetiology: surgical site infections and pressure injuries. Each row simply indexes one image file with its wound-type label; there is no clinical/annotation metadata (patient ID, diagnosis, location, depth, etc.) beyond the wound type.

- **What the dataset contains**: Image file paths and filenames for wound photographs, each tagged with a wound type category.


<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | Wound  |
| **Dataset Owner** | N/A |
| **Status** | Active |
| **Version** | N/A |
| **Classification** | N/A |
| **Licences** | N/A |
| **Created** | N/A |
| **Last Updated** | N/A |
| **Refresh Frequency** | N/A |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 2 CSVs (metadata only; source images referenced by path, not included) |
| Formats | CSV (metadata); JPG (referenced images) |
| extension | .csv |
| Storage Size | 128 rows (surgical); 100 rows (pi) |
| Primary Key(s) | ImageDetail.ImageFilename |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 2 |
| Number of Columns | 6 (both files, identical schema) |
| Number of Rows | 128 (wisconsin_surgical_data); 100 (wisconsin_pi_data) |
| Number of Observations | 1 per image |
| Total Records | 228 combined |
| Data Stucture | Structured (flat tabular CSV) |
| Data Orientation | Row-per-image |
| Partition Strategy | Split by wound type across the two files (surgical vs. pressure injury); no train/val/test split present |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | N/A |
| **Platform** | N/A |
| **Storage Location** |  `https://github.com/AITI-Solutions/Wound-Project/tree/main/Original%20Dataset/Wisconsin_image/raw_data` |
| **Storage Format** | CSV |
| **Region** | N/A |
| **Database** | N/A |
| **Schema** | N/A |
| **Table Name** | N/A  |
| **Environment** | N/A |
| **Compression** | None |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| Surgical Site Infections (SSI) | File | wisconsin_surgical_data.csv — 128 images |
| Pressure Injuries (PI) | File | wisconsin_pi_data.csv — 100 images |

<br><br>

## Documentation

- No overlap in scope with prior `wound_details_*`/`batch_*` datasets — this appears to be a lighter, image-inventory-only export (no diagnosis, location, depth, or patient ID fields).
- Boolean casing for `ImageDetail.hasRuler` differs between the two raw files (`False` vs `FALSE`) — cosmetic, but suggests different export tooling per file.

<br><br>

## External Links

- N/A
