# WISDM – Smartphone and Smartwatch Activity and Biometrics Dataset

## Summary
Large time-series dataset from 51 subjects performing 18 activities for 3 minutes each,
recorded simultaneously from a smartphone AND a smartwatch using both accelerometer and gyroscope.
Unique because it enables device comparison (phone vs. watch) and supports behavioral biometric identification
in addition to activity recognition.

## Details
- **Type:** Multivariate Time-Series
- **Format:** CSV-style TXT, 4 directories (phone/watch × accel/gyro)
- **Size:** 295.9 MB (download)
- **Instances:** 15,630,426 raw sensor readings
- **Features:** 6 per entry (subject-id, activity-code, timestamp, x, y, z)
- **Subjects:** 51 (IDs: 1600–1650)
- **Sampling Rate:** 20 Hz
- **Window Size:** 10-second windows also provided as pre-segmented examples
- **Missing Values:** No
- **License:** CC BY 4.0

## Source
- UCI ML Repository: https://archive.ics.uci.edu/dataset/507/wisdm+smartphone+and+smartwatch+activity+and+biometrics+dataset
- DOI: https://doi.org/10.24432/C5HK59
- Authors: Weiss, G. (2019)

## Data Structure
4 directories, each with 51 files (one per subject):

| Directory | Device | Sensor |
|-----------|--------|--------|
| phone/accel/ | Smartphone | Accelerometer |
| phone/gyro/ | Smartphone | Gyroscope |
| watch/accel/ | Smartwatch | Accelerometer |
| watch/gyro/ | Smartwatch | Gyroscope |

## Columns (per entry)
| Column | Type | Description |
|--------|------|-------------|
| subject-id | int | Subject identifier (1600–1650) |
| activity-code | char | Activity label ('A'–'S', no 'N') |
| timestamp | int | Unix timestamp |
| x | float | Sensor reading — X axis |
| y | float | Sensor reading — Y axis |
| z | float | Sensor reading — Z axis |

## Activity Codes
See `activity_key.txt` in the dataset. 18 total activities labeled A–S (no N).
Examples include: walking, jogging, stairs, sitting, standing, typing, eating, brushing teeth, etc.

## Use Cases
- Human Activity Recognition (HAR) — phone vs. watch comparison
- Behavioral biometric identification (each reading linked to a specific subject)
- Cross-device and cross-sensor generalization
- Deep learning on raw time-series (CNN, LSTM, Transformer)
- 10-second windowed feature extraction benchmarking

## Notes
- Each activity performed for exactly 3 minutes per subject → consistent per-class duration
- The dataset can be used for **both** activity recognition AND **user identification** (biometrics)
- Pre-segmented 10-second window examples are provided alongside raw data
- Detailed description available in `WISDM-dataset-description.pdf` included in the download

## Load with Python (ucimlrepo)
```python
pip install ucimlrepo

from ucimlrepo import fetch_ucirepo
dataset = fetch_ucirepo(id=507)
X = dataset.data.features
y = dataset.data.targets
```
