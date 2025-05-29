#️ SVD-Based Electoral Analysis of Paris Elections

This project performs a structured analysis of Parisian electoral data using singular value decomposition (SVD) and principal component analysis (PCA). It provides insight into voter behavior, ideological structures, and temporal stability across multiple types of elections.

## Project Overview

- **Scope**: Five different Elections in Paris from 2000 to 2022.
- **Methods**: Data cleaning, vote matrix extraction, dimensionality reduction via PCA/SVD
- **Tools**: R, `FactoMineR`, `ggplot2`, `readxl`, `janitor`

The project is fully reproducible via an R Markdown pipeline and includes graphical outputs saved in organized directories.

## Folder Structure
├── XXXXX_processed/            # Cleaned vote matrices
├── PCA_results/                # PCA plots and coordinates
├── Présidentielles/            # Original Excel files
├── Législatives/               # Original Excel files
├── Municipales/                # Original Excel files
├── Régionales/                 # Original Excel files
├── Européennes/                # Original Excel files
├── codeForTests.Rmd            # Main RMarkdown analysis file
├── README.md                   # Project description


## ⚙️ How to Reproduce

To generate the full report:

1. Open `codeForTests.Rmd` in RStudio.
2. Ensure all required packages are installed (see below).
3. Knit to **HTML** or **PDF**.

> **Note**: Due to the large number of images, only the *Présidentielles* PCA results are embedded in the HTML report. Other plots are saved in `PCA_results/`.

## Election Types Covered

- Présidentielles (Presidential)
- Législatives (Legislative)
- Régionales (Regional)
- Européennes (European Parliament)
- Municipales (Municipal)

## Data Processing Pipeline

- Organized by directory (`type/year/round`)
- File parsing using regex patterns
- Vote matrix extraction per polling station
- Standardized cleaning:
  - `janitor::clean_names()`
  - Type enforcement
  - Missing value imputation (`NA → 0` for vote counts)

## Required R Packages

```r
install.packages(c(
  "tidyverse", "readxl", "janitor", "FactoMineR",
  "factoextra", "writexl"
))



