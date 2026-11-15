# Exercise 10. A Polynomial Through Three Points

## Question
We are asked to find a quadratic polynomial $p(x) = ax^2 + bx + c$ whose graph passes through the three points $(0, 1)$, $(1, 3)$, and $(2, 9)$. We must reduce the problem to a system of linear equations and check the result by substituting all three points.

## Solution

### 1. Reducing the Problem to a System of Linear Equations
For the graph $y = p(x)$ to pass through a point $(x_0, y_0)$, the polynomial must satisfy $p(x_0) = y_0$. Substituting each of the three given points into $p(x) = ax^2 + bx + c$ produces one linear equation in the unknown coefficients $a, b, c$:
* At $(0, 1)$: $p(0) = a(0)^2 + b(0) + c = 1 \implies c = 1$.
* At $(1, 3)$: $p(1) = a(1)^2 + b(1) + c = 3 \implies a + b + c = 3$.
* At $(2, 9)$: $p(2) = a(2)^2 + b(2) + c = 9 \implies 4a + 2b + c = 9$.

Ordering the equations with $(a, b, c)$ as variables gives the $3 \times 3$ linear system:
$$\begin{cases} a + b + c = 3, \\ 4a + 2b + c = 9, \\ c = 1. \end{cases}$$

### 2. Solving the System by Gaussian Elimination
We form the augmented matrix and eliminate below the pivots:
$$\left( \begin{array}{ccc|c} 1 & 1 & 1 & 3 \\ 4 & 2 & 1 & 9 \\ 0 & 0 & 1 & 1 \end{array} \right) \xrightarrow{R_2 \leftarrow R_2 - 4R_1} \left( \begin{array}{ccc|c} 1 & 1 & 1 & 3 \\ 0 & -2 & -3 & -3 \\ 0 & 0 & 1 & 1 \end{array} \right)$$

Solving by back-substitution:
* From the third row: $c = 1$.
* From the second row: $-2b - 3(1) = -3 \implies -2b = 0 \implies b = 0$.
* From the first row: $a + 0 + 1 = 3 \implies a = 2$.

Substituting $a = 2$, $b = 0$, and $c = 1$ into $p(x) = ax^2 + bx + c$ gives the polynomial:
$$p(x) = 2x^2 + 1$$

### Verification
We check our polynomial $p(x) = 2x^2 + 1$ by substituting the $x$-coordinates of all three given points:
* At $(0, 1)$: $p(0) = 2(0)^2 + 1 = 0 + 1 = 1$.
* At $(1, 3)$: $p(1) = 2(1)^2 + 1 = 2 + 1 = 3$.
* At $(2, 9)$: $p(2) = 2(2)^2 + 1 = 8 + 1 = 9$.

All three points lie on the graph of $p(x) = 2x^2 + 1$, confirming the result.