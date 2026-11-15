# Exercise 7. Identity Matrix, Zero Matrix, and Powers

## Question
For the matrix:
$$A = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}$$

We need to compute $AI$, $IA$, $A + 0$, $A^2$, and $A^3$. Then, we must explain the roles of the matrices $I$ and $0$, and describe the pattern observed in successive powers of $A$.

## Solution

### 1. Computations with $I$, $0$, and Powers of $A$
Here, $I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$ is the $2 \times 2$ identity matrix and $0 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$ is the $2 \times 2$ zero matrix.

* **Computing $AI$ and $IA$:**
  $$AI = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 2(1) + 1(0) & 2(0) + 1(1) \\ 0(1) + 2(0) & 0(0) + 2(1) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A$$
  $$IA = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 1(2) + 0(0) & 1(1) + 0(2) \\ 0(2) + 1(0) & 0(1) + 1(2) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A$$

* **Computing $A + 0$:**
  $$A + 0 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} + \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 2 + 0 & 1 + 0 \\ 0 + 0 & 2 + 0 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A$$

* **Computing $A^2$ and $A^3$:**
  $$A^2 = A \cdot A = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 2(2) + 1(0) & 2(1) + 1(2) \\ 0(2) + 2(0) & 0(1) + 2(2) \end{pmatrix} = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix}$$
  $$A^3 = A^2 \cdot A = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 4(2) + 4(0) & 4(1) + 4(2) \\ 0(2) + 4(0) & 0(1) + 4(2) \end{pmatrix} = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}$$

### 2. Roles of $I$ and $0$, and Pattern in $A^n$
* **Role of $I$:** The identity matrix $I$ serves as the multiplicative identity (neutral element for multiplication). Multiplying any square matrix by $I$ on either the left or the right leaves the matrix completely unchanged ($AI = IA = A$).
* **Role of $0$:** The zero matrix $0$ serves as the additive identity (neutral element for addition). Adding $0$ to any matrix of the same size leaves the matrix unchanged ($A + 0 = A$).
* **Pattern in Successive Powers of $A$:** Comparing $A^1 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}$, $A^2 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix}$, and $A^3 = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}$, we observe the general formula for any positive integer $n$:
  $$A^n = \begin{pmatrix} 2^n & n \cdot 2^{n-1} \\ 0 & 2^n \end{pmatrix}$$
  Specifically, the main diagonal entries grow as $2^n$, the lower-left entry remains $0$, and the upper-right entry equals $n \cdot 2^{n-1}$.

### Verification
We can verify $A^3$ by computing $A \cdot A^2$ (using associativity of matrix multiplication) and checking the general pattern formula for $n = 3$:
$$A \cdot A^2 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} = \begin{pmatrix} 8 + 0 & 8 + 4 \\ 0 + 0 & 0 + 8 \end{pmatrix} = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}$$
Also, substituting $n = 3$ into the pattern gives diagonal entries $2^3 = 8$ and top-right entry $3 \cdot 2^{3-1} = 3 \cdot 4 = 12$, confirming the result.