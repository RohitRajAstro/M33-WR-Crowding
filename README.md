# M33 Wolf-Rayet Stars: Crowding Analysis and Wind Benchmarks

**Raj et al. (2025)** — *Wolf-Rayet Stars in M33: 
The Impact of Stellar Crowding on Spectral 
Classification and Mass-Loss Diagnostics*  
Submitted to The Astrophysical Journal

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## Overview

This repository contains the data, catalog, and 
analysis code accompanying Raj et al. (2025), 
which presents:

- A photometric crowding analysis of **123 WR stars** 
  in M33 using 0.1″-resolution HST/PHATTER imaging
- A synthetic fiber aperture model computing fractional 
  WR flux contributions (F_WR) for each target
- Six-band HST photometry (F275W–F160W) for each 
  identified WR counterpart
- New Keck/DEIMOS slit spectra and wind-velocity 
  benchmarks for five WN-type WR stars

---

## Repository Contents

| Folder | Contents |
|--------|----------|
| `catalog/` | Full machine-readable catalog (MRT): positions, six-band photometry, crowding classifications, F_WR values |
| `spectra/` | Keck/DEIMOS 1D extracted spectra (FITS) for five WR stars |
| `code/fwr_calculator/` | F_WR synthetic fiber aperture calculator (adaptable to any HST/PSF-fit catalog) |
| `code/crowding_metric/` | Two-parameter crowding diagnostic (d, Δm₁₂) |
| `code/figures/` | Scripts reproducing all publication figures |
| `figures/` | Publication-ready figures (PNG + PDF) |
| `supplementary/` | Postage stamps and local CMDs for all 123 WR stars |

---

## Quickstart: F_WR Calculator

```bash
git clone https://github.com/RohitRajAstro/M33-WR-Crowding
cd M33-WR-Crowding
pip install astropy numpy scipy
python code/fwr_calculator/M33_WR_FWR_calculator.py \
    --catalog your_phatter_catalog.fits \
    --targets your_target_list.txt \
    --filter F275W \
    --aperture 0.75 \
    --fwhm 1.0
```

**Inputs:** PSF-fit photometric catalog (PHATTER-format 
or equivalent), target coordinates  
**Output:** F_WR per target in any specified filter  
**Dependencies:** `astropy`, `numpy`, `scipy`

The code is designed to be dataset-agnostic and can 
be adapted for crowding analysis of any resolved 
stellar population observed with HST or similar 
high-resolution imagers.

---


## Contact

Rohit Raj — [rohitraj@cfa.harvard.edu](mailto:rohitraj@cfa.harvard.edu) [rohit.620159@gmail.com](mailto:rohit.620159@gmail.com)  
Center for Astrophysics | Harvard & Smithsonian
