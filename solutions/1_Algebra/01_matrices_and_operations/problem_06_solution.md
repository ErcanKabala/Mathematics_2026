# Exercise 6. Transpose

## Question
For the matrices:
$$A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}, \quad B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}$$

We need to compute $A^T$, $B^T$, and $AB$, and then verify in this example that the transpose of a product reverses the order of the factors:
$$(AB)^T = B^T A^T$$

## Solution

### 1. Computing $A^T$ and $B^T$
The transpose of a matrix is obtained by interchanging its rows and columns (the $i$-th row becomes the $i$-th column):
$$A^T = \begin{pmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{pmatrix}, \quad B^T = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 3 \end{pmatrix}$$

### 2. Computing $AB$
Since $A$ is $2 \times 3$ and $B$ is $3 \times 2$, their product $AB$ is a $2 \times 2$ matrix:
$$AB = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix} = \begin{pmatrix} 1(1) + 2(2) + 3(-1) & 1(0) + 2(1) + 3(3) \\ 4(1) + 5(2) + 6(-1) & 4(0) + 5(1) + 6(3) \end{pmatrix}$$
$$AB = \begin{pmatrix} 1 + 4 - 3 & 0 + 2 + 9 \\ 4 + 10 - 6 & 0 + 5 + 18 \end{pmatrix} = \begin{pmatrix} 2 & 11 \\ 8 & 23 \end{pmatrix}$$

### 3. Verifying $(AB)^T = B^T A^T$
First, we take the transpose of the product $AB$ found above:
$$(AB)^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}$$

Next, we compute the product $B^T A^T$ (where $B^T$ is $2 \times 3$ and $A^T$ is $3 \times 2$):
$$B^T A^T = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 3 \end{pmatrix} \begin{pmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{pmatrix} = \begin{pmatrix} 1(1) + 2(2) + (-1)(3) & 1(4) + 2(5) + (-1)(6) \\ 0(1) + 1(2) + 3(3) & 0(4) + 1(5) + 3(6) \end{pmatrix}$$
$$B^T A^T = \begin{pmatrix} 1 + 4 - 3 & 4 + 10 - 6 \\ 0 + 2 + 9 & 0 + 5 + 18 \end{pmatrix} = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}$$

### Verification
Comparing the two resulting $2 \times 2$ matrices, we see that $(AB)^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix} = B^T A^T$, which confirms the transpose product identity.