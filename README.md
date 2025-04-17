# auditflow
Automated Data Quality Checker &amp; Audit Report Generator for CSV files

# Auditflow

**Automated Data Quality Checker & Audit Report Generator for CSV files**

Auditflow helps data analysts and engineers audit datasets with a single line of code. It checks for missing values, quality issues, memory usage, and even correlation patterns – and exports a complete audit report to a folder. Perfect for data validation, cleaning pipelines, and client-ready deliverables.

---

## Features

- One-line full audit: `run_audit("yourfile.csv")`
- Missing values and null distribution
- Quality checks (duplicates, constant columns, etc.)
- Correlation matrix + memory usage
- All outputs saved to an export folder
- Works in Colab, Jupyter, and production scripts

---

## Installation

```bash
pip install auditflow

