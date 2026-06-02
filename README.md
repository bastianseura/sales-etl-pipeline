# Sales Data Pipeline

## Project Overview

This project builds a structured sales dataset from multiple exports of a business sales system.

The original system allowed exporting detailed sales transactions by product, but the report did not clearly identify whether each sales document was still valid or had been cancelled later. Because of this, the raw sales detail could contain transactions that should not be included in business analysis.

To solve this, the project automates the extraction of detailed sales reports, organizes the raw files, and prepares the data for later validation, cleaning and analysis.

## Business Problem

The company needed a reliable sales dataset to analyze product sales, customers, revenue and historical trends.

However, the available sales reports had an important limitation:

- The detailed sales report included product-level transactions.
- A separate report was required to identify valid sales documents.
- Cancelled documents had to be removed before performing any analysis.
- Manual extraction was repetitive and time-consuming.

Without this process, revenue, product performance and customer analysis could be distorted.

## Solution

The solution was designed as a data pipeline with the following stages:

1. Automated extraction of daily detailed sales reports using Python and Selenium.
2. Organization of downloaded Excel files by month.
3. Consolidation of all extracted files.
4. Integration with a second report containing valid sales documents.
5. Filtering of cancelled transactions.
6. Data cleaning and type formatting.
7. Export of a final analysis-ready dataset.

## Pipeline

```text
Sales Platform
      ↓
Web Scraping
      ↓
Raw Excel Files
      ↓
File Consolidation
      ↓
Validation with Active Documents
      ↓
Data Cleaning
      ↓
Final Sales Dataset
