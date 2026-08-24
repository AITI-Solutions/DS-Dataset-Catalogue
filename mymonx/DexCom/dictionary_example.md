# Data Dictionary

# DexCom

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| rtime_tz | Datetime | Timestamp of the reading, local timezone | 2023-01-20 11:40:00 | `YYYY-MM-DD HH:MM:SS`; 83 distinct timestamps |
| step | Decimal | Step count for the interval | 253.0 | 8.0–3101.0 |
| cakl | Decimal | Calories burned (kcal) for the interval | 10.0 | 0.0–125.0 |
| des | Decimal | Distance covered for the interval (metres, assumed) | 172.0 | 5.0–2053.0 |
| time_passed | Decimal | Coded elapsed-time/activity-interval indicator | 1.0 | 0.0, 1.0, 2.0 |
| bloodoxygen | Decimal | Blood oxygen saturation, SpO2 (%) | 98.0 | 91.0–98.0; 1 null |
| sbp | Decimal | Systolic blood pressure (mmHg) | 128.0 | 123.0–139.0; 1 null |
| dbp | Decimal | Diastolic blood pressure (mmHg) | 86.0 | 83.0–88.0; 1 null |
| heart_times | Decimal | Heart rate (beats per minute) | 79.0 | 52.0–109.0; 1 null |
| respiratoryrate | Decimal | Respiratory rate (breaths per minute) | 16.0 | 10.0–22.0; 1 null |
| temperature | Decimal | Body temperature (°C) | 36.2 | 35.1–37.0; 1 null |
| sleepStage | Decimal | Coded sleep stage at time of reading | 0.0 | 0.0, 2.0 (0 = Awake, 2 = Deep sleep — coding assumed, not confirmed) |
| Age | Integer | Subject's age in years | 59 | Constant: 59 (single-subject dataset) |
| Sex | Integer | Subject's sex, coded | 0 | Constant: 0 (single-subject dataset; coding scheme e.g. 0=Female — N/A, not confirmed) |
| Height | Integer | Subject's height (cm) | 160 | Constant: 160 |
| Weight | Decimal | Subject's weight (kg) | 65.0 | Constant: 65.0 |
| Skin | Integer | Skin type/tone classification code | 2 | Constant: 2 (coding scheme N/A, not confirmed) |
| BMI | Decimal | Subject's Body Mass Index, calculated | 25.390624999999996 | Constant: 25.39 (derived from Height/Weight) |
| Glucose | Decimal | Blood glucose reading (mmol/L, assumed) | 4.5 | 3.3–9.5 |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.

