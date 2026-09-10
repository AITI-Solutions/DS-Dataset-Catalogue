# Data Dictionary

# Dexcom

The Dexcom dataset contains 8 participant files. Each file shares the same 19 fields but **the column order differs between files**, and the value ranges are participant-specific, so a separate table is provided for each file.

Three files (`GuyThanaponbaiboon.csv`, `RobertaSmith.csv`, `ZinaZukova.csv`) contain only a header row and no data; their field list is documented once at the end.

---

## MiumiuLi.csv

366 data rows · 2022-12-07 00:10:00 → 2022-12-14 08:20:00 · 10-minute cadence (with occasional duplicate timestamps).

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| rtime_tz | String | Datetime stamp of the record (local timezone). | 2022-12-07 00:10:00 | YYYY-MM-DD HH:MM:SS |
| sleepStage | Decimal | Sleep stage category. | 2.0 | 1.0 (Light Sleep), 2.0 (Deep Sleep / REM); no Awake rows present |
| step | Decimal | Interval step count. | 46.0 | Non-negative decimal, observed 19.0–100.0; 361 of 366 missing |
| cakl | Decimal | Active energy / calories burned (kcal). | 1.0 | Non-negative decimal, observed 0.0–3.0; 361 of 366 missing |
| des | Decimal | Physical movement distance (m). | 31.0 | Non-negative decimal, observed 12.0–66.0; 361 of 366 missing |
| time_passed | Decimal | Sub-interval block sequence index. | 1.0 | 0.0, 1.0, 2.0; 361 of 366 missing |
| bloodoxygen | Decimal | Blood oxygen saturation (SpO2, %). | 98.0 | Observed 97.0–98.0; 364 of 366 missing |
| heart_times | Decimal | Heart rate (BPM). | 71.0 | Observed 65.0–71.0; 364 of 366 missing |
| sbp | Decimal | Systolic Blood Pressure (mmHg). | 97.0 | Observed 97.0; 364 of 366 missing |
| dbp | Decimal | Diastolic Blood Pressure (mmHg). | 67.0 | Observed 67.0; 364 of 366 missing |
| temperature | Decimal | Skin / body temperature (°C). | 36.9 | Observed 35.5–36.9; 364 of 366 missing |
| respiratoryrate | Decimal | Respiratory rate (breaths per minute). | 14.0 | Observed 13.0–14.0; 364 of 366 missing |
| Age | Integer | Biological age of the participant (years). | 35 | Constant 35 |
| Sex | Integer | Biological sex of the participant. | -1 | -1 (not recorded); 0 (Female), 1 (Male) elsewhere |
| Height | Integer | Height (cm). | 170 | Constant 170 (default / not measured) |
| Weight | Decimal | Weight (kg). | 70 | Constant 70 (default / not measured) |
| Skin | Integer | Fitzpatrick skin scale type. | -1 | -1 (not recorded); 0–6 otherwise |
| BMI | Decimal | Calculated Body Mass Index. | 24.221453 | Constant 24.221453 (derived from default 170 cm / 70 kg) |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 8.10 | Positive decimal, range 2.50–10.38 |

---

## SimonMcDowell.csv

3 data rows · 2022-12-06 08:00:00 → 2022-12-06 08:20:00.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| rtime_tz | String | Datetime stamp of the record (local timezone). | 2022-12-06 08:00:00 | YYYY-MM-DD HH:MM:SS |
| step | Decimal | Interval step count. | 312.0 | Constant 312.0 |
| cakl | Decimal | Active energy / calories burned (kcal). | 12.0 | Constant 12.0 |
| des | Decimal | Physical movement distance (m). | 269.0 | Constant 269.0 |
| time_passed | Decimal | Sub-interval block sequence index. | 1.0 | 0.0, 1.0, 2.0 |
| temperature | Decimal | Skin / body temperature (°C). | 36.8 | Observed 36.8; 2 of 3 missing |
| bloodoxygen | Decimal | Blood oxygen saturation (SpO2, %). | | All 3 missing |
| sbp | Decimal | Systolic Blood Pressure (mmHg). | | All 3 missing |
| dbp | Decimal | Diastolic Blood Pressure (mmHg). | | All 3 missing |
| heart_times | Decimal | Heart rate (BPM). | | All 3 missing |
| respiratoryrate | Decimal | Respiratory rate (breaths per minute). | | All 3 missing |
| sleepStage | Decimal | Sleep stage category. | 0.0 | Constant 0.0 (Awake) |
| Age | Integer | Biological age of the participant (years). | 56 | Constant 56 |
| Sex | Integer | Biological sex of the participant. | 1 | 1 (Male) |
| Height | Integer | Height (cm). | 170 | Constant 170 (default / not measured) |
| Weight | Decimal | Weight (kg). | 70 | Constant 70 (default / not measured) |
| Skin | Integer | Fitzpatrick skin scale type. | -1 | -1 (not recorded) |
| BMI | Decimal | Calculated Body Mass Index. | 24.221453 | Constant 24.221453 (derived from default 170 cm / 70 kg) |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 6.8 | Positive decimal, range 6.4–6.8 |

---

## SylviaSmit.csv

83 data rows · 2023-01-20 11:40:00 → 2023-01-22 17:50:00.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| rtime_tz | String | Datetime stamp of the record (local timezone). | 2023-01-20 11:40:00 | YYYY-MM-DD HH:MM:SS |
| step | Decimal | Interval step count. | 253.0 | Non-negative decimal, range 8.0–3101.0 |
| cakl | Decimal | Active energy / calories burned (kcal). | 10.0 | Non-negative decimal, range 0.0–125.0 |
| des | Decimal | Physical movement distance (m). | 172.0 | Non-negative decimal, range 5.0–2053.0 |
| time_passed | Decimal | Sub-interval block sequence index. | 1.0 | 0.0, 1.0, 2.0 |
| bloodoxygen | Decimal | Blood oxygen saturation (SpO2, %). | 98.0 | Range 91.0–98.0; 1 of 83 missing |
| sbp | Decimal | Systolic Blood Pressure (mmHg). | 128.0 | Range 123.0–139.0; 1 of 83 missing |
| dbp | Decimal | Diastolic Blood Pressure (mmHg). | 86.0 | Range 83.0–88.0; 1 of 83 missing |
| heart_times | Decimal | Heart rate (BPM). | 79.0 | Range 52.0–109.0; 1 of 83 missing |
| respiratoryrate | Decimal | Respiratory rate (breaths per minute). | 16.0 | Range 10.0–22.0; 1 of 83 missing |
| temperature | Decimal | Skin / body temperature (°C). | 36.2 | Range 35.1–37.0; 1 of 83 missing |
| sleepStage | Decimal | Sleep stage category. | 0.0 | 0.0 (Awake), 2.0 (Deep Sleep / REM) |
| Age | Integer | Biological age of the participant (years). | 59 | Constant 59 |
| Sex | Integer | Biological sex of the participant. | 0 | 0 (Female) |
| Height | Integer | Height (cm). | 160 | Constant 160 |
| Weight | Decimal | Weight (kg). | 65.0 | Constant 65.0 |
| Skin | Integer | Fitzpatrick skin scale type. | 2 | Constant 2 |
| BMI | Decimal | Calculated Body Mass Index. | 25.390625 | Constant 25.390625 |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 4.5 | Positive decimal, range 3.3–9.5 |

---

## TillmanWeyde.csv

468 data rows · 2023-02-17 11:30:00 → 2023-02-27 00:50:00.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| rtime_tz | String | Datetime stamp of the record (local timezone). | 2023-02-17 11:30:00 | YYYY-MM-DD HH:MM:SS |
| step | Decimal | Interval step count. | 2806.0 | Non-negative decimal, range 7.0–4957.0 |
| cakl | Decimal | Active energy / calories burned (kcal). | 116.0 | Non-negative decimal, range 0.0–241.0 |
| des | Decimal | Physical movement distance (m). | 2113.0 | Non-negative decimal, range 4.0–5245.0 |
| time_passed | Decimal | Sub-interval block sequence index. | 0.0 | 0.0, 1.0, 2.0 |
| heart_times | Decimal | Heart rate (BPM). | 87.0 | Range 53.0–110.0; 17 of 468 missing |
| sbp | Decimal | Systolic Blood Pressure (mmHg). | 116.0 | Range 101.0–123.0; 17 of 468 missing |
| dbp | Decimal | Diastolic Blood Pressure (mmHg). | 75.0 | Range 67.0–81.0; 17 of 468 missing |
| respiratoryrate | Decimal | Respiratory rate (breaths per minute). | 18.0 | Range 11.0–22.0; 26 of 468 missing |
| bloodoxygen | Decimal | Blood oxygen saturation (SpO2, %). | 98.0 | Range 92.0–98.0; 26 of 468 missing |
| temperature | Decimal | Skin / body temperature (°C). | 36.2 | Range 33.7–37.2; 42 of 468 missing |
| sleepStage | Decimal | Sleep stage category. | 0.0 | 0.0 (Awake), 1.0 (Light Sleep), 2.0 (Deep Sleep / REM) |
| Age | Integer | Biological age of the participant (years). | 33 | Constant 33 |
| Sex | Integer | Biological sex of the participant. | 1 | 1 (Male) |
| Height | Integer | Height (cm). | 170 | Constant 170 (default / not measured) |
| Weight | Decimal | Weight (kg). | 70 | Constant 70 (default / not measured) |
| Skin | Integer | Fitzpatrick skin scale type. | -1 | -1 (not recorded) |
| BMI | Decimal | Calculated Body Mass Index. | 24.221453 | Constant 24.221453 (derived from default 170 cm / 70 kg) |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 5.7 | Positive decimal, range 3.8–12.4 |

---

## TracyMcDowell.csv

460 data rows · 2023-04-24 10:00:00 → 2023-04-30 20:20:00.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| rtime_tz | String | Datetime stamp of the record (local timezone). | 2023-04-24 10:00:00 | YYYY-MM-DD HH:MM:SS |
| step | Decimal | Interval step count. | 38.0 | Non-negative decimal, range 15.0–1487.0 |
| cakl | Decimal | Active energy / calories burned (kcal). | 1.0 | Non-negative decimal, range 0.0–67.0 |
| des | Decimal | Physical movement distance (m). | 25.0 | Non-negative decimal, range 11.0–985.0 |
| time_passed | Decimal | Sub-interval block sequence index. | 0.0 | 0.0, 1.0, 2.0 |
| bloodoxygen | Decimal | Blood oxygen saturation (SpO2, %). | 98.0 | Range 94.0–98.0; 36 of 460 missing |
| respiratoryrate | Decimal | Respiratory rate (breaths per minute). | 18.0 | Range 11.0–23.0; 36 of 460 missing |
| temperature | Decimal | Skin / body temperature (°C). | 36.5 | Range 0.15–37.9 (0.15 = disconnected sensor / default); 36 of 460 missing |
| heart_times | Decimal | Heart rate (BPM). | 90.0 | Range 56.0–114.0; 36 of 460 missing |
| sbp | Decimal | Systolic Blood Pressure (mmHg). | 131.0 | Range 124.0–137.0; 36 of 460 missing |
| dbp | Decimal | Diastolic Blood Pressure (mmHg). | 88.0 | Range 83.0–92.0; 36 of 460 missing |
| sleepStage | Decimal | Sleep stage category. | 0.0 | 0.0 (Awake), 2.0 (Deep Sleep / REM) |
| Age | Integer | Biological age of the participant (years). | 56 | Constant 56 |
| Sex | Integer | Biological sex of the participant. | 0 | 0 (Female) |
| Height | Integer | Height (cm). | 170 | Constant 170 (default / not measured) |
| Weight | Decimal | Weight (kg). | 70 | Constant 70 (default / not measured) |
| Skin | Integer | Fitzpatrick skin scale type. | -1 | -1 (not recorded) |
| BMI | Decimal | Calculated Body Mass Index. | 24.221453 | Constant 24.221453 (derived from default 170 cm / 70 kg) |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 5.1 | Positive decimal, range 4.0–10.3 |

---

## Empty files — GuyThanaponbaiboon.csv, RobertaSmith.csv, ZinaZukova.csv

Header only, 0 data rows. All three share the same column order:

`rtime_tz, step, cakl, des, time_passed, bloodoxygen, sbp, dbp, heart_times, respiratoryrate, sleepStage, temperature, Age, Sex, Height, Weight, Skin, BMI, Glucose`

Field meanings are identical to the tables above. No values are available.

---

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.

## Notes

- **Sentinel values**: `Sex = -1` and `Skin = -1` indicate the attribute was not recorded (differs from the BerlinStudy encoding, where `Sex` is strictly 0/1). Where `Height = 170`, `Weight = 70` and `BMI = 24.221453` recur across unrelated participants, these are placeholder defaults rather than measured values.
- **Cadence**: Records are nominally at 10-minute intervals, grouped into 3-row blocks by `time_passed` (0.0, 1.0, 2.0). Duplicate timestamps occur (e.g. in `MiumiuLi.csv`) at sleep-stage transitions.
- **Column order is not consistent** across files — always read by header name, not position.
- **Glucose** is the target variable; it is fully populated in every non-empty file.
