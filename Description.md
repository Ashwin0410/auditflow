# Auditflow - Core Module Documentation

The `core.py` file contains the main engine for **Auditflow**, a simple, no-fuss data quality auditing tool. It helps you quickly explore the quality of your data using visual insights and key statistics.

---

## Overview

This module provides:
- Data loading from CSV files
- Missing value analysis and heatmaps
- Data quality checks (duplicates, skewness, constants, cardinality)
- Correlation and memory usage analysis
- HTML reporting with visual charts

---

## Function Reference

---

###  `img_to_base64(img_path)`

**What it does:**  
Converts an image file to a Base64 string so it can be embedded in an HTML report.

**Arguments:**
- `img_path` *(str)* – Path to the image file

**Returns:**  
- Base64 string of the image

---

###  `save_plot(fig, name)`

**What it does:**  
Saves a Matplotlib figure as a PNG image in the `audit_charts` folder. Automatically creates the folder if it doesn’t exist.

**Arguments:**
- `fig` – Matplotlib figure object
- `name` *(str)* – File name for saving the plot

---

###  `load_dataset(file_path)`

**What it does:**  
Loads a CSV file into a Pandas DataFrame.

**Arguments:**
- `file_path` *(str)* – Path to the CSV file

**Returns:**  
- `DataFrame` – Loaded dataset

---

###  `missing_values_analysis(df)`

**What it does:**  
Analyzes missing values in the dataset and generates two visualizations:
1. A heatmap of missing cells
2. A bar chart showing percentage of missing values per column

**Arguments:**
- `df` *(DataFrame)* – Input dataset

**Returns:**  
- Filtered `DataFrame` showing only columns with missing values

---

###  `general_quality_checks(df)`

**What it does:**  
Performs general quality checks on the dataset:
- Counts duplicate rows
- Detects skewed numerical features (and plots them)
- Identifies constant (non-varying) columns
- Finds high-cardinality categorical columns

**Arguments:**
- `df` *(DataFrame)* – Input dataset

**Returns:**  
- `dict` with:
  - `duplicates`
  - `skews`
  - `constants`
  - `cardinals`

---

###  `correlation_and_memory(df)`

**What it does:**  
Analyzes correlation among numerical columns and memory usage of the dataset.

**Outputs:**
- A heatmap of correlations
- A memory usage breakdown per column

**Arguments:**
- `df` *(DataFrame)* – Input dataset

**Returns:**  
- `dict` with:
  - `correlation_matrix`
  - `memory_usage`

---

###  `export_html_report(summary_text)`

**What it does:**  
Creates an HTML report embedding all charts and summaries generated during the audit.

**Arguments:**
- `summary_text` *(str)* – Audit summary or notes to embed in the report

---

###  `run_audit(file_path, save_dir="auditflow_output")`

**What it does:**  
Runs a full data audit:
- Loads the dataset
- Performs missing value, general quality, and memory/correlation checks
- Generates plots
- Saves everything into a specified output directory

**Arguments:**
- `file_path` *(str)* – Path to the dataset
- `save_dir` *(str, default: `"auditflow_output"`) – Directory to save output

---


