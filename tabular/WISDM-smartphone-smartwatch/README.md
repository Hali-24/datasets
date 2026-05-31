# WISDM — Smartphone and Smartwatch Activity and Biometrics Dataset

Simultaneous accelerometer and gyroscope recordings from a smartphone and smartwatch. 51 subjects, 18 activities × 3 minutes each at 20 Hz. Supports both activity recognition and subject identification (behavioral biometrics).

**UCI ID:** 507 · **DOI:** [10.24432/C5HK59](https://doi.org/10.24432/C5HK59)  
**Authors:** Weiss (2019)

---

## Specs

| Property | Value |
|----------|-------|
| Instances | 15,630,426 raw readings |
| Features | 6 per entry |
| Sampling rate | 20 Hz |
| Subjects | 51 (IDs 1600–1650) |
| Missing values | None |
| Format | CSV-style TXT, 51 files per directory |

## Data Directories
```
phone/accel/   — smartphone accelerometer
phone/gyro/    — smartphone gyroscope
watch/accel/   — smartwatch accelerometer
watch/gyro/    — smartwatch gyroscope
```

## Schema
```
subject-id    — int, 1600–1650
activity-code — char, A–S (no N), see activity_key.txt
timestamp     — Unix time (int)
x, y, z       — sensor readings (float)
```

Pre-segmented 10-second window examples are also provided alongside raw data.

## Load
```python
from ucimlrepo import fetch_ucirepo
ds = fetch_ucirepo(id=507)
X, y = ds.data.features, ds.data.targets
```
