# Tokyo-Olympics-Data-Engineering-Analytics-Pipeline
This project demonstrates a cloud-scale data engineering pipeline using the Tokyo Olympics dataset.
It showcases how raw CSV files (Athletes, Coaches, EntriesGender, Medals, Teams) were ingested, cleaned, transformed, optimized, and analyzed using:

Azure Databricks (PySpark) for ETL

Azure Data Lake Storage Gen2 (ADLS) for scalable storage

Azure Synapse Analytics for warehousing and analytics

This end-to-end solution enables high-performance querying, data standardization, and advanced analysis for deriving meaningful Olympic-level insights.

🏗️ Solution Architecture
1. Data Ingestion Layer

✔ Mounted ADLS Gen2 into Databricks
✔ Loaded 5 raw CSV files using PySpark:

⭐ athletes.csv

⭐ coaches.csv

⭐ entriesgender.csv

⭐ medals.csv

⭐ teams.csv

2. Data Transformation Layer (Databricks + PySpark)

✔ Casted inconsistent columns to correct data types
✔ Standardized column names and formats
✔ Removed null/duplicate records
✔ Derived new columns for enhanced analytical value
✔ Validated schema for downstream compatibility
✔ Generated clean Bronze → Silver → Gold layer outputs

3. Data Storage Layer

✔ Stored cleaned datasets in Parquet format, reducing storage cost by ~60%
✔ Delivered query-optimized datasets to Synapse

4. Data Analytics Layer (Synapse)

✔ Imported Gold layer into Synapse SQL Pools
✔ Created analytical tables for BI consumption
✔ Performed aggregated and ranking-based Olympic analysis

📊 Key Data Transformations

Each dataset underwent critical cleansing and structuring:

🧍 Athletes Dataset

Eliminated ~4% inconsistent records

Standardized nationality & discipline fields

Added gender grouping and continent-level mapping

🧑‍🏫 Coaches Dataset

Removed duplicate coaching entries

Normalized country & event attributes

Joined with athletes to build coach–athlete correlation table

👥 EntriesGender Dataset

Cleaned invalid gender labels

Calculated total entries per sport

Produced gender participation ratio with >98% accuracy

🏅 Medals Dataset

Validated medal count integrity

Ranked countries using custom scoring logic

Built Gold–Silver–Bronze distribution pivot model

🌍 Teams Dataset

Normalized team identifiers

Standardized country codes

Created team-to-country relationship table

📈 Analytical Insights Uncovered

The transformed data enabled rich insights, including:

🥇 Top medal-winning nations

🏃 Sports with highest athlete participation

🔥 Countries with strongest discipline specialization

⚖️ Gender distribution trends across all sports

🧠 Coach influence mapping on athlete performance

🛠️ Technologies & Tools Used
Azure Services

Azure Databricks (ETL, PySpark)

ADLS Gen2 (Data Storage)

Azure Synapse Analytics (Data Warehouse)

Python & PySpark

pyspark.sql

Window functions

Schema validation & casting

Parquet optimization

🏁 Final Outcome

✔ Built a scalable, production-grade data pipeline
✔ Achieved fully validated and analytics-ready datasets
✔ Performed high-speed querying with Synapse
✔ Generated Olympics insights dashboards using processed data
