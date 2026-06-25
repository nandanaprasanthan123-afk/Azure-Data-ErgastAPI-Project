Formula1 Drivers Data Analytics using Azure

## Project Overview

This project is an end-to-end Azure Data Engineering solution built using Formula 1 driver data from the OpenF1 API.

The project demonstrates data ingestion, storage, transformation, automation, and reporting using Azure cloud services and Databricks.

The data is extracted from the OpenF1 API, stored in Azure Data Lake Storage Gen2, transformed using Azure Databricks, and prepared for reporting in Power BI.

---

## Architecture

OpenF1 API
      ↓
Raww Layer (ADLS Gen2)
      ↓
Processed Layer (Databricks + Delta Lake)
      ↓
Presentation Layer
      ↓
Power BI Dashboard

---

## Technologies Used

- Azure Data Lake Storage Gen2
- Azure Databricks
- Delta Lake
- Azure Data Factory
- Power BI
- Python
- Apache Spark
- OpenF1 API

---

## Project Workflow

### 1. Data Ingestion

Formula 1 driver data is collected from the OpenF1 API using Python requests.

The extracted JSON data is converted into a Spark DataFrame and stored in the Raw Layer of Azure Data Lake Storage Gen2.

### 2. Raww Layer

The Raww Layer stores the original data received from the API without modifications.

Purpose:
- Preserve source data
- Support reprocessing if required
- Maintain data lineage

### 3. Processed Layer

Data is cleaned and transformed using Azure Databricks.

Transformations include:
- Selecting required columns
- Handling null values
- Structuring data for analytics

### 4. Presentation Layer

Business-ready datasets are created for reporting and dashboarding.

Generated datasets:
- Team-wise Driver Count
- Total colour vs drivercount
- Driver Profile Dataset

### 5. Automation

Databricks Workflow/Jobs are used to automate the execution of notebooks.

Workflow:

Ingestion Notebook
      ↓
Processed Notebook
      ↓
Presentation Notebook

### 6. Reporting

The presentation datasets are exported as CSV files and consumed by Power BI for dashboard creation.

---

## Insights Generated

### Team colour vs drivercount
The analysis grouped the data by team name and team colour and counted the number of unique drivers in each team .

### Team-wise Driver Count
Shows the number of drivers associated with each team.

### Driver Profile
Provides driver information including:
- Driver Number
- Driver Name
- Team Name
- Driver Acronym

---

## Repository Structure

```text
Azure-Data-ErgastAPI-Project

├── notebooks
│   ├── 01_data_ingestion.py
│   ├── 02_data_processing.py
│   └── 03_presentation_layer.py
│
├── screenshots
│   ├── architecture_diagram.png
│   ├── workflow.png
│   └── powerbi_dashboard.png
│
├── sample_data
│   ├── team_analysis.csv
│   ├── teamcolour_analysis.csv
│   └── driver_profile.csv
│
└── README.md
```

---

## Future Enhancements

- Real-time streaming pipeline
- Additional Formula 1 datasets
- Advanced Power BI analytics
- CI/CD integration using Azure DevOps

---

## Author

Nandana.K.K

Azure Data Engineering Project
