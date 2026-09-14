# Data Dictionary

# ISIC 2019 Training (Metadata + GroundTruth)

Two files, joined 1:1 on `image`.

| Field Name | Data Type | Description | Example | Allowed Values / Format | Present In |
|------------|-----------|-------------|---------|-------------------------|------------|
| image | String | Unique identifier for the image | ISIC_0000000 | `ISIC_` + 7-digit number | both |
| age_approx | Decimal | Patient age at imaging, rounded/approximate | 55 | 0.0–85.0; nullable (437 nulls) | Metadata |
| anatom_site_general | String | General anatomical region of the lesion | anterior torso | anterior torso, head/neck, lateral torso, lower extremity, oral/genital, palms/soles, posterior torso, upper extremity; nullable (2,631 nulls) | Metadata |
| lesion_id | String | Identifier grouping multiple images of the same physical lesion | — | Alphanumeric string; 11,847 distinct lesions; nullable (2,084 nulls) | Metadata |
| sex | String | Patient sex | female | female, male; nullable (384 nulls) | Metadata |
| MEL | Decimal (0/1) | One-hot label: Melanoma | 0.0 | 0.0, 1.0 | GroundTruth |
| NV | Decimal (0/1) | One-hot label: Melanocytic nevus | 1.0 | 0.0, 1.0 | GroundTruth |
| BCC | Decimal (0/1) | One-hot label: Basal cell carcinoma | 0.0 | 0.0, 1.0 | GroundTruth |
| AK | Decimal (0/1) | One-hot label: Actinic keratosis | 0.0 | 0.0, 1.0 | GroundTruth |
| BKL | Decimal (0/1) | One-hot label: Benign keratosis (solar lentigo / seborrheic keratosis / lichen planus-like keratosis) | 0.0 | 0.0, 1.0 | GroundTruth |
| DF | Decimal (0/1) | One-hot label: Dermatofibroma | 0.0 | 0.0, 1.0 | GroundTruth |
| VASC | Decimal (0/1) | One-hot label: Vascular lesion | 0.0 | 0.0, 1.0 | GroundTruth |
| SCC | Decimal (0/1) | One-hot label: Squamous cell carcinoma | 0.0 | 0.0, 1.0 | GroundTruth |
| UNK | Decimal (0/1) | One-hot label: Unknown/unclassified diagnosis | 0.0 | 0.0, 1.0 (0.0 for every row in this file — no unknowns present) | GroundTruth |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.
- **Present In**: Which of the 2 files contain this field.

## Notes

- Source files: `ISIC_2019_Training_Metadata.csv` (25,331 records, 5 columns) and `ISIC_2019_Training_GroundTruth.csv` (25,331 records, 10 columns) — row counts match and `image` values align 1:1 across both files (verified).
- `GroundTruth` is a strict one-hot encoding: exactly one of the 9 diagnosis columns equals 1.0 per row (verified — every row sums to 1).
- Class distribution in this file: NV 12,875, MEL 4,522, BCC 3,323, BKL 2,624, AK 867, SCC 628, VASC 253, DF 239, UNK 0 — notably imbalanced (NV alone is ~51% of records).
- `lesion_id` groups images from the same physical lesion (useful to avoid data leakage between train/val splits if lesions have multiple images) but is null for 2,084 rows.
