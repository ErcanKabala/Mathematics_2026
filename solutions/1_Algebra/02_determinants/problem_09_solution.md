# Exercise 9. Area and the Determinant

## Question
The vectors:
$$u = \begin{pmatrix} 3 \\ 1 \end{pmatrix}, \quad v = \begin{pmatrix} 1 \\ 4 \end{pmatrix}$$
span a parallelogram in $\mathbb{R}^2$. We need to compute its area using a determinant, then reverse the order of the vectors and explain what changes in the determinant and what does not change in the area.

## Solution

### 1. Computing the Area Using a Determinant
The area of the parallelogram spanned by two vectors $u, v \in \mathbb{R}^2$ is the absolute value of the determinant of the $2 \times 2$ matrix having $u$ and $v$ as its columns:
$$M_1 = \begin{pmatrix} 3 & 1 \\ 1 & 4 \end{pmatrix}$$
$$\det M_1 = (3)(4) - (1)(1) = 12 - 1 = 11$$
Taking the absolute value gives the area of the parallelogram:
$$\text{Area} = |\det M_1| = |11| = 11$$

### 2. Reversing the Order of the Vectors
Placing $v$ first and $u$ second forms the matrix:
$$M_2 = \begin{pmatrix} 1 & 3 \\ 4 & 1 \end{pmatrix}$$
$$\det M_2 = (1)(1) - (3)(4) = 1 - 12 = -11$$

### 3. Explanation of What Changes and What Does Not
* **What changes in the determinant:** Reversing the order of $u$ and $v$ interchanges the two columns of the matrix, which multiplies the determinant by $-1$ (changing its sign from $+11$ to $-11$). Geometrically, the sign of the determinant encodes orientation: $(u, v)$ is oriented counterclockwise ($\det > 0$), whereas $(v, u)$ is oriented clockwise ($\det < 0$).
* **What does not change in the area:** Geometric area is always a non-negative magnitude given by the absolute value of the determinant. Since $|-11| = |11| = 11$, the area of the parallelogram remains unchanged at **$11$**.

### Verification
We can verify the area using the Euclidean norm and dot product identity $\text{Area} = \sqrt{\|u\|^2 \|v\|^2 - (u \cdot v)^2}$:
* $\|u\|^2 = 3^2 + 1^2 = 10$
* $\|v\|^2 = 1^2 + 4^2 = 17$
* $u \cdot v = 3(1) + 1(4) = 7$
  $$\text{Area} = \sqrt{10 \cdot 17 - 7^2} = \sqrt{170 - 49} = \sqrt{121} = 11$$
  This matches the determinant result of $11$.