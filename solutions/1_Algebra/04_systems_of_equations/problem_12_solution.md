# Exercise 12. Homogeneous System

## Question
We are asked to solve the homogeneous linear system:
$$\begin{cases} x + 2y - z = 0, \\ 2x + 4y - 2z = 0, \\ x - y + 2z = 0, \end{cases}$$
give all solutions in parametric form, and explain why $(0, 0, 0)$ always satisfies a homogeneous system.

## Solution

### 1. Row Reduction to Reduced Row Echelon Form
We form the augmented matrix $[A \mid 0]$ and apply elementary row operations:
$$\left( \begin{array}{ccc|c} 1 & 2 & -1 & 0 \\ 2 & 4 & -2 & 0 \\ 1 & -1 & 2 & 0 \end{array} \right)$$

* **Step 1 ($R_2 \leftarrow R_2 - 2R_1$ and $R_3 \leftarrow R_3 - R_1$):** Eliminate the entries below the first pivot:
  $$\left( \begin{array}{ccc|c} 1 & 2 & -1 & 0 \\ 0 & 0 & 0 & 0 \\ 0 & -3 & 3 & 0 \end{array} \right)$$

* **Step 2 (Interchange $R_2 \leftrightarrow R_3$, then scale $R_2 \leftarrow -\frac{1}{3}R_2$):** Move the zero row to the bottom and normalize the second pivot to $1$:
  $$\left( \begin{array}{ccc|c} 1 & 2 & -1 & 0 \\ 0 & 1 & -1 & 0 \\ 0 & 0 & 0 & 0 \end{array} \right)$$

* **Step 3 ($R_1 \leftarrow R_1 - 2R_2$):** Eliminate the entry above the second pivot:
  $$\left( \begin{array}{ccc|c} 1 & 0 & 1 & 0 \\ 0 & 1 & -1 & 0 \\ 0 & 0 & 0 & 0 \end{array} \right)$$

### 2. Parametric Form of All Solutions
The pivot columns are column $1$ ($x$) and column $2$ ($y$), while column $3$ ($z$) has no pivot, making **$z$ the free variable**. Setting $z = t$ for an arbitrary parameter $t \in \mathbb{R}$:
* From the second row ($y - z = 0$): $y = t$.
* From the first row ($x + z = 0$): $x = -t$.

Thus, all solutions in parametric form are given by:
$$(x, y, z) = (-t, \, t, \, t), \quad t \in \mathbb{R} \qquad \text{or} \qquad \begin{pmatrix} x \\ y \\ z \end{pmatrix} = t \begin{pmatrix} -1 \\ 1 \\ 1 \end{pmatrix}$$

### 3. Why $(0, 0, 0)$ Always Satisfies a Homogeneous System
A homogeneous linear system has the matrix form $Ax = 0$, which means every equation has zero on its right-hand side ($a_{i1}x + a_{i2}y + a_{i3}z = 0$). When we substitute the zero vector $(x, y, z) = (0, 0, 0)$, every term on the left-hand side is multiplied by $0$, so the sum automatically equals $a_{i1}(0) + a_{i2}(0) + a_{i3}(0) = 0$ regardless of the values of the coefficients. Consequently, the trivial solution $(0, 0, 0)$ always satisfies every homogeneous linear system (and corresponds to setting $t = 0$ in our parametric solution).

### Verification
We substitute $(x, y, z) = (-t, t, t)$ into all three original equations to verify that they hold for every $t \in \mathbb{R}$:
* **Equation 1:** $(-t) + 2(t) - t = -t + 2t - t = 0$.
* **Equation 2:** $2(-t) + 4(t) - 2(t) = -2t + 4t - 2t = 0$.
* **Equation 3:** $(-t) - (t) + 2(t) = -2t + 2t = 0$.

All three equations evaluate to $0$, confirming the parametric solution.