# Wilt

Remote sensing dataset for detecting diseased trees in high-resolution Quickbird satellite imagery. Heavily imbalanced — 74 diseased tree samples vs 4,265 other land cover segments.

**UCI ID:** 285 · **DOI:** [10.24432/C5KS4M](https://doi.org/10.24432/C5KS4M)  
**Authors:** Johnson, B. (2013)

---

## Specs

| Property | Value |
|----------|-------|
| Instances | 4,889 (4,339 train / 500 test) |
| Features | 5 |
| Task | Binary Classification |
| Missing Values | None |
| Format | CSV |
| Size | 115.8 KB (zip) |
| Class imbalance | Severe — 74 positive (w) vs 4,265 negative (n) |

## Features

| Column | Description |
|--------|-------------|
| GLCM_Pan | GLCM mean texture — panchromatic band |
| Mean_G | Mean green spectral value |
| Mean_R | Mean red spectral value |
| Mean_NIR | Mean near-infrared value |
| SD_Pan | Standard deviation — panchromatic band |
| class | `w` = diseased tree, `n` = other land cover |

## Use Cases
- Imbalanced binary classification
- Remote sensing / vegetation analysis
- Anomaly detection benchmarking

## Notes
- Testing set corresponds to segmentation scale 15, original multi-spectral image (Table 2, row 5 of source paper)
- Severe class imbalance requires SMOTE, cost-sensitive learning, or similar handling

## Load
```python
from ucimlrepo import fetch_ucirepo
ds = fetch_ucirepo(id=285)
X, y = ds.data.features, ds.data.targets
```
