# Data Visualization – Week 06

## Project Overview

This project is part of Data Visualization – Week 06 and focuses on exploring, preprocessing, analyzing, and visualizing a healthcare dataset using Python.

The project extends basic healthcare data analysis by introducing visualizations for patient distribution across medical conditions and billing amount variation across medical conditions.

The analysis is performed using Pandas, NumPy, Matplotlib, and Seaborn.

---

## Objectives

The main objectives of this project are:

* Load and explore the healthcare dataset
* Understand the structure and statistical summary of the data
* Handle missing values
* Convert admission and discharge dates into datetime format
* Create an admission urgency feature
* Calculate hospital stay duration
* Analyze billing amount statistics
* Analyze hospital stay statistics
* Analyze demographics by medical condition
* Analyze gender distribution by medical condition
* Visualize the number of patients by medical condition
* Visualize billing amount variation across medical conditions

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
DV-Week-06/
│
├── DV_Week_06.ipynb
├── dv_week_06.py
├── healthcare_dataset(3).csv
└── README.md
```

### File Description

| File                        | Description                                                                       |
| --------------------------- | --------------------------------------------------------------------------------- |
| `DV_Week_06.ipynb`          | Complete Google Colab/Jupyter Notebook containing the analysis and visualizations |
| `dv_week_06.py`             | Python script containing the complete analysis                                    |
| `healthcare_dataset(3).csv` | Healthcare dataset used for the project                                           |
| `README.md`                 | Project documentation                                                             |

---

# Dataset

The project uses a healthcare dataset containing patient, admission, medical, billing, and treatment-related information.

The dataset contains **55,500 records and 15 columns**.

### Dataset Columns

| Column               | Description                 |
| -------------------- | --------------------------- |
| `Name`               | Patient name                |
| `Age`                | Patient age                 |
| `Gender`             | Patient gender              |
| `Blood Type`         | Patient blood type          |
| `Medical Condition`  | Patient's medical condition |
| `Date of Admission`  | Patient admission date      |
| `Doctor`             | Assigned doctor             |
| `Hospital`           | Hospital name               |
| `Insurance Provider` | Insurance provider          |
| `Billing Amount`     | Patient billing amount      |
| `Room Number`        | Assigned room number        |
| `Admission Type`     | Type of admission           |
| `Discharge Date`     | Patient discharge date      |
| `Medication`         | Medication provided         |
| `Test Results`       | Medical test result         |

---

# Data Analysis and Preprocessing

## 1. Import Libraries

The project uses Pandas, NumPy, Matplotlib, and Seaborn.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

---

## 2. Load the Dataset

The healthcare dataset is loaded using Pandas.

```python
df = pd.read_csv("healthcare_dataset.csv")
```

The original dataset is displayed for initial inspection.

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

These operations help understand the size, structure, and numerical characteristics of the dataset.

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

This step prepares the dataset for further analysis.

---

## 5. Convert Date Columns

The admission and discharge date columns are converted into datetime format.

```python
df["Date of Admission"] = pd.to_datetime(
    df["Date of Admission"]
)

df["Discharge Date"] = pd.to_datetime(
    df["Discharge Date"]
)
```

The standardized date values are then displayed.

```python
print(df[["Date of Admission", "Discharge Date"]].head())
```

---

# Feature Engineering

## 6. Create Admission Urgency

A new `Urgency` column is created from the `Admission Type` column.

```python
df["Urgency"] = df["Admission Type"].map({
    "Emergency": "Emergency",
    "Elective": "Elective",
    "Urgent": "Urgent"
})
```

The admission type and newly created urgency values are displayed using:

```python
print(df[["Admission Type", "Urgency"]].head())
```

