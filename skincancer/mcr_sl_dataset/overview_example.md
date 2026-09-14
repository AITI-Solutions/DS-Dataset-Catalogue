### Dataset Overview

# MCR-SL_dataset

### Data Description

MCR-SL is a clinical skin lesion image dataset containing referral and diagnostic information for lesions imaged clinically (non-dermoscopic). Each row represents one clinical image of a lesion, with a link to a corresponding diagnostic reference image, patient/subject grouping, and a train/val/test split assignment.

- **What the dataset contains**: Clinical lesion images with referral diagnosis, confirmed lesion diagnosis, malignancy status, anatomical location, lesion diameter, and a corresponding diagnostic reference image link.
- **Business purpose**: N/A (not stated in the file; inferred to support skin lesion classification/triage research using clinical (non-dermoscopic) photography).
- **Primary use cases**: Clinical-image skin lesion classification, malignancy screening, referral-vs-confirmed diagnosis comparison studies.
- **Key entities or metrics included**: Lesion images, referral diagnosis, confirmed lesion diagnosis, malignancy status, anatomical location, lesion diameter, subject/lesion grouping.

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | Skincancer |
| **Dataset Owner** | |
| **Status** | Active |
| **Version** | N/A |
| **Classification** | Public |
| **Licences** | N/A |
| **Created** | N/A |
| **Last Updated** | N/A |
| **Refresh Frequency** | N/A |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 1 CSV (metadata only; source images referenced by path, not included) |
| Formats | CSV (metadata); PNG (referenced images) |
| extension | .csv |
| Storage Size | 227 rows, 14 columns |
| Primary Key(s) | image_id |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 1 |
| Number of Columns | 14 |
| Number of Rows | 227 |
| Number of Observations | 1 per clinical image |
| Total Records | 227 |
| Data Stucture | Structured (flat tabular CSV) |
| Data Orientation | Row-per-image |
| Partition Strategy | Train/Val/Test split via `Set` column (Train 113, Test 58, Val 56) |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | N/A |
| **Platform** | N/A |
| **Storage Location** |  `https://github.com/AITI-Solutions/Skin-Cancer-Project/blob/main/Dataset/MCR-SL_dataset/MCR-SL_dataset.csv` |
| **Storage Format** | CSV |
| **Region** | N/A |
| **Database** | N/A |
| **Schema** |  |
| **Table Name** |  |
| **Environment** | N/A |
| **Compression** | None |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| Train | Field value (`Set` = Train) | 113 records |
| Val | Field value (`Set` = Val) | 56 records |
| Test | Field value (`Set` = Test) | 58 records |

<br><br>

## Documentation

- 59 distinct subjects (`subject_id`) contribute the 227 lesion images — some subjects have multiple lesions/images.
- `location` (25 free-text values) is more granular than `location_group` (7 values); use `location_group` for aggregate analysis.
- `diameter` is stored as text and includes one "unknown" value alongside numeric measurements (1.3–66.0 mm).

<br><br>

## External Links

- N/A
