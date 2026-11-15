# Exercise 5. Row Operations

## Question
For the matrix:
$$A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 1 & 0 \\ -1 & 4 & 2 \end{pmatrix}$$

We need to find $\det A$ by simplifying the matrix with elementary row operations, indicating at each step whether and how the determinant changes.

## Solution

### 1. Step-by-Step Reduction to Upper Triangular Form
Adding a scalar multiple of one row to another row ($R_i \leftarrow R_i + cR_j$) leaves the determinant completely unchanged. We use this operation to create zeros below the main diagonal:

* **Step 1 ($R_2 \leftarrow R_2 - 2R_1$):** Subtracting $2$ times row $1$ from row $2$ changes row $2$ to $\begin{pmatrix} 2 - 2(1) & 1 - 2(2) & 0 - 2(3) \end{pmatrix} = \begin{pmatrix} 0 & -3 & -6 \end{pmatrix}$:
  $$A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ -1 & 4 & 2 \end{pmatrix}$$
  *Effect on determinant:* **Unchanged** ($\det A_1 = \det A$).

* **Step 2 ($R_3 \leftarrow R_3 + R_1$):** Adding row $1$ to row $3$ changes row $3$ to $\begin{pmatrix} -1 + 1 & 4 + 2 & 2 + 3 \end{pmatrix} = \begin{pmatrix} 0 & 6 & 5 \end{pmatrix}$:
  $$A_2 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ 0 & 6 & 5 \end{pmatrix}$$
  *Effect on determinant:* **Unchanged** ($\det A_2 = \det A_1 = \det A$).

* **Step 3 ($R_3 \leftarrow R_3 + 2R_2$):** Adding $2$ times row $2$ to row $3$ changes row $3$ to $\begin{pmatrix} 0 + 2(0) & 6 + 2(-3) & 5 + 2(-6) \end{pmatrix} = \begin{pmatrix} 0 & 0 & -7 \end{pmatrix}$:
  $$A_3 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ 0 & 0 & -7 \end{pmatrix}$$
  *Effect on determinant:* **Unchanged** ($\det A_3 = \det A_2 = \det A$).

### 2. Computing $\det A$
Because $A_3$ is upper triangular and none of the steps altered the determinant, $\det A$ equals the product of the main diagonal entries of $A_3$:
$$\det A = \det A_3 = 1 \cdot (-3) \cdot (-7) = 21$$

### Verification
We verify $\det A$ directly from the original matrix $A$ by cofactor expansion along the second row (which contains a zero):
$$\det A = -2 \cdot \det \begin{pmatrix} 2 & 3 \\ 4 & 2 \end{pmatrix} + 1 \cdot \det \begin{pmatrix} 1 & 3 \\ -1 & 2 \end{pmatrix} - 0 = -2(4 - 12) + 1(2 - (-3)) = -2(-8) + 5 = 16 + 5 = 21$$
The result $21$ is verified.