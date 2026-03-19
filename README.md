#  🌍Global Access to Drinking Water

Urban population show higher basic water access than rural populations.

Mean urban access : 77.79%

Rural access : 62.62%

Gap scale : 15.17%

## Overview

Access to safe drinking water is a critical global development challenge.  
This project analyzes global water access using the **WHO/UNICEF Joint Monitoring Programme (JMP) dataset for 2020**.

The goal of the analysis was to investigate how **population size, urbanization, and national income levels relate to access to different drinking water service levels**.

---

# Key Results 

- Mean national basic water access : 88.5%

- Mean rural basic water access : 62.62%
  
- Mean urban basic water access : 77.79%

  <b> Rural vs Urban gap</b> :
        77.79 - 62.62 = 15.17 %
  
- Mean rural unimproved water access : 6.72%

- Mean urban unimproved water access : 1.41%

- Median national basic water access : 97.10%

- Median rural basic water access : 79.94%

- Median urban basic water access : 96.98%


  
# Dataset

Source:  
WHO / UNICEF Joint Monitoring Programme (JMP)

Dataset:  
**Estimates on the Use of Water (2020)**

<img width="1594" height="583" alt="raw data" src="https://github.com/user-attachments/assets/4bb6623f-059a-4563-ade8-0b90bd04a9b9" />

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

1. What percentage difference exist between rural and urban basic water access   
2. How does water access vary between national, urban, and rural populations?
   
3. What relationship exists between income group and water service access?

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

## Step 1 Correcting Column Separators

Delimiter inconsistencies were corrected using:

Data → Split Text to Columns

Rows containing semicolons were split into the correct columns.

---

## Step 2 Row Validation

A validation column called **value_cnt** was created using the formula:

COUNTA()

This counted the number of populated cells in each row.

Expected value: **16 columns**

Rows with fewer values were filtered and corrected.

<img width="1600" height="370" alt="COUNT A " src="https://github.com/user-attachments/assets/bf882de3-47a9-4f39-ad15-532d068f4beb" />

---

## Step 3 Fixing Incorrect Rows

Five rows were identified where values were incorrectly imported due to semicolon separators.

These rows were corrected by:

- Splitting columns properly
- Re-aligning values into correct feature columns

---

## Step 4 Handling Invalid Percentage Values

Some values exceeded 100%.

A new column was created:

wat_bas_n (rounded)


This column corrected values exceeding logical limits.

---

## Step 5 Handling Formula Errors

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

<img width="1600" height="648" alt="frst" src="https://github.com/user-attachments/assets/62143e8e-2efa-4d32-8e4b-0b5019c25de0" />



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

 Mean measures overall trend
  
Median reduces impact of extreme values

Interquartile range measures spread of middle 50%

These statistics helped understand the **distribution of water access levels across countries**.


<img width="1600" height="590" alt="population                                                                                              (2)" src="https://github.com/user-attachments/assets/257c0046-cad8-4b31-90b1-298f8e9bdd57" />

---

# Data Visualizations

Several charts were created to explore the data.

### Urban vs Rural Population Share

Line chart comparing:

- National population size
- Urban population share
- Rural population share

Insight: Population distribution varies significantly across countries
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
  
Insight: Rural access shows wider variability
---

### Water Access by Population Size

100% stacked column charts were created to compare water access levels based on population size.

These charts helped illustrate how access varies across different population groups.


## Insight: Basic water access dominates
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

  <img width="796" height="342" alt="pvit" src="https://github.com/user-attachments/assets/566adf9f-d22e-463f-85ad-cee61cb32ceb" />



---

# Key Insights

The analysis revealed several important trends:

• Most countries have **high access to basic drinking water services** at the national level.

• **Urban populations tend to have higher water access levels** than rural populations.

• **Lower-income countries show greater reliance on unimproved or surface water sources.**

• **Higher-income countries generally show the highest levels of basic water service access.**

• Population size alone does not explain water access differences; **urbanization and income level are stronger indicators.**

## global-water-access-analysis


<img width="1600" height="620" alt="all" src="https://github.com/user-attachments/assets/f1eb6a07-63bd-4799-8c4e-b1007465434b" />

---

# Tools Used

Google Sheets

Used for:

- Data cleaning

- Data validation

- Statistical analysis

- Visualization

---

# Skills Demonstrated

Data Cleaning  
Exploratory Data Analysis  
Statistical Analysis  
Data Visualization  
Data Validation  
Spreadsheet Analytics

---
