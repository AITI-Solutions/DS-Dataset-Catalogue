### Dataset Overview

# Dexcom

### Physiological and Glucose Monitoring

### Data Description

This dataset consists of multi-sensor physiological telemetry and continuous blood glucose measurements for 8 individuals, each stored as a separate file named after the participant. It sits alongside the BerlinStudy dataset as part of the older ("GroundTruth_old") glucose ground-truth collection, with glucose reference values sourced from Dexcom continuous glucose monitors.

The data captures wearable health telemetry at nominal 10-minute intervals, grouped into 3-row blocks (`time_passed` = 0/1/2). Feature groups:
- **Cardiovascular metrics**: Systolic/Diastolic Blood Pressure (`sbp`, `dbp`), Heart Rate (`heart_times`)
- **Respiratory and blood metrics**: Respiratory Rate (`respiratoryrate`), Blood Oxygen Saturation (`bloodoxygen`)
- **Activity tracking**: Steps (`step`), Calories Burned (`cakl`), Distance (`des`)
- **Other physiological data**: Skin/Body Temperature (`temperature`), Sleep Stage (`sleepStage`)
- **Participant demographics & phenotypes**: Age, Sex, Height, Weight, Fitzpatrick Skin Type (`Skin`), BMI
- **Target variable**: Blood Glucose (`Glucose`) in mmol/L

All 8 files carry the same 19 fields, but **the column order differs between files** and 3 of the 8 files contain only a header row (no data). Data completeness varies widely: `MiumiuLi.csv` has almost all wearable-sensor columns empty (only `sleepStage` and `Glucose` are dense), while `TillmanWeyde.csv` and `TracyMcDowell.csv` are largely complete.

This dataset is designed for glucose modeling, physical activity studies, and personal health/telemetry analysis.

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | MMX (MyMonX) / Health / Telemetry |
| **Dataset Owner** | AITIS |
| **Status** | Active |
| **Version** | v1.0 |
| **Classification** | |
| **Licences** | Proprietary / Commercial use only |
| **Created** |  |
| **Last Updated** |  |
| **Refresh Frequency** | Static |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 8 files (5 with data, 3 header-only) |
| Formats | CSV |
| extension | .csv |
| Storage Size | ~143 KB (146,029 bytes) |
| Primary Key(s) | rtime_tz (not unique — duplicate timestamps occur at sleep-stage transitions) |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 1 (partitioned into 8 participant files) |
| Number of Columns | 19 |
| Number of Rows | 1380 (data rows, excluding headers) |
| Number of Observations | 1380 |
| Total Records | 1380 |
| Data Stucture | Tabular |
| Data Orientation | Row-oriented |
| Partition Strategy | Participant-level files |

<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | NA |
| **Platform** | Github |
| **Storage Location** | https://github.com/AITI-Solutions/MX-Data-Science/tree/main/Data/Glucose/GroundTruth_old/Dexcom |
| **Storage Format** | CSV |
| **Region** | NA |
| **Database ** | NA |
| **Schema** | NA |
| **Table Name** | Dexcom |
| **Environment** | Development |
| **Compression** | NA |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| MiumiuLi.csv | .csv | Participant MiumiuLi — 366 records, 2022-12-07 → 2022-12-14. Only `sleepStage` and `Glucose` densely populated; other sensors nearly all missing. |
| SimonMcDowell.csv | .csv | Participant SimonMcDowell — 3 records, 2022-12-06. Minimal sample; vitals absent. |
| SylviaSmit.csv | .csv | Participant SylviaSmit — 83 records, 2023-01-20 → 2023-01-22. Mostly complete. |
| TillmanWeyde.csv | .csv | Participant TillmanWeyde — 468 records, 2023-02-17 → 2023-02-27. Largely complete (17–42 missing per vital column). |
| TracyMcDowell.csv | .csv | Participant TracyMcDowell — 460 records, 2023-04-24 → 2023-04-30. Largely complete (~36 missing per vital column). |
| GuyThanaponbaiboon.csv | .csv | Header only, 0 data rows. |
| RobertaSmith.csv | .csv | Header only, 0 data rows. |
| ZinaZukova.csv | .csv | Header only, 0 data rows. |

<br><br>

## Documentation


<br><br>

## Related Links
