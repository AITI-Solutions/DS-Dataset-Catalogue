### Dataset Overview

# ISIC Overview Images

### Data Description

This dataset consists of metadata for skin lesion images sourced from the International Skin Imaging Collaboration (ISIC) Archive. It contains diagnostic and clinical information for five specific types of skin conditions:
- **BCC**: Basal Cell Carcinoma
- **MEL**: Melanoma
- **NEV**: Nevus (moles)
- **SCC**: Squamous Cell Carcinoma
- **SKE**: Seborrheic Keratosis

The dataset includes patient demographics (age, sex), anatomical site information, diagnostic details, and image metadata. It is primarily used for skin cancer research and training computer vision models for automated diagnosis.

<br><br>

## Key Information

| Attribute | Value |
|-----------|-------|
| **Domain** | Health / Dermatology |
| **Dataset Owner** | ISIC Archive / AITIS |
| **Status** | Active |
| **Version** | NA |
| **Classification** | Public |
| **Licences** | CC-0 / CC-BY |
| **Created** | 08/10/2026 |
| **Last Updated** | 08/10/2026 |
| **Refresh Frequency** | Static |

<br><br>
## MetaData

| Metric | Value |
|--------|-------|
| Total Files | 5 files |
| Formats | CSV |
| extension | .csv |
| Storage Size | ~80 KB |
| Primary Key(s) | isic_id |
<br><br>

## Data Statistics

| Metric | Value |
|--------|-------|
| Number of Tables | 5 |
| Number of Columns | 20 unique |
| Number of Rows | 383 |
| Number of Observations | 383 |
| Total Records | 383 |
| Data Stucture | Tabular |
| Data Orientation | Row-oriented |
| Partition Strategy | Diagnoses (BCC, MEL, NEV, SCC, SKE) |


<br><br>

# Storage & Location

| Attribute | Value |
|-----------|-------|
| **Cloud Provider** | NA |
| **Platform** | Github |
| **Storage Location** | `mydata/ISIC_overview_images/` -> github link|
| **Storage Format** | CSV |
| **Region** | NA |
| **Database ** | NA |
| **Schema** | NA |
| **Table Name** | NA |
| **Environment** | NA |
| **Compression** | NA |
---

<br><br>

## Partitions

| Partition | Format | Description |
|-----------|--------|-------------|
| BCC | .csv | Basal Cell Carcinoma metadata (126 rows) |
| MEL | .csv | Melanoma metadata (104 rows) |
| NEV | .csv | Nevus metadata (74 rows) |
| SCC | .csv | Squamous Cell Carcinoma metadata (57 rows) |
| SKE | .csv | Seborrheic Keratosis metadata (22 rows) |

<br><br>

## Documentation
- Data Dictionary
- ISIC Archive API Documentation

<br><br>

## External Links
- [ISIC Archive](https://www.isic-archive.com/)
