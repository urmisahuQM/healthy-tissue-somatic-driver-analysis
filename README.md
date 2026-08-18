# Healthy Tissue Somatic Driver Analysis

Python analysis associated with an MSc Cancer Genomics and Data Science dissertation investigating the expression and mutation patterns of somatic driver genes in healthy human tissues.

The project examines whether somatic driver genes identified in healthy tissues show cell type-specific expression patterns and characterises damaging somatic mutations across healthy colon, lung and endometrium.

## Analysis notebooks

The repository contains separate Jupyter notebooks for each tissue:

- `colon_somatic_driver_analysis.ipynb`
- `lung_somatic_driver_analysis.ipynb`
- `endometrium_somatic_driver_analysis.ipynb`

Each notebook contains the data processing, analysis and figure-generation workflow for the corresponding tissue.

## Data sources

The analysis integrates data from three publicly available resources:

- **Human Protein Atlas (HPA)** – single-cell RNA-sequencing data and cell-type annotations.
- **SomaMutDB** – somatic mutation data from healthy human tissues.
- **Network of Cancer Genes (NCG)** – somatic driver gene lists and cancer driver classifications.

## Analysis overview

The analysis was performed separately for colon, lung and endometrium and included:

- processing and log-normalisation of HPA single-cell RNA-sequencing data
- annotation and aggregation of cells using HPA cell-type classifications
- analysis of somatic driver gene expression levels across cell types
- analysis of expression breadth, defined as the proportion of cells expressing each somatic driver gene
- identification and characterisation of damaging somatic mutations
- calculation of the number and proportion of samples and donors harbouring damaging mutations in each somatic driver gene
- calculation of damaged somatic driver gene burden across samples and donors
- linear regression analysis of the relationship between donor age and damaged somatic driver gene burden
- classification of damaging mutations according to predicted functional consequence
- comparison of somatic driver genes across healthy tissues

## Expression analysis

Raw single-cell gene expression counts were normalised to library size and scaled to 10,000 counts per cell, followed by log1p transformation.

Expression was examined using two complementary measures:

1. **Expression level** – average log-normalised expression of each somatic driver gene within each annotated cell type.
2. **Expression breadth** – proportion of cells within each annotated cell type expressing each somatic driver gene.

## Mutation analysis

Somatic mutations were obtained from SomaMutDB and matched to the somatic driver genes analysed in each tissue.

Mutations annotated as damaging or as mutational hotspots were retained for downstream analyses.

For each somatic driver gene, the number and proportion of unique samples and donors harbouring at least one damaging mutation were calculated.

### Damaged somatic driver gene burden

A somatic driver gene was considered damaged when it harboured at least one damaging mutation.

Samples and donors were grouped according to the number of damaged somatic driver genes they contained:

- 0
- 1
- 2
- 3
- >3

The proportion of samples and donors within each category was then calculated.

### Functional classification

Damaging mutations were grouped into broad functional categories based on their annotations:

- Loss of function
- Gain of function
- Other nonsynonymous

Frameshift, stop-gain and stop-loss mutations were classified as loss of function. Mutational hotspots were classified as gain of function, while remaining damaging mutations were classified as other nonsynonymous mutations.

## Donor age analysis

Linear regression was used to investigate the relationship between donor age and damaged somatic driver gene burden.

For each donor, burden was defined as the number of unique somatic driver genes harbouring at least one damaging mutation.

The coefficient of determination (R²) and corresponding P value were used to assess the strength and statistical significance of the association.

## Data availability

The datasets analysed in this project were obtained from publicly available resources and are not redistributed in this repository due to their size.

The original datasets can be obtained from:

- Human Protein Atlas (HPA)
- SomaMutDB
- Network of Cancer Genes (NCG)

The notebooks contain the analysis workflow used to process these datasets and generate the results presented in the dissertation.

## Software

The analyses were performed in Python using Jupyter Notebook.

Major Python packages used in the analysis include:

- pandas
- NumPy
- Matplotlib
- SciPy
- statsmodels

Additional package requirements can be determined from the import statements provided within the notebooks.

## Repository structure

    healthy-tissue-somatic-driver-analysis/
    │
    ├── README.md
    ├── colon_somatic_driver_analysis.ipynb
    ├── lung_somatic_driver_analysis.ipynb
    └── endometrium_somatic_driver_analysis.ipynb

## Reproducibility

The notebooks represent the computational workflows used for the analyses reported in the dissertation.

The original datasets are not included in the repository. Therefore, users wishing to reproduce the analyses will need to obtain the corresponding datasets from the original data sources and update the input file paths within the notebooks as required.

## Author

Urmi Sahu  
MSc Cancer Genomics and Data Science  
Queen Mary University of London

## Academic use

This repository accompanies an MSc dissertation and is provided to support transparency and reproducibility of the computational analyses.
