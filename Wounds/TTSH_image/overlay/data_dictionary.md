# Data Dictionary

# TTSH_image / overlay

This folder holds 26 per-batch CSVs (`batch_01.csv` … `batch_26.csv`) — the raw, pre-merge annotation exports that `Original Dataset (outputs)/new_path_metadata.csv` was later built from (same field names, minus the standardized path/batch columns that get added during that merge). Column counts range from 37 to 40 across batches, but the differences are limited to a handful of columns being present or absent — not a change in meaning for the columns they share — so one table covers all 26 files, with the batch-level differences called out below it.

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| WoundDetail.Id | Integer | Primary key of the wound annotation record. | 9 | Positive integer, or blank |
| ImageDetail.Id | Integer | Primary key of the image record. | 9 | Positive integer, or blank |
| ImageDetail.ImageFilename | String | Filename of the raw (non-overlay) image. | VWI11962 2021-05-05-10-26-05.jpg | `*.jpg` / `*.JPG` / `*.jpeg` |
| ImageDetail.Folder | String | Original Windows folder path on the annotator's local machine where the source image was stored. | `C:\Users\night\Desktop\TTSH\...\Batch 110` | Windows absolute path |
| ImageDetail.PatientId | String | Patient/subject identifier code embedded in the filename. | VWI11962 | `VWI#####`, `TA###`, `WA###`, `TSY######`, or a numeric code (`001`…) |
| ImageDetail.LastAmended | String | Timestamp the annotation record was last edited. | 12/07/2021 14:31:22 | `DD/MM/YYYY HH:MM:SS` (format varies by batch, e.g. also `D/M/YYYY H:MM`) |
| ImageDetail.AmendedBy | String | Name of the annotator who last amended the record. | Audrey Tan | `Audrey Tan`, `Peiting Lai`, or blank (most rows) |
| ImageDetail.ReviewedBy | String | Name of the reviewer who signed off the record. | | 100% missing across all 26 batches |
| ImageDetail.MachineName | String | Hostname of the workstation used to author/export the record. | DESKTOP-90UCE7O | `DESKTOP-90UCE7O`, `DESKTOP-BC269OL` — **column only present in batches 04–23** |
| ImageDetail.Status | String | Annotation workflow status. | ReadyForReview | `ReadyForReview`, `Saved` |
| ImageDetail.hasRuler | Boolean | Whether a physical ruler/scale reference is visible in the image. | False | True / False — **column absent from batch_24 only** |
| ImageDetail.ImageId | String | Internal image identifier; usually mirrors the capture-timestamp portion of the filename. | 2021-05-05-10-26-05 | Free text |
| ImageDetail.WoundType | String | Wound category (target label for classification). | Neuro-Ischemic Ulcers (NIU) | `Neuro-Ischemic Ulcers (NIU)`, `Venous Leg Ulcer (VLU)`, `Surgical Site Infections (SSI)`, `Pressure Injuries (PI)`, `Other` |
| ImageDetail.PriorMinorAmputation | Boolean | Whether the patient has a documented prior minor amputation. | False | True / False — **column only present in batches 04–23** |
| ImageDetail.Notes | String | Free-text annotator notes. | SSG | Free text; rare |
| ImageDetail.ImageWidth | Integer | Raw image width in pixels. | 1200 | Positive integer, observed 410–5472 |
| ImageDetail.ImageHeight | Integer | Raw image height in pixels. | 1600 | Positive integer, observed 461–5472 |
| ImageDetail.HorizontalResolution | Decimal | Horizontal image resolution (DPI) embedded in the file. | 144.0 | 72.0 / 75.0 / 96.0 / 120.0 / 144.0 / 180.0 / 192.0 |
| ImageDetail.VerticalResolution | Decimal | Vertical image resolution (DPI) embedded in the file. | 144.0 | Same set as HorizontalResolution |
| ImageDetail.PixelFormat | String | Image color/bit-depth format. | Format24bppRgb | Constant `Format24bppRgb` (all 2,889 rows) |
| ImageDetail.AreaOfInterestX | Integer | X-origin (pixels) of the image-level annotated area of interest. | 55 | Non-negative integer |
| ImageDetail.AreaOfInterestY | Integer | Y-origin (pixels) of the image-level area of interest. | 300 | Non-negative integer |
| ImageDetail.AreaOfInterestWidth | Integer | Width (pixels) of the image-level area of interest. | 1145 | Non-negative integer |
| ImageDetail.AreaOfInterestHeight | Integer | Height (pixels) of the image-level area of interest. | 1047 | Non-negative integer |
| ImageDetail.NumberOfWounds | Integer | Count of distinct wounds annotated in the image. | 1 | 1, 2, 3, or 5 |
| ImageDetail.OtherUnbrokenSkin | String | Free-text "Other" finding when the unbroken-skin checklist didn't cover it. | Epitheliazation | Free text; extremely rare |
| ImageDetail.OtherBrokenSkin | String | Free-text "Other" finding when the broken-skin checklist didn't cover it. | Abrasion | Free text; extremely rare |
| ImageDetail.OtherWoundBedCategory | String | Free-text "Other" wound-bed category. | Exposed Tendon/Bone | Free text; rare |
| *(unnamed columns)* | — | Empty artifact columns carried over from the source spreadsheet export (blank header text in most batches; literally saved as `Unnamed: 25`/`Unnamed: 26` in batch_24, see notes). | | 100% missing everywhere |
| WoundDetail.ImageDetailId | Integer | Foreign key linking the wound record back to `ImageDetail.Id`. | 9 | Positive integer |
| WoundDetail.WoundNumber | Integer | Sequence number of this wound within the image. | 1 | 1–5 |
| WoundDetail.WoundLength | Decimal | Manually measured wound length. | 0 | Constant 0 (field not in use) |
| WoundDetail.WoundWidth | Decimal | Manually measured wound width. | 0 | Constant 0 (field not in use) |
| WoundDetail.WoundDepth | String | Qualitative wound depth category. | Deep | `Deep`, `Dermal Layer`, `Epidermal Layer`; sparsely populated |
| WoundDetail.Location | String | Anatomical location(s) of the wound, semicolon-delimited. | Left Dorsal Metatarsals; | Free text, `;`-delimited list |
| WoundDetail.AreaOfInterestX | Integer | X-origin (pixels) of the wound-level area of interest. | 55 | Non-negative integer |
| WoundDetail.AreaOfInterestY | Integer | Y-origin (pixels) of the wound-level area of interest. | 300 | Non-negative integer |
| WoundDetail.AreaOfInterestWidth | Integer | Width (pixels) of the wound-level area of interest. | 1145 | Non-negative integer |
| WoundDetail.AreaOfInterestHeight | Integer | Height (pixels) of the wound-level area of interest. | 1047 | Non-negative integer |
| WoundDetail.WoundBedUnfilled | Decimal | Pixel-area of the wound bed left unfilled by the segmentation polygon (annotation-completeness QA metric). | 10391 | Non-negative decimal — **column only present in batches 04–23** |
| WoundDetail.Unfilled | Decimal | Pixel-area of the overall region left unfilled by the segmentation polygon. | 317572 | Non-negative decimal — **column only present in batches 04–23** |

## Remarkable differences between batches

The 26 files are not perfectly uniform. The differences worth flagging:

| Batches | Columns | What's different |
|---------|---------|-------------------|
| `batch_01`, `batch_02`, `batch_03`, `batch_25`, `batch_26` | 39 | Missing `ImageDetail.MachineName`, `ImageDetail.PriorMinorAmputation`, `WoundDetail.WoundBedUnfilled`, `WoundDetail.Unfilled` entirely (column not present, not just blank). Has `ImageDetail.hasRuler`. |
| `batch_04` … `batch_23` (20 batches) | 40 | Full field set — the only batches carrying `MachineName` / `PriorMinorAmputation` / `WoundBedUnfilled` / `Unfilled` (2,387 of 2,889 rows total). |
| `batch_24` | 37 | Same 4 fields missing **and** also missing `ImageDetail.hasRuler` (the only batch without it, 46 rows). Its two empty artifact columns are literally named `Unnamed: 25` / `Unnamed: 26` in the file itself, rather than being blank header text — a sign this file passed through an extra pandas export step the others didn't. |

Everything else — field meaning, data types, value domains — is identical across all 26 files; only presence/absence of the columns above varies. Row counts also vary a lot by batch, from 10 (`batch_09.csv`) to 206 (`batch_05.csv`).
