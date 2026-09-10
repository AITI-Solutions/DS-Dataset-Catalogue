# Data Dictionary

# BerlinStudy

This dictionary applies to all participant files (`BG.csv`, `BJ.csv`, `JK.csv`, `KW.csv`, `MR.csv`, `PF.csv`, `RV.csv`, `SLP.csv`) within the BerlinStudy dataset.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| rtime_tz | String | Datetime stamp of the record (local timezone). | 2023-11-18 08:00:00 | YYYY-MM-DD HH:MM:SS |
| bloodoxygen | Decimal | Blood oxygen saturation levels (SpO2) in percentage. | 98.0 | 0.0 to 100.0 (0.0 represents sensor measurement failure or drop) |
| respiratoryrate | Decimal | Respiratory rate in breaths per minute. | 14.0 | 0.0 to 24.0 (0.0 represents sensor measurement failure or drop) |
| sbp | Decimal | Systolic Blood Pressure in mmHg. | 128.0 | Positive number, typical range 89.0 to 139.0 |
| dbp | Decimal | Diastolic Blood Pressure in mmHg. | 86.0 | Positive number, typical range 64.0 to 95.0 |
| heart_times | Decimal | Heart rate in beats per minute (BPM). | 72.0 | Positive number, typical range 40.0 to 117.0 |
| temperature | Decimal | Skin or body temperature in Celsius. | 36.6 | Decimal, range 0.15 to 37.9 (very low values like 0.15 represent disconnected sensor/default values) |
| step | Decimal | Cumulative or interval-specific step count. | 63.0 | Non-negative decimal/integer, range 8.0 to 3162.0 (contains missing values) |
| cakl | Decimal | Active energy/calories burned in kilocalories (kcal). | 3.0 | Non-negative decimal, range 0.0 to 176.0 (contains missing values) |
| des | Decimal | Physical movement distance (likely in meters or decimeters). | 45.0 | Non-negative decimal, range 5.0 to 2363.0 (contains missing values) |
| time_passed | Decimal | Sub-interval block sequence index or elapsed blocks within a session. | 1.0 | 0.0, 1.0, 2.0 (contains missing values) |
| sleepStage | Decimal | Sleep stage category. | 0.0 | 0.0 (Awake), 1.0 (Light Sleep), 2.0 (Deep Sleep / REM) |
| Age | Integer | Biological age of the participant in years. | 58 | Positive integer, range 19 to 64 |
| Sex | Integer | Biological sex of the participant. | 1 | 0 (Female), 1 (Male) |
| Height | Integer | Height of the participant in centimeters. | 175 | Positive integer, range 158 to 189 |
| Weight | Decimal | Weight of the participant in kilograms. | 94.0 | Positive decimal, range 62.0 to 112.0 |
| Skin | Integer | Fitzpatrick skin scale type. | 2 | 0 to 6 (Fitzpatrick Skin Classification, observed values: 0, 2) |
| BMI | Decimal | Calculated Body Mass Index (BMI). | 30.69 | Positive decimal, range 22.46 to 32.01 |
| Glucose | Decimal | Continuous blood glucose levels in mmol/L (the target variable). | 6.2 | Positive decimal, range 2.3 to 23.9 |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.
