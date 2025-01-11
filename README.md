# News Recommendation System Pipeline

## Overview

This repository details a pipeline for processing and analyzing news data to generate personalized recommendations. The system ingests news content and user behavior data, enriches it through advanced machine learning techniques, and provides targeted news recommendations. This solution leverages Azure services, including Azure Data Factory for orchestration, Azure Databricks for data transformation, and Azure Data Lake Storage Gen2 for data storage.

## Key Technologies:

-   **Azure Data Lake Storage Gen2**: Serves as the primary data storage solution, handling large volumes of structured and unstructured data.
-   **Azure Data Factory**: Orchestrates data flows, managing data ingestion and integration.
-   **Azure Databricks**: Provides a powerful platform for data transformation and analysis using Apache Spark.

![Data Pipeline](/data-pipeline.png)

## Data Ingestion

Data ingestion is managed through Azure Data Factory, which automates the retrieval of data from GitHub, specifically targeting news and user behavior data stored in `.tsv` format within a dataset folder. This data is then loaded into Azure Data Lake Storage Gen2 for further processing.

### Azure Data Factory Pipeline:

The pipeline, named `news_data_pipeline`, is responsible for:

-   Automating data downloads from configured sources.
-   Preprocessing and storing raw data into Azure Data Lake.

### Ingestion Steps:

-   Automated workflows in Azure Data Factory retrieve and store data periodically into Azure Data Lake Storage Gen2.

## Data Transformation

Data transformation tasks are performed in Azure Databricks using PySpark notebooks, which process and prepare both news and behavior data for machine learning.

### Transformation Details:

-   **News Transformation (`News Transformation.ipynb`)**: Processes news data by cleaning, normalizing, and tokenizing the text, preparing it for feature extraction.
-   **Behaviors Transformation (`Behaviors Transformation.ipynb`)**: Processes user behavior data, focusing on cleaning and structuring the data to capture user interactions effectively.

## Machine Learning Model for News Recommendation

The transformed data is used to train machine learning models that predict user preferences and suggest news articles.

### Techniques Used:

-   **BERT Embeddings for Content-Based Filtering**: Utilizes pre-trained BERT models to generate content embeddings that capture semantic meanings of news articles.
-   **Neural Collaborative Filtering (NCF)**: Implements a deep learning approach to model user-item interactions and predict user preferences. The final accuracy reached was 96.18% with a loss of 0.1387.

### Hybrid Recommendation Engine:

-   Combines content-based and collaborative filtering methods to enhance recommendation accuracy and diversity.

This project demonstrates an integration of data ingestion, processing, and machine learning to deliver news recommendation system and utilize Azure's powerful cloud infrastructure for end-to-end data management.
