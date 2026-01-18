# Placenta snATAC preprocessing for scE2G

This repository contains code used to preprocess and integrate placental snATAC-seq (early + term donors) and transfer cell type labels from a paired multiome reference, to generate inputs for scE2G.

## Contents
- `code/` R Markdown notebooks for each analysis step
- `data/` instructions for obtaining public datasets (no raw data stored here)
- `results/` optional outputs/figures

## Data
Raw snATAC-seq: GEO GSE247038 (Cell Ranger ATAC processed per donor)  
Multiome reference: SCP2601 (Single Cell Portal)

See `data/README.md` for download notes and expected file structure.

## How to run
1. Install required R packages (Seurat, Signac, etc.)
2. Run notebooks in `code/` in order:
   - `01_...Rmd`
   - `02_...Rmd`
   - ...

## Notes
- Large files (FASTQs, fragments, matrices) are not tracked in this repo.
- Set file paths at the top of each notebook.
