## East Africa Crop Fields — GPS Coordinates (Error-Corrected)

GPS coordinates of 18,482 crop fields across Kenya, Tanzania, and Rwanda, collected 2016–2017. Original field locations were offset due to sensor inaccuracies; this dataset provides error-corrected centers produced by the winning solution of a Zindi competition using Planet satellite imagery and YOLOv5 object detection.

**Source:** Figshare — [DOI: 10.6084/m9.figshare.15157263](https://doi.org/10.6084/m9.figshare.15157263)  
**Authors:** Eissa, K., Amer, K., Jaeger, J., ElHelw, M., Guerena, D. (2021)  
**Funding:** Lacuna Fund — Agriculture 2020 Award

---

## Specs

| Property | Value |
|----------|-------|
| Instances | 18,482 crop fields |
| Coverage | Kenya, Tanzania, Rwanda |
| Collection period | 2016–2017 |
| Correction method | YOLOv5 on Planet satellite imagery |
| Format | CSV (coordinates + metadata) |
| Version | 2 (2021-08-27) |

## Data Description

Original positions were treated as image centers (0, 0). A displacement vector per field in the training set was provided to competitors; the goal was to predict these vectors for the test set. The final dataset contains both the original approximate locations and the error-corrected field centers from the winning solution.

| Field | Description |
|-------|-------------|
| Original coordinates | Approximate GPS location (potentially offset) |
| Corrected coordinates | Error-corrected field center via YOLOv5 |
| Plot size | Approximate field area |
| Yield | Measured crop yield (where available) |
| Country | Kenya / Tanzania / Rwanda |

## Use Cases
- Geospatial crop field detection and localization
- GPS error correction using satellite imagery
- Yield prediction with remote sensing
- Object detection model validation (YOLOv5 on Planet imagery)
- Agricultural ML dataset for East Africa

## Notes
- Produced from a Zindi-hosted competition
- Planet imagery (3m resolution) used for correction
- Original offsets caused by edge-of-field collection or sensor inaccuracy
- Relevant for projects combining satellite imagery with ground truth agricultural data

## Download
https://figshare.com/articles/dataset/GPS_Coordinates_of_18_482_Crop_Fields_in_East_Africa_with_Improved_Accuracy_using_Planet_Imagery_and_Yolo_v5_Object_Detection_Model/15157263
