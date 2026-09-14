# Data Dictionary

# processed_dataset_wound_scale_batch_01

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| image | String | Relative file path to the wound image | ../../Processed Dataset/Wound_scale/batch_01/images/TA090_V1 220321.jpg | Relative path, .jpg; 1,095 distinct values (unique per row) |
| x0 | Integer | X-coordinate of a reference bounding box point (e.g. ruler/scale marker) | 811 | 0–2981 |
| y0 | Integer | Y-coordinate of a reference bounding box point | 424 | 0–2779 |
| w | Integer | Width of the reference bounding box | 640 | 174–2595 |
| h | Integer | Height of the reference bounding box | 509 | 175–4192 |
| x1 | Integer | X-coordinate of a second reference point (e.g. scale/ruler endpoint) | 88 | 0–1854 |
| y1 | Integer | Y-coordinate of a second reference point | 79 | 0–1472 |
| x2 | Integer | X-coordinate of a third reference point | 481 | 175–4007 |
| y2 | Integer | Y-coordinate of a third reference point | 472 | 174–2469 |
| scale | Decimal | Computed scale factor for the image (e.g. real-world units per pixel, or vice versa) | 0.8549618320610687 | 0.1507–1.9310 |
| date | Datetime | Date/time associated with the image capture or scale computation | 02/10/2022 11:08 | `DD/MM/YYYY HH:MM`; range 31/01/2022–01/12/2022 |
| ppcm | Decimal | Pixels per centimetre — derived scale metric | 92.11949900064594 | 26.14–646.31 |
| eppcm | Decimal | Error/estimated deviation in pixels-per-centimetre calculation | 1.934212416671653 | ~2.88e-14–7.73 |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.

## Notes

- Source file: `batch_01.csv` — 1,095 records, 13 columns, no nulls.
- All `image` paths point into `../../Processed Dataset/Wound_scale/batch_01/images/` — this is a wound-scale/measurement calibration file (likely derived from ruler detection in each image).

