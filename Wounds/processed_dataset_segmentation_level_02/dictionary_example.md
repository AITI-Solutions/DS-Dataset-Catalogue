# Data Dictionary

# Preprocessed_dataset Segmentation Level 02

Covers the combined schema across all 9 batch files. 8 of the 9 files (batch_01–06, batch_17, batch_23) share an identical 40-column schema; `batch_24` has a reduced 37-column schema (see **File Variants** below).

| Field Name | Data Type | Description | Example | Allowed Values / Format | Present In |
|------------|-----------|-------------|---------|-------------------------|------------|
| WoundDetail.Id | Integer | Unique row identifier for the wound record | 7 | Positive integer | all 9 |
| ImageDetail.Id | Integer | Unique identifier for the source image record | 9 | Positive integer | all 9 |
| ImageDetail.ImageFilename | String | Filename of the wound image | VWI11962 2021-05-05-10-26-05.jpg | `<PatientId> <timestamp>.jpg` | all 9 |
| ImageDetail.Folder | String | Original local folder path the image was sourced from | C:\Users\...\Batch 110 | Windows file path | all 9 |
| ImageDetail.PatientId | String | Patient identifier | VWI11962 | Alphanumeric string | all 9 |
| ImageDetail.LastAmended | Datetime | Timestamp the record was last amended | 12/07/2021 14:31:22 | `DD/MM/YYYY HH:MM:SS` | all 9 |
| ImageDetail.AmendedBy | String | Name of the person who last amended the record | — | N/A (entirely null across batch_01–06, batch_17, batch_23) | batch_01–06, batch_17, batch_23 |
| ImageDetail.ReviewedBy | String | Name of the person who reviewed the record | — | N/A (entirely null across batch_01–06, batch_17, batch_23) | batch_01–06, batch_17, batch_23 |
| ImageDetail.MachineName | String | Name/ID of the capture device/machine used | DESKTOP-90UCE7O | DESKTOP-90UCE7O, DESKTOP-BC269OL | batch_01–06, batch_17, batch_23 |
| ImageDetail.Status | String | Review/workflow status of the record | ReadyForReview | ReadyForReview, Saved | all 9 |
| ImageDetail.hasRuler | Boolean | Whether a measurement ruler is visible in the image | False | True, False | batch_01–06, batch_17, batch_23 |
| ImageDetail.ImageId | String | Secondary image identifier (capture timestamp code) | 2021-05-05-10-26-05 | `YYYY-MM-DD-HH-MM-SS` | all 9 |
| ImageDetail.WoundType | String | Wound aetiology/type category | Neuro-Ischemic Ulcers (NIU) | Neuro-Ischemic Ulcers (NIU), Other, Pressure Injuries (PI), Surgical Site Infections (SSI), Venous Leg Ulcer (VLU) | all 9 |
| ImageDetail.PriorMinorAmputation | Boolean | Whether the patient had a prior minor amputation | False | True, False | batch_01–06, batch_17, batch_23 |
| ImageDetail.Notes | String | Free-text notes on the image | Fasciotomy | BKA wound, Fasciotomy, Fasciotomy wound; nullable (mostly null) | all 9 |
| ImageDetail.ImageWidth | Integer | Image width in pixels | 1200 | 463–5472 | all 9 |
| ImageDetail.ImageHeight | Integer | Image height in pixels | 1600 | Positive integer | all 9 |
| ImageDetail.HorizontalResolution | Integer | Horizontal image resolution (DPI) | 144 | 6 distinct values | all 9 |
| ImageDetail.VerticalResolution | Integer | Vertical image resolution (DPI) | 144 | 6 distinct values | all 9 |
| ImageDetail.PixelFormat | String | Image pixel/colour format | Format24bppRgb | Constant: "Format24bppRgb" | all 9 |
| ImageDetail.AreaOfInterestX | Integer | X-coordinate of the annotated area-of-interest bounding box (image level) | 55 | Non-negative integer | all 9 |
| ImageDetail.AreaOfInterestY | Integer | Y-coordinate of the annotated area-of-interest bounding box (image level) | 300 | Non-negative integer | all 9 |
| ImageDetail.AreaOfInterestWidth | Integer | Width of the annotated area-of-interest bounding box (image level) | 1145 | Positive integer | all 9 |
| ImageDetail.AreaOfInterestHeight | Integer | Height of the annotated area-of-interest bounding box (image level) | 1047 | Positive integer | all 9 |
| ImageDetail.NumberOfWounds | Integer | Total number of wounds annotated in the image | 1 | 1, 2 | all 9 |
| ImageDetail.OtherUnbrokenSkin | String | Free-text note on unbroken skin, if applicable | Lichenification | Lichenification, peri-wound gangrene; nullable (mostly null) | all 9 |
| ImageDetail.OtherBrokenSkin | String | Free-text note on broken skin, if applicable | Blister | Blister, Denuded skin, Dermal gangrene; nullable (mostly null) | all 9 |
| ImageDetail.OtherWoundBedCategory | String | Additional wound bed tissue category note | — | N/A (entirely null across batch_01–06, batch_17, batch_23) | all 9 |
| Unnamed: 25 | — | Unlabeled blank column | — | N/A (entirely null; no header, no data) | batch_24 only |
| Unnamed: 26 | — | Unlabeled blank column | — | N/A (entirely null; no header, no data) | batch_24 only |
| WoundDetail.ImageDetailId | Integer | Foreign key linking the wound record to its parent image record | 9 | Positive integer | all 9 |
| WoundDetail.WoundNumber | Integer | Index of this wound within the image (for images with multiple wounds) | 1 | 1, 2 | all 9 |
| WoundDetail.WoundLength | Decimal | Recorded wound length | 0 | Constant: 0 (field appears unused/unpopulated) | all 9 |
| WoundDetail.WoundWidth | Decimal | Recorded wound width | 0 | Constant: 0 (field appears unused/unpopulated) | all 9 |
| WoundDetail.WoundDepth | String | Wound depth classification | Deep | Deep, Dermal Layer, Epidermal Layer; nullable | all 9 |
| WoundDetail.Location | String | Anatomical location of the wound | Left Dorsal Metatarsals; | Free-text anatomical site, semicolon-terminated (156 distinct values); nullable | all 9 |
| WoundDetail.AreaOfInterestX | Integer | X-coordinate of the annotated area-of-interest bounding box (wound level) | 55 | Non-negative integer | all 9 |
| WoundDetail.AreaOfInterestY | Integer | Y-coordinate of the annotated area-of-interest bounding box (wound level) | 300 | Non-negative integer | all 9 |
| WoundDetail.AreaOfInterestWidth | Integer | Width of the annotated area-of-interest bounding box (wound level) | 1145 | Positive integer | all 9 |
| WoundDetail.AreaOfInterestHeight | Integer | Height of the annotated area-of-interest bounding box (wound level) | 1047 | Positive integer | all 9 |
| WoundDetail.WoundBedUnfilled | Integer | Numeric field associated with wound bed annotation | -767671 | -767,671 to 2,199,159; N/A for exact business meaning (not confirmed — likely a pixel-area or coordinate-offset value) | batch_01–06, batch_17, batch_23 |
| WoundDetail.Unfilled | Integer | Numeric field associated with wound annotation | 0 | 0 to 1,980,146; N/A for exact business meaning (not confirmed — likely a pixel-area or coordinate-offset value) | batch_01–06, batch_17, batch_23 |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.
- **Present In**: Which of the 9 batch files contain this field.

## File Variants

- **batch_01, batch_02, batch_03, batch_04, batch_05, batch_06, batch_17, batch_23** — identical 40-column schema. Combined: 1,173 records.
- **batch_24** — reduced 37-column schema: missing `ImageDetail.hasRuler`, `ImageDetail.MachineName`, `ImageDetail.PriorMinorAmputation`, `WoundDetail.WoundBedUnfilled`, `WoundDetail.Unfilled`; instead contains two blank, header-less columns (`Unnamed: 25`, `Unnamed: 26`) in their place. 46 records.
- Total across all 9 files: 1,219 records.
- All 9 files share the same core schema and appear to be sequential capture/export batches of the same underlying wound-image dataset (same field names, same `ImageDetail.ImageFilename`/`ImageDetail.PatientId` conventions as prior wound_details files).
- `ImageDetail.AmendedBy`, `ImageDetail.ReviewedBy`, and `ImageDetail.OtherWoundBedCategory` are entirely null in every batch examined — appear to be unused fields in this export.
- `WoundDetail.WoundBedUnfilled` and `WoundDetail.Unfilled` are numeric (including negative values) in this file set, unlike a prior wound_details export where equivalent-named fields held free text — flagging this discrepancy rather than assuming a shared meaning.
