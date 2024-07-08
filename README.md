# cdc-sales-data-pipeline

This repository contains a comprehensive implementation of a Change Data Capture (CDC) pipeline for real-time sales data analysis. Utilizing AWS services such as DynamoDB, Kinesis Data Streams, Kinesis Firehose, Lambda, S3, and Athena, this project demonstrates how to capture, transform, and analyze sales data in real-time. The pipeline starts with generating mock sales data and ingesting it into a DynamoDB table, followed by capturing data changes using EventBridge. The data is then processed through Kinesis Data Streams and Firehose, transformed using a Lambda function, and stored in S3 for analysis with Athena. This project aims to provide a robust and scalable solution for real-time data analytics.

## Overview
This project demonstrates a robust and scalable Change Data Capture (CDC) pipeline for real-time sales data analysis using Amazon Web Services (AWS). By leveraging various AWS services, this pipeline captures data changes in a DynamoDB table, processes these changes in real-time, and stores the transformed data in an S3 bucket. The stored data is then available for analytical querying using Athena.

## Project Scenario
In this scenario, we simulate an e-commerce company that needs to analyze its sales data in real-time to make timely business decisions. The company wants to track changes in orders, such as new orders, updates, and deletions, and process this data in real-time for analytics. The solution involves the following steps:

- Data Generation and Ingestion: Mock sales data is generated using a Python script and inserted into a DynamoDB table named OrdersRawTable.
- Change Data Capture: Changes in the DynamoDB table are captured using Amazon EventBridge, which triggers a Kinesis Data Stream.
- Data Processing: The Kinesis Data Stream receives the data changes and processes them in batches. A Kinesis Firehose delivery stream is used to further process the data, applying transformations via a Lambda function.
- Data Storage: The transformed data is then stored in an S3 bucket.
- Data Analysis: The data stored in S3 is cataloged using AWS Glue, making it available for querying with Amazon Athena. Business analysts can use Athena to perform real-time queries and generate insights from the sales data.

## Implementation Details
- DynamoDB: Stores raw order data.
- EventBridge: Captures changes in the DynamoDB table.
- Kinesis Data Streams: Streams captured changes for real-time processing.
- Kinesis Firehose: Transforms and delivers data to S3.
- Lambda: Applies transformations to the data.
- S3: Stores the processed data.
- AWS Glue: Catalogs the data for querying.
- Athena: Provides SQL querying capabilities for analysis.


## Folder Structure

```arduino
cdc-sales-data-pipeline/
├── data_generation/
│   └── mock_data_generator.py
├── lambda_functions/
│   └── cdc_transformer.py
├── notebooks/
│   └── aws_service_setup.ipynb
├── README.md
└── setup/
    └── create_aws_resources.py
```
