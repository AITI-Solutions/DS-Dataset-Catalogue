### Dataset Overview

# ISIC-2016


### Data Description

The ISIC 2016 dataset is the first-year archive of the "Skin Lesion Analysis toward Melanoma Detection" challenge, hosted at ISBI 2016 by the International Skin Imaging Collaboration (ISIC). It contains dermoscopic images of skin lesions paired with expert-annotated ground truth for three distinct analysis tasks, further split into 5 task variants (Part 1, 2, 2B, 3, 3B). The dataset is split into a Training set and a Test set.


<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | HEL |
| **Dataset Owner** | AITIS |
| **Status** | |
| **Version** ||
| **Classification** | |
| **Licences** | |
| **Created** | |
| **Last Updated** | |
| **Refresh Frequency** | |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files ||
| Formats | |
| extension ||
| Storage Size | |
| Primary Key(s) | |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | |
| Number of Columns | |
| Number of Rows ||
| Number of Observations ||
| Total Records | |
| Data Stucture | |
| Data Orientation | |
| Partition Strategy | |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | |
| **Platform** | |
| **Storage Location** | https://github.com/AITI-Solutions/Skin-Cancer-Project/tree/main/Dataset/ISIC-2016 |
| **Storage Format** | |
| **Region** | |
| **Database ** | |
| **Schema** | |
| **Table Name** | |
| **Environment** | |
| **Compression** | |
---

<br><br>

## Folder Structure

### Test

| Folder / File | Type | Count & Discription |
|---|---|---|
| `ISBI2016_ISIC_Part1_Test_Data` | Images | 379 |
| `ISBI2016_ISIC_Part1_Test_GroundTruth` | Images (binary mask, .png) | 379 |
| `ISBI2016_ISIC_Part2_Test_Data` | Images | 758 |
| `ISBI2016_ISIC_Part2_Test_GroundTruth` | json  | 359 |
| `ISBI2016_ISIC_Part2B_Test_Data` | Images | 379 |
| `ISBI2016_ISIC_Part2B_Test_GroundTruth` | Images (globules, streaks) |758|
| `ISBI2016_ISIC_Part3_Test_Data` | Images | 379 |
| `ISBI2016_ISIC_Part3_Test_GroundTruth.csv` | CSV | Binary(1, 0) |
| `ISBI2016_ISIC_Part3B_Test_Data` | Images(image, segmentation) | 759 |
| `ISBI2016_ISIC_Part3B_Test_GroundTruth.csv` | CSV | Binary(1, 0) |

### Training

| Folder / File | Type | Count |
|---|---|---|
| `images` | folders | 5 *|
| `ISBI2016_ISIC_Part1_Training_GroundTruth` | Images (Segmentation) | 600 |
| `ISBI2016_ISIC_Part2_Training_GroundTruth` | Dataset (json) | 600 |
| `ISBI2016_ISIC_Part2B_Training_GroundTruth` | Dataset (globules, streaks) | 1614 |
| `ISBI2016_ISIC_Part3_Training_GroundTruth.csv` | CSV | 900 rows (benign, malignant) |
| `ISBI2016_ISIC_Part3B_Training_GroundTruth.csv` | CSV | 900 rows (benign, malignant) |

> Note: Training does not have separate `_Data` subfolders per part — the single `images` folder is shared across all 5 task variants. Test has a separate `_Data` folder per part.

> Note :  ISBI2016_ISIC_Part1_Training_Data, ISBI2016_ISIC_Part2B_Training_Data, ISBI2016_ISIC_Part2_Training_Data, ISBI2016_ISIC_Part3B_Training_Data, ISBI2016_ISIC_Part3_Training_Data - These five subfiles are included in images.

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| | | |
| | | |
| | | |

<br><br>

## Documentation


<br><br>

## External Links
