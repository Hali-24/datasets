## Eyes on the Ground — Smallholder Crop Field Image Data (Kenya)

Georeferenced crop field images with rich ground-truth labels collected across 8 counties in Kenya. A collaboration between ACRE Africa, IFPRI, and the Lacuna Fund under the Picture Based Insurance framework. Combines ground-level field photos with Sentinel-2, ARC, TAMSAT, and ERA5 remote sensing covariates.

**DOI:** [10.34911/rdnt.1bs2jw](https://doi.org/10.34911/rdnt.1bs2jw)  
**Source:** [Source Cooperative](https://source.coop/lacuna/eyes-on-the-ground)  
**Authors:** Waithaka, L., Kramer, B., Hufkens, K., Kivuva, B., Mansabdar, S. (2022)  
**License:** CC-BY-SA-4.0

---

## Specs

| Property | Value |
|----------|-------|
| Coverage | 8 counties, Kenya |
| Modalities | Ground-level crop images + tabular labels |
| Remote sensing | Sentinel-2, ARC, TAMSAT, ERA5 |
| Download size | 2.54 GB (.tar.gz) |
| Created | 2024-06-26 |
| Last updated | 2025-08-21 |

## Labels

| Label Group | Description |
|-------------|-------------|
| Input use | Fertilizer, pesticide, seed type |
| Crop management | Planting date, irrigation, intercropping |
| Phenology | Growth stage at time of photo |
| Crop damage | Type and severity |
| Yield | Measured harvest yield |

## Use Cases
- Crop yield prediction from field photos
- Crop damage detection
- Phenology estimation
- Picture-based insurance ML modeling
- Multi-modal fusion (images + satellite time-series)
- Smallholder agriculture in Sub-Saharan Africa

## Notes
- Built on the Picture Based Insurance (PBI) framework — Ceballos, Kramer & Robles (2019)
- Companion app: [SeeItGrow (Kenya)](https://play.google.com/store/apps/details?id=com.ifpri.seeitgrow.kenya)
- Part of CGIAR Research Program on Policies, Institutions and Markets (PIM)
- Documentation: https://data.source.coop/lacuna/eyes-on-the-ground/Documentation.pdf

## Download
```bash
wget https://data.source.coop/lacuna/eyes-on-the-ground/EotG_data_final.tar.gz
```
