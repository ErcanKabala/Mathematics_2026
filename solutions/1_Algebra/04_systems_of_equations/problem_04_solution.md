# Exercise 4. Infinitely Many Solutions

## Question
We are asked to solve the linear system:
$$\begin{cases} x + y + z = 2, \\ 2x + 2y + 2z = 4, \\ x - y + z = 0. \end{cases}$$

We must give the solution in parametric form, identify a free variable, and for one chosen parameter value check that the resulting point satisfies the system.

## Solution

### 1. Row Reduction of the Augmented Matrix
We form the augmented matrix and apply elementary row operations:
$$\left( \begin{array}{ccc\|c} 1 & 1 & 1 & 2 \\ 2 & 2 & 2 & 4 \\ 1 & -1 & 1 & 0 \end{array} \right)$$

* **Step 1 ($R_2 \leftarrow R_2 - 2R_1$ and $R_3 \leftarrow R_3 - R_1$):** Eliminate the entries below the first pivot:
  $$\left( \begin{array}{ccc\|c} 1 & 1 & 1 & 2 \\ 0 & 0 & 0 & 0 \\ 0 & -2 & 0 & -2 \end{array} \right)$$

* **Step 2 (Interchange $R_2 \leftrightarrow R_3$, then scale $R_2 \leftarrow -\frac{1}{2}R_2$):** Move the zero row to the bottom and normalize the second pivot to $1$:
  $$\left( \begin{array}{ccc\|c} 1 & 1 & 1 & 2 \\ 0 & 1 & 0 & 1 \\ 0 & 0 & 0 & 0 \end{array} \right)$$

### 2. Free Variable and Parametric Form
In the row echelon form above, the leading $1$s (pivots) appear in column $1$ ($x$) and column $2$ ($y$), while column $3$ ($z$) has no pivot. Therefore, **$z$ is a free variable**. Setting $z = t$ for an arbitrary parameter $t \in \mathbb{R}$:
* From the second row: $y = 1$.
* From the first row: $x + y + z = 2 \implies x + 1 + t = 2 \implies x = 1 - t$.

Thus, the complete solution set in parametric form is:
$$(x, y, z) = (1 - t, \, 1, \, t), \quad t \in \mathbb{R} \qquad \text{or} \qquad \begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix} + t \begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix}$$

### Verification
Choosing the parameter value $t = 2$ gives the point $(x, y, z) = (1 - 2, 1, 2) = (-1, 1, 2)$. Substituting this point into all three original equations:
* **Equation 1:** $-1 + 1 + 2 = 2$ (True).
* **Equation 2:** $2(-1) + 2(1) + 2(2) = -2 + 2 + 4 = 4$ (True).
* **Equation 3:** $-1 - 1 + 2 = 0$ (True).

All three equations hold, confirming our parametric solution.