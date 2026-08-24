### Dataset Overview

# overlay-pixel-value-lookup

### Data Description

This is a static reference/lookup table mapping wound and skin tissue types to their overlay pixel encoding and display colours. It is used to interpret or generate annotated overlay images for wound assessment (e.g. tissue-type segmentation masks), where each tissue type is encoded as a single-bit hex value and rendered with a distinct colour.


<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | Wound  |
| **Dataset Owner** | N/A |
| **Status** | Static |
| **Version** | N/A |
| **Classification** | Internal |
| **Licences** | N/A |
| **Created** | N/A |
| **Last Updated** | N/A |
| **Refresh Frequency** | None (static) |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 1 |
| Formats | CSV |
| extension | .csv |
| Storage Size | 18 rows, 6 columns (small, <10 KB) |
| Primary Key(s) | tissue_type |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 1 |
| Number of Columns | 6 |
| Number of Rows | 18 |
| Number of Observations | 1 per tissue type |
| Total Records | 18 |
| Data Stucture | Structured (flat tabular CSV) |
| Data Orientation | Row-per-tissue-type |
| Partition Strategy | None; single static lookup table |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | N/A |
| **Platform** | N/A |
| **Storage Location** | `https://github.com/AITI-Solutions/Wound-Project/blob/main/Script/Segmentation/Level%202/overlay-pixel-value-lookup.csv` |
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
| N/A | N/A | Not partitioned; single static lookup table |

<br><br>

## Documentation

- `overlay_save_value` values are single-bit hex flags (e.g. 0x0100, 0x0200, ... 0x800000), consistent with a bitmask scheme where each tissue type occupies one bit.

<br><br>

## External Links

- N/A
