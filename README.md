 # Netflix Data Pipeline - Overview

This project implements a robust ETL pipeline using AWS services to process and analyze Netflix-related data. 
The pipeline fetches raw data,processes it, and then stores it in Amazon Redshift for further analysis. Below are the key steps involved in the pipeline:

## Step 1: Data Loading and Preprocessing
 ### Objective: Load raw Netflix-related data from CSV files into PostgreSQL.
 ### Process:

  The raw CSV files, including Best_movie_by_year.csv, Best_movie.csv, Best_show_by_year.csv, Best_shows.csv, credits.csv, and Raw_titles.csv, are read using Pandas.
  The data is cleaned and filtered based on certain criteria (e.g., removing duplicates and unnecessary columns).
  The filtered data is then stored in PostgreSQL as tables.


## Step 2: Data Transfer from PostgreSQL to RDS

### Objective: Connect PostgreSQL to Amazon RDS and transfer the tables.

### Process:

The tables stored in PostgreSQL in Step 1 are loaded into Amazon RDS.
This ensures that the data is available in a scalable cloud environment, ready for further processing.


## Step 3: Storing Data in Amazon S3

### Objective: Transfer the data from Amazon RDS to Amazon S3 in CSV format.

### Process:

Data is fetched from RDS and converted into CSV format.
The CSV files are uploaded to Amazon S3, allowing them to be staged for further processing or analysis.

## Step 4: Data Transformation and Loading into Redshift

### Objective: Use AWS Glue to move the data from S3 to Amazon Redshift.

### Process:

The project configures an AWS Glue job to read the data from the S3 bucket and load it into Amazon Redshift.
The Glue job automates the ETL (Extract, Transform, Load) process, preparing the data for analysis within Redshift.

## Key Technologies and Tools Used
 #### AWS Services: Amazon RDS, Amazon S3, AWS Glue, Amazon Redshift
 #### PostgreSQL: For data storage and processing
 #### Pandas: For data cleaning and transformation
 #### Python: For automation and scripting
 #### SQL: For database operations


## Objective and Impact
The primary objective of this project is to create a scalable, efficient data pipeline that automates the process of fetching, processing,
and storing Netflix-related data for analysis. By utilizing AWS services, the pipeline ensures that data is handled in a cloud-native environment, 
providing easy scalability, security, and accessibility for future analytics.
