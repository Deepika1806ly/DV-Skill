# Apple Stock Data Analysis – Week 3

## Project Overview

This project is **Week 3 of the Data Visualization (DV) project series** and focuses on exploring **Apple Inc. (AAPL) historical stock data** using Python.

The project uses **Pandas, NumPy, and Matplotlib** to load, inspect, and clean the historical stock dataset.

The main focus of this project is to understand the structure of the stock market dataset and perform basic data preprocessing by handling missing values and duplicate records.

---

## Objectives

The main objectives of this project are:

* Load Apple historical stock data using Pandas.
* Explore the dataset structure and contents.
* Display the first few records.
* Understand column names and data types.
* Check the dataset information.
* Handle missing values.
* Remove duplicate records.
* Prepare the cleaned dataset for further stock data analysis and visualization.

---

## Dataset

The project uses an **Apple Inc. (AAPL) Historical Data** CSV dataset.

### Dataset Information

| Details       |      Value |
| ------------- | ---------: |
| Total Records |     11,355 |
| Total Columns |          8 |
| File Format   |        CSV |
| Stock         | Apple Inc. |
| Ticker        |       AAPL |

---

## Dataset Columns

| Column   | Description                           |
| -------- | ------------------------------------- |
| `Date`   | Date of the stock record              |
| `Open`   | Opening stock price                   |
| `High`   | Highest stock price during the period |
| `Low`    | Lowest stock price during the period  |
| `Close`  | Closing stock price                   |
| `Volume` | Number of shares traded               |
| `ticker` | Stock ticker symbol                   |
| `name`   | Name of the stock/company             |

---

## Technologies Used

* **Python**
* **Pandas** – Data loading, cleaning, and analysis
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Google Colab** – Development environment

---

# Project Workflow

## 1. Import Required Libraries

The project begins by importing the required Python libraries:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

---

## 2. Load the Dataset

The Apple historical stock data is loaded from the CSV file using Pandas.

```python
df = pd.read_csv("Apple_historical_data.csv")
```

---

## 3. Display the Dataset

The complete DataFrame is displayed for initial inspection.

```python
df
```

---

## 4. View the First Few Records

The first few rows of the dataset are displayed using:

```python
print(df.head())
```

This helps to understand the initial structure and values in the dataset.

---

## 5. Check Dataset Information

The `info()` function is used to inspect:

* Number of records
* Column names
* Data types
* Non-null values
* Memory usage

```python
print(df.info())
```

---

# 6. Data Cleaning

## Handle Missing Values

Missing values are removed from the dataset using:

```python
df = df.dropna()
```

This ensures that rows containing missing values are excluded from the cleaned dataset.

---

## Remove Duplicate Records

Duplicate rows are removed using:

```python
df = df.drop_duplicates()
```

This helps ensure that duplicate records do not affect further analysis.

---

## Data Cleaning Process

The cleaning process consists of:

```text
Original Dataset
       ↓
Check Dataset Information
       ↓
Remove Missing Values
       ↓
Remove Duplicate Records
       ↓
Cleaned Dataset
```

---

# Stock Data Features

The dataset contains important stock-market features such as:

### Open Price

The stock price at the beginning of the trading period.

### High Price

The highest price recorded during the trading period.

### Low Price

The lowest price recorded during the trading period.

### Close Price

The stock price at the end of the trading period.

### Volume

The number of shares traded during the trading period.

---

# Dataset Summary

The Apple historical dataset contains:

* **11,355 records**
* **8 columns**
* Stock ticker: **AAPL**
* Company: **Apple Inc.**
* Historical price information including Open, High, Low, and Close
* Trading volume information

The attached dataset currently contains **no missing values and no duplicate rows** based on the dataset inspection.

---

# Project Structure

```text
Apple-Stock-Data-Analysis/
│
├── apple_stock_data_dv_week_3.py
├── Apple_Stock_Data_DV_Week_3.ipynb
├── Apple_historical_data.csv
└── README.md
```

---

# How to Run the Project

## Step 1 – Clone the Repository

```bash
git clone <your-repository-link>
```

## Step 2 – Install Required Libraries

```bash
pip install pandas numpy matplotlib
```

## Step 3 – Open the Project

The project can be opened using:

* Google Colab
* Jupyter Notebook
* VS Code
* Any Python IDE

## Step 4 – Run the Python File

```bash
python apple_stock_data_dv_week_3.py
```

Or open the following notebook:

```text
Apple_Stock_Data_DV_Week_3.ipynb
```

---

# Concepts Practiced

This project provides practice with:

* CSV file handling
* Pandas DataFrames
* Dataset exploration
* `head()`
* `info()`
* Missing-value handling
* Duplicate removal
* Basic data preprocessing
* Stock market dataset understanding
* Python data analysis

---

# Future Enhancements

The project can be extended with:

* Apple stock price trend visualization
* Open vs Close price analysis
* High vs Low price comparison
* Trading volume analysis
* Moving average calculation
* Daily return calculation
* Stock price distribution
* Candlestick visualization
* Correlation analysis
* Time-series analysis

---
