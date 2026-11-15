# Exercise 11. A Parameter in a System of Three Equations

## Question
We need to analyze the number of solutions of the parameter-dependent linear system:
$$\begin{cases} x + y + z = 1, \\ x + ty + z = 2, \\ x + y + tz = 3, \end{cases}$$
depending on the real parameter $t$. We must use elimination and separately analyze the parameter values for which a standard calculation step ceases to be valid.

## Solution

### 1. Forward Elimination
We write the augmented matrix of the system:
$$\left( \begin{array}{ccc|c} 1 & 1 & 1 & 1 \\ 1 & t & 1 & 2 \\ 1 & 1 & t & 3 \end{array} \right)$$

Applying the row replacement operations $R_2 \leftarrow R_2 - R_1$ and $R_3 \leftarrow R_3 - R_1$ (which are valid for every real number $t$) immediately reduces the matrix to triangular form:
$$\left( \begin{array}{ccc|c} 1 & 1 & 1 & 1 \\ 0 & t - 1 & 0 & 1 \\ 0 & 0 & t - 1 & 2 \end{array} \right)$$

### 2. Identifying When a Standard Calculation Step Ceases to Be Valid
To solve the second and third equations $(t - 1)y = 1$ and $(t - 1)z = 2$ by back-substitution, the standard step is to divide both sides by $(t - 1)$. This division is valid if and only if $t - 1 \neq 0$, and **ceases to be valid when $t = 1$** (where it would cause division by zero).

### 3. Case-by-Case Analysis of the Number of Solutions
* **Case 1: $t = 1$ (Critical value — No solution).**
Substituting $t = 1$ into the reduced augmented matrix yields:
$$\left( \begin{array}{ccc|c} 1 & 1 & 1 & 1 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 0 & 2 \end{array} \right)$$
The second and third rows correspond to the false equations $0 = 1$ and $0 = 2$ (in the original system, all three equations have the identical left-hand side $x + y + z$, which cannot simultaneously equal $1$, $2$, and $3$). Hence, for **$t = 1$**, the system is inconsistent and has **$0$ solutions (no solution)**.

* **Case 2: $t \neq 1$ (Standard step valid — Unique solution).**
When $t \neq 1$, we have $t - 1 \neq 0$ and can safely divide by $(t - 1)$:
  1. From row $3$: $(t - 1)z = 2 \implies z = \frac{2}{t - 1}$.
  2. From row $2$: $(t - 1)y = 1 \implies y = \frac{1}{t - 1}$.
  3. From row $1$: $x + y + z = 1 \implies x = 1 - \frac{1}{t - 1} - \frac{2}{t - 1} = \frac{(t - 1) - 3}{t - 1} = \frac{t - 4}{t - 1}$.
Hence, for every **$t \neq 1$**, the system has **exactly $1$ solution (a unique solution)**:
$$(x, y, z) = \left( \frac{t - 4}{t - 1}, \; \frac{1}{t - 1}, \; \frac{2}{t - 1} \right)$$

### Verification
We verify the unique solution formula for any $t \neq 1$ by substituting it back into all three original equations:
* **Equation 1:** $\frac{t - 4}{t - 1} + \frac{1}{t - 1} + \frac{2}{t - 1} = \frac{t - 1}{t - 1} = 1$.
* **Equation 2:** $\frac{t - 4}{t - 1} + t\left(\frac{1}{t - 1}\right) + \frac{2}{t - 1} = \frac{2t - 2}{t - 1} = \frac{2(t - 1)}{t - 1} = 2$.
* **Equation 3:** $\frac{t - 4}{t - 1} + \frac{1}{t - 1} + t\left(\frac{2}{t - 1}\right) = \frac{3t - 3}{t - 1} = \frac{3(t - 1)}{t - 1} = 3$.

All three equations are satisfied identically for all $t \neq 1$.