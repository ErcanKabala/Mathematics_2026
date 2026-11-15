# Exercise 8. Determinant of a Product

## Question
Let $A$ and $B$ be square matrices of the same size such that $\det A = 3$ and $\det B = -5$. We need to compute $\det(AB)$, $\det(BA)$, and, if it exists, $\det(A^{-1}B)$. We must also explain why the first two results are equal even though usually $AB \neq BA$.

## Solution

### 1. Computing $\det(AB)$, $\det(BA)$, and $\det(A^{-1}B)$
We apply the multiplicative property $\det(XY) = \det X \cdot \det Y$ and the inverse determinant property $\det(X^{-1}) = \frac{1}{\det X}$:

* **Computing $\det(AB)$:**
  $$\det(AB) = \det A \cdot \det B = 3 \cdot (-5) = -15$$

* **Computing $\det(BA)$:**
  $$\det(BA) = \det B \cdot \det A = (-5) \cdot 3 = -15$$

* **Computing $\det(A^{-1}B)$:**
  First, $A^{-1}$ exists because $\det A = 3 \neq 0$, and its determinant is $\det(A^{-1}) = \frac{1}{\det A} = \frac{1}{3}$. Therefore:
  $$\det(A^{-1}B) = \det(A^{-1}) \cdot \det B = \frac{1}{3} \cdot (-5) = -\frac{5}{3}$$

### 2. Why $\det(AB) = \det(BA)$ Despite $AB \neq BA$
Although matrix multiplication is noncommutative (so the product matrices $AB$ and $BA$ generally have completely different entries), the determinant maps each square matrix to a single real number (scalar). Because the determinant of a product equals the product of the individual determinants, and multiplication of real numbers is commutative ($3 \cdot (-5) = (-5) \cdot 3 = -15$), the scalar values $\det(AB)$ and $\det(BA)$ are always identical.

### Verification
We can verify $\det(A^{-1}B) = -\frac{5}{3}$ using the identity $A(A^{-1}B) = IB = B$. Taking determinants on both sides gives:
$$\det A \cdot \det(A^{-1}B) = \det B \implies 3 \cdot \left(-\frac{5}{3}\right) = -5 = \det B$$
The equality holds, confirming our result.