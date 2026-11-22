# Exercise 12. Finding Inverses Without Starting from Scratch

## Question
It is known that the inverse of a $2 \times 2$ matrix $A$ is:
$$A^{-1} = \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix}$$
Without finding $A$, we need to compute $(3A)^{-1}$, $(A^T)^{-1}$, and $(A^2)^{-1}$, and justify each result using the appropriate inverse property.

## Solution

Using the algebraic properties of matrix inverses directly on $A^{-1}$:

### 1. Computing $(3A)^{-1}$
* **Property:** For any invertible matrix $A$ and any non-zero scalar $c \neq 0$, the inverse of a scalar multiple satisfies $(cA)^{-1} = \frac{1}{c}A^{-1}$ (because $(cA)\left(\frac{1}{c}A^{-1}\right) = \left(c \cdot \frac{1}{c}\right)(AA^{-1}) = 1 \cdot I = I$).
* **Computation:** Applying this property with $c = 3$:
  $$(3A)^{-1} = \frac{1}{3} A^{-1} = \frac{1}{3} \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix} = \begin{pmatrix} \frac{2}{3} & -\frac{1}{3} \\ -1 & \frac{2}{3} \end{pmatrix}$$

### 2. Computing $(A^T)^{-1}$
* **Property:** For any invertible matrix $A$, its transpose $A^T$ is also invertible, and the operations of transposition and inversion commute: $(A^T)^{-1} = (A^{-1})^T$ (because $A^T (A^{-1})^T = (A^{-1} A)^T = I^T = I$).
* **Computation:** Transposing the given matrix $A^{-1}$ (interchanging its rows and columns):
  $$(A^T)^{-1} = \left(A^{-1}\right)^T = \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix}^T = \begin{pmatrix} 2 & -3 \\ -1 & 2 \end{pmatrix}$$

### 3. Computing $(A^2)^{-1}$
* **Property:** By the inverse-of-a-product rule $(AB)^{-1} = B^{-1}A^{-1}$ applied with $B = A$, the inverse of the square of an invertible matrix equals the square of its inverse: $(A^2)^{-1} = (AA)^{-1} = A^{-1}A^{-1} = (A^{-1})^2$.
* **Computation:** Squaring the given matrix $A^{-1}$:
  $$(A^2)^{-1} = \left(A^{-1}\right)^2 = \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix} \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix} = \begin{pmatrix} 2(2) + (-1)(-3) & 2(-1) + (-1)(2) \\ (-3)(2) + 2(-3) & (-3)(-1) + 2(2) \end{pmatrix}$$
  $$(A^2)^{-1} = \begin{pmatrix} 4 + 3 & -2 - 2 \\ -6 - 6 & 3 + 4 \end{pmatrix} = \begin{pmatrix} 7 & -4 \\ -12 & 7 \end{pmatrix}$$

### Verification
As an independent check, we can recover $A = (A^{-1})^{-1} = \begin{pmatrix} 2 & 1 \\ 3 & 2 \end{pmatrix}$ (since $\det(A^{-1}) = 4 - 3 = 1$) and verify that each computed inverse multiplies with its corresponding matrix to yield $I_2$:
* $(3A)(3A)^{-1} = \begin{pmatrix} 6 & 3 \\ 9 & 6 \end{pmatrix} \begin{pmatrix} \frac{2}{3} & -\frac{1}{3} \\ -1 & \frac{2}{3} \end{pmatrix} = \begin{pmatrix} 4 - 3 & -2 + 2 \\ 6 - 6 & -3 + 4 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$.
* $A^T (A^T)^{-1} = \begin{pmatrix} 2 & 3 \\ 1 & 2 \end{pmatrix} \begin{pmatrix} 2 & -3 \\ -1 & 2 \end{pmatrix} = \begin{pmatrix} 4 - 3 & -6 + 6 \\ 2 - 2 & -3 + 4 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$.
* $A^2 (A^2)^{-1} = \begin{pmatrix} 7 & 4 \\ 12 & 7 \end{pmatrix} \begin{pmatrix} 7 & -4 \\ -12 & 7 \end{pmatrix} = \begin{pmatrix} 49 - 48 & -28 + 28 \\ 84 - 84 & -48 + 49 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$.
  All three inverses are confirmed.