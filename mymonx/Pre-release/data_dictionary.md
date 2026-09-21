# Data Dictionary

# Pre-release

7 participant files (`ML.csv`, `NP.csv`, `RK.csv`, `RS.csv`, `SM.csv`, `SS.csv`, `TW.csv`). They fall into two distinct schemas — a 12-column group (`ML`, `NP`, `RS`, `SM`) and a 14-column group (`RK`, `SS`, `TW`) that adds `created_at` and `train_id` — and column order differs even within a group, so each file gets its own table below, in that file's actual column order.

---

## ML.csv

868 data rows · 2022-12-06 21:40:00 → 2022-12-16 09:00:00.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| Diastolic Blood Pressure | Decimal | Diastolic Blood Pressure in mmHg. | 69.0 | Range 64.0–75.0 |
| Systolic Blood Pressure | Decimal | Systolic Blood Pressure in mmHg. | 97.0 | Range 91.0–111.0 |
| Respiratory Rate | Decimal | Respiratory rate in breaths per minute. | 15.0 | Range 11.0–22.0 |
| Timestamp | String | Datetime stamp of the record. | 2022-12-06 21:40:00 | YYYY-MM-DD HH:MM:SS |
| Freq Deep Sleep | Decimal | Deep-sleep frequency/count for the interval. | 0.0 | 0.0, 11.0, 13.0 |
| Freq Light Sleep | Decimal | Light-sleep frequency/count for the interval. | 0.0 | 0.0, 3.0, 5.0 |
| Blood Oxygen | Decimal | Blood oxygen saturation (SpO2) in percentage. | 98.0 | 93.0, 96.0, 97.0, 98.0 |
| Heart Rate | Decimal | Heart rate in beats per minute (BPM). | 76.0 | Range 55.0–108.0 |
| Temperature | Decimal | Skin/body temperature in Celsius. | 36.7 | Range 33.3–37.3 |
| Calories Burnt | Decimal | Active energy/calories burned (kcal). | 0.0 | Range 0.0–54.0 |
| Step | Decimal | Interval step count. | 0.0 | Range 0.0–1545.0 |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 6.57 | Range 4.3–9.2 |

---

## NP.csv

2,827 data rows · 2022-12-05 17:54:31 → 2022-12-15 15:04:55.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| Diastolic Blood Pressure | Integer | Diastolic Blood Pressure in mmHg. | 65 | Range 62–81 |
| Systolic Blood Pressure | Integer | Systolic Blood Pressure in mmHg. | 92 | Range 87–124 |
| Respiratory Rate | Integer | Respiratory rate in breaths per minute. | 14 | Range 10–28 |
| Freq Deep Sleep | Integer | Deep-sleep frequency/count for the interval. | 16 | 1, 6, 8, 10, 12, 15, 16 |
| Freq Light Sleep | Integer | Light-sleep frequency/count for the interval. | 2 | 1–8 |
| Blood Oxygen | Integer | Blood oxygen saturation (SpO2) in percentage. | 98 | 91–98 |
| Heart Rate | Integer | Heart rate in beats per minute (BPM). | 69 | Range 52–136 |
| Temperature | Decimal | Skin/body temperature in Celsius. | 36.7 | Range 33.0–37.2 |
| Calories Burnt | Decimal | Active energy/calories burned (kcal). | 1.0 | Range 1.0–24.0 |
| Step | Decimal | Interval step count. | 27.0 | Range 27.0–617.0 |
| Timestamp | String | Datetime stamp of the record. | 2022-12-05 17:54:31 | YYYY-MM-DD HH:MM:SS |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 5.4 | Range 4.0–9.8 |

---

## RK.csv

1,627 data rows · 2023-03-08 09:11:51 → 2023-03-17 23:07:07.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| Timestamp | String | Datetime stamp of the physiological record. | 2023-03-08 09:11:51 | YYYY-MM-DD HH:MM:SS |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 5.8 | Range 4.2–10.2 |
| created_at | String | Timestamp the row was written/exported into this file (constant for the whole file — an export/ingestion time, not a per-reading time). | 2023-03-23 15:30:50.971312 | Constant per file, `YYYY-MM-DD HH:MM:SS.ffffff` |
| Heart Rate | Decimal | Heart rate in beats per minute (BPM). | 85.0 | Range 54.0–125.0 |
| Systolic Blood Pressure | Decimal | Systolic Blood Pressure in mmHg. | 104.0 | Range 92.0–125.0 |
| Diastolic Blood Pressure | Decimal | Diastolic Blood Pressure in mmHg. | 71.0 | Range 64.0–82.0 |
| Blood Oxygen | Decimal | Blood oxygen saturation (SpO2) in percentage. | 98.0 | 0.0 (sensor failure/drop), 93.0–98.0 |
| Calories Burnt | Decimal | Active energy/calories burned (kcal). | 0.0 | Range 0.0–104.0 |
| Step | Decimal | Interval step count. | 0.0 | Range 0.0–2656.0 |
| Respiratory Rate | Decimal | Respiratory rate in breaths per minute. | 17.0 | Range 0.0–26.0 (0.0 = sensor failure/drop) |
| Freq Light Sleep | Decimal | Light-sleep frequency/count for the interval. | 0.0 | 0.0, 3.0, 4.0 |
| Freq Deep Sleep | Decimal | Deep-sleep frequency/count for the interval. | 0.0 | 0.0, 1.0, 7.0, 11.0 |
| Temperature | Decimal | Skin/body temperature in Celsius. | 36.2 | Range 0.15–37.5 (0.15 = disconnected sensor/default) |
| train_id | Integer | Batch/run identifier for the training-data export this file belongs to. | 20230526131553 | Constant 20230526131553 for this file |

---

## RS.csv

2,851 data rows · 2022-12-05 23:03:19 → 2022-12-15 22:23:51.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| Diastolic Blood Pressure | Decimal | Diastolic Blood Pressure in mmHg. | 70.0 | Range 65.0–75.0 |
| Systolic Blood Pressure | Decimal | Systolic Blood Pressure in mmHg. | 103.0 | Range 93.0–113.0 |
| Respiratory Rate | Decimal | Respiratory rate in breaths per minute. | 20.0 | Range 13.0–23.0 |
| Freq Deep Sleep | Integer | Deep-sleep frequency/count for the interval. | 16 | 1, 6, 8, 10, 12, 15, 16 |
| Freq Light Sleep | Integer | Light-sleep frequency/count for the interval. | 2 | 1–8 |
| Blood Oxygen | Integer | Blood oxygen saturation (SpO2) in percentage. | 97 | 95–98 |
| Heart Rate | Decimal | Heart rate in beats per minute (BPM). | 97.0 | Range 64.0–114.0 |
| Temperature | Decimal | Skin/body temperature in Celsius. | 38.6 | Range 35.4–38.6 |
| Calories Burnt | Decimal | Active energy/calories burned (kcal). | 3.0 | Range 1.0–24.0 |
| Step | Decimal | Interval step count. | 46.0 | Range 31.0–617.0 |
| Timestamp | String | Datetime stamp of the record. | 2022-12-05 23:03:19 | YYYY-MM-DD HH:MM:SS |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 5.9 | Range 2.3–9.0 |

---

## SM.csv

2,570 data rows · 2022-12-06 07:28:02 → 2022-12-15 08:43:28.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| Diastolic Blood Pressure | Integer | Diastolic Blood Pressure in mmHg. | 81 | Range 71–85 |
| Systolic Blood Pressure | Integer | Systolic Blood Pressure in mmHg. | 137 | Range 121–139 |
| Respiratory Rate | Integer | Respiratory rate in breaths per minute. | 17 | Range 9–20 |
| Freq Deep Sleep | Integer | Deep-sleep frequency/count for the interval. | 16 | 1, 6, 8, 10, 12, 15, 16 |
| Freq Light Sleep | Integer | Light-sleep frequency/count for the interval. | 4 | 1–8 |
| Blood Oxygen | Integer | Blood oxygen saturation (SpO2) in percentage. | 98 | Range 88–98 |
| Heart Rate | Integer | Heart rate in beats per minute (BPM). | 86 | Range 47–100 |
| Temperature | Decimal | Skin/body temperature in Celsius. | 36.4 | Range 35.1–37.1 |
| Calories Burnt | Decimal | Active energy/calories burned (kcal). | 17.0 | Range 1.0–24.0 |
| Step | Decimal | Interval step count. | 256.0 | Range 31.0–617.0 |
| Timestamp | String | Datetime stamp of the record. | 2022-12-06 07:28:02 | YYYY-MM-DD HH:MM:SS |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 6.3 | Range 3.3–8.4 |

---

## SS.csv

613 data rows · 2023-01-20 12:53:54 → 2023-01-23 00:28:57.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| Timestamp | String | Datetime stamp of the physiological record. | 2023-01-20 12:53:54 | YYYY-MM-DD HH:MM:SS |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 5.4 | Range 2.9–10.0 |
| created_at | String | Timestamp the row was written/exported into this file (constant for the whole file). | 2023-03-13 14:07:17.861276 | Constant per file, `YYYY-MM-DD HH:MM:SS.ffffff` |
| Heart Rate | Decimal | Heart rate in beats per minute (BPM). | 79.0 | Range 42.0–109.0 |
| Systolic Blood Pressure | Decimal | Systolic Blood Pressure in mmHg. | 128.0 | Range 123.0–139.0 |
| Diastolic Blood Pressure | Decimal | Diastolic Blood Pressure in mmHg. | 86.0 | Range 82.0–89.0 |
| Blood Oxygen | Decimal | Blood oxygen saturation (SpO2) in percentage. | 98.0 | Range 83.0–98.0 |
| Calories Burnt | Decimal | Active energy/calories burned (kcal). | 0.0 | Range 0.0–125.0 |
| Step | Decimal | Interval step count. | 0.0 | Range 0.0–3101.0 |
| Respiratory Rate | Decimal | Respiratory rate in breaths per minute. | 16.0 | Range 8.0–22.0 |
| Freq Light Sleep | Decimal | Light-sleep frequency/count for the interval. | 0.0 | 0.0–3.0 |
| Freq Deep Sleep | Decimal | Deep-sleep frequency/count for the interval. | 0.0 | 0.0, 1.0, 2.0, 3.0, 4.0, 9.0 |
| Temperature | Decimal | Skin/body temperature in Celsius. | 36.2 | Range 35.1–**42.7** (max looks like a sensor-error outlier — physiologically implausible) |
| train_id | Integer | Batch/run identifier for the training-data export this file belongs to. | 20230526131553 | Constant 20230526131553 (same value as `RK.csv` and `TW.csv`) |

---

## TW.csv

2,665 data rows · 2023-02-17 12:24:41 → 2023-02-27 09:15:24.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| Timestamp | String | Datetime stamp of the physiological record. | 2023-02-17 12:24:41 | YYYY-MM-DD HH:MM:SS |
| Glucose | Decimal | Continuous blood glucose (mmol/L) — target variable. | 6.8 | Range 2.6–12.4 |
| created_at | String | Timestamp the row was written/exported into this file (constant for the whole file). | 2023-03-13 13:58:48.222918 | Constant per file, `YYYY-MM-DD HH:MM:SS.ffffff` |
| Heart Rate | Decimal | Heart rate in beats per minute (BPM). | 87.0 | Range 49.0–118.0 |
| Systolic Blood Pressure | Decimal | Systolic Blood Pressure in mmHg. | 115.0 | Range 100.0–129.0 |
| Diastolic Blood Pressure | Decimal | Diastolic Blood Pressure in mmHg. | 76.0 | Range 66.0–86.0 |
| Blood Oxygen | Decimal | Blood oxygen saturation (SpO2) in percentage. | 98.0 | Range 0.0 (sensor failure/drop)–98.0 |
| Calories Burnt | Decimal | Active energy/calories burned (kcal). | 0.0 | Range 0.0–241.0 |
| Step | Decimal | Interval step count. | 0.0 | Range 0.0–4957.0 |
| Respiratory Rate | Decimal | Respiratory rate in breaths per minute. | 18.0 | Range 0.0–24.0 (0.0 = sensor failure/drop) |
| Freq Light Sleep | Decimal | Light-sleep frequency/count for the interval. | 0.0 | 0.0–8.0 |
| Freq Deep Sleep | Decimal | Deep-sleep frequency/count for the interval. | 0.0 | Range 0.0–18.0 |
| Temperature | Decimal | Skin/body temperature in Celsius. | 35.4 | Range 0.0 (disconnected sensor/default)–38.3 |
| train_id | Integer | Batch/run identifier for the training-data export this file belongs to. | 20230526131553 | Constant 20230526131553 (same value as `RK.csv` and `SS.csv`) |

---

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.

## Notes

- **Two schemas**: `ML`, `NP`, `RS`, `SM` have the 12-field schema with no `created_at`/`train_id`. `RK`, `SS`, `TW` have a 14-field schema that adds those two fields — all three share the identical `train_id` (`20230526131553`), suggesting they were exported together as one training batch, separately from the other four files.
- **Column order varies** even within the same schema group (e.g. `ML.csv` places `Timestamp` 4th, while `NP`/`RS`/`SM` place it 11th) — always read by header name, not position.
- **`created_at`** is a single constant timestamp repeated on every row of a file — it records when the file was exported, not a per-reading time. Don't confuse it with `Timestamp`.
- **Sentinel/default values**: `Blood Oxygen = 0.0` and `Respiratory Rate = 0.0` (in `RK.csv`, `TW.csv`) and `Temperature ≈ 0.0–0.15` (in `RK.csv`, `TW.csv`) follow the same sensor-failure/disconnected-sensor convention seen in the Dexcom and BerlinStudy datasets.
- **Possible data-quality issue**: `SS.csv` has a `Temperature` max of 42.7°C, well outside the 33–39°C range seen everywhere else in this collection — worth checking before use.
- No missing values were found in any of the 7 files (every populated column is 100% non-null).
