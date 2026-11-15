# Exercise 7. Inverse of a Product

## Question
For the matrices:
$$A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix}$$
we are asked to compute both $(AB)^{-1}$ and $B^{-1}A^{-1}$, verify that the results are identical, and explain the meaning of the reversed order.

## Solution

### 1. Computing $(AB)^{-1}$
First, we compute the matrix product $AB$:
$$AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix} = \begin{pmatrix} 1(2) + 1(0) & 1(0) + 1(3) \\ 0(2) + 1(0) & 0(0) + 1(3) \end{pmatrix} = \begin{pmatrix} 2 & 3 \\ 0 & 3 \end{pmatrix}$$
Since $\det(AB) = (2)(3) - (3)(0) = 6$, the $2 \times 2$ inverse formula yields:
$$(AB)^{-1} = \frac{1}{6} \begin{pmatrix} 3 & -3 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix}$$

### 2. Computing $B^{-1}A^{-1}$
Next, we find $A^{-1}$ and $B^{-1}$ individually:
* Since $\det A = 1(1) - 1(0) = 1$, we have $A^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}$.
* Since $\det B = 2(3) - 0(0) = 6$, we have $B^{-1} = \frac{1}{6}\begin{pmatrix} 3 & 0 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{3} \end{pmatrix}$.

Multiplying $B^{-1}$ by $A^{-1}$ in reversed order gives:
$$B^{-1}A^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{3} \end{pmatrix} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} \frac{1}{2}(1) + 0(0) & \frac{1}{2}(-1) + 0(1) \\ 0(1) + \frac{1}{3}(0) & 0(-1) + \frac{1}{3}(1) \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix}$$

### 3. Comparison and Meaning of the Reversed Order
Both calculations produce the exact same matrix $\begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix}$, confirming that $(AB)^{-1} = B^{-1}A^{-1}$.

**Meaning of the reversed order:** When a product $AB$ acts on a vector $x$ as $(AB)x = A(Bx)$, the transformation $B$ is applied **first**, and the transformation $A$ is applied **second**. To undo this two-step process and return to $x$, we must undo the last transformation ($A$) **first** using $A^{-1}$, and then undo the first transformation ($B$) **second** using $B^{-1}$. Algebraically, the inner factors cancel step by step:
$$(B^{-1}A^{-1})(AB) = B^{-1}(A^{-1}A)B = B^{-1}I_2B = B^{-1}B = I_2$$

### Verification
We also verify that $A^{-1}B^{-1}$ (without reversing the order) gives a different result:
$$A^{-1}B^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{3} \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{3} \\ 0 & \frac{1}{3} \end{pmatrix} \neq (AB)^{-1}$$
This confirms that reversing the order is essential.