# Data Dictionary

# ISIC Overview Images

## metadata-BCC.csv
| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| isic_id | String | Unique identifier | ISIC_0024208 | N/A |
| attribution | String | Institution or source | Anonymous | N/A |
| copyright_license | String | Data license | CC-0 | N/A |
| age_approx | Decimal | Approximate age of the patient | 80.0 | N/A |
| anatom_site_general | String | Anatomical location of the lesion | anterior torso | N/A |
| anatom_site_special | String | Specific anatomical location | acral palms or soles | N/A |
| concomitant_biopsy | Boolean | Was a biopsy taken? | True | N/A |
| diagnosis_1 | String | Top-level diagnostic classification | Malignant | N/A |
| diagnosis_2 | String | Mid-level diagnostic classification | Malignant adnexal epithelial proliferations - Follicular | N/A |
| diagnosis_3 | String | Specific diagnosis | Basal cell carcinoma | N/A |
| diagnosis_confirm_type | String | Confirmation method | histopathology | N/A |
| family_hx_mm | String | Family history of melanoma | False | N/A |
| fitzpatrick_skin_type | String | Skin type classification (I-VI) | I | N/A |
| image_type | String | Type of image | clinical: overview | N/A |
| lesion_id | String | Unique identifier for the lesion | IL_9587318 | N/A |
| melanocytic | String | Is the lesion melanocytic? | False | N/A |
| patient_id | String | Unique identifier for the patient | IP_2079372 | N/A |
| personal_hx_mm | String | Personal history of melanoma | True | N/A |
| sex | String | Biological sex of the patient | male | male, female |

<br>

## metadata-MEL.csv
| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| isic_id | String | Unique identifier | ISIC_0024207 | N/A |
| attribution | String | Institution or source | Anonymous | N/A |
| copyright_license | String | Data license | CC-0 | N/A |
| age_approx | Integer | Approximate age of the patient | 25 | N/A |
| anatom_site_general | String | Anatomical location of the lesion | posterior torso | N/A |
| anatom_site_special | String | Specific anatomical location | acral palms or soles | N/A |
| concomitant_biopsy | Boolean | Was a biopsy taken? | True | N/A |
| diagnosis_1 | String | Top-level diagnostic classification | Malignant | N/A |
| diagnosis_2 | String | Mid-level diagnostic classification | Malignant melanocytic proliferations (Melanoma) | N/A |
| diagnosis_3 | String | Specific diagnosis | Melanoma Invasive | N/A |
| diagnosis_confirm_type | String | Confirmation method | histopathology | N/A |
| family_hx_mm | String | Family history of melanoma | False | N/A |
| fitzpatrick_skin_type | String | Skin type classification (I-VI) | II | N/A |
| image_type | String | Type of image | clinical: overview | N/A |
| lesion_id | String | Unique identifier for the lesion | IL_6961144 | N/A |
| mel_thick_mm | Decimal | Melanoma thickness in mm | 0.3 | N/A |
| melanocytic | String | Is the lesion melanocytic? | True | N/A |
| patient_id | String | Unique identifier for the patient | IP_1218261 | N/A |
| personal_hx_mm | String | Personal history of melanoma | True | N/A |
| sex | String | Biological sex of the patient | female | male, female |

<br>

## metadata-NEV.csv
| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| isic_id | String | Unique identifier | ISIC_0370022 | N/A |
| attribution | String | Institution or source | Hospital Italiano de Buenos Aires | N/A |
| copyright_license | String | Data license | CC-BY | N/A |
| age_approx | Integer | Approximate age of the patient | 40 | N/A |
| anatom_site_general | String | Anatomical location of the lesion | lower extremity | N/A |
| anatom_site_special | String | Specific anatomical location | acral palms or soles | N/A |
| concomitant_biopsy | Boolean | Was a biopsy taken? | False | N/A |
| diagnosis_1 | String | Top-level diagnostic classification | Benign | N/A |
| diagnosis_2 | String | Mid-level diagnostic classification | Benign melanocytic proliferations | N/A |
| diagnosis_3 | String | Specific diagnosis | Nevus | N/A |
| diagnosis_confirm_type | String | Confirmation method | histopathology | N/A |
| family_hx_mm | String | Family history of melanoma | False | N/A |
| fitzpatrick_skin_type | String | Skin type classification (I-VI) | II | N/A |
| image_type | String | Type of image | clinical: overview | N/A |
| lesion_id | String | Unique identifier for the lesion | IL_4510049 | N/A |
| patient_id | String | Unique identifier for the patient | IP_4446353 | N/A |
| personal_hx_mm | String | Personal history of melanoma | True | N/A |
| sex | String | Biological sex of the patient | female | male, female |

<br>

## metadata-SCC.csv
| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| isic_id | String | Unique identifier | ISIC_0024210 | N/A |
| attribution | String | Institution or source | Anonymous | N/A |
| copyright_license | String | Data license | CC-0 | N/A |
| age_approx | Integer | Approximate age of the patient | 85 | N/A |
| anatom_site_general | String | Anatomical location of the lesion | head/neck | N/A |
| concomitant_biopsy | Boolean | Was a biopsy taken? | False | N/A |
| diagnosis_1 | String | Top-level diagnostic classification | Malignant | N/A |
| diagnosis_2 | String | Mid-level diagnostic classification | Malignant epidermal proliferations | N/A |
| diagnosis_3 | String | Specific diagnosis | Squamous cell carcinoma, NOS | N/A |
| diagnosis_confirm_type | String | Confirmation method | histopathology | N/A |
| family_hx_mm | String | Family history of melanoma | True | N/A |
| fitzpatrick_skin_type | String | Skin type classification (I-VI) | II | N/A |
| image_type | String | Type of image | clinical: overview | N/A |
| lesion_id | String | Unique identifier for the lesion | IL_8239498 | N/A |
| melanocytic | String | Is the lesion melanocytic? | False | N/A |
| patient_id | String | Unique identifier for the patient | IP_7256360 | N/A |
| personal_hx_mm | String | Personal history of melanoma | True | N/A |
| sex | String | Biological sex of the patient | male | male, female |

<br>

## metadata-SKE.csv
| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| isic_id | String | Unique identifier | ISIC_0799918 | N/A |
| attribution | String | Institution or source | Hospital Italiano de Buenos Aires | N/A |
| copyright_license | String | Data license | CC-BY | N/A |
| age_approx | Integer | Approximate age of the patient | 85 | N/A |
| anatom_site_general | String | Anatomical location of the lesion | anterior torso | N/A |
| concomitant_biopsy | Boolean | Was a biopsy taken? | True | N/A |
| diagnosis_1 | String | Top-level diagnostic classification | Benign | N/A |
| diagnosis_2 | String | Mid-level diagnostic classification | Benign epidermal proliferations | N/A |
| diagnosis_3 | String | Specific diagnosis | Seborrheic keratosis | N/A |
| diagnosis_confirm_type | String | Confirmation method | histopathology | N/A |
| family_hx_mm | String | Family history of melanoma | False | N/A |
| fitzpatrick_skin_type | String | Skin type classification (I-VI) | II | N/A |
| image_type | String | Type of image | clinical: overview | N/A |
| lesion_id | String | Unique identifier for the lesion | IL_3664250 | N/A |
| patient_id | String | Unique identifier for the patient | IP_3702153 | N/A |
| personal_hx_mm | String | Personal history of melanoma | False | N/A |
| sex | String | Biological sex of the patient | male | male, female |

<br>

## Legend

- **Field Name**: Name of the column or attribute.
- **Data Type**: Data type (e.g., String, Integer, Boolean, Date, Decimal).
- **Description**: Business meaning of the field.
- **Example**: Sample value.
- **Allowed Values / Format**: Valid values, ranges, or formatting rules.
