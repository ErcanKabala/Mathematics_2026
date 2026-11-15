# Exercise 13. Determinant by Elimination

## Question
We are asked to compute the determinant of:
$$A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 5 & 7 \\ 1 & 0 & 2 \end{pmatrix}$$
using Gaussian elimination, and to record the effect of every row operation used on the value of the determinant.

## Solution

### 1. Gaussian Elimination to Upper Triangular Form
We transform $A$ into an upper triangular matrix using elementary row replacement operations ($R_i \leftarrow R_i + cR_j$). Adding a multiple of one row to another row **does not change** the value of the determinant.

* **Step 1 ($R_2 \leftarrow R_2 - 2R_1$):** Subtracting $2$ times row $1$ from row $2$ gives the new second row $\begin{pmatrix} 2 - 2(1) & 5 - 2(2) & 7 - 2(3) \end{pmatrix} = \begin{pmatrix} 0 & 1 & 1 \end{pmatrix}$:
  $$A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 1 & 0 & 2 \end{pmatrix}$$
  *Effect on determinant:* **Unchanged** ($\det A_1 = \det A$).

* **Step 2 ($R_3 \leftarrow R_3 - R_1$):** Subtracting row $1$ from row $3$ gives the new third row $\begin{pmatrix} 1 - 1 & 0 - 2 & 2 - 3 \end{pmatrix} = \begin{pmatrix} 0 & -2 & -1 \end{pmatrix}$:
  $$A_2 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & -2 & -1 \end{pmatrix}$$
  *Effect on determinant:* **Unchanged** ($\det A_2 = \det A_1 = \det A$).

* **Step 3 ($R_3 \leftarrow R_3 + 2R_2$):** Adding $2$ times row $2$ to row $3$ gives the new third row $\begin{pmatrix} 0 + 2(0) & -2 + 2(1) & -1 + 2(1) \end{pmatrix} = \begin{pmatrix} 0 & 0 & 1 \end{pmatrix}$:
  $$A_3 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix}$$
  *Effect on determinant:* **Unchanged** ($\det A_3 = \det A_2 = \det A$).

### 2. Computing $\det A$
Because $A_3$ is upper triangular, its determinant is the product of its main diagonal entries. Since none of the elimination steps changed the determinant:
$$\det A = \det A_3 = 1 \cdot 1 \cdot 1 = 1$$

### Verification
We verify $\det A = 1$ by expanding the original matrix $A$ along the third row (which contains a zero):
$$\det A = 1 \cdot \det \begin{pmatrix} 2 & 3 \\ 5 & 7 \end{pmatrix} - 0 + 2 \cdot \det \begin{pmatrix} 1 & 2 \\ 2 & 5 \end{pmatrix} = 1(14 - 15) + 2(5 - 4) = -1 + 2(1) = 1$$
The cofactor expansion matches our elimination result of $1$.