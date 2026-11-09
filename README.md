# NYC Mobility & Environmental Analytics

An end-to-end analytics project built with Microsoft Fabric, combining NYC Yellow Taxi trip data, air quality measurements, foreign exchange rates, and economic indicators.

## Project Overview

This project demonstrates a modern data engineering and analytics workflow using a Medallion Architecture:

**Bronze → Silver → Gold → Data Warehouse → Semantic Model → Power BI Report**

The goal is to analyze NYC taxi mobility patterns alongside environmental and economic indicators.

## Technology Stack

- Microsoft Fabric
- Fabric Data Engineering Notebooks
- Fabric Data Pipelines
- Lakehouse and Warehouse
- Power BI
- SQL
- Python
- GitHub

## Data Sources

- NYC Yellow Taxi trip data
- OpenAQ PM2.5 air quality measurements
- European Central Bank (ECB) exchange rates
- World Bank GDP indicators
- NYC Taxi Zone lookup data

## Architecture

1. **Bronze:** Raw source data ingestion.
2. **Silver:** Data cleaning, transformation, and validation.
3. **Gold:** Analytical fact and dimension tables.
4. **Warehouse:** SQL-based analytical views and reporting tables.
5. **Semantic Model:** Relationships and analytical measures.
6. **Dashboard:** Interactive visualizations and filtering.

## Main Gold Tables

| Table | Description |
|---|---|
| FactTaxiDaily | Daily taxi activity and revenue |
| FactAirQualityDaily | Daily PM2.5 measurements |
| DimDate | Date dimension |
| DimZone | NYC taxi zone dimension |
| DimFX | Foreign exchange rates |
| DimGDP | GDP indicators |
| DimYear | Year dimension |

## Dashboard Features

- Total Trips
- Total Revenue
- Total Passengers
- Average Fare
- Daily Average PM2.5
- Taxi Trips by Borough
- Daily Taxi Trips Trend
- Revenue by Borough
- Daily Taxi Demand
- USD per EUR Exchange Rate Trend
- GDP Trend by Year
- GDP Growth Trend
- Year and Borough slicers

## Pipeline Orchestration

The master pipeline `PL_NYC_Mobility_Master` coordinates 17 activities covering ingestion, cleaning, Gold transformations, and warehouse loading.

## Repository Structure

```text
NYC-Mobility-Analytics/
│
├── README.md
├── pipeline-content.json
├── *.ipynb
│
└── NYC_Mobility_SQL/
    ├── 01_TaxiRevenue_USD_EUR.sql
    └── 02_DimFX_Latest_Records.sql
```

*The notebook and pipeline files are maintained as source backups. Their actual filenames and folder locations may vary.*

## Important Notes

- API keys and credentials must never be committed to GitHub.
- Pipeline definitions reference existing Fabric workspace item IDs.
- Verify notebook and pipeline references before redeployment.
- The dashboard reflects the available source data and its coverage limitations.

## Project Status

Core data ingestion, transformations, warehouse loading, semantic modeling, and dashboard development have been completed. Source-code backup is maintained in this repository.

## Author

S.M. Adnan Mahmud
