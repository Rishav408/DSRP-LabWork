# DSRP - Data Science using R Programming Lab Work

A comprehensive collection of lab assignments and datasets for the **Data Science using R Programming (DSRP)** course. This repository includes Jupyter Notebooks covering R fundamentals, statistical hypothesis testing, and machine learning models (Regression & Classification).

## 🚀 Repository Overview

This project serves as a structured repository for lab work, exploring various data analysis and predictive modeling techniques using R.

## 📁 Lab Assignments

### [Lab 1: R Programming Fundamentals](./R-LAB1-Basics%20R.ipynb)
Focuses on the core syntax and data structures in R.
- **Concepts Covered**: Variable assignment, control flow (`if-else`, loops), custom functions.
- **Data Structures**: Vectors, Lists, Matrices, Factors, and Data Frames.
- **Key Operations**: Iteration over strings/vectors, sequence generation, and data manipulation.

### [Lab 2: Statistical Hypothesis Testing](./R-LAB2-Hypothesis%20Testing.ipynb)
Explores inferential statistics to draw conclusions from data.
- **Correlation**: Analyzing relationships between variables using scatter plots and correlation matrices.
- **T-Tests**: Performing one-sample, two-sample independent, and paired t-tests.
- **Chi-Square Test**: Testing the independence of categorical variables.
- **ANOVA**: Conducting One-Way Analysis of Variance to compare means across multiple groups.

### [Lab 4: Linear Regression Analysis](./R-Lab4-Linear%20Regression.ipynb)
Implementation of predictive models for continuous variables.
- **Simple Linear Regression**: Modeling the relationship between vehicle weight (`wt`) and fuel efficiency (`mpg`) using the `mtcars` dataset.
- **Multiple Linear Regression**: Step-by-step feature selection and model diagnostic on the `Boston` housing dataset.
- **Visualization**: Scatter plots with regression lines and residual diagnostics.

### [Lab 5: Logistic Regression and Classification](./R-Lab5-Logistic%20Regression.ipynb)
Applying classification techniques for binary outcomes.
- **Case Study**: Predict credit status (Good/Bad) using the `GermanCredit` dataset.
- **Modeling**: Training logistic models and interpreting results.
- **Evaluation**: 
  - Confusion Matrix (Accuracy, Sensitivity, Specificity).
  - ROC Curve & AUC (Area Under the Curve) using `pROC`.
  - Visualization of the Logistic (Sigmoid) function.

## 📊 Datasets Used
- **mtcars**: Motor Trend Car Road Tests (built-in).
- **Boston**: Housing values in suburbs of Boston (from `MASS` package).
- **GermanCredit**: Credit risk data for classification modeling.

## 🛠 Prerequisites
To run these notebooks, you will need:
- **R (>= 4.0)**
- **Required Packages**: `MASS`, `caret`, `pROC`, `ggplot2`.
- **Environment**: Jupyter Notebook or Google Colab with R Kernel.

---
*Created as part of the DSRP Lab work (Sem 6).*
