# Zomato Data Analysis Project in Azure
This repository contains the code and documentation for a comprehensive Zomato data analysis project in Azure. The project involves ingesting raw data, cleaning and transforming the data, and then performing detailed analyses to derive business insights in Azure Databrick. The project leverages both local processing and Azure cloud services to handle the data pipeline.

# Table of Contents
Overview

Architecture & Workflow

Data Sources

Azure Cloud Integration

Azure Blob Storage

Azure Data Factory (ADF)

Azure Databricks

Local Analysis

Key Steps & Components


# Overview
This project analyzes Zomato data to gain insights into restaurant trends, ordering behaviors, and customer preferences. The project is divided into two main parts:

  1. Cloud-based Data Pipeline: Raw Excel files are uploaded to Azure Blob Storage. Azure Data Factory orchestrates data ingestion and transformation, and Azure Databricks is used for advanced processing and cleaning of the data. In this part, we create a sub-dataset that is more refined (fewer columns and cleaner data).

  2. Local Analysis: The raw data is also processed locally on a machine for initial exploration and testing. This section includes SQL transformations, feature engineering, and model evaluations using Python.

# Architecture & Workflow
The overall data pipeline and analysis workflow include:

1. Data Ingestion:

    Source: Excel file containing raw Zomato data.

    Storage: Data is uploaded to Azure Blob Storage.

    Pipeline: Azure Data Factory (ADF) pipelines are configured to ingest and move data from Blob Storage to downstream services.
2. Data Transformation and Cleaning:
    Cloud: Azure Databricks is used to perform SQL transformations and advanced cleaning tasks, resulting in a refined dataset with fewer columns and improved quality.

    Local: A parallel analysis is performed on raw data using Python. The local machine workflow includes feature encoding, scaling, model training, and evaluation.
3. Analysis & Modeling:

    Feature Engineering: Columns are encoded (e.g., converting categorical variables into numerical values), scaled using StandardScaler and RobustScaler, and selected based on statistical tests.

    Modeling: Both linear and ensemble models are created and evaluated to compare performance (using metrics like RMSE and R²).

    Hyperparameter Tuning: Techniques such as RandomizedSearchCV are applied to optimize model performance.
# Data Sources
  Raw Data: Zomato data in Excel format, containing information such as online orders, book table options, restaurant types, votes, approximate cost for two, and more.

  Cleaned Data: A sub-dataset generated in Azure Databricks after cleaning and reducing columns for focused analysis.
# Azure Cloud Integration
## Azure Blob Storage
  Purpose: Acts as the central storage repository for the raw Excel data.

  Process: The data is uploaded manually or via automated scripts, ensuring that the data is readily available for ingestion by Azure Data Factory.

## Azure Data Factory (ADF)
  Purpose: Orchestrates the data pipelines that ingest data from Azure Blob Storage.

  Process: The pipeline uses a Copy Data activity to transfer the Excel file from Blob Storage to a staging area accessible by Azure Databricks.
SQL transformations, such as filtering unnecessary columns, were applied within the pipeline to prepare a cleaner subset of the data.

## Azure Databricks
  Purpose: Provides an environment for advanced data cleaning, transformation, and feature engineering.

  Process: Data loaded into Databricks is processed using Apache Spark SQL and Python. The cleaned data, with reduced columns and higher quality, is then used for downstream analysis and model building.

# Local Analysis
On the local machine, raw data is processed in parallel to validate and experiment with different cleaning techniques and modeling strategies. Key steps include:

  Data Preprocessing: Encoding categorical variables (e.g., online_order, book_table) and scaling numerical features.

  Model Building: Developing linear models (LinearRegression, Ridge, Lasso, ElasticNet) and ensemble models (RandomForest, XGBoost, LightGBM).

  Feature Selection: Using statistical tests like f_regression and mutual information regression to identify key features.

  Hyperparameter Tuning: Employing RandomizedSearchCV for fine-tuning model parameters.

  Visualization & Evaluation: Plotting feature importances, model performance metrics, and correlations to gain insights and improve model accuracy.

# Key Steps & Components
  1. Data Ingestion & Storage: Upload Excel files to Azure Blob Storage.

  2. Pipeline Orchestration: Use ADF to automate data movement and basic transformations.

  3. Data Cleaning & Transformation: Perform in-depth cleaning in Azure Databricks.

  4. Local Experimentation: Validate and test on raw data locally using Python.

  5. Modeling & Evaluation: Build and compare regression models to assess performance.

  6. Documentation & Version Control: Maintain this repository with code, notebooks, and documentation for reproducibility.
