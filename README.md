# UK Police Crime Data Pipeline & Reporting Dataset

## Overview
Developed as part of Rockborne's Data and AI Training Academy, this project delivers a transformed and aggregated crime and enrichment dataset which is ready for BI use.

## Scope & Target Forces
To provide meaningful comparative analysis along a key geographic corridor, the dashboard focuses on four representative police forces spanning the commuter belt across a 5-year period from 2019 to 2024:
* Metropolitan Police
* Surrey Police
* Sussex Police
* Thames Valley Police

## Pipeline Architecture & Methodology
* Iterative Ingestion & Cleaning: Pulls raw monthly crime records using a file-system batch processing loop to protect system memory, automatically skipping redundant whitespace, handling null values and dropping over 1M duplicate rows.
* Feature Engineering & Enrichment: Integrates ONS annual population statistics and English Indices of Deprivation using explicity join keys (Force, Year) to prevent many-to-many errors and derive per-capita metrics.
* Granular Aggregation: Compresses individual records down to a structured reporting grain (Force X Year X LSOA Name X Crime Type), computing aggregated volumes and averaging coordinates

## Tech Stack & Deliverables
* **Tool:** Python, Pandas, Jupyter Notebook
* **Deliverables:** End-to-end Python processing notebook (processingPipeline.ipynb), Statement of Work, workflow documentation and a clean, reporting-ready CSV dataset
