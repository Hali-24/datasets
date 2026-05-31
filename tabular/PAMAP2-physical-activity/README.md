# PAMAP2 — Physical Activity Monitoring

Multi-sensor recordings from 9 subjects performing 18 physical activities. Three IMUs (wrist, chest, ankle) combined with a heart rate monitor at 100 Hz. One of the most referenced wearable HAR benchmarks.

**UCI ID:** 231 · **DOI:** [10.24432/C5NW2H](https://doi.org/10.24432/C5NW2H)  
**Authors:** Reiss, Stricker (2012)

---

## Specs

| Property | Value |
|----------|-------|
| Instances | 3,850,505 timestamped readings |
| Columns | 54 (timestamp + label + 52 sensor features) |
| Sampling rate | 100 Hz (IMU), ~9 Hz (HR) |
| Missing values | Yes — NaN |
| Format | Space-separated .dat, 1 file per subject per session |

## Sensor Placement

| IMU | Position |
|-----|----------|
| IMU 1 | Wrist (dominant) |
| IMU 2 | Chest |
| IMU 3 | Ankle (dominant) |

Each IMU provides: temperature, acceleration ×2 (±16g, ±6g), gyroscope, magnetometer. Orientation columns are invalid — discard.

## Column Layout
```
col 1      — timestamp (s)
col 2      — activityID
col 3      — heart rate (bpm)
cols 4–20  — IMU wrist
cols 21–37 — IMU chest
cols 38–54 — IMU ankle
```

## Activity Labels
```
1  lying          12  ascending stairs
2  sitting        13  descending stairs
3  standing       16  vacuum cleaning
4  walking        17  ironing
5  running        18  folding laundry
6  cycling        19  house cleaning
7  Nordic walking 20  playing soccer
9  watching TV    24  rope jumping
10 computer work   0  transient
11 car driving
```

## Load
```python
from ucimlrepo import fetch_ucirepo
ds = fetch_ucirepo(id=231)
X, y = ds.data.features, ds.data.targets
```
