# House Sales Data Analysis – DV Week 09

## Project Overview

This project focuses on data cleaning, preprocessing, and feature engineering using the House Sales dataset. It uses Python to explore housing data, process sale date and time information, create new property-related features, calculate price metrics, and identify potential outliers in house prices.

The project demonstrates practical data preprocessing techniques using Pandas, NumPy, and other Python data analysis libraries.

## Objectives

- Explore and understand the house sales dataset.
- Inspect dataset structure, columns, and descriptive statistics.
- Check missing values and duplicate records.
- Convert sale date and time values into a datetime format.
- Extract date and time components for further analysis.
- Clean records with missing or invalid property values.
- Create property age and renovation-related features.
- Calculate price per square foot for living area and lot area.
- Identify potential house price outliers using the IQR method.
- Export the processed dataset as a CSV file.

## Dataset Description

The project uses the `kc_house_data.csv` dataset, which contains house sales information and property characteristics.

### Important Features

| Column | Description |
|---|---|
| `id` | Property identifier |
| `date` | Sale date and time |
| `price` | House sale price |
| `bedrooms` | Number of bedrooms |
| `bathrooms` | Number of bathrooms |
| `sqft_living` | Interior living area in square feet |
| `sqft_lot` | Total lot area in square feet |
| `floors` | Number of floors |
| `waterfront` | Waterfront property indicator |
| `view` | Property view rating |
| `condition` | Property condition rating |
| `grade` | Construction and design grade |
| `sqft_above` | Area above ground level |
| `sqft_basement` | Basement area |
| `yr_built` | Year the house was built |
| `yr_renovated` | Year the house was renovated, if applicable |
| `zipcode` | Property ZIP code |
| `lat` | Property latitude |
| `long` | Property longitude |
| `sqft_living15` | Living area of nearby properties |
| `sqft_lot15` | Lot area of nearby properties |

## Technologies Used

- **Python** – Programming language
- **Pandas** – Data manipulation and preprocessing
- **NumPy** – Numerical calculations and conditional operations
- **Matplotlib** – Data visualization library
- **Seaborn** – Statistical data visualization library
- **Jupyter Notebook** – Interactive development environment

## Project Workflow

### 1. Data Loading and Exploration

- Load the CSV dataset into a Pandas DataFrame.
- Display the first and last records.
- Examine dataset information and dimensions.
- Inspect column names and descriptive statistics.
- Check missing values and duplicate records.

### 2. Date and Time Processing

Convert the `date` column into a datetime format using the specified date-time pattern.

Extract the following components:

- `sale_year` – Year of sale
- `sale_month` – Month of sale
- `sale_day` – Day of sale
- `sale_hour` – Hour component
- `sale_minute` – Minute component
- `sale_second` – Second component

These features organize the original sale date and time into separate columns.

### 3. Data Cleaning

- Remove records with missing values in `price`, `sqft_living`, and `sqft_lot`.
- Filter out records with non-positive house prices.
- Remove records with non-positive living areas or lot areas.

These steps help prepare the dataset for subsequent calculations.

### 4. Feature Engineering

Create additional columns to support property-related analysis.

**Property Age**

Calculate the difference between the sale year and the construction year.

`property_age = sale_year - yr_built`

**Renovation Indicator**

Create `is_renovated` to indicate whether a renovation year is recorded.

- `1` – Renovation year is greater than zero.
- `0` – No positive renovation year is recorded.

**Years Since Renovation**

Calculate the difference between the sale year and renovation year for renovated properties. For properties without a recorded renovation year, the value is set to zero.

**Price Per Square Foot**

Calculate two additional metrics:

- `price_per_sqft_living` – House price divided by living area.
- `price_per_sqft_lot` – House price divided by lot area.

### 5. Outlier Detection

Use the Interquartile Range (IQR) method to identify potential outliers in house prices.

The calculation uses:

`IQR = Q3 - Q1`

Where:
- `Q1` represents the first quartile.
- `Q3` represents the third quartile.
- `IQR` represents the interquartile range.

Potential outliers are values outside the following limits:

- Lower limit: `Q1 - 1.5 × IQR`
- Upper limit: `Q3 + 1.5 × IQR`

The program counts and prints the number of house price outliers. These records are identified but are not automatically removed by the outlier detection step.

### 6. Export the Processed Dataset

Save the processed dataset as:

`House_Sales_Data_Cleaned_Week_09.csv`

The exported file includes the original columns retained during processing and the additional engineered features.

## Project Structure

```text
House-Sales-Data-Analysis/
|
|-- dv_week_09.py
|-- DV_Week_09.ipynb
|-- kc_house_data.csv
|-- README.md
```

The cleaned CSV file is generated when the Python script or notebook executes the export statement successfully.

## Installation and Setup

### Prerequisites

Install Python and the required libraries before running the project.

### Step 1: Clone the Repository

```bash
git clone <your-repository-url>
cd House-Sales-Data-Analysis
```

### Step 2: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Step 3: Run the Jupyter Notebook

```bash
jupyter notebook
```

Open `DV_Week_09.ipynb` and run the cells sequentially.

### Step 4: Run the Python Script

The original code uses a Google Colab file path. For local execution, update the CSV loading statement to match the filename uploaded to your repository.

For the current filename:

```python
df = pd.read_csv("kc_house_data(1).csv")
```

Then run:

```bash
python dv_week_09.py
```

After successful execution, the cleaned dataset will be saved in the working directory.

## Key Learning Outcomes

- Understanding and exploring structured datasets.
- Performing data quality checks and preprocessing.
- Converting date-time data and extracting useful components.
- Creating new features from existing data.
- Calculating property-related price metrics.
- Applying the IQR method to detect potential outliers.
- Exporting processed data for further analysis.

## Future Enhancements

- Visualize house price distributions and potential outliers.
- Analyze house price trends across different sale periods.
- Compare prices based on property size, location, and condition.
- Explore correlations between house prices and property characteristics.
- Create an interactive dashboard using Plotly or Tableau.
- Develop a machine learning model for house price prediction.
