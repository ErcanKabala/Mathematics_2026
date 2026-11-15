# Exercise 8. Inverse of a Transformation

## Question
The diagonal matrix:
$$S = \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix}$$
describes a nonuniform scaling of the plane $\mathbb{R}^2$. We need to find $S^{-1}$, explain geometrically what the inverse transformation does, and check the action of the pair $S, S^{-1}$ on one simple vector.

## Solution

### 1. Finding $S^{-1}$
The determinant of $S$ is $\det S = (2)\left(\frac{1}{2}\right) - (0)(0) = 1$. Applying the $2 \times 2$ inverse formula (or taking the reciprocals of the diagonal entries):
$$S^{-1} = \frac{1}{1} \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix}$$

### 2. Geometric Explanation
For any point $\begin{pmatrix} x \\ y \end{pmatrix}$ in the plane:
* The transformation $S$ acts by $S \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 2x \\ \frac{1}{2}y \end{pmatrix}$, which **stretches** vectors horizontally along the $x$-axis by a factor of $2$ and **compresses** them vertically along the $y$-axis by a factor of $\frac{1}{2}$.
* The inverse transformation $S^{-1}$ acts by $S^{-1} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} \frac{1}{2}x \\ 2y \end{pmatrix}$, which reverses $S$ by **compressing** horizontally along the $x$-axis by a factor of $\frac{1}{2}$ (halving the $x$-coordinate) and **stretching** vertically along the $y$-axis by a factor of $2$ (doubling the $y$-coordinate).

### Verification
We check the action of $S$ and $S^{-1}$ on the simple vector $v = \begin{pmatrix} 3 \\ 4 \end{pmatrix}$:
1. Applying $S$ first, followed by $S^{-1}$:
   $$Sv = \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix} \begin{pmatrix} 3 \\ 4 \end{pmatrix} = \begin{pmatrix} 6 \\ 2 \end{pmatrix} \implies S^{-1}(Sv) = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 6 \\ 2 \end{pmatrix} = \begin{pmatrix} 3 \\ 4 \end{pmatrix} = v$$
2. Applying $S^{-1}$ first, followed by $S$:
   $$S^{-1}v = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 3 \\ 4 \end{pmatrix} = \begin{pmatrix} \frac{3}{2} \\ 8 \end{pmatrix} \implies S(S^{-1}v) = \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix} \begin{pmatrix} \frac{3}{2} \\ 8 \end{pmatrix} = \begin{pmatrix} 3 \\ 4 \end{pmatrix} = v$$
   Both compositions return the exact original vector $v$.