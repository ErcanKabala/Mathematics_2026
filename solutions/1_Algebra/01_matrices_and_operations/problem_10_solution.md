# Exercise 10. Columns of a Matrix Product

## Question
Given the matrices:
$$A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} 1 & 2 \\ -1 & 0 \\ 3 & 1 \end{pmatrix}$$
where $b_1$ and $b_2$ denote the first and second columns of $B$, we are asked to:
1. Compute $Ab_1$ and $Ab_2$.
2. Compute the matrix product $AB$.
3. Compare the results and explain why the columns of $AB$ are exactly the vectors $Ab_1$ and $Ab_2$.

## Solution

### 1. Computing $Ab_1$ and $Ab_2$
From the given matrix $B$, its two column vectors are:
$$b_1 = \begin{pmatrix} 1 \\ -1 \\ 3 \end{pmatrix}, \quad b_2 = \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}$$

Multiplying the $2 \times 3$ matrix $A$ by each $3 \times 1$ column vector gives:
* **Computing $Ab_1$:**
  $$Ab_1 = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ -1 \\ 3 \end{pmatrix} = \begin{pmatrix} 1(1) + 2(-1) + 0(3) \\ 0(1) + 1(-1) + 1(3) \end{pmatrix} = \begin{pmatrix} 1 - 2 + 0 \\ 0 - 1 + 3 \end{pmatrix} = \begin{pmatrix} -1 \\ 2 \end{pmatrix}$$

* **Computing $Ab_2$:**
  $$Ab_2 = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 1(2) + 2(0) + 0(1) \\ 0(2) + 1(0) + 1(1) \end{pmatrix} = \begin{pmatrix} 2 + 0 + 0 \\ 0 + 0 + 1 \end{pmatrix} = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$$

### 2. Computing the Matrix Product $AB$
Since $A$ has size $2 \times 3$ and $B$ has size $3 \times 2$, their product $AB$ is a $2 \times 2$ matrix computed via the standard row-by-column rule:
$$AB = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ -1 & 0 \\ 3 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 2(-1) + 0(3) & 1(2) + 2(0) + 0(1) \\ 0(1) + 1(-1) + 1(3) & 0(2) + 1(0) + 1(1) \end{pmatrix} = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}$$

### 3. Comparison and Explanation
Comparing the results shows that the first column of $AB$ is $\begin{pmatrix} -1 \\ 2 \end{pmatrix} = Ab_1$ and the second column of $AB$ is $\begin{pmatrix} 2 \\ 1 \end{pmatrix} = Ab_2$, so:
$$AB = \begin{pmatrix} Ab_1 & Ab_2 \end{pmatrix}$$

**Explanation:** By the definition of matrix multiplication, the $(i, j)$-entry of $AB$ is the dot product of the $i$-th row of $A$ with the $j$-th column of $B$ (which is $b_j$). Consequently, every entry in the $j$-th column of $AB$ is calculated using all rows of $A$ paired exclusively with the single column vector $b_j$. That exact sequence of dot products is the definition of the matrix-vector product $Ab_j$.

### Verification
We can verify this column-wise property by multiplying both sides on the right by the vector $x = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$:
* Using $A(Bx)$: $Bx = b_1 + b_2 = \begin{pmatrix} 3 \\ -1 \\ 4 \end{pmatrix}$, so $A(Bx) = \begin{pmatrix} 1(3) + 2(-1) + 0(4) \\ 0(3) + 1(-1) + 1(4) \end{pmatrix} = \begin{pmatrix} 1 \\ 3 \end{pmatrix}$.
* Using $(AB)x$: $(AB)x = Ab_1 + Ab_2 = \begin{pmatrix} -1 \\ 2 \end{pmatrix} + \begin{pmatrix} 2 \\ 1 \end{pmatrix} = \begin{pmatrix} 1 \\ 3 \end{pmatrix}$.
  Both evaluations yield the same vector, confirming our computations.