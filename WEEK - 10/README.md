# House Price Analysis and Data Visualization

## Project Overview

This project focuses on analyzing and visualizing house price data using Python. It explores the relationship between property prices and various housing features such as living area, property grade, waterfront availability, and geographical location.

The project uses the **King County House Sales Dataset** to understand housing price distributions and identify patterns through different data visualization techniques.

## Objectives

- Analyze house price data using Python.
- Understand the relationship between living area and property prices.
- Compare property prices across different grades.
- Analyze the impact of waterfront availability on house prices.
- Visualize geographical property price distribution.
- Practice data cleaning, preprocessing, and visualization techniques.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook / Google Colab

## Dataset Information

**Dataset:** King County House Sales Dataset

- Total Records: 21,613
- Total Columns: 21
- File Format: CSV

The dataset contains information about house sales, including:

- Price
- Bedrooms
- Bathrooms
- Living Area
- Lot Area
- Floors
- Waterfront
- Property Grade
- Year Built
- Latitude and Longitude

## Data Visualization Techniques

The following visualizations are implemented in this project:

### 1. Living Area vs Property Price
A regression plot is used to understand the relationship between house living area and property price.

### 2. Price Distribution Across Property Grades
A box plot is used to compare property prices across different property grades.

### 3. Price by Waterfront Status
A box plot compares the prices of waterfront and non-waterfront properties.

### 4. Geographic Property Price Distribution
A scatter plot represents house locations using latitude and longitude, with colors indicating property prices.

## Data Preprocessing

The following preprocessing steps are performed:

- Imported the required Python libraries.
- Loaded the CSV dataset using Pandas.
- Inspected the dataset using `head()`, `tail()`, `info()`, and `describe()`.
- Removed unnecessary spaces from column names.
- Converted selected columns into numeric data types.
- Removed missing values from important columns.
- Filtered out invalid property prices and living area values.

## Project Structure

```text
House-Price-Analysis/
│
├── DV_Week_10.ipynb
├── dv_week_10.py
├── kc_house_data.csv
└── README.md
```

## Installation and Execution

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/House-Price-Analysis.git
```

### Step 2: Navigate to the Project Folder

```bash
cd House-Price-Analysis
```

### Step 3: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Step 4: Run the Jupyter Notebook

```bash
jupyter notebook DV_Week_10.ipynb
```

**Note:** Update the CSV file path in the Python code according to your local project folder.

## Expected Outcomes

- Understand housing price patterns.
- Identify the relationship between living area and property prices.
- Compare house prices based on property grades.
- Explore waterfront property price differences.
- Understand geographical variations in house prices through visualization.

## Learning Outcomes

Through this project, I gained practical experience in:

- Data loading and exploration.
- Data cleaning and preprocessing.
- Exploratory Data Analysis (EDA).
- Statistical visualization.
- Creating plots using Matplotlib and Seaborn.
- Interpreting visual patterns in real-world datasets.


