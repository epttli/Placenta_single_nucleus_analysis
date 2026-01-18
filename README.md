# Placenta snATAC preprocessing for scE2G

This repository contains code used to preprocess and integrate human placental
single-nucleus ATAC-seq (snATAC-seq) data from early and term pregnancy, and to
transfer cell type labels from an snRNA-seq reference dataset.
The resulting objects are intended as inputs for downstream enhancer–gene
interaction inference using scE2G.

## Repository structure

- `download_pileup_raw_data/`  
  Example bash scripts illustrating how raw snATAC-seq data were downloaded from
  GEO and processed using Cell Ranger ATAC.  
  These scripts are provided for documentation and reproducibility purposes only.
  
- `snATAC_integration.Rmd`  
  R Markdown notebook for loading, QC filtering, donor integration, dimensionality
  testing, UMAP visualization, and saving the integrated snATAC-seq object.

- `snRNA_labels.Rmd`  
  R Markdown notebook for preprocessing the snRNA-seq component of the paired
  multiome dataset and attaching study-provided cell type labels.  
  This object is used as the RNA reference for label transfer.

- `label_transfer.Rmd`  
  R Markdown notebook for computing gene activity, finding transfer anchors, and
  transferring cell type labels from the snRNA-seq reference to the integrated
  snATAC-seq dataset.



## Data availability

The data used in this project are publicly available:

- Raw snATAC-seq data (early and term placenta):  
  **GEO accession:** GSE247038

- Paired snRNA-seq / snATAC-seq multiome reference:  
  **Single Cell Portal accession:** SCP2601

Raw sequencing files, Cell Ranger outputs, reference genomes, and large intermediate
files are **not included** in this repository.

## How to run

1. Install required R packages (e.g. `Seurat`, `Signac`, `rtracklayer`, `GenomeInfoDb`).
2. Download the datasets from the sources listed above.
3. Update file paths in the R Markdown notebooks to match your local environment.
4. Run the notebooks in the following order:
   1. `snRNA_labels.Rmd`
   2. `snATAC_integration.Rmd`
   3. `label_transfer.Rmd`

## Notes

- Large files (FASTQs, fragment files, matrices, references, `.rds` objects) are
  intentionally excluded from version control.
- File paths are defined explicitly within each script/notebook and should be
  adapted as needed.
