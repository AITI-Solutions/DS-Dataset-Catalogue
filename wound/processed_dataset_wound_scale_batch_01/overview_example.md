### Dataset Overview

# processed_dataset_wound_scale_batch_01

### Data Description

This is a wound-scale/measurement calibration file for "batch_01" of a processed wound dataset. Each row provides reference-point coordinates and derived scale metrics (pixels-per-centimetre and an error estimate) for a wound image, likely derived from detecting a ruler or known-size reference object in the image.

- **What the dataset contains**: Image file paths, bounding-box/reference-point coordinates, a scale factor, capture date, and derived pixel-to-centimetre conversion metrics.
- **Primary use cases**: Wound size/area calculation from images, calibration of pixel-to-cm scale per image.
- **Key entities or metrics included**: Image file path, reference-point coordinates, scale factor, pixels-per-cm, error metric.

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | Wound |
| **Dataset Owner** | AITIS |
| **Status** | Active |
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
| Total Files | 1 |
| Formats | CSV (metadata); JPG (referenced images, not included) |
| extension | .csv |
| Storage Size | 1,095 rows, 13 columns |
| Primary Key(s) | image |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 1 |
| Number of Columns | 13 |
| Number of Rows | 1,095 |
| Number of Observations | 1 per image |
| Total Records | 1,095 |
| Data Stucture | Structured (flat tabular CSV) |
| Data Orientation | Row-per-image |
| Partition Strategy | None; single batch (batch_01) scale file |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | N/A |
| **Platform** | N/A |
| **Storage Location** | `https://github.com/AITI-Solutions/Wound-Project/blob/main/Processed%20Dataset/Wound_scale/batch_01/batch_01.csv` |
| **Storage Format** | CSV |
| **Region** | N/A |
| **Database** | N/A |
| **Schema** | N/A |
| **Table Name** | N/A |
| **Environment** | N/A |
| **Compression** | None |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| N/A | N/A | Not partitioned |

<br><br>

## External Links

- N/A
