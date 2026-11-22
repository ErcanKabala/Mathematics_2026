# Exercise 14. A Matrix That Is Its Own Inverse

## Question
Assume that a square matrix $A$ satisfies the condition:
$$A^2 = I$$
We need to:
1. Show that $A^{-1} = A$.
2. Give a concrete example of a $2 \times 2$ matrix different from $I$ and $-I$ that satisfies this condition, and verify it by multiplication.

## Solution

### 1. Showing That $A^{-1} = A$
By the definition of the matrix inverse, a square matrix $A$ is invertible with inverse $B = A^{-1}$ if and only if:
$$AB = I \quad \text{and} \quad BA = I$$

We are given that $A^2 = I$, which by definition of matrix powers means:
$$A \cdot A = I$$
Setting $B = A$, both required equations $AB = A \cdot A = I$ and $BA = A \cdot A = I$ are satisfied immediately. Because the inverse of an invertible matrix is unique, it follows directly that $A$ is invertible and:
$$A^{-1} = A$$

### 2. Example of a $2 \times 2$ Matrix Different from $I_2$ and $-I_2$
Geometrically, any reflection across a line through the origin in $\mathbb{R}^2$ applied twice returns every vector to its starting position. For instance, reflection across the line $y = x$ (which swaps the coordinates of a vector) is represented by the permutation matrix:
$$A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$$
Clearly, $A \neq \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$ and $A \neq \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} = -I_2$.

### Verification
We verify by direct matrix multiplication that $A^2 = I_2$:
$$A^2 = A \cdot A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 0(0) + 1(1) & 0(1) + 1(0) \\ 1(0) + 0(1) & 1(1) + 0(0) \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$$
Since $A \cdot A = I_2$, the matrix $A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$ satisfies $A^2 = I_2$ and is indeed its own inverse ($A^{-1} = A$).