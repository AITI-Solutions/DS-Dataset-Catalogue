### Dataset Overview

# TTSH_image / overlay

### Data Description

This dataset is the raw, per-batch wound-image annotation export from TTSH — 26 CSV files (`batch_01.csv` … `batch_26.csv`), one per annotation export batch. Each row is an image/wound annotation record: image capture metadata, wound classification and location, area-of-interest bounding boxes at both the image and wound level, and (for most batches) workstation/QA fields.

This is the pre-merge source data: `Original Dataset (outputs)/new_path_metadata.csv` is built by combining these 26 files, renaming batches to a canonical scheme, and standardizing image/overlay file paths. The field set is almost identical across all 26 files, with a few columns present only in a subset of batches — see `data_dictionary.md` for the exact breakdown.

Key entities/metrics:
- **Wound classification**: `WoundType` (VLU, NIU, SSI, PI, Other)
- **Annotation workflow**: Status, reviewer/amender, timestamps
- **Image metadata**: dimensions, resolution, pixel format
- **Bounding boxes**: image-level and wound-level area of interest
- **QA metrics** (batches 04–23 only): unfilled segmentation area, prior amputation flag, authoring machine

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
| Total Files | 26 files |
| Formats | CSV |
| extension | .csv |
| Storage Size | ~930 KB (951,984 bytes) |
| Primary Key(s) | None single-column; keyed by (ImageDetail.Id, WoundDetail.WoundNumber) |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 26 (one per batch, shared schema with minor per-batch variation) |
| Number of Columns | 37–40 depending on batch (36 fields common to all + up to 4 batch-dependent fields) |
| Number of Rows | 2,889 (excluding header rows), ranging from 10 to 206 per batch |
| Number of Observations | 2,889 |
| Total Records | 2,889 |
| Data Stucture | Tabular |
| Data Orientation | Row-oriented |
| Partition Strategy | Batch-level files (per annotation export round) |

<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | NA |
| **Platform** | Github |
| **Storage Location** | https://github.com/AITI-Solutions/Wound-Project/tree/main/TTSH_image/overlay |
| **Storage Format** | CSV |
| **Region** | NA |
| **Database ** | NA |
| **Schema** | NA |
| **Table Name** |  |
| **Environment** | |
| **Compression** | NA |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| batch_01.csv | .csv | 67 records |
| batch_02.csv | .csv | 75 records |
| batch_03.csv | .csv | 45 records |
| batch_04.csv | .csv | 75 records — first batch with MachineName/PriorMinorAmputation/WoundBedUnfilled/Unfilled |
| batch_05.csv | .csv | 206 records (largest batch) |
| batch_06.csv | .csv | 120 records |
| batch_07.csv | .csv | 168 records |
| batch_08.csv | .csv | 144 records |
| batch_09.csv | .csv | 10 records (smallest batch) |
| batch_10.csv | .csv | 172 records |
| batch_11.csv | .csv | 60 records |
| batch_12.csv | .csv | 159 records |
| batch_13.csv | .csv | 164 records |
| batch_14.csv | .csv | 141 records |
| batch_15.csv | .csv | 137 records |
| batch_16.csv | .csv | 121 records |
| batch_17.csv | .csv | 123 records |
| batch_18.csv | .csv | 80 records |
| batch_19.csv | .csv | 143 records |
| batch_20.csv | .csv | 94 records |
| batch_21.csv | .csv | 122 records |
| batch_22.csv | .csv | 25 records |
| batch_23.csv | .csv | 123 records — last batch with the 4 extra QA columns |
| batch_24.csv | .csv | 46 records — only batch missing `hasRuler`; unnamed columns literally named `Unnamed: 25`/`Unnamed: 26` |
| batch_25.csv | .csv | 108 records |
| batch_26.csv | .csv | 161 records |
|database| logs (txt.) & sqlite|
|deprecated|

<br><br>

## Documentation


<br><br>


<br><br>

## Related Links

