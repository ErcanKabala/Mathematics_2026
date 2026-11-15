# Exercise 2. Gaussian Elimination — One Solution

## Question
We are asked to solve the following linear system using Gaussian elimination:
$$\begin{cases} x + y + z = 6, \\ 2x - y + z = 3, \\ x + 2y - z = 2. \end{cases}$$

After solving, we must substitute the result back into all three equations to check consistency.

## Solution

### 1. Forward Elimination to Row Echelon Form
We represent the system as an augmented matrix $[A \mid b]$ and apply elementary row operations to create zeros below the main diagonal:
$$\left( \begin{array}{ccc\|c} 1 & 1 & 1 & 6 \\ 2 & -1 & 1 & 3 \\ 1 & 2 & -1 & 2 \end{array} \right)$$

* **Step 1 ($R_2 \leftarrow R_2 - 2R_1$ and $R_3 \leftarrow R_3 - R_1$):** Eliminate the $x$-terms in the second and third rows:
  $$\left( \begin{array}{ccc\|c} 1 & 1 & 1 & 6 \\ 0 & -3 & -1 & -9 \\ 0 & 1 & -2 & -4 \end{array} \right)$$

* **Step 2 (Interchange $R_2$ and $R_3$, denoted $R_2 \leftrightarrow R_3$):** Bring the leading $1$ in row $3$ into the second pivot position to avoid fractions:
  $$\left( \begin{array}{ccc\|c} 1 & 1 & 1 & 6 \\ 0 & 1 & -2 & -4 \\ 0 & -3 & -1 & -9 \end{array} \right)$$

* **Step 3 ($R_3 \leftarrow R_3 + 3R_2$):** Eliminate the $y$-term in the third row:
  $$\left( \begin{array}{ccc\|c} 1 & 1 & 1 & 6 \\ 0 & 1 & -2 & -4 \\ 0 & 0 & -7 & -21 \end{array} \right)$$

### 2. Back-Substitution
The augmented matrix is now in row echelon form, corresponding to the upper triangular system:
$$\begin{cases} x + y + z = 6, \\ y - 2z = -4, \\ -7z = -21. \end{cases}$$

Solving from the bottom equation upward:
* From the third equation: $-7z = -21 \implies z = \frac{-21}{-7} = 3$.
* Substituting $z = 3$ into the second equation: $y - 2(3) = -4 \implies y - 6 = -4 \implies y = 2$.
* Substituting $y = 2$ and $z = 3$ into the first equation: $x + 2 + 3 = 6 \implies x + 5 = 6 \implies x = 1$.

Thus, the unique solution is **$(x, y, z) = (1, 2, 3)$**.

### Verification
We substitute $x = 1$, $y = 2$, and $z = 3$ into all three original equations to verify consistency:
* **Equation 1:** $1 + 2 + 3 = 6$ (matches $6$).
* **Equation 2:** $2(1) - 2 + 3 = 2 - 2 + 3 = 3$ (matches $3$).
* **Equation 3:** $1 + 2(2) - 3 = 1 + 4 - 3 = 2$ (matches $2$).

All three equations are satisfied identically.