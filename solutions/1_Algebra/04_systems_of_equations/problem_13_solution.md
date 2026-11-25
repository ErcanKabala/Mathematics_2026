# Exercise 13. Does Every Equation Add New Information?

## Question
Consider the linear system of three equations in three unknowns $x_1, x_2, x_3$:
$$\begin{cases} x_1 + x_2 = 10, \\ x_2 + x_3 = 8, \\ x_1 - x_3 = 2. \end{cases}$$

We need to solve the system, check whether all three equations are independently necessary to describe the solution set, and show by calculation if one equation follows from the others.

## Solution

### 1. Solving the System via Gaussian Elimination
Writing the system as an augmented matrix and applying elementary row operations to reach row echelon form:
$$\left( \begin{array}{ccc|c} 1 & 1 & 0 & 10 \\ 0 & 1 & 1 & 8 \\ 1 & 0 & -1 & 2 \end{array} \right)$$

* **Step 1 ($R_3 \leftarrow R_3 - R_1$):** Eliminate the $x_1$-term in the third row:
  $$\left( \begin{array}{ccc|c} 1 & 1 & 0 & 10 \\ 0 & 1 & 1 & 8 \\ 0 & -1 & -1 & -8 \end{array} \right)$$

* **Step 2 ($R_3 \leftarrow R_3 + R_2$):** Eliminate the $x_2$-term in the third row:
  $$\left( \begin{array}{ccc|c} 1 & 1 & 0 & 10 \\ 0 & 1 & 1 & 8 \\ 0 & 0 & 0 & 0 \end{array} \right)$$

The third row reduces completely to zeros ($0 = 0$), leaving $2$ pivot columns (for $x_1$ and $x_2$) and $1$ non-pivot column (for $x_3$). Setting $x_3 = t \in \mathbb{R}$ as a free variable:
* From row $2$: $x_2 + t = 8 \implies x_2 = 8 - t$.
* From row $1$: $x_1 + (8 - t) = 10 \implies x_1 = 2 + t$.

Thus, the complete solution set in parametric form is:
$$(x_1, x_2, x_3) = (2 + t, \; 8 - t, \; t), \quad t \in \mathbb{R} \qquad \text{or} \qquad \begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix} = \begin{pmatrix} 2 \\ 8 \\ 0 \end{pmatrix} + t \begin{pmatrix} 1 \\ -1 \\ 1 \end{pmatrix}$$

### 2. Checking Independence of the Equations
**No, all three equations are not independently necessary.** The third equation is redundant because it follows directly as a linear combination of the first two equations.

**Proof by calculation:** Subtracting the second equation ($E_2: x_2 + x_3 = 8$) from the first equation ($E_1: x_1 + x_2 = 10$) gives:
$$(x_1 + x_2) - (x_2 + x_3) = 10 - 8$$
$$x_1 + x_2 - x_2 - x_3 = 2 \implies x_1 - x_3 = 2$$
This reproduces the third equation ($E_3$) identically ($E_3 = E_1 - E_2$). Therefore, any triple $(x_1, x_2, x_3)$ satisfying the first two equations automatically satisfies the third, and the first two equations alone completely determine the solution set.

### Verification
We substitute $(x_1, x_2, x_3) = (2 + t, 8 - t, t)$ into all three original equations to verify that they hold for every $t \in \mathbb{R}$:
* **Equation 1:** $(2 + t) + (8 - t) = 10$ (True).
* **Equation 2:** $(8 - t) + t = 8$ (True).
* **Equation 3:** $(2 + t) - t = 2$ (True).

For a concrete numerical check, choosing $t = 0$ gives $(2, 8, 0)$, which satisfies $2 + 8 = 10$, $8 + 0 = 8$, and $2 - 0 = 2$. All three equations are satisfied identically.