#  Healthcare Data Analysis – Week 06

##  Project Overview

This project focuses on **Healthcare Data Analysis and Visualization** using Python.

The analysis explores healthcare billing patterns across different **medical conditions** and **insurance providers**. The project includes data cleaning, preprocessing, statistical analysis, aggregation, and visualization techniques to understand the distribution of healthcare billing amounts.

The project is implemented using **Python, Pandas, NumPy, Matplotlib, and Seaborn**.

---

##  Objectives

The main objectives of this project are:

* Load and inspect healthcare data
* Identify and handle missing values
* Convert date columns into appropriate datetime format
* Create an admission urgency classification
* Calculate hospital stay duration
* Analyze billing statistics
* Analyze hospital stay statistics
* Study demographic information by medical condition
* Analyze gender distribution across medical conditions
* Compare billing amounts across medical conditions
* Analyze billing amounts by insurance provider
* Visualize billing patterns using stacked bar charts
* Visualize billing distributions using violin plots

---

##  Dataset

The project uses a healthcare dataset containing patient-related information such as:

* Patient Name
* Age
* Gender
* Blood Type
* Medical Condition
* Date of Admission
* Doctor
* Hospital
* Insurance Provider
* Billing Amount
* Room Number
* Admission Type
* Discharge Date
* Medication
* Test Results

The dataset is loaded into a Pandas DataFrame for analysis.

---

##  Technologies Used

| Technology | Purpose                        |
| ---------- | ------------------------------ |
| Python     | Programming language           |
| Pandas     | Data manipulation and analysis |
| NumPy      | Numerical operations           |
| Matplotlib | Data visualization             |
| Seaborn    | Statistical data visualization |

---

##  Project Structure

```text
Healthcare-Data-Analysis/
│
├── healthcare_data_dv_week_06.py
├── healthcare_dataset.csv
└── README.md
```

---

#  Data Analysis Workflow

## 1. Import Required Libraries

The project starts by importing the required Python libraries:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

Seaborn is also imported later for statistical visualizations.

---

## 2. Load Healthcare Dataset

The healthcare dataset is loaded using Pandas:

```python
df = pd.read_csv("healthcare_dataset.csv")
```

The loaded dataset is stored in a DataFrame named `df`.

---

## 3. Initial Data Exploration

The project performs initial inspection of the dataset using:

```python
df.head()
df.shape
df.describe()
df.isnull().sum()
```

These operations help understand:

* Dataset structure
* Number of rows and columns
* Numerical statistics
* Missing values

---

#  Data Cleaning & Preprocessing

## Handling Missing Values

Missing values are removed using:

```python
df = df.dropna()
```

The project also specifically removes rows where `Medical Condition` is missing:

```python
df = df.dropna(subset=["Medical Condition"])
```

---

##  Date Conversion

The admission and discharge date columns are converted into datetime format:

```python
df["Date of Admission"] = pd.to_datetime(
    df["Date of Admission"]
)

df["Discharge Date"] = pd.to_datetime(
    df["Discharge Date"]
)
```

This makes the date information suitable for further calculations and analysis.

---

#  Admission Urgency

A new `Urgency` column is created from the `Admission Type` column.

```python
df["Urgency"] = df["Admission Type"].map({
    "Emergency": "Emergency",
    "Urgent": "Urgent",
    "Elective": "Elective"
})
```

The classification contains:

* **Emergency**
* **Urgent**
* **Elective**

---

#  Hospital Stay Duration

The project calculates the number of days each patient stayed in the hospital.

```python
df["Stay_Days"] = (
    df["Discharge Date"] -
    df["Date of Admission"]
).dt.days
```

This creates a new column called `Stay_Days`.

---

#  Billing Analysis

The project performs descriptive statistical analysis on the `Billing Amount` column.

```python
df["Billing Amount"].describe()
```

The generated statistics include values such as:

* Count
* Mean
* Standard deviation
* Minimum
* Maximum
* Quartiles

---

#  Hospital Stay Analysis

Descriptive statistics are also generated for hospital stay duration:

```python
df["Stay_Days"].describe()
```

This provides an overview of the distribution of patient hospital stays.

---

#  Demographic Analysis

The project analyzes patient age based on medical condition:

```python
df.groupby("Medical Condition")["Age"].agg(
    ["count", "mean"]
)
```

This provides:

* Patient count for each medical condition
* Average patient age for each medical condition

---

#  Gender Distribution

Gender distribution across medical conditions is analyzed using:

```python
pd.crosstab(
    df["Medical Condition"],
    df["Gender"]
)
```

This allows comparison of gender counts across different medical conditions.

---

#  Billing Analysis by Medical Condition & Insurance Provider

One of the main analyses in this project is the comparison of total billing amounts across medical conditions and insurance providers.

The data is grouped using:

```python
billing_data = df.groupby(
    ['Medical Condition', 'Insurance Provider']
)['Billing Amount'].sum().unstack(fill_value=0)
```

This creates a summarized table where:

* Rows represent **Medical Conditions**
* Columns represent **Insurance Providers**
* Values represent the **total Billing Amount**

---

#  Stacked Bar Chart

The grouped billing data is visualized using a stacked bar chart:

```python
billing_data.plot(
    kind='bar',
    stacked=True,
    figsize=(12, 6)
)
```

This visualization makes it possible to compare the total billing amounts across medical conditions while also seeing the contribution from different insurance providers.

### Visualization

**Total Billing Amount by Medical Condition and Insurance Provider**

The chart uses:

* X-axis → Medical Condition
* Y-axis → Total Billing Amount
* Stacked segments → Insurance Providers

---

#  Billing Distribution by Medical Condition

Seaborn is used to create a violin plot:

```python
sns.violinplot(
    data=df,
    x='Medical Condition',
    y='Billing Amount'
)
```

A violin plot helps visualize the **distribution and spread of billing amounts** for each medical condition.

The chart is configured with:

```python
plt.title(
    'Billing Amount Distribution by Medical Condition'
)

plt.xlabel('Medical Condition')
plt.ylabel('Billing Amount')
```

---

#  Billing Distribution by Insurance Provider

Another violin plot is created to analyze billing amounts across insurance providers:

```python
sns.violinplot(
    data=df,
    x='Insurance Provider',
    y='Billing Amount'
)
```

This visualization helps examine how billing amounts are distributed across different insurance providers.

The plot includes:

```python
plt.title(
    'Billing Amount Distribution by Insurance Provider'
)

plt.xlabel('Insurance Provider')
plt.ylabel('Billing Amount')
```

---

#  Visualizations Included

The project currently includes the following visualizations:

### 1. Stacked Bar Chart

**Purpose:**
Compare total billing amounts by medical condition and insurance provider.

### 2. Violin Plot – Medical Condition

**Purpose:**
Understand the distribution of billing amounts across different medical conditions.

### 3. Violin Plot – Insurance Provider

**Purpose:**
Understand the distribution of billing amounts across insurance providers.

---

#  Analysis Summary

The project performs analysis in the following areas:

| Category                   | Analysis                                |
| -------------------------- | --------------------------------------- |
| Data Inspection            | Dataset structure and statistics        |
| Data Cleaning              | Missing-value handling                  |
| Date Processing            | Admission and discharge date conversion |
| Admission Analysis         | Emergency, Urgent, Elective             |
| Stay Analysis              | Hospital stay duration                  |
| Billing Analysis           | Billing statistics                      |
| Demographics               | Age by medical condition                |
| Gender Analysis            | Gender distribution by condition        |
| Insurance Analysis         | Billing by insurance provider           |
| Medical Condition Analysis | Billing distribution by condition       |
| Visualization              | Bar charts and violin plots             |

---

#  How to Run the Project

## Step 1: Clone the Repository

```bash
git clone <your-repository-url>
```

## Step 2: Navigate to the Project

```bash
cd Healthcare-Data-Analysis
```

## Step 3: Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn
```

## Step 4: Add the Dataset

Place the healthcare dataset in the project directory:

```text
healthcare_dataset.csv
```

## Step 5: Run the Python Script

```bash
python healthcare_data_dv_week_06.py
```

---

#  Requirements

```text
Python 3.x
pandas
numpy
matplotlib
seaborn
```

---

#  Learning Outcomes

Through this project, the following data-analysis concepts are practiced:

* Data loading with Pandas
* Data inspection
* Missing-value handling
* Data type conversion
* Feature creation
* GroupBy operations
* Aggregation
* Cross-tabulation
* Data reshaping using `unstack()`
* Statistical analysis
* Data visualization
* Bar charts
* Stacked bar charts
* Violin plots
* Healthcare data exploration

---

#  Future Improvements

The project can be extended with:

*  Interactive dashboards
*  Hospital-wise billing analysis
*  Doctor-wise analysis
*  Medication analysis
*  Test-result analysis
*  Blood-type analysis
*  Monthly admission trends
*  Admission-type analysis
*  Correlation analysis
*  Interactive visualizations using Plotly
*  Healthcare KPI dashboard
*  Predictive healthcare analytics

---

#  Conclusion

This project demonstrates an end-to-end **Healthcare Data Analysis and Visualization workflow using Python**.

The analysis begins with data inspection and cleaning, followed by date processing, hospital stay calculation, demographic analysis, billing analysis, and visualization.

A major focus of the project is understanding **billing patterns across medical conditions and insurance providers** through grouped analysis, stacked bar charts, and violin plots.

Overall, the project provides practical experience in **data preprocessing, exploratory data analysis, aggregation, statistical analysis, and data visualization** using Python.





