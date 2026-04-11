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

### [Lab 3: Association Rule Mining](./R-LAB3-Association-Rule-using-Apriori.ipynb)
Market basket analysis using the Apriori algorithm.
- **Library**: `arules`, `arulesViz`
- **Metrics**: Support, Confidence, and Lift.
- **Visuals**: Transaction density plots and rule-network graphs.

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
  - ROC Curve & AUC (Area Under the Curve).

### [Lab 6: Naive Bayesian Classifier](./R-LAB6-Naive-Bayesian-Classifier.ipynb)
Probabilistic classification based on Bayes' Theorem.
- **Library**: `e1071`
- **Application**: Predicting outcomes based on prior probabilities and evidence.
- **Key Concepts**: Conditional probability, Laplacian smoothing, and class-wise distributions.

### [Lab 7a: Recursive Partitioning (Decision Trees)](./R-LAB7a-Recursive-Partitioning.ipynb)
Tree-based modeling for non-linear decision boundaries.
- **Library**: `rpart`, `rpart.plot`
- **Functionality**: Splitting data based on Information Gain/Gini Impurity.
- **Visualization**: Plotting the decision tree structure for interpretability.

### [Lab 7b: K-Means Clustering](./R-LAB7b-K-Means-Clustering.ipynb)
Unsupervised learning for grouping similar data points.
- **Concept**: Partitioning $n$ observations into $k$ clusters based on Euclidean distance.
- **Optimization**: Finding the optimal $k$ using the **Elbow Method** (Total Within-Cluster Sum of Squares).
- **Visualization**: Cluster plots using `factoextra`.

### [Lab 8: Random Forest](./R-LAB8-Random-Forest.ipynb)
Ensemble learning for high-accuracy classification.
- **Library**: `randomForest`
- **Methodology**: Combining multiple decision trees to reduce variance and prevent overfitting.
- **Key Outputs**: Feature importance (Variable Importance Plot) and Out-of-Bag (OOB) error estimate.

## 📊 Datasets Used
- **mtcars**: Motor Trend Car Road Tests.
- **Boston**: Housing values in suburbs of Boston.
- **GermanCredit**: Credit risk data for classification.
- **Groceries**: Transactional dataset for Association Rules.
- **Default/Standard Datasets**: Internal datasets used for Naive Bayes and Trees.

## 🎓 VIVA Preparation Guides
Comprehensive study guides for the DSRP VIVA are available here:
- [VIVA Prep Index](./VIVA_Prep_Index.md)
- [Assignment 3: Apriori](./VIVA_Assignment_3.md)
- [Assignment 6: Naive Bayes](./VIVA_Assignment_6.md)
- [Assignment 7a: Decision Trees](./VIVA_Assignment_7a.md)
- [Assignment 7b: K-Means](./VIVA_Assignment_7b.md)
- [Assignment 8: Random Forest](./VIVA_Assignment_8.md)

## 🛠 Prerequisites
To run these notebooks, you will need:
- **R (>= 4.0)**
- **Required Packages**: `MASS`, `caret`, `pROC`, `ggplot2`, `arules`, `arulesViz`, `e1071`, `rpart`, `rpart.plot`, `randomForest`, `factoextra`, `cluster`.
- **Environment**: Jupyter Notebook or Google Colab with R Kernel.

---
*Created as part of the DSRP Lab work (Sem 6).*
