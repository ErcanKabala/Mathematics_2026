# Exercise 2. Determinant of a 3x3 Matrix

## Question
For the $3 \times 3$ matrix:
$$A = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 4 \\ 2 & 1 & 5 \end{pmatrix}$$

We need to compute $\det A$ using Sarrus' rule, and then perform one simple check using a chosen property of the determinant.

## Solution

### 1. Computing $\det A$ via Sarrus' Rule
According to Sarrus' rule, we sum the products of the three downward diagonals (from top-left to bottom-right) and subtract the sum of the products of the three upward diagonals (from bottom-left to top-right):

* **Downward diagonal products:**
  $$(1)(3)(5) + (2)(4)(2) + (-1)(0)(1) = 15 + 16 + 0 = 31$$

* **Upward diagonal products:**
  $$(-1)(3)(2) + (1)(4)(1) + (2)(0)(5) = -6 + 4 + 0 = -2$$

Subtracting the upward sum from the downward sum gives:
$$\det A = 31 - (-2) = 31 + 2 = 33$$

### 2. Verification Using a Determinant Property
A fundamental property of determinants states that adding a scalar multiple of one row to another row ($R_i \leftarrow R_i + cR_j$) does not change the value of the determinant.

Applying $R_3 \leftarrow R_3 - 2R_1$ eliminates the $(3,1)$-entry while preserving $\det A$:
$$\det A = \det \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 4 \\ 2 - 2(1) & 1 - 2(2) & 5 - 2(-1) \end{pmatrix} = \det \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 4 \\ 0 & -3 & 7 \end{pmatrix}$$

Because the first column now has zeros below the $(1,1)$-entry, the determinant reduces directly to $1$ times the determinant of the lower-right $2 \times 2$ submatrix:
$$\det A = 1 \cdot \det \begin{pmatrix} 3 & 4 \\ -3 & 7 \end{pmatrix} = (3)(7) - (4)(-3) = 21 + 12 = 33$$
This matches our Sarrus' rule calculation of $33$.