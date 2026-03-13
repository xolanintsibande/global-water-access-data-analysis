#  🌍Global Access to Drinking Water
Exploratory data analysis of global drinking water access using the WHO/UNICEF JMP dataset (2020). Includes data cleaning, feature engineering, statistical analysis, and visualizations.

## Overview

Access to safe drinking water is a critical global development challenge.  
This project analyzes global water access using the **WHO/UNICEF Joint Monitoring Programme (JMP) dataset for 2020**.

The goal of the analysis was to investigate how **population size, urbanization, and national income levels relate to access to different drinking water service levels**.

This project was completed as part of the **ALX Data Analytics Program** and demonstrates practical data analysis skills including:

- Data cleaning
- Data validation
- Feature engineering
- Statistical analysis
- Data visualization
- Exploratory data analysis

---

# Dataset

Source:  
WHO / UNICEF Joint Monitoring Programme (JMP)

Dataset:  
**Estimates on the Use of Water (2020)**

Official dataset source:
https://washdata.org

The dataset contains **16 original features**, including:

| Feature | Description |
|------|------|
| name | Country name |
| pop_n | National population (in thousands) |
| pop_u | Urban population share (%) |
| income_group | Country income classification |
| wat_bas_n | Population with basic water access |
| wat_lim_n | Population with limited service |
| wat_unimp_n | Population with unimproved service |
| wat_sur_n | Population relying on surface water |

Each water access level is recorded for:

- National population
- Urban population
- Rural population

---

# Project Objective

The objective of this analysis was to answer the following questions:

1. How does the dataset population compare with global population estimates?
2. How does urbanization affect water access levels?
3. How does water access vary between national, urban, and rural populations?
4. What relationship exists between income group and water service access?

---

# Data Challenges

Before analysis could begin, several **data quality issues** were identified.

### 1. Import Errors

When importing the CSV file into Google Sheets, some rows used **semicolon separators instead of commas**, causing multiple columns to merge incorrectly.

### 2. Misaligned Rows

Some records did not contain the expected **16 features**, meaning values were assigned to incorrect columns.

### 3. Invalid Data Values

Some percentage values exceeded **100%**, which is not logically possible for population share variables.

### 4. Spreadsheet Formula Errors

Certain calculations returned **#VALUE! errors**, preventing summary statistics from working correctly.

These issues required a structured data cleaning process before performing analysis.

---

# Data Cleaning Process

## Step 1 — Correcting Column Separators

Delimiter inconsistencies were corrected using:

Data → Split Text to Columns

Rows containing semicolons were split into the correct columns.

---

## Step 2 — Row Validation

A validation column called **value_cnt** was created using the formula:

COUNTA()

This counted the number of populated cells in each row.

Expected value: **16 columns**

Rows with fewer values were filtered and corrected.

---

## Step 3 — Fixing Incorrect Rows

Five rows were identified where values were incorrectly imported due to semicolon separators.

These rows were corrected by:

- Splitting columns properly
- Re-aligning values into correct feature columns

---

## Step 4 — Handling Invalid Percentage Values

Some values exceeded 100%.

A new column was created:
wat_bas_n (rounded)
Copy code

This column corrected values exceeding logical limits.

---

## Step 5 — Handling Formula Errors

Spreadsheet errors (#VALUE!) were converted to **NAN values** to prevent statistical calculations from failing.

---

# Feature Engineering

To support deeper analysis, additional variables were created.

| New Feature | Description |
|------|------|
| value_cnt | Row validation count |
| pop_u_val | Urban population value |
| pop_r | Rural population share |
| pop_n (m) | Population converted to millions |
| pop_u (rounded) | Rounded urban share |
| pop_r (rounded) | Rounded rural share |
| wat_bas_n (rounded) | Cleaned basic water access feature |

After cleaning and feature creation, the dataset contained **23 analytical features**.

---

# Analysis

A new sheet called **Global 2020 Report** was created to summarize the dataset.

The analysis included:

### Population Comparison

- Dataset population vs global population estimates
- Urban vs rural population distribution

Global population estimate used:

7.821 billion people (2020)

Source:  
World Cities Report 2020

---

### Statistical Analysis

Measures calculated for each water service level:

- Maximum
- Minimum
- Mean
- Median
- Mode
- Standard deviation
- Interquartile range (IQR)

These statistics helped understand the **distribution of water access levels across countries**.

---

# Data Visualizations

Several charts were created to explore the data.

### Urban vs Rural Population Share

Line chart comparing:

- National population size
- Urban population share
- Rural population share

---

### Distribution of Water Access

Box and whisker plots were created to visualize:

- Basic water access
- Limited service access
- Unimproved service access
- Surface water access

For:

- National populations
- Urban populations
- Rural populations

---

### Water Access by Population Size

100% stacked column charts were created to compare water access levels based on population size.

These charts helped illustrate how access varies across different population groups.

---

### Water Access by Income Group

A pivot table was created to summarize:

- Total population
- Average urban population share
- Average water service access levels

Grouped by:

- Low income
- Lower-middle income
- Upper-middle income
- High income

---

# Key Insights

The analysis revealed several important trends:

• Most countries have **high access to basic drinking water services** at the national level.

• **Urban populations tend to have higher water access levels** than rural populations.

• **Lower-income countries show greater reliance on unimproved or surface water sources.**

• **Higher-income countries generally show the highest levels of basic water service access.**

• Population size alone does not explain water access differences; **urbanization and income level are stronger indicators.**

---

# Tools Used

Google Sheets  
Data Cleaning  
Feature Engineering  
Statistical Analysis  
Pivot Tables  
Data Visualization

---

# Skills Demonstrated

Data Cleaning  
Exploratory Data Analysis  
Statistical Analysis  
Data Visualization  
Data Validation  
Spreadsheet Analytics

---
