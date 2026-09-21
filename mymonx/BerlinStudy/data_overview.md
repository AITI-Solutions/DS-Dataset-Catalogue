### Dataset Overview

# BerlinStudy

### Physiological and Glucose Monitoring

### Data Description

This dataset consists of physiological metrics and continuous blood glucose measurements for participants in the Berlin Study. It is a multivariate tabular dataset containing 8 individual files, each corresponding to a unique participant (identified by initials such as BG, BJ, JK, KW, MR, PF, RV, and SLP). 

The dataset captures multi-sensor health telemetry recorded in 10-minute intervals. The key telemetry features include:
- **Cardiovascular metrics**: Systolic/Diastolic Blood Pressure (`sbp`, `dbp`), Heart Rate (`heart_times`)
- **Respiratory and Blood metrics**: Respiratory Rate (`respiratoryrate`), Blood Oxygen Saturation (`bloodoxygen`)
- **Activity tracking**: Steps (`step`), Calories Burned (`cakl`), Distance (`des`)
- **Other physiological data**: Skin/Body Temperature (`temperature`), Sleep Stage (`sleepStage`)
- **Participant Demographics & Phenotypes**: Age, Sex, Height, Weight, Fitzpatrick Skin Type (`Skin`), and Body Mass Index (`BMI`)
- **Target Variable**: Blood Glucose (`Glucose`) in mmol/L

This dataset is designed for glucose modeling, physical activity studies, and personal health/telemetry analysis.

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | MMX (MyMonX) / Health / Telemetry |
| **Dataset Owner** | AITIS |
| **Status** | Active |
| **Version** | v1.0 |
| **Classification** | Confidential / Restricted |
| **Licences** | Proprietary / Commercial use only |
| **Created** | 09/03/2026 |
| **Last Updated** | 09/03/2026 |
| **Refresh Frequency** | Static |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 8 files |
| Formats | CSV |
| extension | .csv |
| Storage Size | ~171 KB (171,380 bytes) |
| Primary Key(s) | rtime_tz |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 1 |
| Number of Columns | 19 |
| Number of Rows | 1589 (excluding header rows) |
| Number of Observations | 1589 |
| Total Records | 1589 |
| Data Stucture | Tabular |
| Data Orientation | Row-oriented |
| Partition Strategy | Participant-level files |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | NA |
| **Platform** | Github |
| **Storage Location** | https://github.com/AITI-Solutions/MX-Data-Science/tree/main/Data/Glucose/GroundTruth_old/BerlinStudy |
| **Storage Format** | CSV |
| **Region** | NA |
| **Database ** | NA |
| **Schema** | NA |
| **Table Name** | BerlinStudy |
| **Environment** | Development |
| **Compression** | NA |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| BG.csv | .csv | Participant BG's physical and glucose telemetry (234 records) |
| BJ.csv | .csv | Participant BJ's physical and glucose telemetry (145 records) |
| JK.csv | .csv | Participant JK's physical and glucose telemetry (221 records) |
| KW.csv | .csv | Participant KW's physical and glucose telemetry (230 records) |
| MR.csv | .csv | Participant MR's physical and glucose telemetry (312 records) |
| PF.csv | .csv | Participant PF's physical and glucose telemetry (134 records) |
| RV.csv | .csv | Participant RV's physical and glucose telemetry (241 records) |
| SLP.csv | .csv | Participant SLP's physical and glucose telemetry (72 records) |

<br><br>

## Documentation
- Data Dictionary

<br><br>

## Related Links
- Source Repository: `mydata/Glucose:GroundTruth_old:BerlinStudy`
