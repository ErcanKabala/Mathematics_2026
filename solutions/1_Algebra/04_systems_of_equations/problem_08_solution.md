# Exercise 8. Two Systems with the Same Coefficient Matrix

## Question
We are asked to solve the following two linear systems by elimination:
$$\text{System 1:} \quad \begin{cases} 2x + y = 5, \\ x - y = 1, \end{cases} \qquad \text{System 2:} \quad \begin{cases} 2x + y = 1, \\ x - y = 4. \end{cases}$$

Then, we must compare the successive elimination steps and explain which part of the calculation is the same in both cases, and why.

## Solution

### 1. Solving System 1 by Elimination
Forming the augmented matrix for System 1:
$$\left( \begin{array}{cc|c} 2 & 1 & 5 \\ 1 & -1 & 1 \end{array} \right)$$

We eliminate the $x$-entry in the second row using the pivot $2$ via the row operation $R_2 \leftarrow R_2 - \frac{1}{2}R_1$:
* New row $2$ entries: $\left(1 - \frac{1}{2}(2), \; -1 - \frac{1}{2}(1) \;\middle|\; 1 - \frac{1}{2}(5)\right) = \left(0, \; -\frac{3}{2} \;\middle|\; -\frac{3}{2}\right)$.
  $$\left( \begin{array}{cc|c} 2 & 1 & 5 \\ 0 & -\frac{3}{2} & -\frac{3}{2} \end{array} \right)$$

Back-substituting:
* From row $2$: $-\frac{3}{2}y = -\frac{3}{2} \implies y = 1$.
* From row $1$: $2x + 1 = 5 \implies 2x = 4 \implies x = 2$.

Thus, the solution to System 1 is **$(x, y) = (2, 1)$**.

### 2. Solving System 2 by Elimination
Forming the augmented matrix for System 2:
$$\left( \begin{array}{cc|c} 2 & 1 & 1 \\ 1 & -1 & 4 \end{array} \right)$$

Applying the exact same row operation $R_2 \leftarrow R_2 - \frac{1}{2}R_1$:
* New row $2$ entries: $\left(1 - \frac{1}{2}(2), \; -1 - \frac{1}{2}(1) \;\middle|\; 4 - \frac{1}{2}(1)\right) = \left(0, \; -\frac{3}{2} \;\middle|\; \frac{7}{2}\right)$.
  $$\left( \begin{array}{cc|c} 2 & 1 & 1 \\ 0 & -\frac{3}{2} & \frac{7}{2} \end{array} \right)$$

Back-substituting:
* From row $2$: $-\frac{3}{2}y = \frac{7}{2} \implies y = -\frac{7}{3}$.
* From row $1$: $2x + \left(-\frac{7}{3}\right) = 1 \implies 2x = 1 + \frac{7}{3} = \frac{10}{3} \implies x = \frac{5}{3}$.

Thus, the solution to System 2 is **$(x, y) = \left(\frac{5}{3}, -\frac{7}{3}\right)$**.

### 3. Comparison of Elimination Steps
* **What is the same:** The pivot selection ($2$), the elimination multiplier ($-\frac{1}{2}$, i.e., $R_2 \leftarrow R_2 - \frac{1}{2}R_1$), and the entire resulting left-hand side upper triangular matrix $\begin{pmatrix} 2 & 1 \\ 0 & -\frac{3}{2} \end{pmatrix}$ are completely identical in both calculations.
* **Why:** The row operations and elimination multipliers depend exclusively on the entries of the **coefficient matrix** $A = \begin{pmatrix} 2 & 1 \\ 1 & -1 \end{pmatrix}$, which is identical for both systems. Only the right-hand side column changes during elimination, producing different final values for $x$ and $y$.

### Verification
We substitute both solutions back into their respective original equations:
* **System 1 at $(2, 1)$:** $2(2) + 1 = 5$ and $2 - 1 = 1$ (both hold).
* **System 2 at $\left(\frac{5}{3}, -\frac{7}{3}\right)$:** $2\left(\frac{5}{3}\right) + \left(-\frac{7}{3}\right) = \frac{10 - 7}{3} = 1$ and $\frac{5}{3} - \left(-\frac{7}{3}\right) = \frac{12}{3} = 4$ (both hold).