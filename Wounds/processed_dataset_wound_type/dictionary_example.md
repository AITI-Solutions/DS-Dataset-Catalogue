# Data Dictionary

# processed_dataset_wound_type


| Field Name | Data Type | Description | Example | Allowed Values / Format | Present In |
|------------|-----------|-------------|---------|-------------------------|------------|
| WoundDetail.Id | Integer | Unique row identifier for the wound record | 7 | Positive integer | both |
| ImageDetail.Id | Integer | Unique identifier for the source image record | 9 | Positive integer | both |
| ImageDetail.ImageFilename | String | Filename of the wound image | VWI11962 2021-05-05-10-26-05.jpg | `<PatientId> <timestamp>.jpg` | both |
| ImageDetail.Folder | String | Original local folder path the image was sourced from | C:\Users\...\Batch 110 | Windows file path | both |
| ImageDetail.PatientId | String | Patient identifier | VWI11962 | Alphanumeric string | both |
| ImageDetail.LastAmended | Datetime | Timestamp the record was last amended | 12/7/2021 14:31 | `D/M/YYYY HH:MM` | both |
| ImageDetail.AmendedBy | String | Name of the person who last amended the record | Audrey Tan | N/A (not re-verified full value list); nullable | both |
| ImageDetail.ReviewedBy | String | Name of the person who reviewed the record | — | N/A (entirely null in both files) | both |
| ImageDetail.Status | String | Review/workflow status of the record | ReadyForReview | N/A (not re-verified full value list) | both |
| ImageDetail.hasRuler | Boolean | Whether a measurement ruler is visible in the image | False | True, False; nullable | both |
| ImageDetail.ImageId | String | Secondary image identifier (capture timestamp code) | 2021-05-05-10-26-05 | `YYYY-MM-DD-HH-MM-SS` | both |
| ImageDetail.WoundType | String | Wound aetiology/type category | Neuro-Ischemic Ulcers (NIU) | N/A (not re-verified full value list; 5 distinct values observed) | both |
| ImageDetail.Notes | String | Free-text notes on the image | — | Free text; mostly null | both |
| ImageDetail.ImageWidth | Integer | Image width in pixels | 1200 | N/A (range not re-verified) | both |
| ImageDetail.ImageHeight | Integer | Image height in pixels | 1600 | N/A (range not re-verified) | both |
| ImageDetail.HorizontalResolution | Integer | Horizontal image resolution (DPI) | 144 | N/A | both |
| ImageDetail.VerticalResolution | Integer | Vertical image resolution (DPI) | 144 | N/A | both |
| ImageDetail.PixelFormat | String | Image pixel/colour format | Format24bppRgb | N/A | both |
| ImageDetail.AreaOfInterestX | Integer | X-coordinate of the annotated area-of-interest bounding box (image level) | 55 | N/A | both |
| ImageDetail.AreaOfInterestY | Integer | Y-coordinate of the annotated area-of-interest bounding box (image level) | 300 | N/A | both |
| ImageDetail.AreaOfInterestWidth | Integer | Width of the annotated area-of-interest bounding box (image level) | 1145 | N/A | both |
| ImageDetail.AreaOfInterestHeight | Integer | Height of the annotated area-of-interest bounding box (image level) | 1047 | N/A | both |
| ImageDetail.NumberOfWounds | Integer | Total number of wounds annotated in the image | 1 | N/A | both |
| ImageDetail.OtherUnbrokenSkin | String | Free-text note on unbroken skin, if applicable | — | Free text; mostly null | both |
| ImageDetail.OtherBrokenSkin | String | Free-text note on broken skin, if applicable | — | Free text; mostly null | both |
| ImageDetail.OtherWoundBedCategory | String | Additional wound bed tissue category note | — | N/A (free text, not re-verified); mostly null | both |
| Unnamed: 25 | — | Unlabeled blank column | — | N/A (entirely null; no data) | both |
| Unnamed: 26 | — | Unlabeled blank column | — | N/A (entirely null; no data) | both |
| Unnamed: 27 | — | Unlabeled blank column | — | N/A (entirely null; no data) | both |
| Unnamed: 38 | — | Unlabeled blank column | — | N/A (entirely null; no data) | both |
| WoundDetail.ImageDetailId | Integer | Foreign key linking the wound record to its parent image record | 9 | N/A | both |
| WoundDetail.WoundNumber | Integer | Index of this wound within the image (for images with multiple wounds) | 1 | N/A | both |
| WoundDetail.WoundLength | Decimal | Recorded wound length | 0 | Constant: 0 in this export (field appears unused/unpopulated) | both |
| WoundDetail.WoundWidth | Decimal | Recorded wound width | 0 | Constant: 0 in this export (field appears unused/unpopulated) | both |
| WoundDetail.WoundDepth | String | Wound depth classification | Deep | N/A (not re-verified full value list); nullable | both |
| WoundDetail.Location | String | Anatomical location of the wound | Left Dorsal Metatarsals; | Free-text anatomical site, semicolon-terminated; nullable | both |
| WoundDetail.AreaOfInterestX | Integer | X-coordinate of the annotated area-of-interest bounding box (wound level) | 55 | N/A | both |
| WoundDetail.AreaOfInterestY | Integer | Y-coordinate of the annotated area-of-interest bounding box (wound level) | 300 | N/A | both |
| WoundDetail.AreaOfInterestWidth | Integer | Width of the annotated area-of-interest bounding box (wound level) | 1145 | N/A | both |
| WoundDetail.AreaOfInterestHeight | Integer | Height of the annotated area-of-interest bounding box (wound level) | 1047 | N/A | both |
| image_path | String | Relative file path to the raw wound image (original export path) | 230921 export_a\Raw images\VWI11962 ....jpg | Relative path, .jpg; nullable | both |
| overlay_path | String | Relative file path to the annotated overlay image (original export path) | 230921 export_a\Overlays\Ov_VWI11962 ....jpg | Relative path, .jpg; nullable | both |
| folder | String | Export batch folder name | 230921 export_a | N/A | both |
| ImageDetail.MachineName | String | Name/ID of the capture device/machine used | — | N/A; mostly null | both |
| ImageDetail.PriorMinorAmputation | Boolean | Whether the patient had a prior minor amputation | — | True, False; mostly null | both |
| WoundDetail.WoundBedUnfilled | Decimal | Numeric field associated with wound bed annotation | 217780.0 | N/A for exact business meaning (not confirmed — large numeric values, possibly a pixel-area metric); mostly null | both |
| WoundDetail.Unfilled | Decimal | Numeric field associated with wound annotation | — | N/A for exact business meaning (not confirmed); mostly null | both |
| Batch Name | String | Name of the capture/export batch the record belongs to | batch_01 | `batch_` + 2-digit number; 25 distinct batches observed | wound_type_new_path_metadata only |
| changed_raw_directory | String | Updated/reorganized relative file path to the raw wound image | TTSH_image\raw_data\batch_01\images\VWI11962 ....jpg | Relative path, .jpg | wound_type_new_path_metadata only |
| changed_ov_directory | String | Updated/reorganized relative file path to the overlay image | TTSH_image\overlay\batch_01\images\Ov_VWI11962 ....jpg | Relative path, .jpg | wound_type_new_path_metadata only |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.
- **Present In**: Which of the 2 files contain this field.
