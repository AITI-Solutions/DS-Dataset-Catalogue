# Data Dictionary

# Original Dataset (metadata)

This dictionary applies to `blank_overlay_w_directory.csv`, a single-table manifest of overlay images.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| changed_ov_directory | String | Windows-style relative path to the overlay image within the TTSH_image directory tree, rooted at `TTSH_image\overlay\batch_<NN>\images\`. | `TTSH_image\overlay\batch_24\images\Ov_VWI10023 2020-02-10-07-52-43.jpg` | `TTSH_image\overlay\batch_<2-digit batch number>\images\<ImageDetail.ImageFilename>` |
| ImageDetail.ImageFilename | String | Filename of the overlay image (matches the final path component of `changed_ov_directory`). Prefixed `Ov_` to mark it as an overlay (vs. raw) image. Two naming conventions are present: (1) `Ov_VWI<5-digit ID> <YYYY-MM-DD-HH-MM-SS>.<ext>` or `Ov_VWI<5-digit ID> <YYYY-MM-DD>_<H.MM.SS> <AM/PM>.<ext>`, and (2) `Ov_<2-letter code><3-digit ID>_<DD.MM.YY>_V<visit number>.<ext>`. | `Ov_VWI10023 2020-02-10-07-52-43.jpg` | `Ov_*.jpg` / `Ov_*.jpeg` / `Ov_*.JPG` (case-insensitive extension) |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.

## Notes

- 10 data rows, 2 columns, no missing values.
- `changed_ov_directory` and `ImageDetail.ImageFilename` are redundant — the filename column is always the last path segment of the directory column.
- Batch numbers observed: `01`, `02`, `10`, `24` (2-digit, zero-padded; not contiguous in this sample).
- File extensions observed: `.jpg`, `.JPG`, `.jpeg` (mixed case, not normalized).
- Two distinct patient ID / filename schemes co-exist: `VWI#####` (timestamped) and `TA###` / `WA###` (dated with a visit code `V1`–`V5`).
- No row-level unique identifier is present other than the filename itself.
