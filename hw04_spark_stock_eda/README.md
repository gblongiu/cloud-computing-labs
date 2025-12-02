# Spark Stock EDA (Kroger)

This lab uses **PySpark** to perform basic exploratory data analysis and cleaning on
historical Kroger stock price data. It was originally developed as part of my
*Cloud Computing for Data Science* coursework and adapted here as a standalone,
reproducible example.

The notebook focuses on getting comfortable with the Spark DataFrame API:
loading data, inspecting schema and summary statistics, handling missing values,
and writing cleaned results back to disk.

---

## Contents

- `spark_stock_eda.ipynb`  
  Main notebook for the lab. Walks through environment setup, loading the CSV
  file into a Spark DataFrame, running EDA, and exporting a cleaned dataset.

(Optional if you later add data:)

- `data/`  
  Sample CSV file with historical daily prices for Kroger (ticker: KR).

---

## Goals

This lab demonstrates how to:

- Start a `SparkSession` and verify a working PySpark environment
- Load a CSV file into a Spark DataFrame with inferred schema
- Inspect schema, column types, and basic summary statistics
- Identify and quantify missing values
- Apply simple cleaning steps (e.g., filling or dropping nulls)
- Write a cleaned version of the dataset back to disk

The emphasis is on understanding the Spark DataFrame workflow and how it differs
from pandas, rather than on sophisticated modeling.

---

## Requirements

You can run the notebook either locally or in Google Colab.

### Local (recommended for portfolio use)

- Python 3.10+  
- Java runtime (for Spark)
- PySpark

Install PySpark into your environment:

```bash
pip install pyspark
