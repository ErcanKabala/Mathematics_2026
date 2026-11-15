# Exercise 1. Matrix Size and Entries

## Question
We are given two matrices, $A$ and $B$:
$$A = \begin{pmatrix} 2 & -1 & 3 \\ 0 & 4 & 5 \end{pmatrix}, \quad B = \begin{pmatrix} 1 & 0 \\ -2 & 3 \\ 4 & 1 \end{pmatrix}$$

We are asked to:
1. State the sizes of matrices $A$ and $B$.
2. Read off the specific entries $a_{12}$, $a_{23}$, $b_{21}$, and $b_{32}$.
3. Write the second row of $A$ and the first column of $B$ as vectors.

## Solution

### 1. Sizes of Matrices $A$ and $B$
The size (dimension) of a matrix is defined as $m \times n$, where $m$ denotes the number of horizontal rows and $n$ denotes the number of vertical columns.
* Matrix $A$ consists of $2$ rows and $3$ columns, so its size is **$2 \times 3$**.
* Matrix $B$ consists of $3$ rows and $2$ columns, so its size is **$3 \times 2$**.

### 2. Reading Specific Entries
In standard matrix notation, an entry $m_{ij}$ is located at the intersection of the $i$-th row and the $j$-th column:
* **$a_{12} = -1$** (the entry in row $1$, column $2$ of matrix $A$).
* **$a_{23} = 5$** (the entry in row $2$, column $3$ of matrix $A$).
* **$b_{21} = -2$** (the entry in row $2$, column $1$ of matrix $B$).
* **$b_{32} = 1$** (the entry in row $3$, column $2$ of matrix $B$).

### 3. Row and Column Vectors
Extracting a single row or column from a matrix forms a $1 \times n$ row vector or an $m \times 1$ column vector, respectively:
* The second row of $A$ written as a row vector is:
  $$\begin{pmatrix} 0 & 4 & 5 \end{pmatrix}$$
* The first column of $B$ written as a column vector is:
  $$\begin{pmatrix} 1 \\ -2 \\ 4 \end{pmatrix}$$

### Verification
We can verify the total number of entries using the dimensions: matrix $A$ has $2 \times 3 = 6$ entries and matrix $B$ has $3 \times 2 = 6$ entries, matching the given matrices. Re-indexing from the top-left corner confirms that row $2$, column $3$ of $A$ is indeed $5$, and row $3$, column $2$ of $B$ is $1$.