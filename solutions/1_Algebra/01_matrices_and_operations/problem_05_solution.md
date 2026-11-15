# Exercise 5. Matrix Times Vector

## Question
Let the matrix $A$ and vector $x$ be given by:
$$A = \begin{pmatrix} 2 & -1 \\ 1 & 3 \end{pmatrix}, \quad x = \begin{pmatrix} 4 \\ 2 \end{pmatrix}$$

We are asked to compute the product $Ax$, and then express $Ax$ as a linear combination of the columns of $A$ with coefficients coming from the vector $x$.

## Solution

### 1. Computing $Ax$ via Row-by-Column Multiplication
Multiplying the $2 \times 2$ matrix $A$ by the $2 \times 1$ column vector $x$ produces a $2 \times 1$ vector whose entries are the dot products of the rows of $A$ with $x$:
$$Ax = \begin{pmatrix} 2 & -1 \\ 1 & 3 \end{pmatrix} \begin{pmatrix} 4 \\ 2 \end{pmatrix} = \begin{pmatrix} 2(4) + (-1)(2) \\ 1(4) + 3(2) \end{pmatrix} = \begin{pmatrix} 8 - 2 \\ 4 + 6 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}$$

### 2. Expressing $Ax$ as a Linear Combination of Columns
By definition, the matrix-vector product $Ax$ is equal to the sum of the columns of $A$ weighted by the corresponding entries of $x$:
$$Ax = x_1 \begin{pmatrix} a_{11} \\ a_{21} \end{pmatrix} + x_2 \begin{pmatrix} a_{12} \\ a_{22} \end{pmatrix}$$

Substituting the columns of $A$ and the coefficients $x_1 = 4$ and $x_2 = 2$:
$$Ax = 4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2 \begin{pmatrix} -1 \\ 3 \end{pmatrix} = \begin{pmatrix} 8 \\ 4 \end{pmatrix} + \begin{pmatrix} -2 \\ 6 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}$$

### Verification
Both independent approaches—taking dot products across the rows and forming a linear combination of the columns—yield the exact same result $\begin{pmatrix} 6 \\ 10 \end{pmatrix}$, verifying our calculation.