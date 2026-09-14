### Dataset Overview

# Wisconsin Data (Archived)

### Data Description

This dataset covers a wound image segmentation-to-bounding-box pipeline sourced from "wisconsin_data". It consists of three files representing sequential processing stages: raw image/mask path pairs, the same pairs with fitted bounding-box coordinates in two-corner format, and a reformatted version with bounding boxes in top-left + width/height format alongside image dimensions.

- **What the dataset contains**: Wound image and segmentation mask (label) file path pairs, train/test split assignment, and bounding boxes derived from the masks (in two different coordinate formats across files).
- **Business purpose**: N/A (not stated in the files; inferred to support converting wound segmentation masks into bounding-box annotations, likely for object-detection model training).
- **Primary use cases**: Wound detection/localization model training (bounding-box based), mask-to-box conversion pipeline validation.
- **Key entities or metrics included**: Image path, mask/label path, train/test split, bounding box coordinates, image dimensions.

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | Wound  |
| **Dataset Owner** | N/A |
| **Status** | Active |
| **Version** |  |
| **Classification** | Public |
| **Licences** | N/A |
| **Created** | N/A |
| **Last Updated** | N/A |
| **Refresh Frequency** | N/A |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 3 CSVs (metadata only; source images/masks referenced by path, not included) |
| Formats | CSV (metadata); PNG (referenced images and masks) |
| extension | .csv, .png |
| Storage Size | 1,109 rows each |
| Primary Key(s) | image_filename / image-filename (hash + index naming; shared join key across all 3 files, naming convention differs) |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 3 |
| Number of Columns | 5 (wound_image_paths); 10 (wound_image_paths_with_bounding_box); 11 (wound_image_paths_masks_to_bounding_boxes) |
| Number of Rows | 1,109 (all 3 files) |
| Number of Observations | 1 per image/mask pair |
| Total Records | 1,109 |
| Data Stucture | Structured (flat tabular CSV) |
| Data Orientation | Row-per-image |
| Partition Strategy | Train/Test split via `train_test`/`train-val-test` column (Train 831, Test 278; no val split present) |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | N/A |
| **Platform** | N/A |
| **Storage Location** | `https://github.com/AITI-Solutions/Wound-Project/tree/main/Archived/wisconsin_data` |
| **Storage Format** | CSV |
| **Region** | N/A |
| **Database** | N/A |
| **Schema** | |
| **Table Name** |  |
| **Environment** | N/A |
| **Compression** | None |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| train | Field value | 831 records |
| test | Field value | 278 records |

<br><br>

## Documentation

- **wound_image_paths.csv** — base image/mask path pairs, no bounding boxes.
- **wound_image_paths_with_bounding_box.csv** — adds `x1/y1/x2/y2` (two-corner) bounding boxes fitted from the masks; 69 rows have null box values (masks with no detected region, presumed).
- **wound_image_paths_masks_to_bounding_boxes.csv** — reformatted version with `x/y/width/height` (top-left + size) bounding boxes, values stored as single-element list strings, plus explicit image/mask dimensions `(224, 224, 3)`.
- All images/masks are a fixed 224×224×3 size per the third file.
- N/A for confirmation that the two bounding-box formats (`with_bounding_box` vs. `masks_to_bounding_boxes`) agree row-for-row on the same image — not independently cross-checked in this pass.

<br><br>

## External Links

- N/A
