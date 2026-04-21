# VIVA Study Guide: Assignment 5
## Topic: Logistic Regression and Classification

### 1. Objective
To predict the probability of a binary outcome (e.g., Success/Failure, Yes/No) using predictor variables.

### 2. Theoretical Concepts
*   **Logistic Function (Sigmoid):** Maps any value to $(0, 1)$. Formula: $P = \frac{1}{1 + e^{-y}}$.
*   **Link Function:** Uses **Logit** link - $\ln(\frac{P}{1-P})$.
*   **Difference from Linear Regression:** Used for categorical outcomes (Classification), not continuous values.
*   **Performance Metrics:**
    *   **Confusion Matrix:** A $2 \times 2$ table showing TP, TN, FP, FN.
    *   **Accuracy:** $\frac{TP + TN}{\text{Total}}$.
    *   **Sensitivity (Recall):** $\frac{TP}{TP + FN}$.
    *   **Specificity:** $\frac{TN}{TN + FP}$.
    *   **ROC Curve:** Graph of Sensitivity vs. (1-Specificity).
    *   **AUC:** Area under ROC curve; closer to 1 is better.

### 3. Coding Workflow in R
1.  **Training:**
    *   `model <- glm(Class ~ ., data = train, family = "binomial")`
2.  **Summary:**
    *   `summary(model)`
3.  **Prediction (Probabilities):**
    *   `probs <- predict(model, test, type = "response")`
4.  **Evaluation:**
    *   `library(caret)`
    *   `confusionMatrix(as.factor(ifelse(probs > 0.5, "Good", "Bad")), test$Class)`
5.  **ROC Curve:**
    *   `library(pROC)`
    *   `plot(roc(test$Class, probs))`

### 4. Key Functions to Remember
*   `glm()`: Generalized Linear Model (use `family = "binomial"`).
*   `predict(..., type = "response")`: Returns probabilities.
*   `confusionMatrix()`: From the `caret` package.
*   `roc()`: From the `pROC` package.

### 5. Potential VIVA Questions
*   **Q: Why can't we use Linear Regression for Classification?**
    *   A: Linear regression can predict values outside the 0-1 range and is sensitive to outliers in a classification context.
*   **Q: What does AUC represent?**
    *   A: It represents the model's ability to distinguish between classes.
*   **Q: What is a Confusion Matrix?**
    *   A: It is a performance measurement for classification problems where output can be two or more classes.
