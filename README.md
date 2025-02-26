# Redfin-Big-Data-Pipeline-with-Apache-Airflow-AWS-EMR-EC2-S3-and-VPC
## Overview
This project automates the extraction, transformation, and processing of Redfin housing market data using Apache Airflow, AWS EMR, PySpark, and S3. The workflow is designed to efficiently handle large-scale data processing using distributed computing.

## Architecture
Data Extraction

Redfin data is pulled from an external source and stored in an AWS S3 bucket.

AWS Infrastructure Setup

AWS EC2 Instance: Used for development, hosting Airflow, and managing the pipeline.

AWS VPC: Configured to securely connect to Visual Studio Code via SSH for remote development.

AWS EMR Cluster: Created using Airflow’s EmrCreateJobFlowOperator, running Spark and JupyterEnterpriseGateway for distributed processing.

## Data Transformation with PySpark

A PySpark script processes and cleans the data:

Extracts relevant columns

Handles missing values

Extracts and formats date fields

Saves the transformed dataset in Parquet format on S3

## Workflow Automation with Airflow
Airflow DAG automates the entire pipeline, ensuring smooth execution with sensors and operators.

##Cluster & Resource Management
EMR cluster is automatically terminated after processing to optimize AWS costs.

## Tech Stack
Apache Airflow – Orchestration
AWS EC2 – Development & Airflow Host
AWS VPC – Secure Networking for SSH & EMR Connectivity
AWS EMR – Distributed Computing with Spark
PySpark – Data Transformation
AWS S3 – Data Storage

## Project Files
redfin_analytics_dag.py – Airflow DAG defining the pipeline
transform_redfin_data.py – PySpark script for processing data
ingest.sh – Shell script for data ingestion
