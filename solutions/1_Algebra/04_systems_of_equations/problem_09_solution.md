# Exercise 9. A System from a Sum Condition

## Question
We need to find numbers $x, y$ satisfying the two linear conditions:
$$x + y = 10, \quad 2x + 5y = 32.$$

We must solve the system and explain geometrically why the solution is unique.

## Solution

### 1. Solving the System
Writing the two conditions as a system and forming the augmented matrix:
$$\left( \begin{array}{cc|c} 1 & 1 & 10 \\ 2 & 5 & 32 \end{array} \right)$$

Applying the row operation $R_2 \leftarrow R_2 - 2R_1$ eliminates the $x$-entry in the second row:
$$\left( \begin{array}{cc|c} 1 & 1 & 10 \\ 0 & 3 & 12 \end{array} \right)$$

Solving by back-substitution:
* From the second row: $3y = 12 \implies y = \frac{12}{3} = 4$.
* From the first row: $x + 4 = 10 \implies x = 10 - 4 = 6$.

Thus, the numbers are **$x = 6$** and **$y = 4$**.

### 2. Geometric Explanation of Uniqueness
In the $xy$-coordinate plane $\mathbb{R}^2$, each linear equation in two variables represents a straight line. Rewriting both equations in slope-intercept form ($y = mx + c$):
* **First line:** $x + y = 10 \iff y = -x + 10$, which has slope $m_1 = -1$.
* **Second line:** $2x + 5y = 32 \iff y = -\frac{2}{5}x + \frac{32}{5}$, which has slope $m_2 = -\frac{2}{5}$.

Because the two lines have different slopes ($m_1 = -1 \neq -\frac{2}{5} = m_2$), they are neither parallel nor identical. Two non-parallel straight lines in a plane intersect at **exactly one point**, namely $(6, 4)$, which geometrically guarantees that the solution is unique.

### Verification
We check that $x = 6$ and $y = 4$ satisfy both original conditions:
* First condition: $6 + 4 = 10$ (True).
* Second condition: $2(6) + 5(4) = 12 + 20 = 32$ (True).