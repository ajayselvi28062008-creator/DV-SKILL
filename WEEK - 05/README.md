# Data Visualization – Week 05

## Project Overview

This project is part of Data Visualization – Week 05 and focuses on exploring, preprocessing, and analyzing a healthcare dataset using Python.

The project demonstrates practical data preprocessing and exploratory analysis techniques using Pandas and NumPy. The analysis includes handling missing values, standardizing date columns, creating new features, calculating hospital stay duration, analyzing billing amounts, and studying demographics by medical condition.

---

## Objectives

The main objectives of this project are:

* Load and explore the healthcare dataset
* Understand the structure and statistical summary of the data
* Handle missing values
* Standardize admission and discharge date columns
* Create an admission urgency feature
* Calculate hospital stay duration
* Analyze billing amount statistics
* Analyze hospital stay statistics
* Study age demographics by medical condition
* Analyze gender distribution across medical conditions

---

## Technologies Used

* Python
* Pandas
* NumPy
* Google Colab / Jupyter Notebook

---

## Project Structure

```text
DV-Week-05/
│
├── DV_Week_05.ipynb
├── dv_week_05.py
├── healthcare_dataset(2).csv
└── README.md
```

### File Description

| File                        | Description                                                    |
| --------------------------- | -------------------------------------------------------------- |
| `DV_Week_05.ipynb`          | Complete Google Colab/Jupyter Notebook containing the analysis |
| `dv_week_05.py`             | Python script containing the data preprocessing and analysis   |
| `healthcare_dataset(2).csv` | Healthcare dataset used for the analysis                       |
| `README.md`                 | Project documentation                                          |

---

# Dataset

The project uses a healthcare dataset containing patient-related information such as admission details, medical conditions, dates, billing information, age, and gender.

The analysis works with fields including:

* `Date of Admission`
* `Discharge Date`
* `Admission Type`
* `Medical Condition`
* `Age`
* `Gender`
* `Billing Amount`

---

# Data Analysis and Preprocessing

## 1. Import Libraries

The project uses Pandas and NumPy for data processing and analysis.

```python
import pandas as pd
import numpy as np
```

---

## 2. Load the Dataset

The healthcare dataset is loaded using Pandas:

```python
df = pd.read_csv("healthcare_dataset.csv")
```

The original data is then displayed for initial inspection.

```python
print("Original Data:")
print(df.head())
```

---

## 3. Explore the Dataset

The shape of the dataset is checked using:

```python
print(df.shape)
```

Statistical information is obtained using:

```python
print(df.describe())
```

These operations help understand the size and numerical characteristics of the dataset.

---

## 4. Handle Missing Values

Missing records are removed using:

```python
df = df.dropna()
```

The dataset is then checked for remaining missing values:

```python
print(df.isnull().sum())
```

This preprocessing step ensures that missing values are handled before performing further analysis.

---

## 5. Standardize Date Columns

The admission and discharge date columns are converted into datetime format.

```python
df["Date of Admission"] = pd.to_datetime(
    df["Date of Admission"]
)

df["Discharge Date"] = pd.to_datetime(
    df["Discharge Date"]
)
```

The standardized dates are then displayed:

```python
print(df[["Date of Admission", "Discharge Date"]].head())
```

---

# Feature Engineering

## 6. Create Admission Urgency

A new `Urgency` column is created based on the `Admission Type` column.

```python
df["Urgency"] = df["Admission Type"].map({
    "Emergency": "Emergency",
    "Elective": "Elective",
    "Urgent": "Urgent"
})
```

The resulting admission type and urgency values are displayed using:

```python
print(df[["Admission Type", "Urgency"]].head())
```

This creates a standardized urgency classification for the admission types present in the dataset.

---

## 7. Calculate Hospital Stay Duration

A new `Stay_Days` column is created by calculating the difference between discharge date and admission date.

```python
df["Stay_Days"] = (
    df["Discharge Date"] - df["Date of Admission"]
).dt.days
```

This feature represents the number of days a patient stayed in the hospital.

---

# Statistical Analysis

## 8. Billing Amount Statistics

The statistical summary of billing amounts is calculated using:

```python
print(df["Billing Amount"].describe())
```

This provides statistical measures such as:

* Count
* Mean
* Standard deviation
* Minimum
* Maximum
* Quartiles

---

## 9. Hospital Stay Statistics

The statistical summary of hospital stay duration is calculated using:

```python
print(df["Stay_Days"].describe())
```

This helps understand the distribution and variation of hospital stay durations.

---

# Demographic Analysis

## 10. Demographics by Medical Condition

Age demographics are analyzed for each medical condition using group-by aggregation.

```python
demographics = df.groupby(
    "Medical Condition"
)["Age"].agg(["count", "mean"])
```

The results are displayed using:

```python
print("\nDemographics by Medical Condition:")
print(demographics)
```

This analysis provides:

* Number of records for each medical condition
* Average age associated with each medical condition

---

## 11. Gender Distribution by Medical Condition

A cross-tabulation is used to analyze gender distribution across medical conditions.

```python
gender_distribution = pd.crosstab(
    df["Medical Condition"],
    df["Gender"]
)
```

The result is displayed using:

```python
print("\nGender Distribution by Medical Condition:")
print(gender_distribution)
```

This provides a structured view of gender counts for each medical condition.

---

# Analysis Workflow

```text
Load Healthcare Dataset
        |
        v
Explore Dataset
        |
        v
Check Dataset Structure
        |
        v
Remove Missing Values
        |
        v
Convert Date Columns
        |
        v
Create Admission Urgency
        |
        v
Calculate Hospital Stay Days
        |
        v
Analyze Billing Statistics
        |
        v
Analyze Hospital Stay Statistics
        |
        v
Analyze Demographics
        |
        v
Analyze Gender Distribution
```

---

# Concepts Covered

This project demonstrates the following concepts:

* Data Loading
* Data Exploration
* Data Preprocessing
* Missing Value Handling
* Date and Time Conversion
* Feature Engineering
* GroupBy Operations
* Aggregation
* Statistical Analysis
* Cross Tabulation
* Demographic Analysis
* Healthcare Data Analysis

---

# How to Run

## Google Colab

1. Open `DV_Week_05.ipynb` in Google Colab.
2. Upload the healthcare CSV dataset.
3. Make sure the dataset filename matches the filename used in the notebook.
4. Run the notebook cells from top to bottom.

## Jupyter Notebook

Install the required libraries:

```bash
pip install pandas numpy
```

Open:

```text
DV_Week_05.ipynb
```

Run the cells sequentially.

## Python Script

Run the Python script using:

```bash
python dv_week_05.py
```

Make sure the healthcare CSV dataset is available in the expected location.

---

# Project Outcome

This project provides practical experience in working with healthcare data using Python.

The dataset is explored and prepared through missing-value handling and date conversion. Additional features such as admission urgency and hospital stay duration are created for further analysis.

The project also performs statistical analysis of billing amounts and hospital stays, along with demographic analysis based on medical conditions and gender distribution.

---


