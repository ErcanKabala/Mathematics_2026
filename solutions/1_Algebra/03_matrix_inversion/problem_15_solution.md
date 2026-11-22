# Exercise 15. Two Methods for Solving the Same System

## Question
For the matrix $A$ and right-hand side vector $b$:
$$A = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}, \quad b = \begin{pmatrix} 7 \\ 8 \end{pmatrix}$$
we need to solve the linear system $Ax = b$ in two different ways:
1. Using $x = A^{-1}b$.
2. Using Gaussian elimination.

Then, we must compare both solutions, compare the number of essential steps, and state which method was simpler in this example.

## Solution

### 1. Method 1: Solving via $x = A^{-1}b$
* **Step 1 (Compute $\det A$):**
$$\det A = (2)(3) - (1)(1) = 6 - 1 = 5 \neq 0$$
* **Step 2 (Compute $A^{-1}$):** Using the $2 \times 2$ inverse formula $A^{-1} = \frac{1}{\det A}\begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$:
$$A^{-1} = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix}$$
* **Step 3 (Compute $x = A^{-1}b$):**
$$x = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 7 \\ 8 \end{pmatrix} = \frac{1}{5} \begin{pmatrix} 3(7) + (-1)(8) \\ (-1)(7) + 2(8) \end{pmatrix} = \frac{1}{5} \begin{pmatrix} 21 - 8 \\ -7 + 16 \end{pmatrix} = \frac{1}{5} \begin{pmatrix} 13 \\ 9 \end{pmatrix} = \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix}$$

### 2. Method 2: Solving via Gaussian Elimination
* **Step 1 (Form augmented matrix and swap rows to get a unit pivot):**
$$\left( \begin{array}{cc|c} 2 & 1 & 7 \\ 1 & 3 & 8 \end{array} \right) \xrightarrow{R_1 \leftrightarrow R_2} \left( \begin{array}{cc|c} 1 & 3 & 8 \\ 2 & 1 & 7 \end{array} \right)$$
* **Step 2 (Eliminate below the pivot via $R_2 \leftarrow R_2 - 2R_1$):**
$$\left( \begin{array}{cc|c} 1 & 3 & 8 \\ 0 & -5 & -9 \end{array} \right)$$
* **Step 3 (Back-substitution):**
  * From the second row: $-5x_2 = -9 \implies x_2 = \frac{9}{5}$.
  * From the first row: $x_1 + 3\left(\frac{9}{5}\right) = 8 \implies x_1 = \frac{40}{5} - \frac{27}{5} = \frac{13}{5}$.

Thus, Gaussian elimination gives:
$$x = \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix}$$

### 3. Comparison of Solutions, Essential Steps, and Simplicity
* **Comparison of Solutions:** Both methods produce the exact same unique solution $x = \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix}$ (or $(2.6, \, 1.8)$).
* **Number of Essential Steps:** Both methods require roughly $3$ essential steps here: Method 1 requires computing $\det A$, forming $A^{-1}$, and multiplying $A^{-1}b$; Method 2 requires forming the augmented matrix, performing one elimination step ($R_2 \leftarrow R_2 - 2R_1$), and performing back-substitution.
* **Which Method Was Simpler:** In this single-system example, **Gaussian elimination** was slightly simpler and more direct because it avoids computing a determinant and constructing a full inverse matrix when we only need to solve for a single right-hand side vector $b$ (the inverse method $A^{-1}b$ only becomes more efficient when solving multiple systems $Ax = b_i$ that share the same matrix $A$).

### Verification
We substitute $x = \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix}$ back into the original matrix equation $Ax = b$:
$$Ax = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix} \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 2\left(\frac{13}{5}\right) + 1\left(\frac{9}{5}\right) \\ 1\left(\frac{13}{5}\right) + 3\left(\frac{9}{5}\right) \end{pmatrix} = \begin{pmatrix} \frac{26 + 9}{5} \\ \frac{13 + 27}{5} \end{pmatrix} = \begin{pmatrix} \frac{35}{5} \\ \frac{40}{5} \end{pmatrix} = \begin{pmatrix} 7 \\ 8 \end{pmatrix} = b$$
Both equations hold identically, verifying the solution.