# Exercise 15. Combining Determinant Properties

## Question
Let $A$ and $B$ be invertible $2 \times 2$ matrices with:
$$\det A = -2, \quad \det B = 3$$
Without finding the entries of the matrices, we need to compute:
$$\det\left(B^{-1} A^T B\right)$$
state the determinant properties used in order, and explain why the factors involving $B$ eventually cancel.

## Solution

### 1. Step-by-Step Computation Using Determinant Properties
We evaluate $\det(B^{-1} A^T B)$ by applying three determinant properties in sequence:

* **Step 1 — Multiplicative Property of Determinants:**
  For any square matrices $X, Y, Z$ of the same size, the determinant of a product equals the product of the individual determinants ($\det(XYZ) = \det(X)\det(Y)\det(Z)$). Applying this splits the expression into three scalar factors:
  $$\det\left(B^{-1} A^T B\right) = \det\left(B^{-1}\right) \cdot \det\left(A^T\right) \cdot \det(B)$$

* **Step 2 — Determinant of an Inverse Matrix:**
  For any invertible matrix $B$, the determinant of its inverse is the reciprocal of its determinant ($\det(B^{-1}) = \frac{1}{\det B}$). Since $\det B = 3$:
  $$\det\left(B^{-1}\right) = \frac{1}{3}$$

* **Step 3 — Determinant of a Transpose Matrix:**
  Transposing a square matrix leaves its determinant unchanged ($\det(A^T) = \det A$). Since $\det A = -2$:
  $$\det\left(A^T\right) = -2$$

* **Step 4 — Combining the Scalar Values:**
  Substituting all three values back into the product gives:
  $$\det\left(B^{-1} A^T B\right) = \left(\frac{1}{3}\right) \cdot (-2) \cdot 3 = -2$$

### 2. Why the Factors Involving $B$ Eventually Cancel
Although matrix multiplication is noncommutative (so $B^{-1}$ and $B$ cannot be moved past $A^T$ inside the matrix product $B^{-1}A^T B$), taking the determinant converts each matrix factor into a real number (scalar). Because $B$ is invertible, $\det B = 3 \neq 0$, and ordinary multiplication of real numbers is commutative and associative. Consequently, we can rearrange the scalar factors $\det(B^{-1}) = \frac{1}{\det B}$ and $\det B$ next to each other:
$$\det\left(B^{-1}\right) \cdot \det(B) = \frac{1}{\det B} \cdot \det B = \frac{1}{3} \cdot 3 = 1$$
Geometrically, $B$ scales areas by a factor of $3$ and $B^{-1}$ scales areas by the reciprocal factor of $\frac{1}{3}$, so their net area-scaling effects cancel out completely, leaving $\det(B^{-1}A^T B) = \det(A^T) = \det A = -2$.

### Verification
We can verify our result using two concrete $2 \times 2$ matrices with $\det A = -2$ and $\det B = 3$:
$$A = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix} \quad (\det A = -2), \qquad B = \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} \quad (\det B = 3)$$
Here, $A^T = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix}$ and $B^{-1} = \begin{pmatrix} \frac{1}{3} & 0 \\ 0 & 1 \end{pmatrix}$. Computing the matrix product $B^{-1} A^T B$ explicitly gives:
$$B^{-1} A^T B = \begin{pmatrix} \frac{1}{3} & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} -\frac{2}{3} & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix}$$
Taking the determinant of the resulting matrix yields $\det\begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix} = (-2)(1) - (0)(0) = -2$, confirming our property-based calculation.