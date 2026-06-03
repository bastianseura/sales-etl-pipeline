# Sales ETL Pipeline

## Overview

This project documents the complete process of transforming raw sales exports into a validated and analysis-ready dataset.

The original sales platform provided detailed product-level sales reports, but these reports alone were not sufficient for reliable business analysis. Additional validation was required to identify active sales documents and remove cancelled transactions.

To solve this problem, an automated ETL pipeline was developed using Python, Selenium and Pandas.

The pipeline automates data extraction, consolidates multiple report files, validates transactions against active sales documents and produces a clean dataset ready for analytics.

---

## Business Problem

The company required a reliable historical sales dataset to support:

* Revenue analysis
* Product performance analysis
* Customer analytics
* Business reporting
* Forecasting and machine learning projects

However, the available reports presented several limitations:

* Detailed sales reports contained product-level transactions but did not clearly indicate whether documents remained active.
* A second report was required to identify valid sales documents.
* Cancelled transactions had to be removed before analysis.
* Report extraction was repetitive and time-consuming.
* Multiple files had to be consolidated manually.

Without a validation process, key business metrics such as revenue, product demand and customer behavior could be distorted.

---

## Solution

A two-stage ETL pipeline was designed and implemented.

### Stage 1 — Sales Data Extraction

Automated extraction of daily sales reports from the sales platform.

Main tasks:

* Login automation
* Date filtering
* Excel report export
* Download management
* File organization by period

Tools:

* Python
* Selenium
* WebDriver Manager

### Stage 2 — Sales Data Consolidation and Validation

Consolidation of extracted reports and validation against active sales documents.

Main tasks:

* Batch loading of Excel reports
* Dataset consolidation
* Folio validation
* Removal of cancelled transactions
* Duplicate removal
* Export of validated dataset

Tools:

* Python
* Pandas
* Excel

---

## ETL Pipeline

```text
┌──────────────────────┐
│   Sales Platform     │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Automated Extraction │
│      (Selenium)      │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   Raw Excel Reports  │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Dataset Consolidation│
│      (Pandas)        │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Document Validation  │
│  Active Documents    │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   Clean Dataset      │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Analytics Ready Data │
└──────────────────────┘
```

---

## Project Outcome

The final output of this pipeline is a validated sales dataset that:

* Consolidates multiple daily sales exports.
* Removes cancelled transactions.
* Preserves product-level sales detail.
* Standardizes data structure.
* Serves as the foundation for analytics and forecasting projects.

---

## Project Structure

```text
sales-etl-pipeline/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   ├── 01_sales_data_extraction.ipynb
│   └── 02_sales_data_consolidation_validation.ipynb
│
└── images/
```

---

## Technologies

* Python
* Pandas
* Selenium
* Jupyter Notebook
* Excel
* Git
* GitHub

---

## Skills Demonstrated

* ETL Design
* Data Extraction
* Web Scraping
* Data Validation
* Data Cleaning
* Data Quality Control
* Python Automation
* Pandas
* Selenium
* Excel Processing
* Business Data Preparation

---

## Notebooks

### 01 — Sales Data Extraction

Automates the extraction of daily sales reports from the sales platform.

Key features:

* Automated authentication
* Dynamic date filtering
* Automated Excel downloads
* File organization by period
* Reproducible extraction process

### 02 — Sales Data Consolidation and Validation

Combines extracted reports into a single dataset and validates transactions against active sales documents.

Key features:

* Multi-file consolidation
* Folio-based validation
* Removal of cancelled transactions
* Duplicate detection and removal
* Quality control reporting

---

## Output

The resulting dataset contains:

* Product-level sales transactions
* Active sales documents only
* Consolidated historical records
* Standardized structure for analysis

The dataset is ready to be consumed by:

* Power BI dashboards
* KPI reporting
* Customer analytics
* Product analytics
* Revenue analysis
* Forecasting models
* Machine learning projects

---

## Security and Privacy

Credentials, proprietary business information and production datasets are not included in this repository.

Authentication is handled through environment variables and sensitive business data has been excluded from version control.

---

## Repository Scope

This repository focuses exclusively on the ETL process required to create a reliable sales dataset.

Business analytics, dashboard development and predictive modeling are intentionally maintained as separate projects that consume the dataset generated by this pipeline.

Future repositories may include:

* Sales Analytics
* Customer Segmentation
* Demand Forecasting
* Power BI Dashboards
* Machine Learning Applications
