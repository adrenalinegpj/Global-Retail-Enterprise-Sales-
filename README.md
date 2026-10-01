Global Retail Enterprise Sales & Profitability Cube

Project Overview

This project analyzes retail sales and profitability data using Python, Pandas, NumPy, Matplotlib, Seaborn, and Power BI.

The workflow starts with data entry and exploration, followed by data cleaning and preparation. The cleaned dataset can then be used for business analysis and dashboard development.

Project Files

Global Retail cleaned.csv - Cleaned retail dataset used for analysis.

Global_Retail_Enterprise_Sales_pbi(1).pbix - Power BI project containing the business intelligence and visualization layer.

global_retail_enterprise_sales_&_profitability_cube(1).py - Python data loading, exploration, and cleaning workflow.

Dataset

The dataset contains retail order information including:

Order and shipping dates

Shipping mode

Customer information

Customer segment

Country, city, state, and region

Product category and sub-category

Postal code

Sales

Quantity

Discount

Profit

The uploaded cleaned dataset contains 9,994 rows and 21 columns.

Python Workflow

1. Libraries

The project uses:

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

2. Data Loading

The original dataset is loaded with Pandas:

df = pd.read_csv("Sample - Superstore.csv", encoding="latin1")

3. Data Exploration

The workflow checks:

Dataset preview

Column names

Dataset shape

Data types

Numerical descriptive statistics

Categorical descriptive statistics

Missing values

Duplicate rows

Examples:

df.head()
df.columns.to_list()
df.shape
df.info()
df.dtypes
df.describe()
df.describe(include="object")
df.isnull().sum()
df.duplicated().sum()

4. Categorical Data Cleaning

Categorical columns are inspected for unique values and then cleaned by removing extra spaces and standardizing capitalization.

for col in cat_cols:
    df[col] = df[col].str.strip()
    df[col] = df[col].str.capitalize()

5. Numerical Data Cleaning

The numerical columns are converted to numeric data types:

for col in num_cols:
    df[col] = pd.to_numeric(df[col])

The numerical fields include:

Postal Code

Sales

Quantity

Discount

Profit

6. Date Cleaning

Order and shipping dates are converted to datetime values. Invalid date values are converted to missing values using errors="coerce".

for col in date_cols:
    df[col] = pd.to_datetime(df[col], errors="coerce")

7. Exporting the Cleaned Dataset

The cleaned dataframe is exported as a CSV file:

df.to_csv("cleaned_data.csv", index=False)

Dataset Columns

The cleaned dataset includes the following fields:

Row ID

Order ID

Order Date

Ship Date

Ship Mode

Customer ID

Customer Name

Segment

Country

City

State

Postal Code

Region

Product ID

Category

Sub-Category

Product Name

Sales

Quantity

Discount

Profit

Tools and Technologies

Python

Pandas

NumPy

Matplotlib

Seaborn

Power BI

CSV

Project Objective

The objective is to prepare retail data for reliable analysis by:

Loading the source dataset.

Exploring its structure and quality.

Identifying missing and duplicate records.

Cleaning categorical values.

Converting numerical fields to appropriate data types.

Converting date fields to datetime format.

Exporting a cleaned dataset.

Using the cleaned data as the foundation for business intelligence and profitability analysis in Power BI.

Project Structure

Global Retail Enterprise Sales & Profitability Cube/
|
|-- global_retail_enterprise_sales_&_profitability_cube(1).py
|-- Global Retail cleaned.csv
|-- Global_Retail_Enterprise_Sales_pbi(1).pbix
|-- README.md

How to Run the Python Workflow

Open the Python script or notebook in Google Colab or a compatible Python environment.

Make sure the source CSV file is available in the working directory.

Run the data loading and exploration cells.

Run the data cleaning steps.

Export the cleaned dataset.

Open the Power BI file to continue with visualization and business analysis.

Notes

The Python workflow was originally generated in Google Colab. The uploaded script documents the data-entry, exploration, cleaning, and export stages of the project.
