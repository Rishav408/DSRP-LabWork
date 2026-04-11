# VIVA Study Guide: Assignment 3
## Topic: Association Rule Mining using Apriori Algorithm

### 1. Objective
To find frequent itemsets and generate association rules from a transactional dataset (e.g., Groceries) to understand relationships between items purchased together.

### 2. Theoretical Concepts
*   **Association Rule:** An implication expression of the form $X \rightarrow Y$, where $X$ and $Y$ are disjoint itemsets.
*   **Key Metrics:**
    *   **Support:** Frequency of an itemset. $Supp(X) = \frac{\text{Count}(X)}{\text{Total Transactions}}$. It determines if a rule is significant enough.
    *   **Confidence:** Reliability of the rule. $Conf(X \rightarrow Y) = \frac{Supp(X \cup Y)}{Supp(X)}$. It measures how often $Y$ appears in transactions that contain $X$.
    *   **Lift:** The strength of the association. $Lift = \frac{Conf(X \rightarrow Y)}{Supp(Y)}$.
        *   $Lift > 1$: Positive correlation (Items are likely bought together).
        *   $Lift = 1$: Independent.
        *   $Lift < 1$: Negative correlation (Items are unlikely to be bought together).
*   **Apriori Principle:** If an itemset is frequent, then all of its subsets must also be frequent. (This helps in pruning the search space).

### 3. Coding Workflow in R
1.  **Library:** `library(arules)` and `library(arulesViz)`.
2.  **Dataset:** Load using `data("Groceries")`.
3.  **Inspection:**
    *   `summary(Groceries)`: Shows transaction count, item count, and most frequent items.
    *   `itemFrequencyPlot(Groceries, topN = 20)`: Visualizes the most common items.
4.  **Model Training:**
    *   `rules <- apriori(Groceries, parameter = list(supp = 0.001, conf = 0.8))`
    *   *Note:* Choosing Support and Confidence is a trial-and-error process. Setting them too high yields no rules; too low yields too many redundant rules.
5.  **Sorting & Inspection:**
    *   `rules <- sort(rules, by = "lift", descending = TRUE)`
    *   `inspect(rules[1:10])`: View the top 10 rules.

### 4. Key Functions to Remember
*   `apriori()`: The main algorithm function.
*   `inspect()`: To printer the rules in a readable table.
*   `subset()`: To filter rules (e.g., rules containing "whole milk").
*   `plot(rules, method="graph")`: Visualizes rules as a network node diagram.

### 5. Potential VIVA Questions
*   **Q: What is the downside of the Apriori algorithm?**
    *   A: It can be computationally expensive as it requires multiple passes over the dataset and generates many candidates.
*   **Q: Why do we use Lift instead of just Confidence?**
    *   A: Confidence can be misleading if the item in the Consequent is very popular anyway. Lift accounts for the base popularity of the item.
*   **Q: How do you handle redundant rules?**
    *   A: By using `is.redundant()` and `pruning` based on higher confidence for the same support.
