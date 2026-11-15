# Exercise 3. Inconsistent System

## Question
We need to solve or show that the following system is inconsistent:
$$\begin{cases} x + 2y = 3, \\ 2x + 4y = 7. \end{cases}$$

We must show how the contradiction appears in the augmented matrix after elimination and interpret it in terms of equations.

## Solution

### 1. Gaussian Elimination on the Augmented Matrix
We write the system in augmented matrix form:
$$\left( \begin{array}{cc\|c} 1 & 2 & 3 \\ 2 & 4 & 7 \end{array} \right)$$

To eliminate the entry below the top-left pivot $1$, we apply the elementary row operation $R_2 \leftarrow R_2 - 2R_1$ (replacing row $2$ with $\begin{pmatrix} 2 - 2(1) & 4 - 2(2) \mid 7 - 2(3) \end{pmatrix} = \begin{pmatrix} 0 & 0 \mid 1 \end{pmatrix}$):
$$\left( \begin{array}{cc\|c} 1 & 2 & 3 \\ 0 & 0 & 1 \end{array} \right)$$

### 2. Interpretation in Terms of Equations
Translating the reduced augmented matrix back into scalar equations yields:
$$\begin{cases} x + 2y = 3, \\ 0x + 0y = 1. \end{cases}$$

The second row corresponds to the equation **$0 = 1$**, which is a mathematical contradiction. Since no real numbers $x$ and $y$ can make $0 = 1$ true, the solution set is empty and the system is **inconsistent** (it has no solution).

### Verification
We can verify inconsistency directly from the algebraic equations: multiplying the first equation $x + 2y = 3$ by $2$ gives $2x + 4y = 6$, which directly conflicts with the second equation $2x + 4y = 7$ since $6 \neq 7$. Geometrically, the two equations represent parallel lines $y = -\frac{1}{2}x + \frac{3}{2}$ and $y = -\frac{1}{2}x + \frac{7}{4}$ with the same slope $-\frac{1}{2}$ but different $y$-intercepts, so they never intersect.