# Individual Household Electric Power Consumption

Nearly 4 years of minute-resolution electric power consumption measurements from a single household in Sceaux, France (Dec 2006 – Nov 2010). Widely used for time-series forecasting and energy consumption modeling.

**UCI ID:** 235 · **DOI:** [10.24432/C58K54](https://doi.org/10.24432/C58K54)  
**Authors:** Hebrail, G. & Berard, A. (2006)

---

## Specs

| Property | Value |
|----------|-------|
| Instances | 2,075,259 |
| Features | 9 |
| Sampling rate | 1 minute |
| Coverage | 47 months |
| Missing Values | Yes (~1.25% of rows) |
| Format | Semicolon-separated TXT |
| Size | 126.8 MB (raw), 19.7 MB (zip) |

## Schema

| Column | Unit | Description |
|--------|------|-------------|
| Date | dd/mm/yyyy | Date of measurement |
| Time | hh:mm:ss | Time of measurement |
| Global_active_power | kW | Household global active power |
| Global_reactive_power | kW | Household global reactive power |
| Voltage | V | Minute-averaged voltage |
| Global_intensity | A | Minute-averaged current intensity |
| Sub_metering_1 | Wh | Kitchen (dishwasher, oven, microwave) |
| Sub_metering_2 | Wh | Laundry room (washer, dryer, fridge) |
| Sub_metering_3 | Wh | Water heater + air conditioner |

## Use Cases
- Time-series forecasting (LSTM, Transformer, N-BEATS)
- Anomaly detection in energy consumption
- Sub-metering disaggregation
- Regression and clustering on energy data

## Notes
- Unmeasured consumption = `(global_active_power × 1000/60) − sub_metering_1 − sub_metering_2 − sub_metering_3`
- Missing values: absent between consecutive semicolons — not NaN-encoded
- 29 citations in literature — well-established forecasting benchmark

## Load
```python
from ucimlrepo import fetch_ucirepo
ds = fetch_ucirepo(id=235)
X, y = ds.data.features, ds.data.targets
```
