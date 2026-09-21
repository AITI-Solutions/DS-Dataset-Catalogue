### Dataset Overview

# Pre-release

### Physiological and Glucose Monitoring

### Data Description

This dataset consists of physiological telemetry and continuous blood glucose measurements for 7 participants, each stored as a separate file named by initials (`ML`, `NP`, `RK`, `RS`, `SM`, `SS`, `TW`). It sits alongside `BerlinStudy` and `Dexcom` as another glucose ground-truth collection in the MyMonX (MMX) data — labeled "pre-release" as it predates those two.

Feature groups:
- **Cardiovascular metrics**: Systolic/Diastolic Blood Pressure, Heart Rate
- **Respiratory and blood metrics**: Respiratory Rate, Blood Oxygen Saturation
- **Activity tracking**: Step count, Calories Burnt
- **Other physiological data**: Skin/Body Temperature, Sleep frequency (Deep/Light)
- **Target variable**: Blood Glucose (mmol/L)

Two schemas are present: 4 files (`ML`, `NP`, `RS`, `SM`) have a 12-field layout, while 3 files (`RK`, `SS`, `TW`) have a 14-field layout that adds `created_at` (export timestamp) and `train_id` (a shared batch identifier — all three carry the same value, suggesting they were exported together, separately from the other four). Column order also varies between files within the same schema. See `data_dictionary.md` for the full per-file breakdown.

This dataset is designed for glucose modeling, physical activity studies, and personal health/telemetry analysis.

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | MMX (MyMonX) / Health / Telemetry |
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
| Total Files | 7 files |
| Formats | CSV |
| extension | .csv |
| Storage Size | ~1.08 MB (1,134,629 bytes) |
| Primary Key(s) | Timestamp (not unique — dense per-participant time series) |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 1 (partitioned into 7 participant files) |
| Number of Columns | 12 (4 files) or 14 (3 files) |
| Number of Rows | 14,021 (excluding header rows) |
| Number of Observations | 14,021 |
| Total Records | 14,021 |
| Data Stucture | Tabular |
| Data Orientation | Row-oriented |
| Partition Strategy | Participant-level files |

<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | NA |
| **Platform** | Github |
| **Storage Location** | https://github.com/AITI-Solutions/MX-Data-Science/tree/main/Data/Glucose/Pre-release |
| **Storage Format** | CSV |
| **Region** | NA |
| **Database ** | NA |
| **Schema** | NA |
| **Table Name** | Pre-release |
| **Environment** | |
| **Compression** | NA |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| ML.csv | .csv | Participant ML's physical and glucose telemetry (868 records, 2022-12-06 → 2022-12-16) |
| NP.csv | .csv | Participant NP's physical and glucose telemetry (2,827 records, 2022-12-05 → 2022-12-15) |
| RK.csv | .csv | Participant RK's physical and glucose telemetry (1,627 records, 2023-03-08 → 2023-03-17); 14-field schema |
| RS.csv | .csv | Participant RS's physical and glucose telemetry (2,851 records, 2022-12-05 → 2022-12-15) |
| SM.csv | .csv | Participant SM's physical and glucose telemetry (2,570 records, 2022-12-06 → 2022-12-15) |
| SS.csv | .csv | Participant SS's physical and glucose telemetry (613 records, 2023-01-20 → 2023-01-23); 14-field schema; contains a likely sensor-error temperature outlier (42.7°C) |
| TW.csv | .csv | Participant TW's physical and glucose telemetry (2,665 records, 2023-02-17 → 2023-02-27); 14-field schema |

<br><br>

## Documentation


<br><br>

## Related Links

