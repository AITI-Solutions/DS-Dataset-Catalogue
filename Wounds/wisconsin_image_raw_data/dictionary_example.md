# Data Dictionary

# Wisconsin Wound Data (raw data)

Same 6-column schema across both files.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| Unnamed: 0 | Integer | Row index column (unlabeled in source) | 0 | Non-negative integer, sequential |
| image_path | String | Relative file path to the wound image | Wisconsin_surgical_wounds\Raw images\W_SSI_1.jpg | Relative Windows path, .jpg; unique per row |
| folder | String | Source folder name for the image batch | Wisconsin_surgical_wounds | Constant per file: "Wisconsin_surgical_wounds" (surgical file), "Wisconsin_pressure_wounds" (pi file) |
| ImageDetail.ImageFilename | String | Filename of the wound image | W_SSI_1.jpg | .jpg; unique per row |
| ImageDetail.hasRuler | Boolean | Whether a measurement ruler is visible in the image | False | Constant: False (all rows in both files) |
| ImageDetail.WoundType | String | Wound aetiology/type category | Surgical Site Infections (SSI) | Constant per file: "Surgical Site Infections (SSI)" (surgical file), "Pressure Injuries (PI)" (pi file) |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.

## Notes

- Source files: `wisconsin_surgical_data.csv` (128 records) and `wisconsin_pi_data.csv` (100 records), 6 columns each, identical schema, no nulls.
- Both files are single-wound-type inventories: `folder` and `ImageDetail.WoundType` are constant within each file, differing only between the two files.
- `ImageDetail.hasRuler` is `False` for every row in both files — no ruler-containing images in this batch.
- Raw CSV text differs slightly in boolean casing (`False` in the surgical file vs. `FALSE` in the pi file) — cosmetic only; both parse to the same boolean value, but this suggests the two files may have been exported by different tools/steps.
- No `ImageDetail.PatientId`, diagnosis, or annotation fields present — these files appear to be a simple raw-image inventory/index, not full clinical metadata (unlike the earlier `wound_details_*`/`batch_*` files).
