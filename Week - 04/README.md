# Shopify Stock Data Analysis – Week 4

## Project Overview

This project is **Week 4 of the Data Visualization (DV) project series** and focuses on analyzing **Shopify stock market data** using Python.

The project uses **Pandas, NumPy, and Matplotlib** to load the Shopify historical stock dataset and visualize stock price movement and daily returns.

The analysis includes:

* Shopify closing price visualization
* Daily return calculation
* Daily return distribution visualization

---

## Objectives

The main objectives of this project are:

* Load Shopify stock data using Pandas.
* Explore the stock dataset.
* Visualize Shopify's closing price over time.
* Calculate daily stock returns.
* Understand the distribution of daily returns.
* Practice basic financial data visualization using Python.

---

## Dataset

The project uses a historical **Shopify stock dataset** stored in CSV format.

### Dataset Information

| Details           |                 Value |
| ----------------- | --------------------: |
| Number of Records |                 2,469 |
| Number of Columns |                     7 |
| File Format       |                   CSV |
| Company           |               Shopify |
| Dataset Type      | Historical Stock Data |

---

## Dataset Columns

| Column      | Description                                   |
| ----------- | --------------------------------------------- |
| `date`      | Date of the stock record                      |
| `open`      | Opening stock price                           |
| `high`      | Highest stock price during the trading period |
| `low`       | Lowest stock price during the trading period  |
| `close`     | Closing stock price                           |
| `adj_close` | Adjusted closing price                        |
| `volume`    | Number of shares traded                       |

---

## Technologies Used

* **Python**
* **Pandas** – Data loading and DataFrame operations
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

The Shopify stock dataset is loaded using Pandas:

```python
df = pd.read_csv("shopify_stock.csv")
```

---

## 3. Display Initial Data

The first few records are displayed using:

```python
print(df.head())
```

This helps in understanding the structure and values of the stock dataset.

---

# 4. Shopify Closing Price Visualization

A line plot is created to visualize Shopify's closing price.

```python
plt.plot(df["date"], df["close"])

plt.xlabel("Date")
plt.ylabel("Closing Price")
plt.title("Shopify Closing Price")

plt.show()
```

### Purpose

This visualization helps observe how Shopify's **closing stock price changes over time**.

### Visualization

**Chart:** Line Plot

* X-axis → Date
* Y-axis → Closing Price
* Title → Shopify Closing Price

---

# 5. Calculate Daily Returns

Daily returns are calculated using the percentage change in the closing price.

```python
df["Daily_Return"] = df["close"].pct_change()
```

### Formula

```text
Daily Return = (Today's Close - Previous Close) / Previous Close
```

The `pct_change()` function calculates the percentage change between the current and previous closing price.

---

# 6. Daily Return Distribution

A histogram is created to visualize the distribution of daily returns.

```python
plt.hist(
    df["Daily_Return"].dropna(),
    bins=30
)

plt.title("Daily Returns")
plt.xlabel("Daily Return")
plt.ylabel("Frequency")

plt.show()
```

### Purpose

The histogram helps understand how frequently different daily return values occur.

### Visualization

**Chart:** Histogram

* X-axis → Daily Return
* Y-axis → Frequency
* Number of bins → 30

---

# Visualizations Included

This project contains two main visualizations:

### 1. Shopify Closing Price

A line chart showing the movement of Shopify's closing price over time.

### 2. Daily Returns

A histogram showing the distribution of Shopify's daily stock returns.

---

# Data Processing

The project performs the following steps:

```text
Load CSV Dataset
       ↓
Explore Initial Records
       ↓
Visualize Closing Price
       ↓
Calculate Daily Returns
       ↓
Remove NaN Daily Return
       ↓
Plot Daily Return Distribution
```

---

# Project Structure

```text
Shopify-Stock-Data-Analysis/
│
├── shopify_stock_data_dv_week_04.py
├── Shopify_Stock_Data_DV_Week_04.ipynb
├── shopify_stock.csv
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

You can run the project using:

* Google Colab
* Jupyter Notebook
* VS Code
* Any Python IDE

## Step 4 – Run the Python File

```bash
python shopify_stock_data_dv_week_04.py
```

Or open:

```text
Shopify_Stock_Data_DV_Week_04.ipynb
```

in Google Colab or Jupyter Notebook.

---

# Concepts Practiced

Through this project, the following concepts were practiced:

* Reading CSV files using Pandas
* DataFrame operations
* Stock market data analysis
* Line plots
* Histograms
* Percentage change
* Daily return calculation
* Financial data visualization
* Basic time-series visualization

---

# Future Enhancements

The project can be extended by adding:

* Moving averages
* 7-day and 30-day price trends
* Trading volume visualization
* Open vs Close price comparison
* High vs Low price analysis
* Volatility analysis
* Candlestick charts
* Monthly and yearly returns
* Stock price trend analysis
* Interactive stock dashboard

---
