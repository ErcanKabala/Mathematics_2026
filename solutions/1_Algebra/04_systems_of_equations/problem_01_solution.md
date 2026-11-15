# Exercise 1. From a System to a Matrix

## Question
We are given the system of three linear equations in three unknowns:
$$\begin{cases} 2x - y + z = 4, \\ x + 3y - 2z = 1, \\ 3x + y + z = 7. \end{cases}$$

We need to write this system in the matrix-vector form $Ax = b$, identify the coefficient matrix $A$, the vector of unknowns $x$, and the right-hand side vector $b$, and explain how each row of the matrix corresponds to one equation.

## Solution

### 1. Writing the System in the Form $Ax = b$
Aligning the variables $x$, $y$, and $z$ into columns, we rewrite the system as the matrix-vector product:
$$\begin{pmatrix} 2 & -1 & 1 \\ 1 & 3 & -2 \\ 3 & 1 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 4 \\ 1 \\ 7 \end{pmatrix}$$

### 2. Identifying the Matrix and Vectors
From the equation $Ax = b$ above, the three components are:
* **Coefficient matrix ($A$):**
  $$A = \begin{pmatrix} 2 & -1 & 1 \\ 1 & 3 & -2 \\ 3 & 1 & 1 \end{pmatrix}$$
* **Vector of unknowns ($x$):**
  $$x = \begin{pmatrix} x \\ y \\ z \end{pmatrix}$$
* **Right-hand side vector ($b$):**
  $$b = \begin{pmatrix} 4 \\ 1 \\ 7 \end{pmatrix}$$

### 3. How Each Row Corresponds to One Equation
By the definition of matrix-vector multiplication, the $i$-th entry of the product $Ax$ is the dot product of the $i$-th row of $A$ with the column vector $x$. Equating the $i$-th entry of $Ax$ to the $i$-th entry of $b$ reconstructs the $i$-th scalar equation:
* **Row 1** $\begin{pmatrix} 2 & -1 & 1 \end{pmatrix}$ dotted with $\begin{pmatrix} x \\ y \\ z \end{pmatrix}$ gives $2x - 1y + 1z$, and equating it to $b_1 = 4$ recovers the first equation $2x - y + z = 4$.
* **Row 2** $\begin{pmatrix} 1 & 3 & -2 \end{pmatrix}$ dotted with $\begin{pmatrix} x \\ y \\ z \end{pmatrix}$ gives $1x + 3y - 2z$, and equating it to $b_2 = 1$ recovers the second equation $x + 3y - 2z = 1$.
* **Row 3** $\begin{pmatrix} 3 & 1 & 1 \end{pmatrix}$ dotted with $\begin{pmatrix} x \\ y \\ z \end{pmatrix}$ gives $3x + 1y + 1z$, and equating it to $b_3 = 7$ recovers the third equation $3x + y + z = 7$.

### Verification
Carrying out the full matrix multiplication $Ax$ directly confirms that the matrix equation reproduces the exact original system:
$$Ax = \begin{pmatrix} 2(x) + (-1)(y) + 1(z) \\ 1(x) + 3(y) + (-2)(z) \\ 3(x) + 1(y) + 1(z) \end{pmatrix} = \begin{pmatrix} 2x - y + z \\ x + 3y - 2z \\ 3x + y + z \end{pmatrix} = \begin{pmatrix} 4 \\ 1 \\ 7 \end{pmatrix} = b$$