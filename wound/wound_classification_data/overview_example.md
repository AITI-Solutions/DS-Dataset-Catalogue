### Dataset Overview

# wound_classification (AZH Wound and Vascular Center / UWM)

### Data Description

This dataset includes 538 wound images across four wound types — diabetic, venous, surgical, and pressure — provided through a collaboration between AZH Wound and Vascular Center in Milwaukee and the Big Data Analytics and Visualization Laboratory at the University of Wisconsin–Milwaukee (UWM). The original images are used here, split into train and validation sets. The dataset was introduced in the preprint "Multiclass Wound Image Classification using an Ensemble Deep CNN-based Classifier".

- **What the dataset contains**: Original wound images and corresponding region-of-interest (cropped) versions, each labeled with one of four wound types and a train/val split assignment.
- **Business purpose**: Support multiclass wound image classification research, as described in the associated preprint.
- **Primary use cases**: Wound type classification (diabetic / pressure / surgical / venous) using deep CNN-based classifiers.
- **Key entities or metrics included**: Image path, ROI path, wound type label, encoded label, train/val split.

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** |  Wound  |
| **Dataset Owner** | AITIS |
| **Status** | Active |
| **Version** | N/A |
| **Classification** | Public |
| **Licences** | N/A |
| **Created** | N/A |
| **Last Updated** | N/A |
| **Refresh Frequency** | None (static) |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 1 CSV (metadata only; 538 source images + ROI crops referenced by path, not included) |
| Formats | CSV (metadata); JPG (referenced original and ROI images) |
| extension | .csv, .jpg |
| Storage Size | 538 rows, 6 columns |
| Primary Key(s) | image-path (unique per row) |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 1 |
| Number of Columns | 6 |
| Number of Rows | 538 |
| Number of Observations | 1 per image |
| Total Records | 538 |
| Data Stucture | Structured (flat tabular CSV) |
| Data Orientation | Row-per-image |
| Partition Strategy | Train/Val split via `train-val` column (Train 429, Val 109); also organized by class subfolder in file paths |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | N/A |
| **Platform** | N/A |
| **Storage Location** | `https://github.com/AITI-Solutions/Wound-Project/blob/main/Archived/wound_classification_data/wound_classification.csv` |
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
| train | Field value (`train-val` = train) | 429 records |
| val | Field value (`train-val` = val) | 109 records |
| D (Diabetic) | Field value (`image-label` = D) | 154 records |
| P (Pressure) | Field value (`image-label` = P) | 100 records |
| S (Surgical) | Field value (`image-label` = S) | 128 records |
| V (Venous) | Field value (`image-label` = V) | 156 records |

<br><br>

## Documentation

- Source: collaboration between AZH Wound and Vascular Center (Milwaukee) and the Big Data Analytics and Visualization Laboratory, University of Wisconsin–Milwaukee (UWM).
- Introduced in the preprint: "Multiclass Wound Image Classification using an Ensemble Deep CNN-based Classifier".

<br><br>


