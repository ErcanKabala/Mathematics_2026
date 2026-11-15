# Exercise 12. A Parameter Revealed by a Row Operation

## Question
For the parameter-dependent matrix:
$$A(t) = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & t \\ 0 & 1 & 1 \end{pmatrix}$$

We need to:
1. Perform the row operation $R_2 \leftarrow R_2 - 2R_1$ before computing the determinant and use the resulting structure.
2. Find all values of $t$ for which the matrix $A(t)$ is not invertible.
3. Explain what special thing happens to the rows of $A(t)$ for the parameter value found.

## Solution

### 1. Applying $R_2 \leftarrow R_2 - 2R_1$ and Computing $\det A(t)$
Subtracting a scalar multiple of one row from another row leaves the determinant unchanged. Applying $R_2 \leftarrow R_2 - 2R_1$ replaces row $2$ with $\begin{pmatrix} 2 - 2(1) & 4 - 2(2) & t - 2(3) \end{pmatrix} = \begin{pmatrix} 0 & 0 & t - 6 \end{pmatrix}$:
$$A_1(t) = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & t - 6 \\ 0 & 1 & 1 \end{pmatrix}, \quad \det A(t) = \det A_1(t)$$

Notice that the second row of $A_1(t)$ has two zeros and only one non-zero entry $(t - 6)$ in the $(2,3)$-position. Expanding $\det A_1(t)$ along this second row (where position $(2,3)$ carries a minus sign since $(-1)^{2+3} = -1$) gives:
$$\det A(t) = -(t - 6) \cdot \det \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} = -(t - 6)(1 \cdot 1 - 2 \cdot 0) = -(t - 6) = 6 - t$$

### 2. Finding Values of $t$ for Noninvertibility
A square matrix is not invertible (singular) if and only if its determinant is equal to zero:
$$\det A(t) = 0 \implies 6 - t = 0 \implies t = 6$$

Thus, $A(t)$ is not invertible only when **$t = 6$**.

### 3. Special Behavior of the Rows at $t = 6$
When $t = 6$, the original matrix becomes:
$$A(6) = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 1 \end{pmatrix}$$
At this value, the second row is an exact scalar multiple of the first row ($R_2 = 2R_1$), which means the rows are **linearly dependent**. Equivalently, performing $R_2 \leftarrow R_2 - 2R_1$ produces an entire row of zeros $\begin{pmatrix} 0 & 0 & 0 \end{pmatrix}$, confirming why the matrix loses rank and fails to be invertible.

### Verification
We verify that $\det A(6) = 0$ by expanding the original matrix at $t = 6$ along the third row (which contains a zero):
$$\det A(6) = 0 - 1 \cdot \det \begin{pmatrix} 1 & 3 \\ 2 & 6 \end{pmatrix} + 1 \cdot \det \begin{pmatrix} 1 & 2 \\ 2 & 4 \end{pmatrix} = -1(6 - 6) + 1(4 - 4) = 0 + 0 = 0$$
This confirms that $t = 6$ is the exact value where the determinant vanishes.