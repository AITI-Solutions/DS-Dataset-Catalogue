# Data Dictionary

# Hospital Italiano de Buenos Aires - Skin Lesions

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| isic_id | String | Unique identifier for the image record in the ISIC archive | ISIC_0079358 | `ISIC_` + 7-digit number |
| attribution | String | Source/institution credited for the image | Hospital Italiano de Buenos Aires | Constant: "Hospital Italiano de Buenos Aires" (all rows) |
| copyright_license | String | Licence under which the image is released | CC-BY | Constant: "CC-BY" (all rows) |
| age_approx | Decimal | Patient age at imaging, rounded/approximate | 35 | 5.0–85.0; nullable (5 nulls) |
| anatom_site_general | String | General anatomical region of the lesion | anterior torso | anterior torso, head/neck, lateral torso, lower extremity, oral/genital, palms/soles, posterior torso, upper extremity; nullable (110 nulls) |
| anatom_site_special | String | Special-case anatomical site not covered by general hierarchy | acral palms or soles | acral palms or soles, oral or genital; nullable (1,604 nulls — only populated for special sites) |
| benign_malignant | String | Malignancy status of the lesion | benign | benign, malignant |
| concomitant_biopsy | Boolean | Whether a biopsy was taken concurrently with imaging | True | True, False |
| dermoscopic_type | String | Dermoscopy technique/lighting used to capture the image | contact polarized | Constant: "contact polarized" where populated; nullable (355 nulls — clinical-only images) |
| diagnosis | String | Specific diagnosis of the lesion | nevus | actinic keratosis, basal cell carcinoma, dermatofibroma, lichenoid keratosis, melanoma, nevus, seborrheic keratosis, solar lentigo, squamous cell carcinoma, vascular lesion |
| diagnosis_1 | String | Top-level diagnosis category | Benign | Benign, Indeterminate, Malignant |
| diagnosis_2 | String | Second-level diagnostic grouping | Benign melanocytic proliferations | Benign epidermal proliferations, Benign melanocytic proliferations, Benign soft tissue proliferations - Fibro-histiocytic, Benign soft tissue proliferations - Vascular, Indeterminate epidermal proliferations, Malignant adnexal epithelial proliferations - Follicular, Malignant epidermal proliferations, Malignant melanocytic proliferations (Melanoma) |
| diagnosis_3 | String | Third-level (most specific) diagnosis | Nevus | Basal cell carcinoma, Dermatofibroma, Lichen planus like keratosis, Melanoma NOS, Nevus, Seborrheic keratosis, Solar lentigo, Solar or actinic keratosis, Squamous cell carcinoma NOS; nullable (51 nulls) |
| diagnosis_confirm_type | String | Method by which the diagnosis was confirmed | histopathology | histopathology, single image expert consensus; nullable (583 nulls) |
| family_hx_mm | Boolean | Patient-reported family history of melanoma | False | True, False; nullable (874 nulls) |
| fitzpatrick_skin_type | String | Fitzpatrick skin phototype classification | II | I, II, III, IV; nullable (118 nulls) |
| image_type | String | Type of clinical image | dermoscopic | clinical: close-up, clinical: overview, dermoscopic |
| lesion_id | String | Identifier grouping multiple images of the same physical lesion | IL_3989348 | `IL_` + numeric string; 1,257 distinct lesions |
| patient_id | String | Identifier grouping multiple lesions/images from the same patient | IP_9328831 | `IP_` + numeric string; 628 distinct patients |
| personal_hx_mm | Boolean | Patient's personal history of melanoma | False | True, False; nullable (744 nulls) |
| sex | String | Patient sex | female | female, male; nullable (5 nulls) |


## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.