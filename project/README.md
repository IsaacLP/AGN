# AGN Final Project

Classification and physical characterisation of active galactic nuclei (AGN) in a sample of 10,000 SDSS emission-line galaxies cross-matched with WISE.

## Contents

| File | Description |
|------|-------------|
| `final_project.ipynb` | Main analysis notebook |
| `final_project.pdf` | Exported version of the notebook |
| `agn_sample.csv` / `agn_sample_high_snr.csv` | SDSS emission-line sample (fluxes, EWs, [OIII] σ) queried via SciServer |
| `agn_sample_wise.csv` / `agn_sample_wise_high_snr.csv` | Sample with WISE photometry and the derived classifications, n_e and M_BH |
| `blobs.tiff` | Image used in the notebook |

## Analysis

1. **Sample selection**: narrow-line objects only (FWHM < 500 km/s), SNR > 5 and emission on all diagnostic lines.
2. **Optical classification**: BPT diagram with Kewley et al. (2001) and Kauffmann et al. (2003) lines, plus the WHAN diagram.
3. **Infrared classification**: WISE W1−W2 vs W2−W3 colours with the Mateos et al. (2012) AGN wedge.
4. **NLR gas properties**: electron density from the [SII] λ6716/λ6731 ratio (Sanders et al. 2015) and [OIII] velocity dispersion.
5. **SMBH masses**: M_BH–σ relation (Tremaine et al. 2002), using σ_[OIII] as a proxy for σ_*.

## Requirements

Python 3 with `numpy`, `pandas`, `matplotlib`, `seaborn`, `python-dotenv` and `SciServer`.

The SDSS query needs SciServer credentials, loaded from a `.env` file. To skip the query, load the CSV files provided instead (the `pd.read_csv` lines are commented out in the notebook).
