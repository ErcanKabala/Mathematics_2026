# Exercise 6. A System with a Parameter — Which Cases Actually Occur?

## Question
We need to analyze the parameter-dependent linear system:
$$\begin{cases} x + y = 2, \\ ax + ay = 4, \end{cases}$$
depending on the real parameter $a$. Among the three theoretical possibilities — **exactly one solution**, **infinitely many solutions**, and **no solution** — we must determine which cases actually occur and for which values of $a$, and explain why any remaining case cannot occur.

## Solution

### 1. Elimination in Terms of $a$
We form the augmented matrix and eliminate the $x$-entry in the second row using $R_2 \leftarrow R_2 - aR_1$:
$$\left( \begin{array}{cc|c} 1 & 1 & 2 \\ a & a & 4 \end{array} \right) \xrightarrow{R_2 \leftarrow R_2 - aR_1} \left( \begin{array}{cc|c} 1 & 1 & 2 \\ 0 & 0 & 4 - 2a \end{array} \right)$$

The second row corresponds to the equation:
$$0x + 0y = 4 - 2a$$

### 2. Analyzing Which Cases Occur
* **Case 1: Infinitely many solutions (occurs for $a = 2$).**
  When $4 - 2a = 0$, we obtain $a = 2$. In this case, the second row becomes $\begin{pmatrix} 0 & 0 \mid 0 \end{pmatrix}$ (the second equation $2x + 2y = 4$ is simply twice the first equation $x + y = 2$). The system reduces to $x + y = 2$, leaving $y = t \in \mathbb{R}$ as a free variable and $x = 2 - t$, which yields **infinitely many solutions**.

* **Case 2: No solution (occurs for all $a \neq 2$).**
  Whenever $a \neq 2$, we have $4 - 2a \neq 0$, so the second row reads $0 = 4 - 2a \neq 0$. This is a contradiction, meaning the system is inconsistent and has **no solution** for every $a \neq 2$.

* **Case 3: Exactly one solution (never occurs).**
  There is **no value of $a$** for which the system has a unique solution.

### 3. Why a Unique Solution Cannot Occur
For any value of $a$, the second row of the coefficient matrix $\begin{pmatrix} a & a \end{pmatrix} = a \begin{pmatrix} 1 & 1 \end{pmatrix}$ is a scalar multiple of the first row (equivalently, the coefficient determinant is $\det \begin{pmatrix} 1 & 1 \\ a & a \end{pmatrix} = a - a = 0$ for all $a$). Because the two rows of the coefficient matrix are always linearly dependent, elimination always eliminates both $x$ and $y$ in the second row simultaneously, leaving at most $1$ pivot for $2$ unknowns. Geometrically, for $a \neq 0$ the two equations represent parallel lines ($x + y = 2$ and $x + y = \frac{4}{a}$) that either coincide ($a = 2$) or never meet ($a \neq 2$), while for $a = 0$ the second equation $0 = 4$ has no points at all.

### Verification
We verify both occurring cases with concrete parameter values:
* At $a = 2$: the system is $x + y = 2$ and $2x + 2y = 4$, which is satisfied by infinitely many points $(2 - t, t)$ since $(2 - t) + t = 2$ and $2(2 - t) + 2t = 4$.
* At $a = 1$: the system is $x + y = 2$ and $x + y = 4$, which yields $2 = 4$, confirming no solution exists.