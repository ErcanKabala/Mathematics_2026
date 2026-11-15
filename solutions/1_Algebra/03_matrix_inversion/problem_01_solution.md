# Exercise 1. Definition of the Inverse

## Question
For the $2 \times 2$ matrices:
$$A = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix}$$

We need to check, without using an inverse formula, whether $B = A^{-1}$. Specifically, we must compute both $AB$ and $BA$ and relate the results to the formal definition of the matrix inverse.

## Solution

### 1. Computing $AB$ and $BA$
Using standard row-by-column matrix multiplication, we compute both products directly:

* **Product $AB$:**
  $$AB = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix} = \begin{pmatrix} 2(1) + 1(-1) & 2(-1) + 1(2) \\ 1(1) + 1(-1) & 1(-1) + 1(2) \end{pmatrix} = \begin{pmatrix} 2 - 1 & -2 + 2 \\ 1 - 1 & -1 + 2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$$

* **Product $BA$:**
  $$BA = \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} = \begin{pmatrix} 1(2) + (-1)(1) & 1(1) + (-1)(1) \\ -1(2) + 2(1) & -1(1) + 2(1) \end{pmatrix} = \begin{pmatrix} 2 - 1 & 1 - 1 \\ -2 + 2 & -1 + 2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$$

### 2. Relation to the Definition of the Inverse
By definition, an $n \times n$ square matrix $A$ is invertible if there exists an $n \times n$ matrix $B$ such that:
$$AB = I_n \quad \text{and} \quad BA = I_n$$
In that case, $B$ is uniquely determined and is called the inverse of $A$, denoted $B = A^{-1}$. Since our calculations confirm that both $AB = I_2$ and $BA = I_2$, we conclude directly from the definition that **$B = A^{-1}$**.

### Verification
We can verify that $B$ undoes the linear transformation of $A$ on an arbitrary vector $v = \begin{pmatrix} x \\ y \end{pmatrix}$:
$$Av = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 2x + y \\ x + y \end{pmatrix}$$
Applying $B$ to the resulting vector $Av$ yields:
$$B(Av) = \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 2x + y \\ x + y \end{pmatrix} = \begin{pmatrix} (2x + y) - (x + y) \\ -(2x + y) + 2(x + y) \end{pmatrix} = \begin{pmatrix} x \\ y \end{pmatrix} = v$$
Because $B$ restores the original vector $v$, $B = A^{-1}$ is verified.