# VIVA Study Guide: Assignment 1
## Topic: R Programming Fundamentals

### 1. Objective
To understand the basic syntax, data structures, and programming constructs in the R language for statistical computing and data analysis.

### 2. Theoretical Concepts
*   **Data Structures in R:**
    *   **Vector:** 1D array of same data types. Created using `c()`.
    *   **List:** Can contain elements of different data types and structures.
    *   **Matrix:** 2D arrangement of same data types.
    *   **Factor:** Used for categorical data with predefined levels.
    *   **Data Frame:** Table-like structure where each column can have a different type. The most common structure for datasets.
*   **Logical Operators:** Includes symbols like `&` (AND), `|` (OR), and `!` (NOT).
*   **Control Flow:**
    *   `if-else`: Conditional execution.
    *   `for`, `while`: Loops for iteration.

### 3. Coding Workflow in R
1.  **Creation:**
    ```r
    # Vector
    num_vec <- c(1, 2, 3)
    # Data Frame
    df <- data.frame(ID=1:3, Name=c("A","B","C"))
    ```
2.  **Basic Functions:**
    *   `length()`, `dim()`, `str()`, `summary()`.
3.  **Custom Functions:**
    ```r
    sum_two <- function(a, b) {
      return(a + b)
    }
    ```
4.  **Iteration:**
    ```r
    for (i in 1:10) {
      print(i * i)
    }
    ```

### 4. Key Functions to Remember
*   `c()`: Combine elements into a vector.
*   `class()`: To check the data type of an object.
*   `seq(from, to, by)`: To generate a sequence of numbers.
*   `rep(x, times)`: To repeat elements.

### 5. Potential VIVA Questions
*   **Q: What is the difference between a Vector and a List?**
    *   A: A vector is homogeneous (elements must be of the same type), while a list is heterogeneous (can store different types).
*   **Q: How do you access a column in a Data Frame?**
    *   A: Using the `$` operator (e.g., `df$ColumnName`) or indexing `df[, "ColumnName"]`.
*   **Q: What is a Factor?**
    *   A: It is a data structure used for fields that have a fixed and known set of possible values (categorical variables).
