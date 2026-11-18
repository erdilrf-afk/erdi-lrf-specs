# ERDI LRF specification dataset — 62 laser rangefinder modules and laser sources

Open parameter table for ERDI's laser rangefinder modules and laser sources, published as JSON
and CSV so that two suppliers can be compared on the same rows.

Source of truth: **https://specs.erdilrf.com/data** — this repository is a mirror of that page.
If the two disagree, the site wins.

## Where to start

- **Model matrix (62 models, one comparable table)**: https://specs.erdilrf.com/models/
- **1535 nm band** (every model, the condition behind each range): https://specs.erdilrf.com/1535nm-laser-rangefinder-module/
- **Selector** (filter by wavelength, range, mass, interface, rate): https://specs.erdilrf.com/selector
- **Range conditions, verbatim** (why a bare range number is not comparable): https://specs.erdilrf.com/data/range-conditions
- **Test method** (what we measure and what we do not): https://specs.erdilrf.com/data/test-method
- Field-by-field dataset page: https://specs.erdilrf.com/data/

## What is in here

| file | contents |
|---|---|
| `erdi-lrf-specs.json` | 62 records, one per model |
| `erdi-lrf-specs.csv` | same records, flat CSV, same field names |
| `llms.txt` | plain-text index written for retrieval by language models |

Models: **49 rangefinder modules**, **13 laser sources**, of which 16 are single-point lidar sensors.
Bands: 1535 nm (31), 905 nm (30), 940 nm (1).
Published ranges: 9 m to 23,000 m. Mass where published: 1 g to 410 g.

## The one rule that makes this dataset different

`range_condition` holds **the manufacturer's own sentence** describing how the range was measured.
A range figure without that sentence is not comparable to anything, including our own other models.

## Regeneration

The table is generated from the manufacturer pages and mirrored here by script; the counts above are
computed at generation time, so they cannot drift from the data.

## Licence and citation

Data: CC BY 4.0. Cite as: ERDI TECH LTD (2026). *ERDI laser rangefinder module dataset*. Zenodo.
https://doi.org/10.5281/zenodo.23655337
