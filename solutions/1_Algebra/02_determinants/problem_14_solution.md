# Exercise 14. A System of Equations and the Determinant

## Question
Consider the linear system $Ax = b$, where the coefficient matrix is given by:
$$A = \begin{pmatrix} 1 & 2 \\ k & 4 \end{pmatrix}$$
We need to:
1. Determine all values of $k$ for which the system has **exactly one solution** for every right-hand side vector $b$.
2. For the remaining value of $k$, provide one concrete example of a right-hand side vector $b$ for which the system has **infinitely many solutions**, and one concrete example of $b$ for which the system has **no solution**.

## Solution

### 1. Values of $k$ Giving a Unique Solution for Every $b$
By the Invertible Matrix Theorem, a square linear system $Ax = b$ has a unique solution ($x = A^{-1}b$) for every right-hand side vector $b \in \mathbb{R}^2$ if and only if the coefficient matrix $A$ is invertible, which occurs if and only if $\det A \neq 0$.

Computing the determinant of $A$ in terms of $k$ gives:
$$\det A = (1)(4) - (2)(k) = 4 - 2k$$

Setting $\det A \neq 0$:
$$4 - 2k \neq 0 \implies 2k \neq 4 \implies k \neq 2$$

Therefore, the system has **exactly one solution for every $b$ whenever $k \neq 2$**.

### 2. Analyzing the Remaining Value $k = 2$
When $k = 2$, we have $\det A = 0$, and the coefficient matrix becomes $A = \begin{pmatrix} 1 & 2 \\ 2 & 4 \end{pmatrix}$. For a general right-hand side $b = \begin{pmatrix} b_1 \\ b_2 \end{pmatrix}$, we apply the row operation $R_2 \leftarrow R_2 - 2R_1$ to the augmented matrix:
$$\left( \begin{array}{cc|c} 1 & 2 & b_1 \\ 2 & 4 & b_2 \end{array} \right) \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \left( \begin{array}{cc|c} 1 & 2 & b_1 \\ 0 & 0 & b_2 - 2b_1 \end{array} \right)$$

The second row corresponds to the equation $0 = b_2 - 2b_1$, which splits into two cases:

* **Example for Infinitely Many Solutions:**
  To make the system consistent, we need $b_2 - 2b_1 = 0$, or $b_2 = 2b_1$. Choosing $b_1 = 1$ gives $b_2 = 2$, so one valid example is:
  $$b = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$$
  With this $b$, the second row becomes $\begin{pmatrix} 0 & 0 \mid 0 \end{pmatrix}$ ($0 = 0$) and the system reduces to the single equation $x + 2y = 1$. Setting $y = t \in \mathbb{R}$ as a free variable gives infinitely many solutions $(x, y) = (1 - 2t, \, t)$.

* **Example for No Solution:**
  To create a contradiction in the second row, we need $b_2 - 2b_1 \neq 0$. Choosing $b_1 = 1$ and $b_2 = 3$ gives $b_2 - 2b_1 = 3 - 2(1) = 1 \neq 0$, so one valid example is:
  $$b = \begin{pmatrix} 1 \\ 3 \end{pmatrix}$$
  With this $b$, the second row reads $\begin{pmatrix} 0 & 0 \mid 1 \end{pmatrix}$, which translates to the false equation $0 = 1$. Since no real numbers $x$ and $y$ can satisfy $0 = 1$, the system is inconsistent and has no solution.

### Verification
We verify all three cases directly:
* **For $k \neq 2$:** Since $\det A = 4 - 2k \neq 0$, the inverse matrix $A^{-1} = \frac{1}{4 - 2k}\begin{pmatrix} 4 & -2 \\ -k & 1 \end{pmatrix}$ exists, guaranteeing the unique solution $x = A^{-1}b$ for any $b$.
* **For $k = 2$ and $b = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$:** Testing $t = 0$ gives $(1, 0)$, where $1 + 2(0) = 1$ and $2(1) + 4(0) = 2$; testing $t = 1$ gives $(-1, 1)$, where $-1 + 2(1) = 1$ and $2(-1) + 4(1) = 2$, confirming infinitely many solutions.
* **For $k = 2$ and $b = \begin{pmatrix} 1 \\ 3 \end{pmatrix}$:** Multiplying the first equation $x + 2y = 1$ by $2$ yields $2x + 4y = 2$, which directly contradicts the second equation $2x + 4y = 3$.

All three cases are verified.