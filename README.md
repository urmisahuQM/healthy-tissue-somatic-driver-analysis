# Healthy Tissue Somatic Driver Analysis

Python analysis associated with an MSc dissertation investigating somatic driver gene expression and damaging mutation patterns in healthy colon, lung and endometrium.

## Analysis notebooks

- `colon_somatic_driver_analysis.ipynb`
- `lung_somatic_driver_analysis.ipynb`
- `endometrium_somatic_driver_analysis.ipynb`

## Data sources

- Human Protein Atlas (HPA): single-cell RNA sequencing data
- SomaMutDB: healthy tissue somatic mutation data
- Network of Cancer Genes (NCG): healthy tissue somatic driver gene lists

## Analysis overview

The analysis was performed separately for colon, lung and endometrium and included:

- processing and log-normalisation of HPA single-cell RNA-sequencing data
- annotation of cells using HPA cell-type classifications
- analysis of somatic driver gene expression levels
- analysis of expression breadth across cell types
- identification and characterisation of damaging somatic mutations
- calculation of damaged somatic driver gene burden across samples and donors
- linear regression analysis of damaged driver gene burden with donor age
- classification of damaging mutations according to predicted functional consequence
- comparison of somatic driver genes across healthy tissues
