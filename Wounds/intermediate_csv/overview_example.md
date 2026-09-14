### Dataset Overview

# Intermediate CSV

### Data Description

This dataset contains clinical wound images and their associated annotation metadata, used for chronic wound assessment/classification research. Wounds are labeled by class (D, P, S, V), with anatomical location, wound depth, and — in two of the five files — paths to classification-ready cropped/uncropped image copies organized by train/val split.

The five uploaded files are different export/processing stages of the same underlying dataset, not five separate datasets. One file (`wound_loc_and_class.csv`) has no shared key with the others and cannot be row-joined back to them.

- **What the dataset contains**: Wound images with patient/image metadata, wound classification labels, anatomical location, wound depth, one-hot encoded location features, and classification-split image paths.
- **Business purpose**: N/A (not stated in the files).
- **Primary use cases**: Wound-type classification (class labels D/P/S/V), anatomical location modeling, wound depth/tissue classification — inferred from field structure, not explicitly stated.
- **Key entities or metrics included**: Patients, images, individual wound annotations (an image can contain multiple wounds), wound class, wound depth, anatomical location, train/val split assignment (in `wound_data_with_loc_v1`).

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** |  Wound |
| **Dataset Owner** | AITIS |
| **Status** | N/A |
| **Version** | N/A |
| **Classification** | Internal |
| **Licences** | N/A |
| **Created** | N/A |
| **Last Updated** | N/A |
| **Refresh Frequency** | N/A |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 5 CSVs |
| Formats | CSV (metadata); JPEG (referenced wound/overlay/classification images) |
| extension | .csv, .jpg |
| Storage Size | N/A |
| Primary Key(s) | ImageDetail.ImageFilename (join key for 4 of the 5 files); wound_loc_and_class.csv has no key field |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 5 (one per file) |
| Number of Columns | 9 to 72 depending on file (see data dictionary) |
| Number of Rows | 461 to 1,711 depending on file |
| Number of Observations | 1 per wound annotation (an image with multiple wounds has multiple rows) |
| Total Records | 5,241 |
| Data Stucture | Structured (flat tabular CSV) |
| Data Orientation | Row-per-wound-annotation |
| Partition Strategy | N/A |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | N/A |
| **Platform** | N/A |
| **Storage Location** | N/A |
| **Storage Format** | CSV |
| **Region** | N/A |
| **Database** | N/A |
| **Schema** | N/A |
| **Table Name** | N/A |
| **Environment** | N/A |
| **Compression** | N/A |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| train / val | Folder path segment | `wound_data_with_loc_v1.csv`'s `image_class_path`/`image_class_path_uncropped` fields organize images into `train` and `val` subfolders by class; no `test` split observed in this file |

<br><br>

## Documentation

- **wound_details_updated_mar22.csv** (1,304 rows, 44 cols) — full image + wound metadata, file paths, and `class` label.
- **wound_data_with_loc_v1.csv** (1,711 rows, 47 cols) — superset of `wound_details_updated_mar22`, adding `index`, `image_class_path`, and `image_class_path_uncropped`. Row count difference from `updated_mar22` (1,711 vs 1,304) is N/A — not independently explained by the file contents.
- **wound_loc_and_class.csv** (1,304 rows, 64 cols) — `class` + 63 one-hot anatomical-location columns only; **no filename/ID field, so it cannot be joined to the other files**.
- **wound_details_with_specific_cols.csv** (461 rows, 9 cols) — reduced subset with core classification fields only.
- **wound_details_with_new_cols.csv** (461 rows, 72 cols) — same 461-row subset, extended with 63 one-hot location columns.
- `index` in `wound_data_with_loc_v1.csv` contains 285 rows with the literal value "False" instead of a number — a data quality issue worth flagging to whoever generated the export.

<br><br>

## External Links

- N/A
