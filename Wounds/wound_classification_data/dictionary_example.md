# Data Dictionary

# wound_classification (AZH Wound and Vascular Center / UWM)

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| image-filename | String | Filename of the wound image | 1.jpg | `<number>.jpg`; 156 distinct filenames (reused across classes, since files are organized into class subfolders) |
| image-path | String | Relative file path to the original wound image | original images/train/D/1.jpg | `original images/<split>/<label>/<filename>.jpg`; unique per row |
| image-label | String | Wound type classification label | D | D = Diabetic, P = Pressure, S = Surgical, V = Venous |
| train-val | String | Data split assignment | train | train, val |
| encoded-label | Integer | Numeric encoding of `image-label`, used for model training | 0 | 0 = D (Diabetic), 1 = P (Pressure), 2 = S (Surgical), 3 = V (Venous) |
| roi-path | String | Relative file path to the region-of-interest (cropped wound area) version of the image | ROI/D/1.jpg | `ROI/<label>/<filename>.jpg`; unique per row |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.

## Notes

- Source file: `wound_classification.csv` — 538 records, 6 columns, no nulls.
- Provided by collaboration between AZH Wound and Vascular Center (Milwaukee) and the Big Data Analytics and Visualization Laboratory at University of Wisconsin–Milwaukee (UWM); introduced in the preprint "Multiclass Wound Image Classification using an Ensemble Deep CNN-based Classifier".
- Class distribution: Venous (V) 156, Diabetic (D) 154, Surgical (S) 128, Pressure (P) 100 — reasonably balanced across the 4 classes.
- Split: Train 429, Val 109 (no separate test split in this file).
- Each image has both an `image-path` (original) and `roi-path` (region-of-interest / cropped) version.
