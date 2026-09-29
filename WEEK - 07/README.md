# Data Visualization – Week 07

## Project Overview

This project is part of Data Visualization – Week 07 and focuses on exploring and analyzing student performance data using Python.

The project uses the Students Performance dataset to understand students' scores in Mathematics, Reading, and Writing. It includes data exploration, descriptive statistics, score analysis, total score calculation, percentage calculation, and outlier detection using the Interquartile Range (IQR) method.

The analysis is performed using Pandas, NumPy, Matplotlib, and Seaborn.

---

## Objectives

The main objectives of this project are:

* Load and explore the student performance dataset
* Understand the structure and characteristics of the data
* Check for missing values and duplicate records
* Analyze Mathematics, Reading, and Writing scores
* Calculate descriptive statistics for score columns
* Calculate total scores for students
* Calculate student percentages
* Analyze score quartiles
* Detect outliers in Mathematics scores using the IQR method

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Google Colab / Jupyter Notebook

---

## Project Structure

```text
DV-Week-07/
│
├── DV_Week_07.ipynb
├── dv_week_07.py
├── StudentsPerformance.csv
└── README.md
```

### File Description

| File                      | Description                                                    |
| ------------------------- | -------------------------------------------------------------- |
| `DV_Week_07.ipynb`        | Complete Google Colab/Jupyter Notebook containing the analysis |
| `dv_week_07.py`           | Python script containing the data analysis                     |
| `StudentsPerformance.csv` | Student performance dataset used for the project               |
| `README.md`               | Project documentation                                          |

---

# Dataset

The project uses the `StudentsPerformance.csv` dataset, which contains student performance information.

The main score columns analyzed in this project are:

| Column          | Description                 |
| --------------- | --------------------------- |
| `math score`    | Student's Mathematics score |
| `reading score` | Student's Reading score     |
| `writing score` | Student's Writing score     |

The analysis focuses mainly on these three academic performance scores.

---

# Data Exploration

## 1. Import Libraries

The following Python libraries are used for data analysis and visualization:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

---

## 2. Load the Dataset

The dataset is loaded using Pandas:

```python
df = pd.read_csv("StudentsPerformance.csv")
```

The complete DataFrame is then displayed for initial inspection.

---

## 3. View the Dataset

The first records are displayed using:

```python
df.head()
```

The last records are viewed using:

```python
df.tail()
```

These operations help understand the beginning and ending records of the dataset.

---

## 4. Descriptive Statistics

The `describe()` function is used to obtain statistical information:

```python
df.describe()
```

This provides measures such as:

* Count
* Mean
* Standard deviation
* Minimum
* Maximum
* Quartiles

---

## 5. Dataset Shape

The number of rows and columns is checked using:

```python
df.shape
```

This helps understand the overall size of the dataset.

---

## 6. Dataset Information

The structure and data types of the dataset are examined using:

```python
df.info()
```

This provides information about:

* Column names
* Data types
* Non-null values
* Number of records

---

# Data Quality Analysis

## 7. Missing Value Check

Missing values are checked using:

```python
df.isnull().sum()
```

This helps identify whether any columns contain missing values.

---

## 8. Duplicate Record Check

Duplicate records are checked using:

```python
df.duplicated().sum()
```

This determines the number of duplicate rows present in the dataset.

---

# Score Analysis

## 9. Select Score Columns

The three academic score columns are selected:

```python
score_columns = [
    'math score',
    'reading score',
    'writing score'
]
```

The selected columns can then be displayed using:

```python
score_columns
```

---

## 10. Score Descriptive Statistics

Descriptive statistics for the three score columns are calculated using:

```python
df[score_columns].describe()
```

This provides statistical information about Mathematics, Reading, and Writing scores.

---

## 11. Calculate First Quartile

The first quartile (Q1) is calculated for the Mathematics score:

```python
df[score_columns].quantile(0.25)
```

The first quartile represents the value below which approximately 25% of the observations fall.

---

# Total Score Calculation

## 12. Calculate Total Score

A new `Total Score` column is created by adding Mathematics, Reading, and Writing scores.

```python
df["Total Score"] = (
    df["math score"]
    + df["reading score"]
    + df["writing score"]
)
```

The available columns can then be checked using:

```python
df.columns
```

The total score represents the combined performance across the three subjects.

---

# Percentage Calculation

## 13. Calculate Percentage

A new `Percentage` column is created from the total score.

Since the maximum possible total score is 300, the percentage is calculated using:

```python
df["Percentage"] = (
    df["Total Score"] / 300
) * 100
```

The calculated total score and percentage are displayed using:

```python
df[["Total Score", "Percentage"]].head()
```

---

# Outlier Detection

## 14. Mathematics Score Outliers

The Interquartile Range (IQR) method is used to identify potential outliers in Mathematics scores.

### Step 1: Calculate Q1

```python
Q1 = df['math score'].quantile(0.25)
```

### Step 2: Calculate Q3

```python
Q3 = df['math score'].quantile(0.75)
```

### Step 3: Calculate IQR

```python
IQR = Q3 - Q1
```

### Step 4: Identify Outliers

The lower and upper boundaries are calculated using the standard IQR rule:

```python
outliers = df[
    (df['math score'] < (Q1 - 1.5 * IQR)) |
    (df['math score'] > (Q3 + 1.5 * IQR))
]
```

The number of detected Mathematics score outliers is then displayed:

```python
print(
    f"Number of outliers in math score: {len(outliers)}"
)
```

---

# Analysis Workflow

```text
Load Student Performance Dataset
            |
            v
Explore Dataset
            |
            v
Check Shape and Information
            |
            v
Check Missing Values
            |
            v
Check Duplicate Records
            |
            v
Analyze Subject Scores
            |
            v
Calculate Total Score
            |
            v
Calculate Percentage
            |
            v
Calculate Quartiles
            |
            v
Calculate IQR
            |
            v
Detect Mathematics Score Outliers
```

---

# Concepts Covered

This project demonstrates the following Data Analysis and Data Visualization concepts:

* Data Loading
* Data Exploration
* DataFrame Operations
* Descriptive Statistics
* Data Quality Checking
* Missing Value Analysis
* Duplicate Record Analysis
* Quartile Calculation
* Total Score Calculation
* Percentage Calculation
* Interquartile Range (IQR)
* Outlier Detection
* Student Performance Analysis

---

# How to Run

## Google Colab

1. Open `DV_Week_07.ipynb` in Google Colab.
2. Upload `StudentsPerformance.csv`.
3. Make sure the CSV filename matches the filename used in the notebook.
4. Run the notebook cells from top to bottom.

## Jupyter Notebook

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn
```

Open:

```text
DV_Week_07.ipynb
```

Run the cells sequentially.

## Python Script

Run the Python script using:

```bash
python dv_week_07.py
```

Make sure `StudentsPerformance.csv` is available in the expected location.

---

# Project Outcome

This project provides practical experience in analyzing student performance data using Python.

The dataset is explored through descriptive statistics and data quality checks. Mathematics, Reading, and Writing scores are analyzed individually, after which a combined Total Score and Percentage are calculated for each student.

The project also introduces the IQR method for detecting potential outliers in Mathematics scores, providing a foundation for further statistical analysis and visualization.

---
