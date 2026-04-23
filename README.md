# Homework 4 – HCRIS Analysis
**Course:** Econ 470 - Research in Health Economics 
**Author:** Zara Mecklai
**Final Version:** hwk4s3.ipynb (Submission 3)

---

## Overview

This project analyzes hospital cost and pricing data using the Hospital Cost Report Information System (HCRIS). The analysis covers data from 2009–2019 and estimates the effects of HRRP/VBP penalties on hospital prices using OLS and instrumental variables (IV) methods.

---

## Repository Structure

All scripts live in the `hwk4/` folder on Open On Demand. There are no subfolders — the files are flat:

| File | Purpose |
|---|---|
| `H1_HCRISv1996.ipynb` | Cleans and processes HCRIS v1996 data |
| `H2_HCRISv2010.ipynb` | Cleans and processes HCRIS v2010 data |
| `HCRIS-data.ipynb` | Combines v1996 and v2010 into a single final dataset |
| `hwk4s3.ipynb` | **Final submission** — all analysis and figures |

---

## Data Access (Open On Demand)

> **Raw data is NOT included in this repository.** It is accessed via the shared course data on Open On Demand.

The scripts assume the following directory layout on Open On Demand:

```
work/
├── data/
│   └── output/
│       ├── HCRIS_Data_v1996.csv
│       ├── HCRIS_Data_v2010.csv
│       └── HCRIS_Data.csv          ← final combined file used in hwk4s3.ipynb
└── hwk4/
    ├── H1_HCRISv1996.ipynb
    ├── H2_HCRISv2010.ipynb
    ├── HCRIS-data.ipynb
    └── hwk4s3.ipynb
```

The data output files are written to `../data/output/` relative to the `hwk4/` folder. As long as your folder structure on Open On Demand mirrors the above, paths should work without any changes.

---

## How to Replicate

Follow these steps **in order**:

### Step 1 — Generate the v1996 dataset
Open and run all cells in:
```
H1_HCRISv1996.ipynb
```
This reads raw HCRIS v1996 files and writes:
```
../data/output/HCRIS_Data_v1996.csv
```

### Step 2 — Generate the v2010 dataset
Open and run all cells in:
```
H2_HCRISv2010.ipynb
```
This reads raw HCRIS v2010 files and writes:
```
../data/output/HCRIS_Data_v2010.csv
```

### Step 3 — Combine into final dataset
Open and run all cells in:
```
HCRIS-data.ipynb
```
This merges the two versioned datasets and writes:
```
../data/output/HCRIS_Data.csv
```

### Step 4 — Run the final analysis
Open and run all cells in:
```
hwk4s3.ipynb
```
This is the **main submission file** containing all answers, figures, and tables for the assignment.

---

## Dependencies

The analysis is written in **R** and uses the following packages. Make sure they are installed before running:

```r
install.packages(c(
  "tidyverse",
  "ggplot2",
  "dplyr",
  "readr",
  "fixest",     # for IV/2SLS estimation
  "modelsummary" # for regression tables
))
```

---

## Notes for the Reviewer

- The only change you should need to make is ensuring your Open On Demand folder structure matches the layout shown above. No hardcoded absolute paths are used — all paths are relative.
- If you run into a file-not-found error, check that the `data/output/` folder exists one level up from where `hwk4/` lives.
- Steps 1–3 must be completed before Step 4 will run, since `hwk4s3.ipynb` reads from the combined `HCRIS_Data.csv`.
- If you have already run the data setup scripts for your own homework, your `../data/output/` folder likely already contains the needed files and you can skip straight to Step 4.
