# ttc-service-reliability-analytics
## Project Overview

This project analyzes Toronto Transit Commission (TTC) service delays across Bus, Subway, Streetcar, and Light Rail Transit (LRT) from January 2025 to August 2026.

I built an end-to-end data pipeline in Microsoft Fabric using a Bronze-Silver-Gold Medallion Architecture. PySpark was used to clean and transform more than 176,000 transit incident records, which were modeled and visualized in an interactive Power BI dashboard to analyze delay patterns across routes, locations, time periods, and incident causes.

## Project Architecture

The project follows a Bronze-Silver-Gold Medallion Architecture in Microsoft Fabric:

**Toronto Open Data → Bronze → Silver → Gold → Power BI**

- **Bronze:** Ingests raw TTC Bus, Subway, Streetcar, and LRT delay data from Toronto Open Data into OneLake.
- **Silver:** Cleans and transforms the raw datasets using PySpark, standardizes the data across transit modes, and maps TTC incident codes to descriptions.
- **Gold:** Combines the transformed data and creates analytics-ready fact and dimension tables for reporting.
- **Power BI:** Uses the Gold-layer data to build an interactive service reliability dashboard.

## Automation

The data workflow is automated using Microsoft Fabric Data Pipelines. The pipeline runs the Bronze, Silver, and Gold notebooks on a weekly schedule, followed by refreshes of the semantic model and Power BI dashboard to keep the analysis up to date.
