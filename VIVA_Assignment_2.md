# VIVA Study Guide: Assignment 2
## Topic: Statistical Hypothesis Testing

### 1. Objective
To perform inferential statistics and hypothesis testing to determine the significance of relationships and differences between groups in a dataset.

### 2. Theoretical Concepts
*   **Null Hypothesis ($H_0$):** Assumes no effect or no difference.
*   **Alternative Hypothesis ($H_1$):** Assumes there is a significant effect or difference.
*   **P-Value:** Probability of observing the results given $H_0$ is true. 
    *   If $p < 0.05$: Reject $H_0$ (Significant).
    *   If $p \ge 0.05$: Fail to reject $H_0$ (Not significant).
*   **Tests covered:**
    *   **Correlation:** Measures strength of linear relationship ($r$ between -1 and 1).
    *   **T-Test:** Compares means of two groups.
    *   **ANOVA:** Compares means of three or more groups.
    *   **Chi-Square:** Checks independence of categorical variables.

### 3. Coding Workflow in R
1.  **Correlation:** 
    *   `cor(df$col1, df$col2)`
    *   `pairs(df)` for visualize matrix.
2.  **T-Test:**
    *   `t.test(df$val ~ df$group)` (Independent)
    *   `t.test(val1, val2, paired = TRUE)` (Paired)
3.  **ANOVA:**
    *   `model <- aov(val ~ group, data = df)`
    *   `summary(model)`
4.  **Chi-Square:**
    *   `chisq.test(table(df$cat1, df$cat2))`

### 4. Key Functions to Remember
*   `cor.test()`: For correlation significance.
*   `t.test()`: For comparing two means.
*   `aov()`: For Analysis of Variance.
*   `chisq.test()`: For categorical independence.

### 5. Potential VIVA Questions
*   **Q: What is the significance of $p < 0.05$?**
    *   A: It indicates that there is less than a 5% chance the observed results are due to random variation, leading to the rejection of the Null Hypothesis.
*   **Q: When do we use ANOVA instead of a T-test?**
    *   A: Use ANOVA when comparing the means of more than two groups.
*   **Q: What does a correlation of -0.8 signify?**
    *   A: A strong negative linear relationship (as one variable increases, the other decreases).
