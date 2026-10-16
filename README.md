# TTC Service Reliability Analytics
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

## Power BI Dashboard

**[View Interactive Power BI Dashboard](https://app.powerbi.com/view?r=eyJrIjoiMmYxMGYyYWEtZDhjNy00ZTU0LWFjNzUtZmRkNTc5NDA3YzRhIiwidCI6IjJiOTBmNjgwLTBjNzMtNDU4NC05Y2U1LWM5MzQzMTk0MzlkMSJ9)**

The interactive Power BI dashboard provides a consolidated view of TTC service reliability and allows users to explore delay patterns across different transit modes, routes, locations, and time periods.

The dashboard includes:

- KPI cards for total incidents, delay incidents, average delay, and average service gap.
- Delay analysis across Bus, Subway, Streetcar, and LRT.
- Most affected routes and subway lines.
- Analysis of the most common identified delay causes.
- Day-of-week and hourly delay patterns.
- Monthly delay trends.
- Interactive filters and drill-through analysis.

### Dashboard Preview

![TTC Service Reliability Dashboard](TTC%20Dashboard.png)

### Fabric Data Pipeline

![Microsoft Fabric Medallion Data Pipeline](Medallion%20Data%20Pipeline.png)

## Technologies Used

- **Microsoft Fabric** – Data engineering, Lakehouse, OneLake, and pipeline orchestration
- **PySpark** – Data cleaning and transformation
- **Delta Lake** – Silver and Gold layer tables
- **Power BI** – Data modeling, DAX, and interactive dashboard development
- **Toronto Open Data** – Source for TTC transit delay datasets

## Repository Structure

```text
ttc-service-reliability-analytics/
├── README.md
├── TTC Dashboard.png
├── Medallion Data Pipeline.png
└── notebooks/
    ├── README.md
    ├── NB_TTC_Bronze_Ingestion.ipynb
    ├── NB_TTC_Silver_Transformation.ipynb
    └── NB_TTC_Gold_Transformation.ipynb
```
