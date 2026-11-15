# Exercise 4. Gauss–Jordan

## Question
We need to find $A^{-1}$ using the Gauss–Jordan elimination method for the matrix:
$$A = \begin{pmatrix} 1 & 2 \\ 3 & 5 \end{pmatrix}$$
We must show the augmented matrix $[A \mid I]$ after each successive elementary row operation and explain why obtaining $I$ on the left side yields $A^{-1}$ on the right side.

## Solution

### 1. Gauss–Jordan Row Operations on $[A \mid I]$
We form the augmented matrix $[A \mid I_2]$ and apply elementary row operations to transform the left block into the identity matrix $I_2$:

* **Initial augmented matrix:**
  $$\left( \begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 3 & 5 & 0 & 1 \end{array} \right)$$

* **Step 1 ($R_2 \leftarrow R_2 - 3R_1$):** Eliminate the entry below the top-left pivot:
  $$\left( \begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & -1 & -3 & 1 \end{array} \right)$$

* **Step 2 ($R_2 \leftarrow -R_2$):** Scale row $2$ so the second pivot equals $1$:
  $$\left( \begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & 1 & 3 & -1 \end{array} \right)$$

* **Step 3 ($R_1 \leftarrow R_1 - 2R_2$):** Eliminate the entry above the second pivot:
  $$\left( \begin{array}{cc|cc} 1 & 0 & -5 & 2 \\ 0 & 1 & 3 & -1 \end{array} \right)$$

Reading off the right-hand block gives:
$$A^{-1} = \begin{pmatrix} -5 & 2 \\ 3 & -1 \end{pmatrix}$$

### 2. Why Obtaining $I$ on the Left Gives $A^{-1}$ on the Right
Each elementary row operation is equivalent to multiplying the augmented matrix on the left by an invertible elementary matrix $E_k$. If a sequence of row operations $E_1, E_2, \dots, E_m$ transforms $A$ into $I$, then:
$$(E_m \cdots E_2 E_1) A = I$$
By the definition of the inverse, the combined product of these elementary matrices must equal $A^{-1}$ (that is, $E_m \cdots E_2 E_1 = A^{-1}$). Because we perform the exact same row operations simultaneously on the identity matrix $I$ on the right side, the right block becomes:
$$(E_m \cdots E_2 E_1) I = A^{-1} I = A^{-1}$$

### Verification
We verify our result by multiplying $A$ by $A^{-1}$:
$$A A^{-1} = \begin{pmatrix} 1 & 2 \\ 3 & 5 \end{pmatrix} \begin{pmatrix} -5 & 2 \\ 3 & -1 \end{pmatrix} = \begin{pmatrix} 1(-5) + 2(3) & 1(2) + 2(-1) \\ 3(-5) + 5(3) & 3(2) + 5(-1) \end{pmatrix} = \begin{pmatrix} -5 + 6 & 2 - 2 \\ -15 + 15 & 6 - 5 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$$
This confirms that $A^{-1}$ is correct.