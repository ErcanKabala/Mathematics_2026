# Exercise 4. Triangular Matrix

## Question
Without expanding the determinant, we are asked to compute:
$$\det \begin{pmatrix} 2 & 4 & 1 \\ 0 & -3 & 5 \\ 0 & 0 & 7 \end{pmatrix}$$

Additionally, we must state the determinant rule for an arbitrary triangular matrix and explain it using this example.

## Solution

### 1. Computing the Determinant
Since the given matrix is upper triangular, its determinant is equal to the product of its main diagonal entries:
$$\det \begin{pmatrix} 2 & 4 & 1 \\ 0 & -3 & 5 \\ 0 & 0 & 7 \end{pmatrix} = 2 \cdot (-3) \cdot 7 = -42$$

### 2. General Rule and Explanation
**Rule:** For any arbitrary $n \times n$ upper triangular matrix (all entries below the main diagonal are zero) or lower triangular matrix (all entries above the main diagonal are zero), the determinant is simply the product of the entries on its main diagonal:
$$\det T = t_{11} \cdot t_{22} \cdots t_{nn}$$

**Explanation using this example:** In our $3 \times 3$ upper triangular matrix, all entries below the main diagonal are zero ($t_{21} = t_{31} = t_{32} = 0$). If we were to apply cofactor expansion repeatedly along the first column, the zeros in positions $(2,1)$ and $(3,1)$ would eliminate all terms except the first diagonal entry $2$, leaving $2 \cdot \det \begin{pmatrix} -3 & 5 \\ 0 & 7 \end{pmatrix}$. Repeating this along the first column of the remaining $2 \times 2$ submatrix eliminates the $0$ in the bottom-left and leaves $2 \cdot (-3) \cdot 7 = -42$. Thus, entries above the diagonal ($4$, $1$, and $5$) never enter the final value.

### Verification
We can verify the result using Sarrus' rule:
* Forward diagonals: $(2)(-3)(7) + (4)(5)(0) + (1)(0)(0) = -42 + 0 + 0 = -42$.
* Backward diagonals: $(1)(-3)(0) + (2)(5)(0) + (4)(0)(7) = 0 + 0 + 0 = 0$.
* $\det = -42 - 0 = -42$, confirming the diagonal product rule.