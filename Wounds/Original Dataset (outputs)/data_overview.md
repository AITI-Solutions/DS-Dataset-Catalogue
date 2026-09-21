### Dataset Overview

# Original Dataset (outputs)

### Data Description

This dataset holds the processed outputs derived from the raw TTSH/Wisconsin wound-image annotation exports: path-corrected image/wound metadata, the train/test/val segmentation splits built from it, and the batch-renaming lookup tables that tie the two together. It contains 8 files:

- **new_path_metadata.csv** — the master metadata table (image + wound annotation fields) with standardized batch names and directory paths, covering 28 batches.
- **new_path_metadata_seg_level2.csv** — a second ("level 2") annotation pass over a 7-batch subset, same schema.
- **segmentation_train_df.csv / segmentation_test_df.csv / segmentation_val_df.csv** — the train/test/validation split of the merged, cleaned metadata (26 batches) used to train the wound segmentation model.
- **new batch name_level 1.csv / new batch name_level 2.csv** — lookup tables mapping original annotator export folder names to the canonical `batch_<NN>` naming scheme.
- **blank_overlay_w_directory.csv** — QA manifest of overlay images flagged as blank (also documented under `Wounds/Original Dataset (metadata)`).

The five metadata/split files share one 52-field schema (image capture metadata, wound-level annotation fields, area-of-interest bounding boxes, and standardized/legacy file paths); see `data_dictionary.md` for the full field list and per-file specifics.

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | HEL (Health) / Wounds |
| **Dataset Owner** | AITIS |
| **Status** | Active |
| **Version** | |
| **Classification** | |
| **Licences** | |
| **Created** | |
| **Last Updated** | |
| **Refresh Frequency** | Static |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 8 files |
| Formats | CSV |
| extension | .csv |
| Storage Size | ~4.07 MB (4,273,165 bytes) |
| Primary Key(s) | None single-column; metadata/split files are keyed by (ImageDetail.Id, WoundDetail.WoundNumber) |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 8 (5 sharing a 52-field schema, 3 small lookup/QA tables) |
| Number of Columns | 52 (common schema) / 2 (lookup tables) |
| Number of Rows | 6,699 total across all 8 files (excluding headers) |
| Number of Observations | 6,699 |
| Total Records | 6,699 |
| Data Stucture | Tabular |
| Data Orientation | Row-oriented |
| Partition Strategy | By processing stage (master metadata → level-2 pass → train/test/val split) plus standalone lookup tables |

<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | NA |
| **Platform** | Github |
| **Storage Location** |https://github.com/AITI-Solutions/Wound-Project/tree/main/Original%20Dataset|
| **Storage Format** | CSV |
| **Region** | NA |
| **Database ** | NA |
| **Schema** | NA |
| **Table Name** | Original Dataset (outputs) |
| **Environment** | |
| **Compression** | NA |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| new_path_metadata.csv | .csv | Master metadata — 3,104 rows, 28 batches |
| new_path_metadata_seg_level2.csv | .csv | Level-2 annotation pass — 973 rows, 7 batches |
| segmentation_train_df.csv | .csv | Segmentation training split — 1,931 rows, 26 batches |
| segmentation_test_df.csv | .csv | Segmentation test split — 258 rows, 24 batches |
| segmentation_val_df.csv | .csv | Segmentation validation split — 386 rows, 26 batches |
| new batch name_level 1.csv | .csv | Level-1 batch-name lookup — 28 rows |
| new batch name_level 2.csv | .csv | Level-2 batch-name lookup — 9 rows |
| blank_overlay_w_directory.csv | .csv | Blank-overlay QA manifest — 10 rows |

<br><br>

## Documentation


<br><br>

## Related Links

