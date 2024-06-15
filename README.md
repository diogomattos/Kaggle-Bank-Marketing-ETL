# Kaggle-Bank-Marketing-ETL

This project demonstrates an ETL (Extract, Transform, Load) pipeline using Google Colab, Kaggle datasets, and Google BigQuery. The pipeline processes the `train.csv` and `test.csv` files from a Kaggle dataset related to bank marketing campaigns, cleans and transforms the data, and loads it into BigQuery for analysis.

## Dataset

The dataset is related to direct marketing campaigns (phone calls) of a Portuguese banking institution. The goal is to predict if the client will subscribe to a term deposit.

## Files

- `train.csv`: Training data with client information and call details.
- `test.csv`: Test data with the same structure as `train.csv`.

## Steps

1. **Environment Setup**: Install necessary libraries and authenticate with Google Cloud.
2. **Data Extraction**: Download and load the dataset from Kaggle.
3. **Data Cleaning and Transformation**: Clean and transform the data.
4. **Data Loading**: Load the cleaned data into BigQuery.
5. **Data Analysis**: Run SQL queries on BigQuery to analyze the data.

## Instructions

### 1. Environment Setup

First, install the necessary libraries and authenticate with Google Cloud:

```python
!pip install google-cloud-bigquery pandas kaggle

import pandas as pd
from google.cloud import bigquery
from google.colab import auth
import os

# Authenticate with Google Cloud
auth.authenticate_user()

# Configure Google Cloud project
os.environ['GOOGLE_CLOUD_PROJECT'] = 'your_project_id'
client = bigquery.Client(project=os.environ['GOOGLE_CLOUD_PROJECT'])

# Configure Kaggle
os.environ['KAGGLE_USERNAME'] = 'your_kaggle_username'
os.environ['KAGGLE_KEY'] = 'your_kaggle_key'
