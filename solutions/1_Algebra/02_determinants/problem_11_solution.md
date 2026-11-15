# Exercise 11. Shortening the Calculation with Row Operations

## Question
We are asked to compute:
$$\det \begin{pmatrix} 1 & 2 & 3 \\ 1 & 3 & 4 \\ 1 & 4 & 6 \end{pmatrix}$$
by first performing elementary row operations that create as many zeros as possible, and to state which operations do not change the determinant.

## Solution

### 1. Effect of Row Operations on the Determinant
Adding a scalar multiple of one row to another row ($R_i \leftarrow R_i + cR_j$, called a row replacement operation) **does not change** the value of the determinant. In contrast, swapping two rows multiplies the determinant by $-1$, and scaling a row by $c$ multiplies the determinant by $c$. Therefore, using only row replacement operations preserves the exact determinant throughout the simplification.

### 2. Step-by-Step Reduction to Create Zeros
We apply row replacement operations to eliminate all off-diagonal entries and create the maximum possible number of zeros (six zeros):

* **Step 1 ($R_2 \leftarrow R_2 - R_1$):** Subtracting row $1$ from row $2$ produces a zero in position $(2,1)$:
  $$A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 1 & 4 & 6 \end{pmatrix} \quad (\det A_1 = \det A)$$

* **Step 2 ($R_3 \leftarrow R_3 - R_1$):** Subtracting row $1$ from row $3$ produces a zero in position $(3,1)$:
  $$A_2 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 2 & 3 \end{pmatrix} \quad (\det A_2 = \det A)$$

* **Step 3 ($R_3 \leftarrow R_3 - 2R_2$):** Subtracting $2$ times row $2$ from row $3$ produces a zero in position $(3,2)$, yielding an upper triangular matrix:
  $$A_3 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix} \quad (\det A_3 = \det A)$$

* **Step 4 ($R_2 \leftarrow R_2 - R_3$ and $R_1 \leftarrow R_1 - 3R_3$):** Using the $1$ in position $(3,3)$ to eliminate the entries above it gives:
  $$A_4 = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} \quad (\det A_4 = \det A)$$

* **Step 5 ($R_1 \leftarrow R_1 - 2R_2$):** Eliminating the remaining off-diagonal entry in position $(1,2)$ reduces the matrix to the $3 \times 3$ identity matrix $I_3$:
  $$A_5 = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} = I_3 \quad (\det A_5 = \det A)$$

### 3. Final Determinant Value
Since none of the row replacement operations altered the determinant and the determinant of a diagonal (or triangular) matrix is the product of its main diagonal entries:
$$\det A = \det I_3 = 1 \cdot 1 \cdot 1 = 1$$

### Verification
We verify the result directly from the original matrix $A$ using cofactor expansion along the first row:
$$\det A = 1 \cdot \det \begin{pmatrix} 3 & 4 \\ 4 & 6 \end{pmatrix} - 2 \cdot \det \begin{pmatrix} 1 & 4 \\ 1 & 6 \end{pmatrix} + 3 \cdot \det \begin{pmatrix} 1 & 3 \\ 1 & 4 \end{pmatrix}$$
$$\det A = 1(18 - 16) - 2(6 - 4) + 3(4 - 3) = 1(2) - 2(2) + 3(1) = 2 - 4 + 3 = 1$$
Both methods yield $1$, confirming the calculation.