# VIVA Study Guide: Assignment 8
## Topic: Random Forest Classifier

### 1. Objective
To improve classification accuracy by building an "ensemble" of multiple decision trees and taking a majority vote to determine the final class.

### 2. Theoretical Concepts
*   **Ensemble Learning:** Combining multiple models (weak learners) to create a stronger model.
*   **Bootstrap Aggregating (Bagging):**
    *   **Bootstrapping:** Creating multiple subsets of the training data with replacement.
    *   **Aggregating:** Taking the average or majority vote of the results.
*   **Randomness:** Unlike a single Decision Tree that considers *all* variables for every split, Random Forest picks a **random subset** of features at each node. This reduces correlation between trees and makes the model more robust.
*   **OOB (Out-of-Bag) Error:** The error calculated on the data samples that were *not* picked during bootstrapping. It's a built-in cross-validation.

### 3. Coding Workflow in R
1.  **Library:** `library(randomForest)`.
2.  **Dataset:** Heart Disease dataset (requires cleaning and factoring).
3.  **Model Training:**
    *   `rf_fit <- randomForest(target ~ ., data = train_data, ntree = 500, mtry = 3, importance = TRUE)`
    *   `ntree`: Number of trees (more is usually better but slower).
    *   `mtry`: Number of features to try at each split $(\sqrt{p}$ for classification).
4.  **Evaluation:**
    *   `plot(rf_fit)`: Shows how the error decreases as more trees are added.
    *   `importance(rf_fit)`: Shows which variables are most useful.
    *   `varImpPlot(rf_fit)`: Visualizes variable importance (Gini vs. Accuracy).

### 4. Key Metrics
*   **Mean Decrease Accuracy:** How much the accuracy drops if we remove a specific variable.
*   **Mean Decrease Gini:** How much a variable contributes to the purity of nodes.

### 5. Potential VIVA Questions
*   **Q: Why is Random Forest better than a single Decision Tree?**
    *   A: A single tree is prone to overfitting and is sensitive to small changes in data. Random Forest averages many trees, reducing variance and noise.
*   **Q: Do we need a separate test set if we have OOB error?**
    *   A: OOB error is a good estimate of generalization error, but a final hold-out test set is still recommended for unbiased evaluation.
*   **Q: What is the downside of Random Forest?**
    *   A: It is a "black-box" model (hard to visualize exactly how it made a specific decision compared to a single tree) and requires more memory/CPU.
