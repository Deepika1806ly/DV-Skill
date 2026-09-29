#  Healthcare Data Analysis

A Python-based healthcare data analysis project that explores patient information, medical conditions, hospital admissions, billing amounts, hospital stay duration, and demographic patterns using **Pandas, NumPy, and Matplotlib**.

##  Project Overview

This project performs basic **data cleaning, preprocessing, and exploratory data analysis (EDA)** on a healthcare dataset containing **55,500 patient records and 15 attributes**.

The analysis focuses on:

* Understanding the structure of healthcare data
* Handling missing values
* Converting admission and discharge dates into datetime format
* Creating a new urgency classification from admission type
* Calculating patient hospital stay duration
* Analyzing billing amount statistics
* Studying hospital stay statistics
* Exploring medical-condition-wise age demographics
* Examining gender distribution across medical conditions

The main analysis is implemented in Python using **Pandas, NumPy, and Matplotlib**.

---

##  Project Structure

```text
Healthcare-Data-Analysis/
│
├── healthcare_data_dv_week_05.py
├── healthcare_dataset.csv
└── README.md
```

---

##  Dataset Information

The dataset contains **55,500 records** with **15 columns**.

### Dataset Columns

| Column               | Description                              |
| -------------------- | ---------------------------------------- |
| `Name`               | Patient name                             |
| `Age`                | Patient age                              |
| `Gender`             | Patient gender                           |
| `Blood Type`         | Patient blood group                      |
| `Medical Condition`  | Patient's medical condition              |
| `Date of Admission`  | Date on which the patient was admitted   |
| `Doctor`             | Doctor associated with the patient       |
| `Hospital`           | Hospital associated with the patient     |
| `Insurance Provider` | Patient's insurance provider             |
| `Billing Amount`     | Healthcare billing amount                |
| `Room Number`        | Assigned hospital room number            |
| `Admission Type`     | Type of admission                        |
| `Discharge Date`     | Date on which the patient was discharged |
| `Medication`         | Medication provided                      |
| `Test Results`       | Patient test result                      |

---

## 🛠️ Technologies Used

* **Python**
* **Pandas** – Data loading, cleaning, transformation, and analysis
* **NumPy** – Numerical operations
* **Matplotlib** – Data visualization

---

## Data Analysis Workflow

### 1. Import Libraries

The project uses the following Python libraries:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

These libraries are used for data manipulation, numerical processing, and visualization.

### 2. Load the Dataset

The healthcare dataset is loaded into a Pandas DataFrame:

```python
df = pd.read_csv("healthcare_dataset.csv")
```

### 3. Initial Data Inspection

The project checks the dataset using:

```python
df.head()
df.shape
df.describe()
df.isnull().sum()
```

This provides an initial understanding of the dataset, including its dimensions, statistical summary, and missing values.

---

##  Data Cleaning

Missing values are handled using:

```python
df = df.dropna()
```

The project also specifically removes records where the `Medical Condition` value is missing:

```python
df = df.dropna(subset=["Medical Condition"])
```

Date columns are converted into Pandas datetime format:

```python
df["Date of Admission"] = pd.to_datetime(df["Date of Admission"])
df["Discharge Date"] = pd.to_datetime(df["Discharge Date"])
```

These preprocessing steps prepare the data for further analysis.

---

##  Admission Urgency Classification

A new `Urgency` column is created based on the existing `Admission Type` column.

```python
df["Urgency"] = df["Admission Type"].map({
    "Emergency": "Emergency",
    "Urgent": "Urgent",
    "Elective": "Elective"
})
```

This provides a separate classification that represents the urgency category of each admission.

---

##  Hospital Stay Duration

The project calculates the number of days each patient stayed in the hospital.

```python
df["Stay_Days"] = (
    df["Discharge Date"] - df["Date of Admission"]
).dt.days
```

The resulting `Stay_Days` column is then used for hospital stay analysis.

---

##  Billing Analysis

The project generates descriptive statistics for the `Billing Amount` column:

```python
df["Billing Amount"].describe()
```

This provides statistical information such as:

* Count
* Mean
* Standard deviation
* Minimum
* Maximum
* Quartiles

The output is displayed under **Billing Statistics**.

---

##  Hospital Stay Analysis

Descriptive statistics are generated for the calculated `Stay_Days` column:

```python
df["Stay_Days"].describe()
```

This helps understand the distribution of hospital stay durations.

---

##  Demographic Analysis

The project analyzes patient age by medical condition using:

```python
df.groupby("Medical Condition")["Age"].agg(["count", "mean"])
```

This produces:

* Number of patients for each medical condition
* Average age for each medical condition

---

##  Gender Distribution

Gender distribution across medical conditions is analyzed using a cross-tabulation:

```python
pd.crosstab(
    df["Medical Condition"],
    df["Gender"]
)
```

This helps compare the number of patients by gender across different medical conditions.

---

##  Key Analysis Areas

The project currently covers the following analysis areas:

| Analysis                  | Method                          |
| ------------------------- | ------------------------------- |
| Dataset inspection        | `head()`, `shape`, `describe()` |
| Missing-value analysis    | `isnull().sum()`                |
| Missing-value handling    | `dropna()`                      |
| Date preprocessing        | `pd.to_datetime()`              |
| Admission classification  | `map()`                         |
| Hospital stay calculation | Date difference                 |
| Billing analysis          | `describe()`                    |
| Stay-duration analysis    | `describe()`                    |
| Age demographics          | `groupby()`                     |
| Gender distribution       | `crosstab()`                    |

---

##  How to Run the Project

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd Healthcare-Data-Analysis
```

### 2. Install Required Libraries

```bash
pip install pandas numpy matplotlib
```

### 3. Place the Dataset

Make sure `healthcare_dataset.csv` is available in the project directory.

### 4. Run the Python File

```bash
python healthcare_data_dv_week_05.py
```

---

##  Requirements

```text
Python 3.x
Pandas
NumPy
Matplotlib
```

---

##  Project Objectives

The main objectives of this project are:

1. To understand and inspect healthcare-related data.
2. To clean and preprocess the dataset.
3. To handle missing values appropriately.
4. To transform date-related columns into usable datetime values.
5. To calculate hospital stay duration.
6. To analyze healthcare billing statistics.
7. To understand demographic patterns based on medical conditions.
8. To analyze gender distribution across medical conditions.

---

##  Future Enhancements

The project can be extended with:

*  Visual analysis of medical conditions
*  Billing amount visualizations
*  Hospital-wise patient analysis
*  Medication analysis
*  Test-result analysis
*  Doctor-wise patient analysis
*  Blood-type distribution
*  Admission-type comparison
*  Monthly/yearly admission trends
*  Correlation analysis between numerical variables
*  Interactive dashboards using Power BI or Tableau

---

##  Conclusion

This project demonstrates a basic **Healthcare Exploratory Data Analysis workflow using Python**. The dataset is cleaned and transformed before analyzing billing amounts, hospital stay durations, demographic information, and gender distribution across medical conditions.

It provides a foundation for further healthcare data exploration and visualization.

---





