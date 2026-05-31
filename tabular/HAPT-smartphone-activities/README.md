# HAPT — Smartphone-Based Recognition of Human Activities and Postural Transitions

Sensor recordings from 30 subjects (ages 19–48) wearing a waist-mounted Samsung Galaxy S II. Captures 6 basic activities and 6 postural transitions at 50 Hz via 3-axial accelerometer and gyroscope.

**UCI ID:** 341 · **DOI:** [10.24432/C54G7M](https://doi.org/10.24432/C54G7M)  
**Authors:** Reyes-Ortiz, Anguita, Oneto, Parra (2015)

---

## Specs

| Property | Value |
|----------|-------|
| Instances | 10,929 windows |
| Features | 561 (time + frequency domain) |
| Sampling rate | 50 Hz |
| Window size | 2.56 s, 50% overlap |
| Missing values | None |
| Split | 70% train / 30% test (by subject) |

## Labels

| ID | Activity | ID | Activity |
|----|----------|----|----------|
| 1 | Walking | 7 | Stand→Sit |
| 2 | Walking Upstairs | 8 | Sit→Stand |
| 3 | Walking Downstairs | 9 | Sit→Lie |
| 4 | Sitting | 10 | Lie→Sit |
| 5 | Standing | 11 | Stand→Lie |
| 6 | Lying | 12 | Lie→Stand |

## Files
```
RawData/acc_expXX_userYY.txt   — raw 3-axis accelerometer @ 50Hz
RawData/gyro_expXX_userYY.txt  — raw 3-axis gyroscope @ 50Hz
Train/X_train.txt              — 561-feature vectors (normalized [-1,1])
Train/y_train.txt              — activity labels
Test/X_test.txt / y_test.txt   — test split
```

## Load
```python
from ucimlrepo import fetch_ucirepo
ds = fetch_ucirepo(id=341)
X, y = ds.data.features, ds.data.targets
```
