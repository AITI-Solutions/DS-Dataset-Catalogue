# Data Dictionary

# Closeup Segmentation

| Field Name | Data Type | Description | Example | Allowed Values / Format |
|------------|-----------|-------------|---------|-------------------------|
| image_id | String | Unique identifier for the image record | ISIC_0000000 | Alphanumeric string; prefixes vary by source (ISIC, PAT, skin, SSM, D, Moneypox, Melanoma, LMM, NM, images, papillomavirus, AMM ) |
| image_path | String | Relative file path to the source image | ../../Dataset/ISIC-2016/training/images/ISBI2016_ISIC_Part3B_Training_Data/ISIC_0000000.jpg | Relative path, .jpg/.png |
| seg_path | String | Relative file path to the corresponding segmentation mask | ../../Dataset/ISIC-2016/training/images/ISBI2016_ISIC_Part3B_Training_Data/ISIC_0000000_Segmentation.png | Relative path, .png |
| image_type | String | Capture modality of the image | dermoscopic | dermoscopic, Smartphone |
| dataset | String | Data split assignment for model development | Train | Train, Test, Val |

