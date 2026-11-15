# Exercise 2. Addition and Scalar Multiplication

## Question
For the given matrices:
$$A = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix}, \quad B = \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix}$$

We need to compute $A + B$, $A - B$, and $3A - 2B$. Additionally, we must explain why matrix addition is only possible for matrices of the same size.

## Solution

### 1. Matrix Computations
Matrix addition, subtraction, and scalar multiplication are performed entry-by-entry on corresponding positions.

* **Computing $A + B$:** We add each entry of $A$ to the corresponding entry of $B$:
  $$A + B = \begin{pmatrix} 1 + 4 & 2 + (-2) \\ -1 + 0 & 3 + 5 \end{pmatrix} = \begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix}$$

* **Computing $A - B$:** We subtract each entry of $B$ from the corresponding entry of $A$:
  $$A - B = \begin{pmatrix} 1 - 4 & 2 - (-2) \\ -1 - 0 & 3 - 5 \end{pmatrix} = \begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix}$$

* **Computing $3A - 2B$:** First, we apply scalar multiplication by multiplying every entry of $A$ by $3$ and every entry of $B$ by $2$, and then we subtract the two resulting matrices:
  $$3A = \begin{pmatrix} 3(1) & 3(2) \\ 3(-1) & 3(3) \end{pmatrix} = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix}, \quad 2B = \begin{pmatrix} 2(4) & 2(-2) \\ 2(0) & 2(5) \end{pmatrix} = \begin{pmatrix} 8 & -4 \\ 0 & 10 \end{pmatrix}$$
  $$3A - 2B = \begin{pmatrix} 3 - 8 & 6 - (-4) \\ -3 - 0 & 9 - 10 \end{pmatrix} = \begin{pmatrix} -5 & 10 \\ -3 & -1 \end{pmatrix}$$

### 2. Condition for Matrix Addition
Matrix addition is defined strictly as a component-wise operation where every entry $(i, j)$ in the first matrix is paired with the exact same position $(i, j)$ in the second matrix. If two matrices have different dimensions, at least one entry in the larger matrix will lack a corresponding entry in the other matrix, making the operation undefined.

### Verification
We can verify our subtraction result by checking whether $(A - B) + B = A$:
$$(A - B) + B = \begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix} + \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} -3 + 4 & 4 - 2 \\ -1 + 0 & -2 + 5 \end{pmatrix} = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = A$$
Since we recover matrix $A$, the entry-wise calculations are verified.