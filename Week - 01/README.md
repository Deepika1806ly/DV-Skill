# Super Store Sales Data Analysis

## Project Overview

This project focuses on exploring and understanding a **Super Store Sales dataset** using Python.

The project uses Python libraries such as **Pandas, NumPy, Matplotlib, and Seaborn** to load the dataset and perform basic data exploration.

The main purpose of this project is to understand the structure of the sales dataset, inspect the available data, and obtain basic statistical information.

---

## Objectives

* Load the Super Store Sales dataset using Python.
* Explore the structure and contents of the dataset.
* Display the first few records.
* Understand the data types and information of each column.
* Generate basic statistical summaries.
* Prepare the dataset for further data analysis and visualization.

---

## Dataset

The dataset contains information about orders, customers, products, sales, discounts, and profits.

### Dataset Details

* **Rows:** 10,194
* **Columns:** 21
* **File Format:** CSV

### Main Columns

| Column         | Description                     |
| -------------- | ------------------------------- |
| Row ID         | Unique row identifier           |
| Order ID       | Unique order identifier         |
| Order Date     | Date when the order was placed  |
| Ship Date      | Date when the order was shipped |
| Ship Mode      | Shipping method used            |
| Customer ID    | Unique customer identifier      |
| Customer Name  | Name of the customer            |
| Segment        | Customer segment                |
| Country/Region | Country or region               |
| City           | Customer city                   |
| State/Province | Customer state or province      |
| Postal Code    | Postal code                     |
| Region         | Sales region                    |
| Product ID     | Unique product identifier       |
| Category       | Product category                |
| Sub-Category   | Product sub-category            |
| Product Name   | Name of the product             |
| Sales          | Sales amount                    |
| Quantity       | Quantity of products ordered    |
| Discount       | Discount applied                |
| Profit         | Profit generated                |

---

## Technologies Used

* **Python**
* **Pandas** – Data loading and data analysis
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical data visualization
* **Google Colab / Jupyter Notebook** – Development environment

---

## Project Workflow

### 1. Import Libraries

The required Python libraries are imported:

```python
import pandas as pd
import numpy as np

import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. Load the Dataset

The CSV dataset is loaded using Pandas:

```python
df = pd.read_csv("samplesuperstore - samplesuperstore.csv")
```

### 3. View the Dataset

The first few records are displayed using:

```python
df.head()
```

### 4. Understand Dataset Information

The structure, column names, data types, and non-null information are inspected using:

```python
df.info()
```

### 5. Generate Statistical Summary

Basic statistical information is obtained using:

```python
df.describe()
```

---

## Basic Data Exploration

The project explores:

* Dataset dimensions
* Column names
* Data types
* First few records
* Numerical statistics
* Sales information
* Quantity information
* Discount information
* Profit information
* Product and customer-related information

---

## Project Structure

```text
Super-Store-Sales-Data-Analysis/
│
├── super_store_sales_data_dv_week_1.py
├── Super_Store_Sales_Data_DV_Week_1.ipynb
├── samplesuperstore - samplesuperstore.csv
└── README.md
```

---

## How to Run

### Step 1: Clone the Repository

```bash
git clone <your-repository-link>
```

### Step 2: Open the Project

You can open the project using:

* Jupyter Notebook
* Google Colab
* VS Code
* Any Python-supported IDE

### Step 3: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn
```

### Step 4: Run the Python File

```bash
python super_store_sales_data_dv_week_1.py
```

Or open the `.ipynb` file in **Google Colab/Jupyter Notebook** and run the cells.

---

## Dataset Summary

The dataset contains **10,194 sales records** with information covering:

* Orders
* Customers
* Products
* Categories
* Regions
* Shipping methods
* Sales
* Quantity
* Discounts
* Profits

This makes the dataset suitable for further **Exploratory Data Analysis (EDA)** and visualization.

---

## Future Enhancements

The project can be extended by adding:

* Data cleaning
* Missing-value analysis
* Duplicate-value analysis
* Sales by category
* Profit by region
* Sales by customer segment
* Monthly sales trends
* Category-wise profit analysis
* Correlation analysis
* Interactive visualizations
* Business insights

---

