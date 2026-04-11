# DSRP Lab VIVA Preparation Guide
## Assignments: 3, 6, 7a, 7b, 8

This guide is designed to help you prepare for your Data Science and R Programming (DSRP) VIVA. It breaks down each assignment by theory, logic, and coding implementation.

### Navigation
1. [Assignment 3: Association Rule Mining (Apriori)](file:///d:/College/Sem%206/DSRP/DSRP-LabWork/VIVA_Assignment_3.md)
2. [Assignment 6: Naive Bayesian Classifier](file:///d:/College/Sem%206/DSRP/DSRP-LabWork/VIVA_Assignment_6.md)
3. [Assignment 7a: Recursive Partitioning (Decision Trees)](file:///d:/College/Sem%206/DSRP/DSRP-LabWork/VIVA_Assignment_7a.md)
4. [Assignment 7b: K-Means Clustering](file:///d:/College/Sem%206/DSRP/DSRP-LabWork/VIVA_Assignment_7b.md)
5. [Assignment 8: Random Forest](file:///d:/College/Sem%206/DSRP/DSRP-LabWork/VIVA_Assignment_8.md)

---

### General R Tips for VIVA
- **Libraries:** Always remember the main package for each algorithm (e.g., `arules` for Apriori, `e1071` for Naive Bayes, `rpart` for Decision Trees, `randomForest` for RF).
- **Data Types:** Be clear on `factor` vs. `numeric`. Most classification models in R require the target variable to be a `factor`.
- **Scaling:** Remember that distance-based algorithms like K-Means require `scale()`, while tree-based ones (DT, RF) do not.
- **Visualization:** Know your plotting functions: `inspect()`, `plot()`, `fviz_cluster()`, `varImpPlot()`.

---

### Bonus: Quick R Command Palette
| Task | Command |
| :--- | :--- |
| Load Package | `library(package_name)` |
| View File Head | `head(df)` |
| Structure of Data | `str(df)` |
| Summary Statistics | `summary(df)` |
| Check for NAs | `colSums(is.na(df))` |
| Drop NAs | `na.omit(df)` |
| Convert to Factor | `as.factor(column)` |
| Split Training Data | `sample.split` or `createDataPartition` |
| Table of counts | `table(df$column)` |
