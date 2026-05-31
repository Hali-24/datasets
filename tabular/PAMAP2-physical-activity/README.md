# PAMAP2 – Physical Activity Monitoring

## Summary
Time-series dataset from 9 subjects performing 18 physical activities (walking, cycling, soccer, rope jumping, etc.)
while wearing 3 inertial measurement units (wrist, chest, ankle) and a heart rate monitor.
One of the richest wearable-sensor datasets available, with diverse activity types and multi-sensor fusion.

## Details
- **Type:** Multivariate Time-Series
- **Format:** Space-separated TXT (.dat), 1 file per subject per session
- **Size:** 656.3 MB (download)
- **Instances:** 3,850,505 timestamped sensor readings
- **Features:** 52 sensor attributes + timestamp + activity label = 54 columns total
- **Subjects:** 9
- **Sampling Rate:** 100 Hz (IMU), ~9 Hz (heart rate)
- **Missing Values:** Yes (indicated as NaN)
- **License:** CC BY 4.0

## Source
- UCI ML Repository: https://archive.ics.uci.edu/dataset/231/pamap2+physical+activity+monitoring
- DOI: https://doi.org/10.24432/C5NW2H
- Authors: Reiss, A. (2012)
- Paper: *Introducing a New Benchmarked Dataset for Activity Monitoring* — Reiss & Stricker, 2012

## Sensor Placement
| Sensor | Position |
|--------|----------|
| IMU 1 | Wrist (dominant arm) |
| IMU 2 | Chest |
| IMU 3 | Ankle (dominant side) |
| HR Monitor | Chest |

## Column Structure (54 columns per row)
| Column(s) | Content |
|-----------|---------|
| 1 | Timestamp (seconds) |
| 2 | Activity ID (ground truth label) |
| 3 | Heart rate (bpm) |
| 4–20 | IMU Hand: temperature, acceleration (×2), gyroscope, magnetometer, orientation |
| 21–37 | IMU Chest: same as above |
| 38–54 | IMU Ankle: same as above |

## Activity Labels
| ID | Activity | ID | Activity |
|----|----------|----|----------|
| 1  | Lying | 12 | Ascending stairs |
| 2  | Sitting | 13 | Descending stairs |
| 3  | Standing | 16 | Vacuum cleaning |
| 4  | Walking | 17 | Ironing |
| 5  | Running | 18 | Folding laundry |
| 6  | Cycling | 19 | House cleaning |
| 7  | Nordic walking | 20 | Playing soccer |
| 9  | Watching TV | 24 | Rope jumping |
| 10 | Computer work | 0  | Other (transient) |
| 11 | Car driving | | |

## Use Cases
- Multi-class physical activity recognition
- Activity intensity estimation
- Multi-sensor / multi-position fusion experiments
- Heart rate integration with motion data
- Handling missing values in time-series (NaN imputation)

## Notes
- Two session types: `Protocol/` (12 required activities per subject) and `Optional/` (extra activities)
- Orientation columns are marked as invalid in the collection — do not use
- Scale for acceleration: ±16g (13-bit) and ±6g (13-bit) — two separate accelerometers per IMU
- Gyroscope units: rad/s; Magnetometer units: µT; Temperature: °C
- Missing values should be handled before training (interpolation or removal)

## Load with Python (ucimlrepo)
```python
pip install ucimlrepo

from ucimlrepo import fetch_ucirepo
dataset = fetch_ucirepo(id=231)
X = dataset.data.features
y = dataset.data.targets
```
