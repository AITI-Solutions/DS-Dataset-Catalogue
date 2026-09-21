### Dataset Overview

# Original Dataset (metadata)

### Overlay Image Directory Manifest

### Data Description

This dataset is a small manifest file (`blank_overlay_w_directory (1).csv`) that maps wound overlay images flagged as having a blank/missing overlay annotation to their location within the `TTSH_image/overlay` directory tree. Each row pairs the image's full relative directory path with its filename, allowing the flagged overlay images to be located and reviewed or re-annotated against the batch folder structure used by the wider TTSH wound-image dataset (`Wounds/TTSH_image:overlay`).

Key entities/metrics:
- **Directory path** (`changed_ov_directory`): the batch folder and filename where the overlay image lives.
- **Filename** (`ImageDetail.ImageFilename`): the overlay image's filename, prefixed `Ov_`.

Primary use case: a QA/audit list for identifying overlay images that need correction, keyed by patient ID and (for most rows) capture timestamp.

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | HEL (Health) / Wounds |
| **Dataset Owner** | AITIS |
| **Status** | Active |
| **Version** |  |
| **Classification** |  |
| **Licences** | |
| **Created** |  |
| **Last Updated** |  |
| **Refresh Frequency** | Static |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 1 file |
| Formats | CSV |
| extension | .csv |
| Storage Size | ~1 KB (1,035 bytes) |
| Primary Key(s) | ImageDetail.ImageFilename (not guaranteed unique, but unique within this sample) |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 1 |
| Number of Columns | 2 |
| Number of Rows | 10 (excluding header row) |
| Number of Observations | 10 |
| Total Records | 10 |
| Data Stucture | Tabular |
| Data Orientation | Row-oriented |
| Partition Strategy | None (single flat file) |

<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | NA |
| **Platform** | Github |
| **Storage Location** | https://github.com/AITI-Solutions/Wound-Project/blob/main/Original%20Dataset/blank_overlay_w_directory.csv|
| **Storage Format** | CSV |
| **Region** | NA |
| **Database ** | NA |
| **Schema** | NA |
| **Table Name** | blank_overlay_w_directory |
| **Environment** |  |
| **Compression** | NA |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| blank_overlay_w_directory (1).csv | .csv | Full manifest — 10 flagged overlay images spanning batches 01, 02, 10, and 24 |

<br><br>

## Documentation


<br><br>

## Related Links

