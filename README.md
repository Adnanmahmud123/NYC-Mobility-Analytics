# NYC Mobility & Environmental Analytics

**An End-to-End Data Engineering and Business Intelligence Project using Microsoft Fabric**

## 1. Project Overview

NYC Mobility & Environmental Analytics is an end-to-end data engineering and analytics project built using Microsoft Fabric.

The project combines NYC Yellow Taxi trip data, air quality measurements, foreign exchange rates, and economic indicators to provide insights into urban mobility, environmental conditions, and economic trends.

The solution follows the Medallion Architecture (Bronze, Silver, and Gold) and integrates data engineering, data warehousing, semantic modeling, and business intelligence.

## 2. Project Objectives

- Build an automated end-to-end data engineering pipeline.
- Ingest data from multiple external sources.
- Clean and transform raw datasets.
- Implement a scalable Medallion Architecture.
- Build analytical fact and dimension tables.
- Create a centralized SQL Data Warehouse.
- Develop a Direct Lake semantic model.
- Build an interactive Power BI dashboard.
- Maintain project code and definitions in GitHub.

## 3. Technology Stack

| Technology | Purpose |
|---|---|
| Microsoft Fabric | Unified analytics platform |
| Fabric Lakehouse | Data storage |
| Fabric Notebooks | Data ingestion and transformation |
| Fabric Data Pipelines | Workflow orchestration |
| Python | Data processing |
| PySpark | Large-scale data transformation |
| SQL | Data analysis and warehouse queries |
| Power BI | Interactive reporting |
| Direct Lake | Semantic model storage mode |
| GitHub | Version control and source backup |

## 4. Data Sources

The project integrates the following data sources:

### NYC Yellow Taxi
Provides taxi trip records, including pickup dates, locations, passengers, distances, and fare information.

### OpenAQ
Provides PM2.5 air quality measurements for environmental analysis.

### European Central Bank (ECB)
Provides foreign exchange rates used for currency conversion and financial analysis.

### World Bank
Provides GDP indicators for economic trend analysis.

### NYC Taxi Zone Lookup
Provides taxi zone identifiers and location information for geographic analysis.

## 5. Data Architecture

The project follows the Medallion Architecture.

**Bronze → Silver → Gold → Data Warehouse → Semantic Model → Power BI Dashboard**

### Bronze Layer
- Ingest raw NYC Yellow Taxi data.
- Ingest OpenAQ air quality measurements.
- Ingest ECB exchange rate data.
- Ingest World Bank GDP indicators.
- Ingest NYC Taxi Zone lookup data.

### Silver Layer
- Clean and transform raw datasets.
- Handle missing and invalid values.
- Standardize data types.
- Prepare analytical datasets.

### Gold Layer
Create business-ready fact and dimension tables.

## 6. Gold Data Model

### Fact Tables

| Table | Description |
|---|---|
| FactTaxiDaily | Daily taxi activity, revenue, distance, and passenger metrics |
| FactAirQualityDaily | Daily PM2.5 air quality measurements |

### Dimension Tables

| Table | Description |
|---|---|
| DimDate | Calendar and date attributes |
| DimZone | NYC taxi zone information |
| DimFX | Foreign exchange rates |
| DimGDP | GDP economic indicators |
| DimYear | Year-based analytical dimension |

## 7. Data Warehouse

The project uses a Microsoft Fabric Data Warehouse for centralized analytical querying.

SQL views support reporting and analytical use cases, including:

- Taxi revenue converted between USD and EUR.
- Taxi activity analysis.
- Geographic revenue analysis.
- Foreign exchange rate analysis.

## 8. Semantic Model

A Direct Lake semantic model connects the Gold analytical tables.

The model includes relationships between fact and dimension tables to support interactive reporting.

Key analytical measures include:

- Total Trips
- Total Revenue
- Total Passengers
- Average Fare
- Average Trip Distance
- Average Trip Duration
- Average PM2.5

## 9. Power BI Dashboard

**Dashboard Title:** NYC Mobility & Environmental Analytics Dashboard

The dashboard focuses on:

- Total Taxi Trips
- Total Revenue
- Total Passengers
- Average Fare
- Taxi Trips by Borough
- Revenue by Borough
- Daily Taxi Demand
- Daily Taxi Activity Trends
- Air Quality and PM2.5 Analysis
- USD/EUR Exchange Rate Trends
- GDP Trends and Economic Indicators

Interactive filters support analytical exploration by date, year, and borough where applicable.

## 10. Pipeline Orchestration

The project includes a master Fabric Data Pipeline:

`PL_NYC_Mobility_Master`

The master pipeline coordinates 17 activities, including:

- NYC Taxi ingestion and transformation.
- OpenAQ ingestion and transformation.
- ECB exchange rate ingestion and transformation.
- World Bank GDP ingestion and transformation.
- NYC Taxi Zone ingestion and transformation.
- Gold dimension and fact table creation.
- Warehouse loading.

Existing child pipelines:

- `PL_Ingest_NYC_Taxi`
- `PL_Load_Gold_To_Warehouse`

The pipeline definition is maintained in the repository as a JSON backup.

## 11. Repository Structure

```text
NYC-Mobility-Analytics/
│
├── README.md
│
├── pipeline-content.json
│
├── NB_01_...ipynb
├── NB_02_...ipynb
├── NB_03_...ipynb
├── ...
├── NB_15_...ipynb
│
├── Notebook 1.ipynb
│
├── 01_TaxiRevenue_USD_EUR.sql
│
└── 02_DimFX_Latest_Records.sql
```

*Notebook filenames above are representative. Refer to the actual files in the repository for their exact names.*

## 12. SQL Examples

### Taxi Revenue Analysis

```sql
SELECT TOP 10 *
FROM dbo.vw_TaxiRevenue_USD_EUR
ORDER BY date;
```

### Latest Foreign Exchange Records

```sql
SELECT TOP 10 *
FROM dbo.DimFX
ORDER BY [date] DESC;
```

## 13. Data Quality and Validation

Data quality checks are performed during the transformation process.

Examples include:

- Checking missing values.
- Validating taxi trip records.
- Checking invalid fare values.
- Validating location identifiers.
- Checking date coverage.
- Validating transformed analytical tables.

## 14. Security and Deployment Notes

- API keys and credentials are excluded from the repository.
- Sensitive configuration values should be stored securely.
- Pipeline definitions reference existing Fabric workspace item IDs.
- Notebook and pipeline references must be verified before deployment.
- The pipeline JSON is a source definition backup, not a standalone deployment executable.
- External API availability and data coverage may affect pipeline execution.

## 15. Project Status

The project includes:

- Data ingestion workflows.
- Bronze, Silver, and Gold data layers.
- Analytical fact and dimension tables.
- Fabric Data Warehouse.
- SQL analytical views.
- Direct Lake semantic model.
- Power BI dashboard.
- Master pipeline orchestration.
- GitHub source backups.

## 16. Future Improvements

Potential future enhancements include:

- Automated data quality monitoring.
- Improved pipeline failure notifications.
- Historical data expansion.
- Additional environmental indicators.
- Advanced forecasting and predictive analytics.
- Automated deployment and CI/CD.

## 17. Author

GitHub: [Adnanmahmud123](https://github.com/Adnanmahmud123)

Repository: [NYC-Mobility-Analytics](https://github.com/Adnanmahmud123/NYC-Mobility-Analytics)

---

*Built with Microsoft Fabric, Python, PySpark, SQL, and Power BI.*
