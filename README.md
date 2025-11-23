# INFOSYS-INTERNSHIP-6.0

Architecture of the project:-
![WhatsApp Image 2025-11-22 at 18 16 06_f9e224ed](https://github.com/user-attachments/assets/dbcd8f3c-8f32-4f86-ab04-87857cf29b64)
This project implements an end-to-end cloud-based forecasting system designed to predict Azure Compute and Storage demand. It integrates multi-cloud data ingestion, scalable storage, advanced feature engineering, machine learning model training, and interactive Power BI dashboards to support Azure’s capacity planning and supply chain decision-making.
1. System Architecture

(Image: “WhatsApp Image 2025-11-22 at 18 16 06_f9e224ed”)
The architecture consists of the following layers:

1) Data Sources
2) Data Ingestion Layer (ADF)
3) Data Lake & Processing Layer (ADLS + Databricks)
4) ML Model Training Layer
5) Visualization Layer (Power BI)
   2. Data Sources
The system integrates data from three major platforms to ensure a rich and diverse dataset:

❄️✔ Snowflake DB

-> Provides structured enterprise usage and infrastructure data.
Acts as a primary internal signal for Azure demand.

✔ Google Cloud Platform (GCP)

-> Offers external cloud-usage indicators.

-> Provides additional global demand signals.

✔ Render API

-> Supplies real-time consumption metrics via API calls.
-> Enhances short-term demand prediction accuracy.

These sources combine internal + external drivers, creating a holistic multi-cloud demand dataset.

3. Data Ingestion Layer (Azure Data Factory)
-> Azure Data Factory (ADF) is responsible for orchestrating all ingestion activities.

🏪ADF Capabilities Used

-> Automates ingestion pipelines

-> Connects securely to Snowflake, GCP, and REST API endpoints

-> Handles data scheduling, triggers, transformations, and logging

🏬Azure Data Lake Storage (ADLS)

-> Acts as the centralized raw data repository
->Stores data in a hierarchical folder structure
->Seamlessly integrates with Azure Databricks
->This layer ensures scalable, secure, and fault-tolerant ingestion of multi-cloud datasets.

4. Data Processing Layer (Azure Databricks)
-> Azure Databricks serves as the primary data engineering and machine learning workspace.

-> Lakehouse Architecture with Medallion Layers
🥉  ✔ Bronze Layer (Raw Data) - Stores unprocessed data exactly as ingested, Preserves full lineage and fidelity

🥈✔ Silver Layer (Cleaned + Enriched Data)- Data cleaning (nulls, outliers, schema fixes)

Feature engineering:

-> Lag features ,Moving averages ,Seasonality extraction ,Growth rates ,Economic indicators

Time-series normalization & alignment

🏅✔ Gold Layer (Model-Ready Data)
Optimized dataset for ML training
Used for dashboard and analytics consumption
This Lakehouse approach ensures clean, accurate, high-quality data for forecasting.

5. Machine Learning Model Training

Model training is performed using Databricks ML Runtime.
Models Implemented
Random Forest Regressor
XGBoost Regressor
Prophet
ARIMA (Auto-ARIMA)


Random Forest outperformed other models due to its ability to learn complex multivariate patterns from correlated signals.

Model Outputs
Predicted Compute demand
Predicted Storage demand
Weekly & monthly demand trends
Model performance metrics (MAE, RMSE, SMAPE)

6. Visualization Layer (Power BI)

The final forecasts are pushed to Power BI dashboards enabling:
Dashboard Capabilities
Real-time interactive forecasting visuals
Compute & Storage demand trend analysis
Regional and SKU-level breakdowns
Weekly/monthly forecasting views
Model performance monitoring


DEMO VIDEO-  https://github.com/ishupatil/INFOSYS-INTERNSHIP-6.0/blob/main/Demo_video/Azure-Based%20Demand%20Forecasting%20and%20Capacity%20Optimization%20Project%20Overview.mp4




 Dashboard Results:-  ![d1](https://github.com/user-attachments/assets/ae327a4f-c052-4d90-8889-1ac68d5bc211)
                      ![d2](https://github.com/user-attachments/assets/df5008db-60fb-43dc-b9fd-91d6567d67cf)
                      ![d3](https://github.com/user-attachments/assets/46b2badc-d633-4581-bd8f-110684859e33)
                      ![d4](https://github.com/user-attachments/assets/946651f2-5da8-4347-9202-ce3347ab142f)




 Project View Link-   https://app.powerbi.com/view?r=eyJrIjoiOGRhOTVmZDItNThhZC00MWJmLTkxNzUtYWVkYTZkNGM4NzRkIiwidCI6IjI5MTk2MTM0LTRiNzktNDY1NS1hYTZjLTAyNTc2MzQ5NGI2NCJ9


✔ Project Summary

This system provides a fully automated forecasting pipeline from data ingestion → cleaning → feature engineering → ML training → dashboard reporting. It supports Azure’s enterprise-level capacity planning with highly accurate demand predictions.


