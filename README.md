# PrizePicks
Problem
The purpose of this project is to take the emotion out of sports betting leveraing machine learning.

Technologies used: Spark, Azure Synapse, Azure SQL Database, Azure Data Lake Gen2
Languages used: Python
1. ### Introduction
   The aim of this project is to eliminate emotions from sports betting by establishing an end-to-end data solution that harnesses the power of machine learning.
2. ### Project Architecture
   PrizePicks employs a medallion architecture in its data processing framework. In this architecture:
   - Bronze Layer: This is the foundational layer responsible for raw data ingestion and historical data storage. It contains the data in its original, unprocessed form.
   - Silver Layer: The silver layer is the intermediate layer where data is filtered, cleaned, and transformed into a more usable and structured format. It acts as an intermediary between the raw data in the bronze layer and the final aggregated data in the gold layer.
   - Gold Layer: The gold layer represents the top-level of the architecture and contains the highest quality, business-level aggregates. This layer is where data is processed and aggregated to provide valuable insights and analytics for business operations.

3. ### Data Ingestion
   - **Data Source**: Balldontlie API
   - **Storage**: Raw JSON files are stored in the bronze layer of Azure Data Lake Gen2  
   **Files**:  
   [ingest_api_games](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/bronze/ingest_api_games.ipynb)
5. 











