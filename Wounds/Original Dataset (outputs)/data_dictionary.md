# Data Dictionary

# Original Dataset (outputs)

This folder holds 8 CSV files. Five of them (`new_path_metadata.csv`, `new_path_metadata_seg_level2.csv`, `segmentation_train_df.csv`, `segmentation_test_df.csv`, `segmentation_val_df.csv`) share the **same 52-field Image/Wound metadata schema** (column order varies, and the `segmentation_*` files carry extra leftover pandas index columns). To avoid repeating 52 identical rows five times, that shared schema is documented once below, and each of those five files then gets its own short table calling out only what differs (row count, index columns, class/batch distribution, role). The remaining 3 small lookup files each get their own full field table, same as before.

---

## Common Schema — Image & Wound Metadata

Applies to `new_path_metadata.csv`, `new_path_metadata_seg_level2.csv`, `segmentation_train_df.csv`, `segmentation_test_df.csv`, `segmentation_val_df.csv`.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| Unnamed: 0.1 | Integer | Leftover pandas row-index column carried over from an earlier merge/export step. Not a stable identifier — values repeat across the file. | 0 | Non-negative integer |
| WoundDetail.Id | Integer | Primary key of the wound annotation record. Missing where no wound record was joined to the image row. | 9.0 | Positive integer, or blank |
| ImageDetail.Id | Integer | Primary key of the image record. | 9.0 | Positive integer, or blank |
| ImageDetail.ImageFilename | String | Filename of the raw (non-overlay) image. | VWI11962 2021-05-05-10-26-05.jpg | `*.jpg` / `*.JPG` / `*.jpeg` |
| ImageDetail.Folder | String | Original Windows folder path on the annotator's local machine where the source image was stored (legacy path, superseded by `changed_raw_directory`). | `C:\Users\night\Desktop\TTSH\...\Batch 110` | Windows absolute path |
| ImageDetail.PatientId | String | Patient/subject identifier code embedded in the filename. | VWI11962 | `VWI#####`, `TA###`, `WA###`, `TSY######`, or free-form code |
| ImageDetail.LastAmended | String | Timestamp the annotation record was last edited. | 12/07/2021 14:31:22 | `DD/MM/YYYY HH:MM:SS` (format varies by export batch, e.g. also `D/M/YYYY H:MM`) |
| ImageDetail.AmendedBy | String | Name of the annotator who last amended the record. | Audrey Tan | Free text; ~97% missing |
| ImageDetail.ReviewedBy | String | Name of the reviewer who signed off the record. | | 100% missing in every file observed |
| ImageDetail.Status | String | Annotation workflow status. | ReadyForReview | `ReadyForReview`, `Saved` |
| ImageDetail.hasRuler | Boolean | Whether a physical ruler/scale reference is visible in the image. | False | True / False |
| ImageDetail.ImageId | String | Internal image identifier; usually mirrors the capture-timestamp portion of the filename. | 2021-05-05-10-26-05 | Free text |
| ImageDetail.WoundType | String | Wound category (target label for classification). | Neuro-Ischemic Ulcers (NIU) | `Neuro-Ischemic Ulcers (NIU)`, `Venous Leg Ulcer (VLU)`, `Surgical Site Infections (SSI)`, `Pressure Injuries (PI)`, `Other` |
| ImageDetail.Notes | String | Free-text annotator notes. | SSG | Free text; rare (<0.2% populated) |
| ImageDetail.ImageWidth | Integer | Raw image width in pixels. | 1200.0 | Positive integer, observed 410–5472 |
| ImageDetail.ImageHeight | Integer | Raw image height in pixels. | 1600.0 | Positive integer, observed 461–5472 |
| ImageDetail.HorizontalResolution | Decimal | Horizontal image resolution (DPI) embedded in the file. | 144.0 | One of 72.0, 75.0, 96.0, 120.0, 144.0, 180.0, 192.0 |
| ImageDetail.VerticalResolution | Decimal | Vertical image resolution (DPI) embedded in the file. | 144.0 | Same set as HorizontalResolution |
| ImageDetail.PixelFormat | String | Image color/bit-depth format. | Format24bppRgb | Constant `Format24bppRgb` |
| ImageDetail.AreaOfInterestX | Integer | X-origin (pixels) of the image-level annotated area of interest. | 55.0 | Non-negative integer, 0–2981 |
| ImageDetail.AreaOfInterestY | Integer | Y-origin (pixels) of the image-level area of interest. | 300.0 | Non-negative integer, 0–2779 |
| ImageDetail.AreaOfInterestWidth | Integer | Width (pixels) of the image-level area of interest. | 1145.0 | Non-negative integer, 0–4032 |
| ImageDetail.AreaOfInterestHeight | Integer | Height (pixels) of the image-level area of interest. | 1047.0 | Non-negative integer, 0–4192 |
| ImageDetail.NumberOfWounds | Integer | Count of distinct wounds annotated in the image. | 1.0 | 1, 2, or 5 |
| ImageDetail.OtherUnbrokenSkin | String | Free-text "Other" finding when the unbroken-skin checklist didn't cover it. | Epitheliazation | Free text; extremely rare |
| ImageDetail.OtherBrokenSkin | String | Free-text "Other" finding when the broken-skin checklist didn't cover it. | Abrasion | Free text; extremely rare |
| ImageDetail.OtherWoundBedCategory | String | Free-text "Other" wound-bed category. | Exposed Tendon/Bone | Free text; rare |
| Unnamed: 26 | — | Empty artifact column carried over from the source spreadsheet export. | | 100% missing in every file |
| Unnamed: 27 | — | Empty artifact column carried over from the source spreadsheet export. | | 100% missing in every file |
| WoundDetail.ImageDetailId | Integer | Foreign key linking the wound record back to `ImageDetail.Id`. | 9.0 | Positive integer |
| WoundDetail.WoundNumber | Integer | Sequence number of this wound within the image. | 1.0 | 1–5 |
| WoundDetail.WoundLength | Decimal | Manually measured wound length. | 0.0 | Constant 0.0 (field not in use / deprecated) |
| WoundDetail.WoundWidth | Decimal | Manually measured wound width. | 0.0 | Constant 0.0 (field not in use / deprecated) |
| WoundDetail.WoundDepth | String | Qualitative wound depth category. | Deep | `Deep`, `Dermal Layer`, `Epidermal Layer`; sparsely populated |
| WoundDetail.Location | String | Anatomical location(s) of the wound, semicolon-delimited. | Left Dorsal Metatarsals; | Free text, `;`-delimited list |
| WoundDetail.AreaOfInterestX | Integer | X-origin (pixels) of the wound-level area of interest (may refine the image-level box). | 55.0 | Non-negative integer |
| WoundDetail.AreaOfInterestY | Integer | Y-origin (pixels) of the wound-level area of interest. | 300.0 | Non-negative integer |
| WoundDetail.AreaOfInterestWidth | Integer | Width (pixels) of the wound-level area of interest. | 1145.0 | Non-negative integer |
| WoundDetail.AreaOfInterestHeight | Integer | Height (pixels) of the wound-level area of interest. | 1047.0 | Non-negative integer |
| Unnamed: 38 | — | Empty artifact column carried over from the source spreadsheet export. | | 100% missing in every file |
| image_path | String | Relative path to the raw image inside the original annotator "export batch" folder tree (predates batch renaming). | `230921 export_a\Raw images\VWI11962 ....jpg` | `<export folder>\Raw images\<filename>` |
| overlay_path | String | Relative path to the overlay image inside the original "export batch" folder tree. | `230921 export_a\Overlays\Ov_VWI11962 ....jpg` | `<export folder>\Overlays\Ov_<filename>` |
| folder | String | Name of the original annotator export batch folder (pre-rename). | 230921 export_a | Free text, one of 28 observed export folder names |
| ImageDetail.MachineName | String | Hostname of the workstation used to author/export the record. | DESKTOP-90UCE7O | One of 2 observed hostnames, or blank |
| ImageDetail.PriorMinorAmputation | Boolean | Whether the patient has a documented prior minor amputation. | False | True / False |
| WoundDetail.WoundBedUnfilled | Decimal | Pixel-area of the wound bed left unfilled by the segmentation polygon (annotation-completeness QA metric). | 10391.0 | Non-negative decimal |
| WoundDetail.Unfilled | Decimal | Pixel-area of the overall region left unfilled by the segmentation polygon. | 317572.0 | Non-negative decimal |
| Unnamed: 25 | — | Empty artifact column carried over from the source spreadsheet export. | | 100% missing in every file |
| Unnamed: 0 | Integer | Leftover pandas row-index from a smaller source table that was merged in; only populated for the subset of rows that came from that table. | 0.0 | Non-negative integer, or blank |
| Batch Name | String | Canonical renamed batch identifier (maps raw export folders to a consistent scheme via `new batch name_level 1.csv` / `new batch name_level 2.csv`). | batch_01 | `batch_01`…`batch_26`, `batch_pressure`, `batch_surgical` |
| changed_raw_directory | String | Standardized relative path to the raw image under the canonical `TTSH_image\raw_data\<batch>\images\` (or `Wisconsin_image\...` for the surgical batch) tree. | `TTSH_image\raw_data\batch_01\images\VWI11962 ....jpg` | `<Source>_image\raw_data\batch_<NN or name>\images\<filename>` |
| changed_ov_directory | String | Standardized relative path to the overlay image under the canonical `TTSH_image\overlay\<batch>\images\` tree. | `TTSH_image\overlay\batch_01\images\Ov_VWI11962 ....jpg` | `<Source>_image\overlay\batch_<NN or name>\images\Ov_<filename>` |

### File-specific summaries

#### new_path_metadata.csv

| Metric | Value |
|--------|-------|
| Role | Master path-corrected metadata table — the full annotated image/wound export with standardized batch names and directory paths. |
| Rows / Columns | 3104 / 52 |
| Extra index columns | None beyond `Unnamed: 0.1` / `Unnamed: 0` (part of the common schema) |
| WoundType distribution | VLU 1354, NIU 1255, SSI 368, PI 124, Other 3 |
| Status distribution | Saved 2386, ReadyForReview 490, missing 228 |
| hasRuler | False 1865, True 1194, missing 45 |
| Batches covered | 28 — `batch_01`…`batch_26`, `batch_pressure`, `batch_surgical` |

#### new_path_metadata_seg_level2.csv

| Metric | Value |
|--------|-------|
| Role | Second annotation pass ("level 2") over a subset of images — same schema, smaller batch coverage. |
| Rows / Columns | 973 / 52 (same 52 fields as above, different column order) |
| Extra index columns | None beyond `Unnamed: 0.1` / `Unnamed: 0` |
| WoundType distribution | NIU 624, VLU 228, SSI 103, PI 9, Other 9 |
| Status distribution | ReadyForReview 973 (all rows) |
| hasRuler | False 721, True 206, missing 46 |
| Batches covered | 7 — `batch_01`, `batch_02`, `batch_03`, `batch_04`, `batch_05`, `batch_06`, `batch_24` |
| WoundDetail.Id missing | 0 (fully joined, unlike the master table) |

#### segmentation_train_df.csv

| Metric | Value |
|--------|-------|
| Role | Training split of the merged/cleaned metadata used for the segmentation model. |
| Rows / Columns | 1931 / 53 |
| Extra index columns | Adds `Unnamed: 0.2` (0–1931, unique per row — the true row index of this split) on top of `Unnamed: 0.1` and the always-empty `Unnamed: 0` |
| WoundType distribution | VLU 933, NIU 831, SSI 150, PI 14, Other 3 |
| Status distribution | Saved 1732, ReadyForReview 199 |
| hasRuler | False 1069, True 834, missing 28 |
| Batches covered | 26 — `batch_01`…`batch_26` |

#### segmentation_test_df.csv

| Metric | Value |
|--------|-------|
| Role | Test split of the merged/cleaned metadata used for the segmentation model. |
| Rows / Columns | 258 / 53 |
| Extra index columns | Same as `segmentation_train_df.csv` — `Unnamed: 0.2` is a unique 0–257 row index |
| WoundType distribution | NIU 118, VLU 113, SSI 24, PI 3 |
| Status distribution | Saved 224, ReadyForReview 34 |
| hasRuler | False 154, True 100, missing 4 |
| Batches covered | 24 |

#### segmentation_val_df.csv

| Metric | Value |
|--------|-------|
| Role | Validation split of the merged/cleaned metadata used for the segmentation model. |
| Rows / Columns | 386 / 53 |
| Extra index columns | Same as `segmentation_train_df.csv` — `Unnamed: 0.2` is a unique 0–385 row index |
| WoundType distribution | VLU 193, NIU 159, SSI 29, PI 5 |
| Status distribution | Saved 346, ReadyForReview 40 |
| hasRuler | False 211, True 170, missing 5 |
| Batches covered | 26 |

---

## new batch name_level 1.csv

Lookup table mapping the original "level 1" annotator export folder names to the canonical batch naming scheme.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| Original Name | String | Original annotator export folder name (matches `folder` in the metadata tables). | 230921 export_a | Free text |
| Batch Name | String | Canonical renamed batch identifier (matches `Batch Name` / `changed_raw_directory` in the metadata tables). | batch_01 | `batch_<NN>` |

28 rows, 1:1 mapping (28 unique original names → 28 unique batch names).

---

## new batch name_level 2.csv

Lookup table mapping the "level 2" (second annotation pass) export folder names to canonical batch names.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| Original Name | String | Original level-2 export folder name. | AITIS level 2_130922 | Free text |
| Batch Name | String | Canonical renamed batch identifier. | batch_01 | `batch_<NN>` |

9 rows over 7 unique original names (2 names each map to 2 different batch names, e.g. duplicate exports re-batched separately) → 9 unique batch names.

---

## blank_overlay_w_directory.csv

Same file already documented in `Wounds/Original Dataset (metadata)/data_dictionary.md` — a 10-row, 2-column manifest (`changed_ov_directory`, `ImageDetail.ImageFilename`) of overlay images flagged as blank, with their location under `TTSH_image\overlay\batch_<NN>\images\`. See that file for the full field table; not repeated here.

---

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.

## Notes

- The four `Unnamed: *` empty artifact columns (`25`, `26`, `27`, `38`) are 100% missing in every file and are safe to drop for downstream use.
- `WoundDetail.WoundLength` and `WoundDetail.WoundWidth` are constant `0.0` everywhere observed — the field is not actually populated despite existing in the schema.
- Column **order differs between files** even where the field set is identical — always read by header name, not position.
- `segmentation_train_df.csv` / `_test_df.csv` / `_val_df.csv` are a fixed split of a merged, cleaned metadata table (26 batches, 2575 rows combined) — likely the direct input to `Wounds/Processed Dataset:Segmentation:Level_01`.
