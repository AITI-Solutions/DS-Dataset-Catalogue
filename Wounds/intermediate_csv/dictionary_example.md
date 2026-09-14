# Data Dictionary

# Intermediate CSV

Covers the combined schema across all five uploaded files. See **Present In** for which file(s) contain each field. 

| Field Name | Data Type | Description | Example | Allowed Values / Format | Present In |
|------------|-----------|-------------|---------|-------------------------|------------|
| index | Integer | Row index column | 0 | Mostly integer, but contains 285 rows with literal value "False" instead of a number — data quality issue, not a valid index value | wound_data_with_loc_v1 |
| WoundDetail.Id | Integer | Unique row identifier for the wound record | 7 | Positive integer | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.Id | Integer | Unique identifier for the source image record | 9 | Positive integer | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.ImageFilename | String | Filename of the wound image | VWI11962 2021-05-05-10-26-05.jpg | `<PatientId> <timestamp>.jpg` | wound_details_updated_mar22, wound_data_with_loc_v1, wound_details_with_specific_cols, wound_details_with_new_cols |
| ImageDetail.Folder | String | Original local folder path the image was sourced from | C:\Users\...\Batch 110 | Windows file path | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.PatientId | String | Patient identifier | VWI11962 | Alphanumeric string | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.LastAmended | Datetime | Timestamp the record was last amended | 12/07/2021 14:31:22 | `DD/MM/YYYY HH:MM:SS` | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.AmendedBy | String | Name of the person who last amended the record | Audrey Tan | N/A (allowed value list not re-verified for this dataset version) | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.ReviewedBy | String | Name of the person who reviewed the record | — | N/A (empty in all sampled rows) | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.Status | String | Review/workflow status of the record | ReadyForReview | N/A (not re-verified for this dataset version) | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.hasRuler | Boolean | Whether a measurement ruler is visible in the image | False | True, False; nullable | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.ImageId | String | Secondary image identifier (capture timestamp code) | 2021-05-05-10-26-05 | `YYYY-MM-DD-HH-MM-SS` | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.WoundType | String | Wound aetiology/type category | Neuro-Ischemic Ulcers (NIU) | N/A (not re-verified for this dataset version) | all 5 |
| ImageDetail.Notes | String | Free-text notes on the image | — | Free text; mostly null | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.ImageWidth | Integer | Image width in pixels | 1200 | N/A (range not re-verified) | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.ImageHeight | Integer | Image height in pixels | 1600 | N/A (range not re-verified) | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.HorizontalResolution | Integer | Horizontal image resolution (DPI) | 144 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.VerticalResolution | Integer | Vertical image resolution (DPI) | 144 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.PixelFormat | String | Image pixel/colour format | Format24bppRgb | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.AreaOfInterestX | Integer | X-coordinate of the annotated area-of-interest bounding box (image level) | 55 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.AreaOfInterestY | Integer | Y-coordinate of the annotated area-of-interest bounding box (image level) | 300 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.AreaOfInterestWidth | Integer | Width of the annotated area-of-interest bounding box (image level) | 1145 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.AreaOfInterestHeight | Integer | Height of the annotated area-of-interest bounding box (image level) | 1047 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.NumberOfWounds | Integer | Total number of wounds annotated in the image | 1 | N/A | all 5 |
| ImageDetail.OtherUnbrokenSkin | String | Free-text note on unbroken skin, if applicable | — | Free text; mostly null | all 5 |
| ImageDetail.OtherBrokenSkin | String | Free-text note on broken skin, if applicable | — | Free text; mostly null | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.OtherWoundBedCategory | String | Additional wound bed tissue category note | Healthy tissue | N/A (free text, not re-verified for this dataset version) | all 5 |
| WoundDetail.ImageDetailId | Integer | Foreign key linking the wound record to its parent image record | 9 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| WoundDetail.WoundNumber | Integer | Index of this wound within the image (for images with multiple wounds) | 1 | N/A | all 5 |
| WoundDetail.WoundLength | Decimal | Recorded wound length | 0 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| WoundDetail.WoundWidth | Decimal | Recorded wound width | 0 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| WoundDetail.WoundDepth | String | Wound depth classification | Deep | N/A (not re-verified for this dataset version) | all 5 |
| WoundDetail.Location | String | Anatomical location of the wound | Left Dorsal Metatarsals; | Free-text anatomical site, semicolon-terminated; nullable | all 5 |
| WoundDetail.AreaOfInterestX | Integer | X-coordinate of the annotated area-of-interest bounding box (wound level) | 55 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| WoundDetail.AreaOfInterestY | Integer | Y-coordinate of the annotated area-of-interest bounding box (wound level) | 300 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| WoundDetail.AreaOfInterestWidth | Integer | Width of the annotated area-of-interest bounding box (wound level) | 1145 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| WoundDetail.AreaOfInterestHeight | Integer | Height of the annotated area-of-interest bounding box (wound level) | 1047 | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| image_path | String | Relative file path to the raw wound image | 230921 export_a\Raw images\VWI11962 ....jpg | Relative path, .jpg; nullable | wound_details_updated_mar22, wound_data_with_loc_v1 |
| overlay_path | String | Relative file path to the annotated overlay image | 230921 export_a\Overlays\Ov_VWI11962 ....jpg | Relative path, .jpg; nullable | wound_details_updated_mar22, wound_data_with_loc_v1 |
| folder | String | Export batch folder name | 230921 export_a | N/A | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.MachineName | String | Name/ID of the capture device/machine used | — | N/A; mostly null | wound_details_updated_mar22, wound_data_with_loc_v1 |
| ImageDetail.PriorMinorAmputation | Boolean | Whether the patient had a prior minor amputation | False | True, False; mostly null | wound_details_updated_mar22, wound_data_with_loc_v1 |
| WoundDetail.WoundBedUnfilled | String | Unfilled/free-text wound bed tissue description | — | Free text; mostly null | wound_details_updated_mar22, wound_data_with_loc_v1 |
| WoundDetail.Unfilled | String | General unfilled/free-text field | — | Free text; mostly null | wound_details_updated_mar22, wound_data_with_loc_v1 |
| class | String | Short-code label for wound aetiology | D | D, S, V, P — N/A for full mapping confirmation (see notes) | all 5 |
| image_class_path | String | Relative path to the cropped, class/split-organized version of the image, used for classification model training | ../../wound_classification_data/ttsh_images/train/D/VWI11962 ....jpg | Relative path of form `.../ttsh_images/<split>/<class>/<filename>.jpg`; split values observed: train, val | wound_data_with_loc_v1 |
| image_class_path_uncropped | String | Relative path to the uncropped, class/split-organized version of the image | ../../wound_classification_data/ttsh_images_uncropped/train/D/VWI11962 ....jpg | Relative path of form `.../ttsh_images_uncropped/<split>/<class>/<filename>.jpg` | wound_data_with_loc_v1 |
| \<Location\> one-hot columns (63 columns) | Boolean (0/1) | One column per specific anatomical location (e.g. "Left Dorsal Metatarsals", "Right Plantar Calcaneus"), flagging whether that location applies to the row | 1 | 0, 1 | wound_details_with_new_cols, wound_loc_and_class |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.
- **Present In**: Which of the 5 source files contain this field.

## File Variants

- **wound_details_updated_mar22.csv** (1,304 rows, 44 cols) — full ImageDetail/WoundDetail metadata, file paths, and `class` label.
- **wound_data_with_loc_v1.csv** (1,711 rows, 47 cols) — superset of `wound_details_updated_mar22`, adding `index`, `image_class_path`, and `image_class_path_uncropped` (paths to classification-ready, split-organized image copies). Row count is higher (1,711 vs 1,304) — N/A for the exact cause of the difference; not independently verified.
- **wound_loc_and_class.csv** (1,304 rows, 64 cols) — `class` plus 63 one-hot anatomical-location columns only. **No image filename or ID column present, so this file cannot be row-joined back to the others** — it appears to be a standalone ML-ready feature/label table.
- **wound_details_with_specific_cols.csv** (461 rows, 9 cols) — a slimmed-down subset with core identifying/classification fields (filename, class, location, depth, wound type/count).
- **wound_details_with_new_cols.csv** (461 rows, 72 cols) — same 461-row subset as `with_specific_cols`, extended with the 63 one-hot location columns.
