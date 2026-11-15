# Exercise 6. Solving a System Using the Inverse

## Question
We need to solve the linear system $Ax = b$, where:
$$A = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}, \quad b = \begin{pmatrix} 5 \\ 7 \end{pmatrix}$$
using the formula $x = A^{-1}b$, and then substitute the resulting vector back into $Ax = b$ to check the result.

## Solution

### 1. Finding $A^{-1}$
First, we compute the determinant of $A$:
$$\det A = (2)(3) - (1)(1) = 6 - 1 = 5 \neq 0$$
Using the $2 \times 2$ inverse formula $A^{-1} = \frac{1}{\det A}\begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$ gives:
$$A^{-1} = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix}$$

### 2. Computing $x = A^{-1}b$
Multiplying both sides of $Ax = b$ on the left by $A^{-1}$ isolates $x = A^{-1}b$. Substituting $A^{-1}$ and $b$:
$$x = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 5 \\ 7 \end{pmatrix} = \frac{1}{5} \begin{pmatrix} 3(5) + (-1)(7) \\ (-1)(5) + 2(7) \end{pmatrix} = \frac{1}{5} \begin{pmatrix} 15 - 7 \\ -5 + 14 \end{pmatrix} = \frac{1}{5} \begin{pmatrix} 8 \\ 9 \end{pmatrix} = \begin{pmatrix} \frac{8}{5} \\ \frac{9}{5} \end{pmatrix}$$

### Verification
We substitute $x = \begin{pmatrix} \frac{8}{5} \\ \frac{9}{5} \end{pmatrix}$ back into the left-hand side $Ax$:
$$Ax = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix} \begin{pmatrix} \frac{8}{5} \\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 2\left(\frac{8}{5}\right) + 1\left(\frac{9}{5}\right) \\ 1\left(\frac{8}{5}\right) + 3\left(\frac{9}{5}\right) \end{pmatrix} = \begin{pmatrix} \frac{16}{5} + \frac{9}{5} \\ \frac{8}{5} + \frac{27}{5} \end{pmatrix} = \begin{pmatrix} \frac{25}{5} \\ \frac{35}{5} \end{pmatrix} = \begin{pmatrix} 5 \\ 7 \end{pmatrix} = b$$
The equation $Ax = b$ holds identically, confirming our solution.