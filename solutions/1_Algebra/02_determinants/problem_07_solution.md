# Exercise 7. Using Properties Instead of Recomputing

## Question
Suppose that for a $3 \times 3$ matrix $A$, we are given $\det A = -4$. We need to compute:
$$\det(2A), \quad \det(A^T), \quad \det(A^2), \quad \det(-A)$$
and justify each answer using the appropriate determinant property.

## Solution

Using the determinant properties for an $n \times n$ matrix with $n = 3$ and $\det A = -4$:

1. **Computing $\det(2A)$:**
   $$\det(2A) = 2^3 \det A = 8 \cdot (-4) = -32$$
   *Justification:* Scaling an $n \times n$ matrix $A$ by a scalar $c$ multiplies every one of its $n$ rows by $c$, so $\det(cA) = c^n \det A$. Here $c = 2$ and $n = 3$, giving a factor of $2^3 = 8$.

2. **Computing $\det(A^T)$:**
   $$\det(A^T) = \det A = -4$$
   *Justification:* Transposing a matrix interchanges its rows and columns without altering the determinant value: $\det(A^T) = \det A$.

3. **Computing $\det(A^2)$:**
   $$\det(A^2) = \det(A \cdot A) = (\det A)^2 = (-4)^2 = 16$$
   *Justification:* By the multiplicative property of determinants, $\det(AB) = \det A \cdot \det B$. Setting $B = A$ yields $\det(A^2) = (\det A)^2$.

4. **Computing $\det(-A)$:**
   $$\det(-A) = \det((-1)A) = (-1)^3 \det A = (-1) \cdot (-4) = 4$$
   *Justification:* Since $-A = (-1)A$, applying $\det(cA) = c^n \det A$ with $c = -1$ and $n = 3$ multiplies the determinant by $(-1)^3 = -1$.

### Verification
We can verify all four values using a concrete $3 \times 3$ diagonal matrix whose determinant is $-4$, such as $A = \begin{pmatrix} -4 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix}$:
* $2A = \begin{pmatrix} -8 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix} \implies \det(2A) = (-8)(2)(2) = -32$.
* $A^T = A \implies \det(A^T) = -4$.
* $A^2 = \begin{pmatrix} 16 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} \implies \det(A^2) = (16)(1)(1) = 16$.
* $-A = \begin{pmatrix} 4 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & -1 \end{pmatrix} \implies \det(-A) = (4)(-1)(-1) = 4$.
  All four results match our property-based calculations.