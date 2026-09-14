# Data Dictionary

# MCR-SL_dataset

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| image_id | String | Unique identifier for the clinical image record | I_C00000 | `I_C` + 5-digit zero-padded number |
| lesion_id | String | Identifier for the physical lesion depicted (may link to multiple images of the same lesion) | L0001 | `L` + 4-digit zero-padded number |
| modality | String | Imaging modality used to capture the image | clinical | Constant: "clinical" (all rows) |
| subject_id | String | Identifier for the patient/subject the lesion belongs to | S0001 | `S` + 4-digit zero-padded number; 59 distinct subjects |
| referral_diagnosis | String | Diagnosis/reason the lesion was referred or sampled | Melanoma | BCC, Melanoma, Morbus bowen carcinoma, Nevus, SK, Voluntary sample |
| lesion_status_when_captured | String | Clinical status of the lesion at the time the image was taken | Lesion | Biopsied lesion, Lesion |
| location | String | Specific anatomical location of the lesion | Back | Free-text anatomical site (25 distinct values, e.g. Abdomen, Face, Left cheek, Scalp); "unknown" where not recorded |
| location_group | String | Grouped/generalized anatomical region | Back | Arms, Back, Face, Head, Legs, Torso, unknown |
| diameter | Decimal (String w/ "unknown") | Lesion diameter in millimetres | 5.2 | Numeric 1.3–66.0, or "unknown"; nullable |
| malignancy | String | Malignancy status of the lesion | Non-malignant | Malignant, Non-malignant, unknown |
| lesion_diagnosis | String | Confirmed/coded diagnosis of the lesion | NEV | BCC, MEL, NEV, SCC, SEK, other |
| diagnosis_image_id | String | Identifier of the corresponding dermoscopic/diagnostic reference image for this lesion | I_D00000 | `I_D` + 5-digit zero-padded number; nullable |
| image_path | String | Relative file path to the clinical image file | ../../Dataset/MCR-SL_dataset/clinical/I_C00000.png | Relative path, .png |
| Set | String | Data split assignment for model development | Train | Train, Val, Test |

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.

## Notes

- Source file: `MCR-SL_dataset.csv` — 227 records, 14 columns.
- `modality` is constant ("clinical") across all rows in this file.
- `diameter` is stored as text and contains one "unknown" value alongside numeric measurements (1.3–66.0 mm) — clean/cast before numeric analysis.
- `location` (25 values) is a more granular free-text field than `location_group` (7 values); the latter is the recommended field for aggregate analysis.
- Split sizes: Train = 113, Test = 58, Val = 56.
- 59 distinct subjects (`subject_id`) across 227 lesion images — some subjects contribute multiple lesions/images.
