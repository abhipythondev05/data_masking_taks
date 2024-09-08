# PySpark Data Generation and Masking

This project demonstrates how to generate fake data using the `Faker` library and process it with PySpark. The generated data is then saved to CSV files, and sensitive information is masked.

## Prerequisites

- Apache Spark (with PySpark)
- Python
- `Faker` library (for generating fake data)
- `pandas` (optional, for any local data manipulation)
- Azure resource group
- Azure storage account
- Databricks Workspace
- Databricks Cluster

## Setup

### Installation

Before running the notebook, install the required Python packages:

```bash
%pip install faker pandas


##Dcokerfile
Dockerfile . a image can be build and containerised and and when eun the juoyter notebook is accessble at port 8888 and the masking2.ipynb can be executed and the csv's will be saved in the confainer directory.

##Databricks

Databricks is used to run Databricks_masking.ipynb notebook using pyspark the csv's will be saved on to dbfs.

