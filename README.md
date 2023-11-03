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
    
   **Pipelines**:  
   [pl ingest raw data](https://github.com/rosstheboss94/PrizePicks/blob/main/Pipelines/ingestions/pl_ingest_raw_data.jpg)  
   
   **Notebooks**:  
   [ingest api games](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/bronze/ingest_api_games.ipynb)  
   [ingest api players](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/bronze/ingest_api_players.ipynb)  
   [ingest api stats](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/bronze/ingest_api_stats.ipynb)  
   [ingest api teams](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/bronze/ingest_api_teams.ipynb)

4. ### Staging
   - **Data Source**: Bronze layer
   - **Storage**: JSON files are stored in the silver layer of Azure Data Lake Gen2

   **Pipelines**:     
   [pl extract to staging](https://github.com/rosstheboss94/PrizePicks/blob/main/Pipelines/extractions/pl_extract_to_staging.jpg)  

   **Notebooks**:  
   [ingest teams json](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/silver/1_ingest_teams_json.ipynb)  
   [ingest players json](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/silver/2_ingest_players_json.ipynb)  
   [ingest games json](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/silver/3_ingest_games_json.ipynb)  
   [ingest stats json](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/silver/4_ingest_stats_json.ipynb)

5. ### Data Transformation
   - **Data Source**: Silver layer
   - **Storage**: JSON files are stored in the gold layer of Azure Data Lake Gen2

   **Pipelines**:   
   [pl transform dim games](https://github.com/rosstheboss94/PrizePicks/blob/main/Pipelines/transformations/pl_transform_dim_games.jpg)  
   [pl transform dim tables](https://github.com/rosstheboss94/PrizePicks/blob/main/Pipelines/transformations/pl_transform_dim_tables.jpg)  
   [pl transform fact stats](https://github.com/rosstheboss94/PrizePicks/blob/main/Pipelines/transformations/pl_transform_fact_stats.jpg)  
   [pl transform fact tables](https://github.com/rosstheboss94/PrizePicks/blob/main/Pipelines/transformations/pl_transform_fact_tables.jpg)

   **Notebooks**:   
   [trans dim players](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/gold/trans_dim_players.ipynb)   
   [trans dim teams](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/gold/trans_dim_teams.ipynb)   
   [trans fact games](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/gold/trans_fact_games.ipynb)   
   [trans fact stats](https://github.com/rosstheboss94/PrizePicks/blob/main/ingestions/gold/trans_fact_stats.ipynb)   










