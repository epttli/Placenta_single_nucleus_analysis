# Placenta snATAC preprocessing for scE2G

This repository contains code used to preprocess and integrate human placental snATAC-seq data from early and term pregnancy, and to transfer cell type labels from a paired multiome reference, in order to generate inputs for scE2G.

## Repository contents
- `code/`  
  R Markdown notebooks for each analysis step (QC, integration, dimensionality testing, label transfer).
- `scripts/`  
  Example bash scripts showing how raw snATAC-seq data were downloaded and processed using Cell Ranger ATAC.
- `results/`  
  Optional output figures generated during analysis.

## Data availability
- Raw snATAC-seq data: GEO accession **GSE247038**
- Paired snRNA-seq/snATAC-seq multiome reference: Single Cell Portal accession **SCP2601**

Raw sequencing files, Cell Ranger outputs, and reference files are not included in this repository.

## How to run
1. Install required R packages (e.g. Seurat, Signac).
2. Download the data from the sources listed above.
3. Update file paths in the scripts and notebooks as needed.
4. Run the R Markdown notebooks in `code/` in order.

## Notes
- Large files (FASTQs, fragment files, matrices, references) are intentionally excluded.
- File paths are defined explicitly in each script/notebook and should be adapted to the local environment.
