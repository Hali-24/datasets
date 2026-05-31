# HAPT – Smartphone-Based Recognition of Human Activities and Postural Transitions

## Summary
Time-series dataset collected from 30 subjects wearing a waist-mounted Samsung Galaxy S II smartphone.
Covers 6 basic activities (walking, walking upstairs, walking downstairs, sitting, standing, lying)
plus 6 postural transitions between static postures (e.g. stand-to-sit, lie-to-stand).
Sensor signals come from the phone's accelerometer and gyroscope at 50Hz.

## Details
- **Type:** Multivariate Time-Series
- **Format:** TXT (raw signals) + TXT (561-feature vectors)
- **Size:** 75.9 MB (download)
- **Instances:** 10,929 activity windows
- **Features:** 561 (time & frequency domain features per window)
- **Subjects:** 30 volunteers, age 19–48
- **Sampling Rate:** 50 Hz
- **Window Size:** 2.56 sec with 50% overlap (128 readings/window)
- **Missing Values:** No
- **License:** CC BY 4.0

## Source
- UCI ML Repository: https://archive.ics.uci.edu/dataset/341/smartphone+based+recognition+of+human+activities+and+postural+transitions
- DOI: https://doi.org/10.24432/C54G7M
- Authors: Reyes-Ortiz, J., Anguita, D., Oneto, L., & Parra, X. (2015)

## Activity Labels
| ID | Activity |
|----|----------|
| 1  | Walking |
| 2  | Walking Upstairs |
| 3  | Walking Downstairs |
| 4  | Sitting |
| 5  | Standing |
| 6  | Lying |
| 7  | Stand-to-Sit |
| 8  | Sit-to-Stand |
| 9  | Sit-to-Lie |
| 10 | Lie-to-Sit |
| 11 | Stand-to-Lie |
| 12 | Lie-to-Stand |

## Key Columns (feature vectors)
| File | Description |
|------|-------------|
| X_train.txt / X_test.txt | 561-feature vectors (normalized, bounded [-1,1]) |
| y_train.txt / y_test.txt | Activity labels |
| RawData/acc_expXX_userYY.txt | Raw 3-axis accelerometer at 50Hz |
| RawData/gyro_expXX_userYY.txt | Raw 3-axis gyroscope at 50Hz |
| subject_id_train/test.txt | Subject identifier (1–30) |

## Use Cases
- Human Activity Recognition (HAR) classification
- Postural transition detection
- Sensor fusion (accelerometer + gyroscope)
- Sliding window segmentation benchmarking
- Transfer learning across subjects

## Notes
- Updated version of the original HAR dataset — adds raw inertial signals and postural transitions
- 70/30 train/test split by subject
- Features are normalized and bounded within [-1, 1]
- Accelerometer units: g (9.80665 m/s²); Gyroscope units: rad/s
- Experiment video: http://www.youtube.com/watch?v=XOEN9W05_4A

## Load with Python (ucimlrepo)
```python
pip install ucimlrepo

from ucimlrepo import fetch_ucirepo
dataset = fetch_ucirepo(id=341)
X = dataset.data.features
y = dataset.data.targets
```
