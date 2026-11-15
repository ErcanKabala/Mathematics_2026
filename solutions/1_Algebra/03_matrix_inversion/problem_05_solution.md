# Exercise 5. A 3x3 Matrix

## Question
We need to use Gauss–Jordan elimination to find the inverse of the $3 \times 3$ matrix:
$$A = \begin{pmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \\ 1 & 0 & 1 \end{pmatrix}$$
and then check the result by matrix multiplication.

## Solution

### 1. Gauss–Jordan Elimination on $[A \mid I_3]$
We set up the augmented matrix $[A \mid I_3]$ and reduce the left side to $I_3$:

* **Initial augmented matrix:**
  $$\left( \begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 1 & 0 & 1 & 0 & 0 & 1 \end{array} \right)$$

* **Step 1 ($R_3 \leftarrow R_3 - R_1$):** Create a zero in position $(3,1)$:
  $$\left( \begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & -1 & 1 & -1 & 0 & 1 \end{array} \right)$$

* **Step 2 ($R_3 \leftarrow R_3 + R_2$):** Create a zero in position $(3,2)$:
  $$\left( \begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & 0 & 2 & -1 & 1 & 1 \end{array} \right)$$

* **Step 3 ($R_3 \leftarrow \frac{1}{2} R_3$):** Scale row $3$ so the third pivot becomes $1$:
  $$\left( \begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array} \right)$$

* **Step 4 ($R_2 \leftarrow R_2 - R_3$):** Eliminate the entry above the third pivot in row $2$:
  $$\left( \begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array} \right)$$

* **Step 5 ($R_1 \leftarrow R_1 - R_2$):** Eliminate the entry above the second pivot in row $1$:
  $$\left( \begin{array}{ccc|ccc} 1 & 0 & 0 & \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\ 0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array} \right)$$

Thus, the inverse matrix is:
$$A^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1 \end{pmatrix}$$

### Verification
We check the result by computing the product $A A^{-1}$:
$$A A^{-1} = \frac{1}{2} \begin{pmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \\ 1 & 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1 \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 1 + 1 + 0 & -1 + 1 + 0 & 1 - 1 + 0 \\ 0 + 1 - 1 & 0 + 1 + 1 & 0 - 1 + 1 \\ 1 + 0 - 1 & -1 + 0 + 1 & 1 + 0 + 1 \end{pmatrix}$$
$$A A^{-1} = \frac{1}{2} \begin{pmatrix} 2 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} = I_3$$
Since $A A^{-1} = I_3$, the inverse is verified.