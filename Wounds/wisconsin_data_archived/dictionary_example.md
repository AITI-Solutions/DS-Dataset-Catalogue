# Data Dictionary

# Wisconsin Data (Archived)

Covers the combined schema across all three files. Each represents a different stage of the same image → segmentation mask → bounding box pipeline. See **File Variants** below.

| Field Name | Data Type | Description | Example | Allowed Values / Format | Present In |
|------------|-----------|-------------|---------|-------------------------|------------|
| (unnamed index) | Integer | Row index column (unlabeled in source) | 0 | Non-negative integer | wound_image_paths_with_bounding_box |
| image_path | String | Relative file path to the wound image | wound_image_data/test/images/b586407933e66b112820f28448783627_0.png | Relative path, .png | wound_image_paths, wound_image_paths_with_bounding_box |
| image_filename | String | Filename of the wound image | b586407933e66b112820f28448783627_0.png | `<32-char hash>_<index>.png` | wound_image_paths, wound_image_paths_with_bounding_box |
| train_test | String | Data split assignment | test | train, test (no val split in this file); Train=831, Test=278 | wound_image_paths, wound_image_paths_with_bounding_box |
| label_path | String | Relative file path to the corresponding segmentation mask (label) image | wound_image_data/test/labels/b586407933e66b112820f28448783627_0.png | Relative path, .png | wound_image_paths, wound_image_paths_with_bounding_box |
| label_filename | String | Filename of the segmentation mask image | b586407933e66b112820f28448783627_0.png | Same filename convention as image_filename | wound_image_paths, wound_image_paths_with_bounding_box |
| x1 | Decimal | X-coordinate of the top-left corner of the bounding box derived from the segmentation mask | 8.0 | 0.0–86.0; nullable (69 nulls, likely masks with no detected wound region) | wound_image_paths_with_bounding_box |
| y1 | Decimal | Y-coordinate of the top-left corner of the bounding box | 11.0 | 0.0–205.0; nullable | wound_image_paths_with_bounding_box |
| x2 | Decimal | X-coordinate of the bottom-right corner of the bounding box | 29.0 | 1.0–175.0; nullable | wound_image_paths_with_bounding_box |
| y2 | Decimal | Y-coordinate of the bottom-right corner of the bounding box | 31.0 | 2.0–214.0; nullable | wound_image_paths_with_bounding_box |
| train-val-test | String | Data split assignment | test | train, test (no val split in this file); Train=831, Test=278 | wound_image_paths_masks_to_bounding_boxes |
| image-filename | String | Filename of the wound image | b23232898bafcf304b2138af86be40b9_0.png | `<32-char hash>_<index>.png` | wound_image_paths_masks_to_bounding_boxes |
| image-path | String | Relative file path to the wound image | wisconsin_data/wound_image_data/test/images/b23232898bafcf304b2138af86be40b9_0.png | Relative path, .png | wound_image_paths_masks_to_bounding_boxes |
| image-size | String | Image dimensions as (height, width, channels) | (224, 224, 3) | Constant: "(224, 224, 3)" (all rows) | wound_image_paths_masks_to_bounding_boxes |
| image-label-filename | String | Filename of the segmentation mask image | b23232898bafcf304b2138af86be40b9_0.png | Same filename convention as image-filename | wound_image_paths_masks_to_bounding_boxes |
| image-label-path | String | Relative file path to the segmentation mask image | wisconsin_data/wound_image_data/test/labels/b23232898bafcf304b2138af86be40b9_0.png | Relative path, .png | wound_image_paths_masks_to_bounding_boxes |
| image-label-size | String | Segmentation mask dimensions as (height, width, channels) | (224, 224, 3) | Constant: "(224, 224, 3)" (all rows) | wound_image_paths_masks_to_bounding_boxes |
| x | String (list-encoded) | X-coordinate of the bounding box top-left corner, derived from the mask, stored as a single-element list string | [6] | `[integer]` string format | wound_image_paths_masks_to_bounding_boxes |
| y | String (list-encoded) | Y-coordinate of the bounding box top-left corner | [31] | `[integer]` string format | wound_image_paths_masks_to_bounding_boxes |
| width | String (list-encoded) | Width of the bounding box | [55] | `[integer]` string format | wound_image_paths_masks_to_bounding_boxes |
| height | String (list-encoded) | Height of the bounding box | [26] | `[integer]` string format | wound_image_paths_masks_to_bounding_boxes |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.
- **Present In**: Which of the 3 source files contain this field.

## File Variants

These three files represent sequential stages of the same image/mask/bounding-box pipeline, all covering 1,109 records (831 train / 278 test):

- **wound_image_paths.csv** (1,109 rows, 5 cols) — base file: image and mask (label) file paths plus train/test split, no bounding box data yet.
- **wound_image_paths_with_bounding_box.csv** (1,109 rows, 10 cols) — same as base file, with an added unnamed index column and 4 bounding-box coordinate columns (`x1, y1, x2, y2`) as plain decimals, presumably derived by fitting a box to each segmentation mask. 69 rows have null bounding-box values.
- **wound_image_paths_masks_to_bounding_boxes.csv** (1,109 rows, 11 cols) — a differently-formatted/renamed version of the same pipeline output: uses hyphenated column names, includes image/mask dimensions `(224, 224, 3)`, and stores bounding box coordinates in `x/y/width/height` (top-left + size) format rather than `x1/y1/x2/y2` (two-corner) format, with each value wrapped as a single-element list string (e.g. `[6]`) rather than a plain number.
- All three files share `image_filename`/`image-filename` (hash + index naming) as a common join key, though column naming conventions differ (underscore vs. hyphen) across files.
- N/A for confirmation of exactly how the `x1/y1/x2/y2` box in `with_bounding_box` corresponds to the `x/y/width/height` box in `masks_to_bounding_boxes` for the same image — not independently cross-verified row-by-row in this pass.
