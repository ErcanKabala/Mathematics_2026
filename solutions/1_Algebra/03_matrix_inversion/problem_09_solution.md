# Exercise 9. Matrix Equation

## Question
Given the matrices:
$$A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix}$$
we need to solve the matrix equation $AX = B$ for the unknown matrix $X$. Before calculating, we must decide on which side of the equation $A^{-1}$ must be applied, and at the end we must check the result by computing $AX$.

## Solution

### 1. Deciding Which Side to Multiply by $A^{-1}$
Because matrix multiplication is noncommutative, the side on which we multiply matters. In the equation $AX = B$, the matrix $A$ stands on the **left** of $X$. Therefore, we must multiply both sides of the equation on the **left** by $A^{-1}$ so that $A^{-1}$ is adjacent to $A$:
$$A^{-1}(AX) = A^{-1}B \implies (A^{-1}A)X = A^{-1}B \implies I_2 X = A^{-1}B \implies X = A^{-1}B$$
*(Multiplying on the right would yield $AXA^{-1} = BA^{-1}$, which fails to isolate $X$.)*

### 2. Computing $A^{-1}$ and Solving for $X$
First, we compute $A^{-1}$ using $\det A = (1)(1) - (2)(0) = 1$:
$$A^{-1} = \frac{1}{1} \begin{pmatrix} 1 & -2 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -2 \\ 0 & 1 \end{pmatrix}$$

Next, we compute $X = A^{-1}B$:
$$X = \begin{pmatrix} 1 & -2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix} = \begin{pmatrix} 1(3) + (-2)(2) & 1(1) + (-2)(4) \\ 0(3) + 1(2) & 0(1) + 1(4) \end{pmatrix} = \begin{pmatrix} 3 - 4 & 1 - 8 \\ 2 & 4 \end{pmatrix} = \begin{pmatrix} -1 & -7 \\ 2 & 4 \end{pmatrix}$$

### Verification
We substitute $X = \begin{pmatrix} -1 & -7 \\ 2 & 4 \end{pmatrix}$ back into $AX$ to verify that it equals $B$:
$$AX = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -1 & -7 \\ 2 & 4 \end{pmatrix} = \begin{pmatrix} 1(-1) + 2(2) & 1(-7) + 2(4) \\ 0(-1) + 1(2) & 0(-7) + 1(4) \end{pmatrix} = \begin{pmatrix} -1 + 4 & -7 + 8 \\ 2 & 4 \end{pmatrix} = \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix} = B$$
Since $AX = B$, the solution matrix $X$ is verified.