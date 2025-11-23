# INFOSYS-INTERNSHIP-6.0
This is the project file of Azure Based Demand Forecasting &amp; Capacity Optimization System of Infosys 6.0 internship.

Architecture of the project:-
![WhatsApp Image 2025-11-22 at 18 16 06_f9e224ed](https://github.com/user-attachments/assets/dbcd8f3c-8f32-4f86-ab04-87857cf29b64)
This project implements an end-to-end cloud-based forecasting system designed to predict Azure Compute and Storage demand. The workflow integrates multi-cloud data ingestion, scalable storage, advanced feature engineering, machine learning model training, and Power BI–based visualization to support Azure’s capacity planning and supply chain decision-making. image

1. Data Sources

The solution brings together data from three major platforms:

Snowflake DB – provides structured enterprise usage and infrastructure data.
Google Cloud Platform (GCP) – supplies external cloud usage signals and demand indicators.
Render API – provides API-level real-time consumption metrics. These diverse sources create a rich dataset combining internal and external demand drivers.
image
2. Data Ingestion Layer

All incoming data is ingested through:

✔ Azure Data Factory (ADF)

Automates ingestion workflows
Connects securely to Snowflake, GCP, and API endpoints
Handles scheduling, pipelines, and logging
✔ Azure Data Lake Storage (ADLS)

Acts as the centralized raw data storage location
Stores data in hierarchical folders for easy integration with Databricks This ensures scalable, fault-tolerant data handling capable of growing with Azure’s infrastructure signals.
image
3. Data Processing Layer (Azure Databricks)

Azure Databricks is the core data processing and ML environment in this architecture.

✔ Bronze Layer (Raw Data)

Stores unprocessed data exactly as received
Maintains full data lineage and fidelity
✔ Silver Layer (Clean + Enriched Data)

Data cleaning applied
Feature engineering performed (lags, moving averages, seasonality, growth, economic indicators, etc.)
Time-series alignment and normalization
✔ Gold Layer (Model-Ready Data)

Final curated dataset
Used for machine learning and dashboard consumption
This multi-layered Lakehouse approach ensures clean, high-quality, reliable input for modeling.

image
4. Machine Learning Model Training

The Model Training block uses Databricks ML runtime to build multiple forecasting models:

Random Forest
XGBoost Regressor
Prophet
ARIMA (Auto-ARIMA)
Each model is trained on engineered features from the Silver/Gold layers.

Model Accuracy- Random Forest: 97.69% (Best), XGBoost: 97.47%, ARIMA: 84.2%, Prophet: 84.19%

Random Forest performed the best due to its ability to learn complex patterns from multiple correlated signals.

The final outputs include:

Predicted Compute demand
Predicted Storage demand
Weekly and monthly trend insights
Model performance metrics (MAE, RMSE, SMAPE)
5. Visualization Layer (Power BI)

The final forecasts and performance metrics are published to Power BI, enabling:

Real-time interactive dashboards
Demand trend reports
Regional and service-level breakdowns
Capacity planning insights
Model accuracy monitoring

 Dashboard Results:-  ![d1](https://github.com/user-attachments/assets/ae327a4f-c052-4d90-8889-1ac68d5bc211)
                      ![d2](https://github.com/user-attachments/assets/df5008db-60fb-43dc-b9fd-91d6567d67cf)
                      ![d3](https://github.com/user-attachments/assets/46b2badc-d633-4581-bd8f-110684859e33)
                      ![d4](https://github.com/user-attachments/assets/946651f2-5da8-4347-9202-ce3347ab142f)




 Project View Link-   https://app.powerbi.com/view?r=eyJrIjoiOGRhOTVmZDItNThhZC00MWJmLTkxNzUtYWVkYTZkNGM4NzRkIiwidCI6IjI5MTk2MTM0LTRiNzktNDY1NS1hYTZjLTAyNTc2MzQ5NGI2NCJ9
 



