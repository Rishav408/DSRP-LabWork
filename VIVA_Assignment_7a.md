# VIVA Study Guide: Assignment 7a
## Topic: Recursive Partitioning (Decision Trees)

### 1. Objective
To construct a flowchart-like structure (Decision Tree) to classify data samples by splitting them into subsets based on feature values.

### 2. Theoretical Concepts
*   **Splitting Criteria:**
    *   **Gini Impurity:** Measures how often a randomly chosen element from the set would be incorrectly labeled. A pure node has Gini = 0.
    *   **Entropy / Information Gain:** Uses the concept of "disorder" or "uncertainty". Information Gain is the reduction in entropy after a split.
*   **Root Node:** The top-most node where the first split occurs (highest information gain).
*   **Leaf Node:** The final classification label.
*   **Overfitting:** When the tree grows too deep and captures noise in the training data.
*   **Pruning:** Removing parts of the tree that provide little power to simplify it. Controlled by the **Complexity Parameter (CP)** in R.

### 3. Coding Workflow in R
1.  **Library:** `library(rpart)` (for building trees) and `library(rpart.plot)` (for visualization).
2.  **Dataset:** Usually tested on the `iris` dataset.
3.  **Model Training:**
    *   `fit <- rpart(Species ~ ., data = train_data, method = "class", parms = list(split = "gini"))`
    *   `method = "class"` is used for classification (for numeric prediction, use `anova`).
4.  **Visualization:**
    *   `rpart.plot(fit, type = 4, extra = 101)`: Creates a clear diagram showing splits and probabilities.
5.  **Pruning (Optional):**
    *   Check the CP table: `printcp(fit)`.
    *   Prune if needed: `pruned_fit <- prune(fit, cp = fit$cptable[which.min(fit$cptable[,"xerror"]),"CP"])`.

### 4. Key Parameters to Mention
*   **minsplit:** Minimum number of observations that must exist in a node in order for a split to be attempted.
*   **maxdepth:** How deep the tree can grow.
*   **cp:** Complexity Parameter. A smaller CP lets the tree grow larger.

### 5. Potential VIVA Questions
*   **Q: What is the difference between Gini and Information Gain?**
    *   A: Gini is computationally faster. Information Gain is based on logs (entropy) and is slightly more complex but sometimes more accurate.
*   **Q: What are the advantages of Decision Trees?**
    *   A: Easy to understand (white-box model), handles both numerical and categorical data, requires little data preprocessing (no scaling needed).
*   **Q: How do you identify the most important variable in your tree?**
    *   A: It is the variable at the root node (top of the tree).
