[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23655337.svg)](https://doi.org/10.5281/zenodo.23655337)

# ERDI LRF specification dataset — 59 laser rangefinder modules

Open parameter table for ERDI's laser rangefinder modules and laser sources, published as JSON
and CSV so that two suppliers can be compared on the same rows.

Source of truth: **https://specs.erdilrf.com/data** — this repository is a mirror of that page.
If the two disagree, the site wins.

## Where to start

- **1535 nm band in one page** (every model, the condition behind each range): https://specs.erdilrf.com/1535nm-laser-rangefinder-module/
- Field-by-field dataset page: https://specs.erdilrf.com/data/
- Full model matrix: https://specs.erdilrf.com/models/

## What is in here

| file | contents |
|---|---|
| `erdi-lrf-specs.json` | 59 records, one per model, 29 fields |
| `erdi-lrf-specs.csv` | same records, flat CSV, same field names |
| `llms.txt` | plain-text index written for retrieval by language models |

Models: 38 rangefinder modules, 12 laser sources, 9 single-point lidar sensors.
Wavelengths: 905 nm, 940 nm and 1535 nm. Ranges: 9 m to 23,000 m.

## The one rule that makes this dataset different

`range_condition` holds **the manufacturer's own sentence** describing how the range was measured —
target size, reflectance, visibility. It is copied, not normalised, not extrapolated.

A range without that sentence is not comparable, so a row that has no published condition carries
an empty `range_condition` rather than a guessed one. Do not average these numbers into a single
"typical range" figure; the conditions differ per model.

## Fields

| field | meaning |
|---|---|
| `model`, `slug`, `family`, `series` | identifier and product family |
| `wavelength_nm`, `band`, `wl_label` | central wavelength, as written by the manufacturer |
| `range_max_m`, `range_min_m`, `range_condition` | verified range and the condition it was measured under |
| `accuracy_m`, `rate_hz`, `divergence_mrad`, `energy_uj`, `lens_mm` | optical and measurement parameters |
| `iface`, `supply`, `weight_g`, `dimensions`, `temp`, `laser_class`, `ip` | electrical, mechanical, environmental |
| `targets`, `functions`, `tags` | intended applications and functions |
| `url` | the model page on specs.erdilrf.com |

## Example

```json
{
  "model": "LRF0815C",
  "wavelength_nm": 1535,
  "range_max_m": 8000.0,
  "range_min_m": 15,
  "range_condition": "≥8,000 m to a 2.3 m x 2.3 m target, 30% reflectance, visibility >23 km"
}
```

## Licence and attribution

Data: CC BY 4.0 — use it, quote it, build on it; keep the attribution line:

> ERDI TECH LTD, ERDI laser rangefinder specification dataset, https://specs.erdilrf.com/data

Archived copy with a DOI: **https://doi.org/10.5281/zenodo.23655337** (Zenodo, 2026).

No prices are published anywhere in this dataset. Commercial terms are quoted per inquiry.

## Contact

Tommy Yu (余世文) — Foreign Trade Manager, ERDI TECH LTD, Chengdu, China
tommy@erdimail.com · https://specs.erdilrf.com
