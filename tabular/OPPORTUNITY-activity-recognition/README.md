# OPPORTUNITY — Activity Recognition

Dense multi-sensor dataset for human activity recognition in a richly instrumented environment. Combines body-worn, object, and ambient sensors. Used as the benchmark for the 2011 IEEE SMC OPPORTUNITY Challenge.

**UCI ID:** 226 · **DOI:** [10.24432/C5M027](https://doi.org/10.24432/C5M027)  
**Authors:** Roggen, Calatroni et al. (2010)

---

## Specs

| Property | Value |
|----------|-------|
| Instances | 2,551 |
| Features | 242 |
| Subjects | 4 |
| Runs | 6 per subject (5 ADL + 1 drill) |
| Task | Classification |
| Missing Values | Yes |
| Format | Space-separated .dat |
| Size | 292.4 MB |

## Sensor Modalities

| Type | Count | Attributes |
|------|-------|------------|
| Body-worn IMUs + accelerometers | 19 sensors | 145 attributes |
| Instrumented objects | 12 objects | 60 attributes |
| Ambient sensors (switches + accel) | 21 sensors | 37 attributes |

## Annotation Tracks

| Track | Description |
|-------|-------------|
| Locomotion | Standing, sitting, walking, lying |
| Low-level actions | Reach, grasp, release — per hand, per object |
| Mid-level gestures | 17 classes (recommended for first use) |
| High-level activities | 5 classes: relaxing, early morning, coffee time, sandwich time, cleanup |

## Use Cases
- Multi-modal sensor fusion
- Hierarchical activity recognition
- Data imputation (missing values)
- Automatic segmentation
- Transfer and multi-task learning
- Sensor selection

## Notes
- Mid-level gesture annotations recommended as starting point
- Drill run provides dense scripted activity sequences; ADL runs are naturalistic
- Challenge baseline benchmarks and replication scripts included in package

## Load
```python
from ucimlrepo import fetch_ucirepo
ds = fetch_ucirepo(id=226)
X, y = ds.data.features, ds.data.targets
```
