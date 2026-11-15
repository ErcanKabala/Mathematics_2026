# Exercise 3. Swapping Two Rows

## Question
For the matrix:
$$A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 3 & 1 \\ 2 & 1 & 1 \end{pmatrix}$$

We are asked to:
1. Compute $\det A$.
2. Form a matrix $B$ by swapping the first and second rows of $A$.
3. First predict $\det B$ using a determinant property, and then verify the prediction by direct calculation.

## Solution

### 1. Computing $\det A$
Expanding $\det A$ along the first row (which conveniently contains a zero in the $(1,3)$-position):
$$\det A = 1 \cdot \det \begin{pmatrix} 3 & 1 \\ 1 & 1 \end{pmatrix} - 2 \cdot \det \begin{pmatrix} 0 & 1 \\ 2 & 1 \end{pmatrix} + 0 \cdot \det \begin{pmatrix} 0 & 3 \\ 2 & 1 \end{pmatrix}$$
$$\det A = 1(3 \cdot 1 - 1 \cdot 1) - 2(0 \cdot 1 - 1 \cdot 2) = 1(2) - 2(-2) = 2 + 4 = 6$$

### 2. Forming Matrix $B$ and Predicting $\det B$
Swapping the first row $R_1 = \begin{pmatrix} 1 & 2 & 0 \end{pmatrix}$ and the second row $R_2 = \begin{pmatrix} 0 & 3 & 1 \end{pmatrix}$ of $A$ produces:
$$B = \begin{pmatrix} 0 & 3 & 1 \\ 1 & 2 & 0 \\ 2 & 1 & 1 \end{pmatrix}$$

**Prediction:** An alternating property of determinants states that interchanging any two rows of a matrix multiplies its determinant by $-1$ (reversing its sign). Since $\det A = 6$, we predict that:
$$\det B = -\det A = -6$$

### 3. Verification by Direct Calculation
We compute $\det B$ directly by expanding along its first row:
$$\det B = 0 \cdot \det \begin{pmatrix} 2 & 0 \\ 1 & 1 \end{pmatrix} - 3 \cdot \det \begin{pmatrix} 1 & 0 \\ 2 & 1 \end{pmatrix} + 1 \cdot \det \begin{pmatrix} 1 & 2 \\ 2 & 1 \end{pmatrix}$$
$$\det B = 0 - 3(1 \cdot 1 - 0 \cdot 2) + 1(1 \cdot 1 - 2 \cdot 2) = -3(1) + 1(1 - 4) = -3 - 3 = -6$$
The direct calculation gives $-6$, confirming our prediction.