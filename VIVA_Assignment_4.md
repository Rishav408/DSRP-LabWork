# VIVA Study Guide: Assignment 4
## Topic: Linear Regression Analysis

### 1. Objective
To model the linear relationship between a dependent (target) variable and one or more independent (predictor) variables to make predictions.

### 2. Theoretical Concepts
*   **Simple Linear Regression:** $Y = \beta_0 + \beta_1 X + \epsilon$.
*   **Multiple Linear Regression:** $Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + ... + \epsilon$.
*   **Key Parameters:**
    *   **Intercept ($\beta_0$):** Value of $Y$ when $X=0$.
    *   **Slope ($\beta_1$):** Change in $Y$ for a unit change in $X$.
*   **Evaluation Metrics:**
    *   **R-Squared ($R^2$):** Proportion of variance in $Y$ explained by the model (ranges 0 to 1).
    *   **Adjusted R-Squared:** Penalizes for adding insignificant predictors.
    *   **Residuals:** Difference between actual and predicted values.

### 3. Coding Workflow in R
1.  **Model Training:**
    *   `model <- lm(mpg ~ wt, data = mtcars)`
2.  **Summary Inspection:**
    *   `summary(model)`: Check coefficients, p-values, and R-squared.
3.  **Visualization:**
    *   `plot(mtcars$wt, mtcars$mpg)`
    *   `abline(model, col = "red")`: Add regression line.
4.  **Prediction:**
    *   `predict(model, newdata = data.frame(wt = 3.0))`

### 4. Key Functions to Remember
*   `lm()`: Linear Model function.
*   `summary()`: To get detailed model statistics.
*   `abline()`: To plot the regression line.
*   `residuals()`: To extract the error terms.

### 5. Potential VIVA Questions
*   **Q: What does a high R-squared indicate?**
    *   A: It indicates that the model fits the data well and explains a large portion of the variance in the dependent variable.
*   **Q: What is the purpose of the P-value in the coefficients table?**
    *   A: It tests the hypothesis that the coefficient is zero. A $p < 0.05$ suggests the predictor is significantly related to the target.
*   **Q: What are the assumptions of Linear Regression?**
    *   A: Linearity, Independence, Homoscedasticity (Equal variance), and Normality of residuals.
