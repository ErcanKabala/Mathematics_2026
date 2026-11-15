# Exercise 4. Matrix Multiplication and Noncommutativity

## Question
For the matrices:
$$A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix}$$

We need to compute both $AB$ and $BA$, determine whether $AB = BA$, and use this example to explain what the noncommutativity of matrix multiplication means.

## Solution

### 1. Computing $AB$ and $BA$
Using the row-by-column rule for matrix multiplication, the $(i, j)$-entry of a product is the dot product of the $i$-th row of the first matrix and the $j$-th column of the second matrix.

* **Product $AB$:**
  $$AB = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix} = \begin{pmatrix} 1(2) + 2(3) & 1(0) + 2(1) \\ 0(2) + 1(3) & 0(0) + 1(1) \end{pmatrix} = \begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix}$$

* **Product $BA$:**
  $$BA = \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 2(1) + 0(0) & 2(2) + 0(1) \\ 3(1) + 1(0) & 3(2) + 1(1) \end{pmatrix} = \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix}$$

### 2. Comparison and Noncommutativity
Comparing the two results clearly shows that **$AB \neq BA$**, as $\begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix} \neq \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix}$.

**Explanation:** Unlike real numbers where multiplication is commutative ($ab = ba$), matrix multiplication is **noncommutative**. Changing the order of the factors alters which rows are paired with which columns, generally producing completely different matrices.

### Verification
Although $AB \neq BA$, the determinant of a product must satisfy $\det(AB) = \det(BA) = \det(A)\det(B)$:
* $\det(A) = 1(1) - 2(0) = 1$ and $\det(B) = 2(1) - 0(3) = 2$, so $\det(A)\det(B) = 2$.
* $\det(AB) = 8(1) - 2(3) = 2$.
* $\det(BA) = 2(7) - 4(3) = 14 - 12 = 2$.
  All determinants match, confirming our matrix products are consistent.