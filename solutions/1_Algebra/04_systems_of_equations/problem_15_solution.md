# Exercise 15. Classifying Three Systems

## Question
For each of the following three linear systems, we need to perform only as much Gaussian elimination as necessary to recognize its type, and justify its classification as having **one solution**, **infinitely many solutions**, or **no solution**:

* **System 1:**
  $$\begin{cases} x + y = 2, \\ x - y = 0, \end{cases}$$
* **System 2:**
  $$\begin{cases} x + y = 2, \\ 2x + 2y = 4, \end{cases}$$
* **System 3:**
  $$\begin{cases} x + y = 2, \\ 2x + 2y = 5. \end{cases}$$

## Solution

### 1. Classifying System 1
Forming the augmented matrix and performing a single elimination step ($R_2 \leftarrow R_2 - R_1$):
$$\left( \begin{array}{cc|c} 1 & 1 & 2 \\ 1 & -1 & 0 \end{array} \right) \xrightarrow{R_2 \leftarrow R_2 - R_1} \left( \begin{array}{cc|c} 1 & 1 & 2 \\ 0 & -2 & -2 \end{array} \right)$$
* **Classification:** **One solution** (a unique solution).
* **Justification:** We can stop elimination here because the matrix is already in row echelon form with no contradictory row and $2$ non-zero pivots (in columns $1$ and $2$) for the $2$ unknowns $x$ and $y$. There are $2 - 2 = 0$ free variables, guaranteeing a unique solution.

### 2. Classifying System 2
Forming the augmented matrix and performing a single elimination step ($R_2 \leftarrow R_2 - 2R_1$):
$$\left( \begin{array}{cc|c} 1 & 1 & 2 \\ 2 & 2 & 4 \end{array} \right) \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \left( \begin{array}{cc|c} 1 & 1 & 2 \\ 0 & 0 & 0 \end{array} \right)$$
* **Classification:** **Infinitely many solutions**.
* **Justification:** Elimination stops immediately because the second row becomes $\begin{pmatrix} 0 & 0 \mid 0 \end{pmatrix}$, representing the consistent identity $0 = 0$. Since there is only $1$ pivot column (column $1$) for $2$ unknowns, there is $2 - 1 = 1$ free variable ($y = t \in \mathbb{R}$, with $x = 2 - t$), producing infinitely many solutions.

### 3. Classifying System 3
Forming the augmented matrix and performing a single elimination step ($R_2 \leftarrow R_2 - 2R_1$):
$$\left( \begin{array}{cc|c} 1 & 1 & 2 \\ 2 & 2 & 5 \end{array} \right) \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \left( \begin{array}{cc|c} 1 & 1 & 2 \\ 0 & 0 & 1 \end{array} \right)$$
* **Classification:** **No solution** (inconsistent).
* **Justification:** Elimination stops immediately because the second row becomes $\begin{pmatrix} 0 & 0 \mid 1 \end{pmatrix}$, which translates to the false equation $0x + 0y = 1$, or $0 = 1$. Since no values of $x$ and $y$ can satisfy $0 = 1$, the system is inconsistent and has no solution.

### Verification
We verify each classification directly:
* **System 1:** Solving $-2y = -2 \implies y = 1$ and $x + 1 = 2 \implies x = 1$ gives the unique point $(1, 1)$, which satisfies $1 + 1 = 2$ and $1 - 1 = 0$.
* **System 2:** Testing two distinct parameter values $t = 0$ and $t = 2$ in $(2 - t, t)$ gives $(2, 0)$ and $(0, 2)$; both satisfy $x + y = 2$ and $2x + 2y = 4$.
* **System 3:** Doubling the first equation $x + y = 2$ yields $2x + 2y = 4$, which directly contradicts the second equation $2x + 2y = 5$ since $4 \neq 5$.