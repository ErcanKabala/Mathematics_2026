# Exercise 10. Detecting Dependence

## Question
Without carrying out a full determinant calculation, we are asked to explain why:
$$\det \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 5 \end{pmatrix} = 0$$

We must identify a specific dependence between the rows and connect it with the noninvertibility of the matrix.

## Solution

### 1. Specific Row Dependence and Why $\det = 0$
By inspecting the entries of the first two rows, we observe that the second row is an exact scalar multiple of the first row:
$$R_2 = 2R_1, \quad \text{since } 2 \begin{pmatrix} 1 & 2 & 3 \end{pmatrix} = \begin{pmatrix} 2 & 4 & 6 \end{pmatrix}$$

Because $R_2 = 2R_1$, the rows of the matrix are linearly dependent. Applying the elementary row operation $R_2 \leftarrow R_2 - 2R_1$ does not change the determinant, yet it turns the entire second row into zeros ($\begin{pmatrix} 0 & 0 & 0 \end{pmatrix}$). Any matrix containing a row of zeros automatically has a determinant equal to $0$.

### 2. Connection to Noninvertibility
By the Invertible Matrix Theorem, a square matrix is invertible if and only if its rows are linearly independent, which holds if and only if its determinant is non-zero ($\det A \neq 0$). Since the rows are linearly dependent ($R_2 = 2R_1$) and $\det A = 0$, the matrix is singular and therefore **not invertible**.

### Verification
Applying the single row operation $R_2 \leftarrow R_2 - 2R_1$ confirms our reasoning directly:
$$\det \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 5 \end{pmatrix} = \det \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & 0 \\ 0 & 1 & 5 \end{pmatrix} = 0$$
Expanding along the second row gives $0 \cdot C_{21} + 0 \cdot C_{22} + 0 \cdot C_{23} = 0$, verifying the result without a full determinant expansion.