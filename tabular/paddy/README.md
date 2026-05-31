# Paddy Dataset

Agricultural dataset for predicting paddy (rice) yield and recommending varieties based on soil, nursery, and farming parameters. Built using a Hybrid ML model with Combined Wrapper Feature Selection (HMLCWFS).

**UCI ID:** 1186 · **DOI:** [10.24432/C55W3J](https://doi.org/10.24432/C55W3J)  
**Authors:** Subramaniyan, M. et al. (2023)

---

## Specs

| Property | Value |
|----------|-------|
| Instances | 2,790 |
| Features | 45 |
| Feature Type | Categorical + Integer + Continuous |
| Tasks | Classification, Regression, Clustering |
| Missing Values | None |
| Format | CSV |
| Size | 16.2 KB (zip) |

## Key Features (sample)

| Column | Type | Description |
|--------|------|-------------|
| Hectares | Integer | Farm area |
| Agriblock | Categorical | Agricultural block identifier |
| Variety | Categorical | Paddy variety |
| Soil Types | Categorical | Soil classification |
| Seedrate(in Kg) | Integer | Seed quantity used |
| LP_Mainfield(in Tonnes) | Continuous | Land preparation manure — main field |
| DAP_20days | Integer | DAP fertilizer applied in first 20 days |

## Use Cases
- Crop yield prediction
- Paddy variety recommendation
- Feature selection benchmarking (5 FS methods applied in source paper)
- Agricultural classification

## Load
```python
from ucimlrepo import fetch_ucirepo
ds = fetch_ucirepo(id=1186)
X, y = ds.data.features, ds.data.targets
```
