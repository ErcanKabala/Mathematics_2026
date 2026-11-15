# Exercise 2. Formula for a 2x2 Matrix

## Question
We are asked to find the inverse of the matrix:
$$A = \begin{pmatrix} 3 & 2 \\ 5 & 4 \end{pmatrix}$$
using the explicit formula for a $2 \times 2$ matrix, and then check the result by computing one product with $A$.

## Solution

### 1. Applying the $2 \times 2$ Inverse Formula
For a general $2 \times 2$ matrix $A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$, the inverse exists if and only if $\det A = ad - bc \neq 0$, and is given by:
$$A^{-1} = \frac{1}{ad - bc} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$$

First, we compute the determinant of $A$:
$$\det A = (3)(4) - (2)(5) = 12 - 10 = 2$$
Since $\det A = 2 \neq 0$, the matrix is invertible. Substituting $a = 3, b = 2, c = 5, d = 4$ into the formula gives:
$$A^{-1} = \frac{1}{2} \begin{pmatrix} 4 & -2 \\ -5 & 3 \end{pmatrix} = \begin{pmatrix} \frac{4}{2} & -\frac{2}{2} \\ -\frac{5}{2} & \frac{3}{2} \end{pmatrix} = \begin{pmatrix} 2 & -1 \\ -\frac{5}{2} & \frac{3}{2} \end{pmatrix}$$

### Verification
We check the result by computing the product $A A^{-1}$:
$$A A^{-1} = \begin{pmatrix} 3 & 2 \\ 5 & 4 \end{pmatrix} \begin{pmatrix} 2 & -1 \\ -\frac{5}{2} & \frac{3}{2} \end{pmatrix} = \begin{pmatrix} 3(2) + 2\left(-\frac{5}{2}\right) & 3(-1) + 2\left(\frac{3}{2}\right) \\ 5(2) + 4\left(-\frac{5}{2}\right) & 5(-1) + 4\left(\frac{3}{2}\right) \end{pmatrix}$$
$$A A^{-1} = \begin{pmatrix} 6 - 5 & -3 + 3 \\ 10 - 10 & -5 + 6 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$$
Since $A A^{-1} = I_2$, our inverse matrix is confirmed.