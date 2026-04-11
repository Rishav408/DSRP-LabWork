# VIVA Study Guide: Assignment 6
## Topic: Naive Bayesian Classifier

### 1. Objective
To build a classification model based on Bayes' Theorem to predict class labels (e.g., predicting Diabetes in the Pima Indians dataset).

### 2. Theoretical Concepts
*   **Bayes' Theorem:** $P(C|X) = \frac{P(X|C)P(C)}{P(X)}$
    *   $P(C|X)$ is the posterior probability of class $C$ given predictor $X$.
    *   $P(X|C)$ is the likelihood.
    *   $P(C)$ is the class prior probability.
    *   $P(X)$ is the predictor prior probability.
*   **The "Naive" Assumption:** It assumes that all predictors (features) are **independent** of each other given the class label. While rarely true in real life, it simplifies the math and often works surprisingly well.
*   **Laplace Smoothing:** Used to handle the "Zero Frequency" problem (when a category doesn't appear in training for a class, making the whole product zero).

### 3. Coding Workflow in R
1.  **Library:** `library(e1071)` (contains the classifier) and `library(caret)` (for confusion matrix).
2.  **Preprocessing:**
    *   **Handling Zero Values:** In medical datasets, variables like blood pressure or glucose can't be zero. These are often missing values. We use `impute` or replace zeros with `median` or `mean`.
    *   **Data Splitting:** Use `createDataPartition()` from `caret` to split into 70% train and 30% test.
3.  **Model Training:**
    *   `model <- naiveBayes(Outcome ~ ., data = train_data)`
4.  **Prediction:**
    *   `pred <- predict(model, test_data)`
5.  **Evaluation:**
    *   `confusionMatrix(pred, test_data$Outcome)`: Check Accuracy, Precision, Recall (Sensitivity), and F1-score.
    *   **ROC Curve:** Plot the True Positive Rate against the False Positive Rate to see the model's trade-off.

### 4. Evaluation Metrics Explained
*   **Accuracy:** Overall correct predictions.
*   **Sensitivity (Recall):** Ability to find all positive cases (True Positives / Actual Positives). Crucial in healthcare!
*   **Specificity:** Ability to identify negative cases correctly (True Negatives / Actual Negatives).
*   **AUC (Area Under Curve):** Closer to 1.0 means the model is excellent at distinguishing between classes.

### 5. Potential VIVA Questions
*   **Q: Why is it called "Naive"?**
    *   A: Because it assumes independence between features, which is a "naive" assumption in real-world data.
*   **Q: How does Naive Bayes handle continuous variables?**
    *   A: It usually assumes a Gaussian (Normal) distribution for continuous features and calculates the likelihood using the bell curve formula.
*   **Q: When would Naive Bayes perform poorly?**
    *   A: When features are highly correlated (it overemphasizes their impact) or when the training set is too small to represent the feature distribution.
