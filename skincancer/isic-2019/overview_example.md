### Dataset Overview

# ISIC 2019 Training (Metadata + GroundTruth)

### Data Description

ISIC 2019 is a public skin lesion image dataset released as part of the ISIC (International Skin Imaging Collaboration) 2019 Challenge, combining images from the HAM10000, BCN20000, and MSK datasets. This upload consists of the training set's metadata (patient demographics, anatomical site, lesion grouping) and ground-truth diagnosis labels (one-hot across 9 diagnostic categories) for 25,331 images.

- **What the dataset contains**: Per-image patient demographics (age, sex), anatomical site, lesion grouping ID, and a one-hot diagnosis label across 9 skin lesion categories (melanoma, nevus, basal cell carcinoma, actinic keratosis, benign keratosis, dermatofibroma, vascular lesion, squamous cell carcinoma, unknown).
- **Business purpose**: Support development and benchmarking of automated skin lesion classification algorithms.
- **Primary use cases**: Multi-class skin lesion classification, melanoma detection, class-imbalance research.
- **Key entities or metrics included**: Image ID, patient demographics, anatomical site, lesion ID, 9-class diagnosis label.

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | Skincancer |
| **Dataset Owner** | ISIC |
| **Status** | Active |
| **Version** | |
| **Classification** | Public |
| **Licences** | CC-BY-NC |
| **Created** |  |
| **Last Updated** | N/A |
| **Refresh Frequency** | None (static challenge dataset) |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 2 CSVs (metadata only; source images not included) |
| Formats | CSV (metadata); JPEG (source images, referenced by `image` ID) |
| extension | .csv |
| Storage Size | 25,331 rows each |
| Primary Key(s) | |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 2 |
| Number of Columns | 5 (Metadata); 10 (GroundTruth) |
| Number of Rows | 25,331 (both files) |
| Number of Observations | 1 per image |
| Total Records | 25,331 |
| Data Stucture | Structured (flat tabular CSV) |
| Data Orientation | Row-per-image |
| Partition Strategy | None; single training set (no train/val/test split column present in these files) |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | N/A |
| **Platform** | ISIC Archive / ISIC 2019 Challenge |
| **Storage Location** | ISIC_2019_Training_Metadata.csv, ISIC_2019_Training_GroundTruth.csv (local files); source: https://challenge.isic-archive.com/data/ |
| **Storage Format** | CSV |
| **Region** | N/A |
| **Database** | N/A |
| **Schema** | Flat metadata table + flat one-hot label table |
| **Table Name** |  |
| **Environment** | Public |
| **Compression** | None |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| N/A | N/A | Not partitioned; this is the training set only — ISIC 2019 also has a separate, unlabeled test set (not included here) |

<br><br>

## Documentation

- ISIC 2019 Challenge Datasets page: https://challenge.isic-archive.com/data/
- Combines images from HAM10000, BCN20000, and MSK dataset dataset sources (per known ISIC 2019 composition — not independently re-derived from these two files alone).
- Class distribution is notably imbalanced: NV (nevus) accounts for ~51% of the training set, while DF and VASC each make up under 1%.

<br><br>

## External Links

- https://challenge.isic-archive.com/data/
- https://www.isic-archive.com
