# Exercise 3. When Does the Inverse Not Exist?

## Question
For the matrix:
$$A = \begin{pmatrix} 2 & 4 \\ 1 & 2 \end{pmatrix}$$
we must explain in two different ways why $A^{-1}$ does not exist: first using the determinant, and second using dependence between the rows.

## Solution

### 1. Explanation Using the Determinant
A square matrix $A$ is invertible if and only if its determinant is non-zero ($\det A \neq 0$). Computing the determinant of $A$ gives:
$$\det A = (2)(2) - (4)(1) = 4 - 4 = 0$$
Because $\det A = 0$, the matrix is singular and $A^{-1}$ does not exist (in the $2 \times 2$ inverse formula, this would require dividing by $\det A = 0$, which is undefined).

### 2. Explanation Using Row Dependence
Inspecting the two rows of $A$, $R_1 = \begin{pmatrix} 2 & 4 \end{pmatrix}$ and $R_2 = \begin{pmatrix} 1 & 2 \end{pmatrix}$, we observe that the first row is an exact scalar multiple of the second row:
$$R_1 = 2R_2$$
Thus, the rows of $A$ are linearly dependent. If we attempt to find $A^{-1}$ via Gauss–Jordan elimination on $[A \mid I_2]$, applying the row operation $R_1 \leftarrow R_1 - 2R_2$ turns the entire first row on the left side into zeros:
$$\left( \begin{array}{cc\|cc} 2 & 4 & 1 & 0 \\ 1 & 2 & 0 & 1 \end{array} \right) \xrightarrow{R_1 \leftarrow R_1 - 2R_2} \left( \begin{array}{cc\|cc} 0 & 0 & 1 & -2 \\ 1 & 2 & 0 & 1 \end{array} \right)$$
Because a row of zeros appears on the left, it is impossible to reduce $A$ to the identity matrix $I_2$, proving that $A^{-1}$ does not exist.

### Verification
We can verify noninvertibility by showing that the homogeneous system $Ax = 0$ has a non-zero solution, such as $x = \begin{pmatrix} 2 \\ -1 \end{pmatrix}$:
$$Ax = \begin{pmatrix} 2 & 4 \\ 1 & 2 \end{pmatrix} \begin{pmatrix} 2 \\ -1 \end{pmatrix} = \begin{pmatrix} 4 - 4 \\ 2 - 2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}$$
If $A^{-1}$ existed, multiplying both sides by $A^{-1}$ would force $x = A^{-1}0 = \begin{pmatrix} 0 \\ 0 \end{pmatrix}$, contradicting $x \neq 0$.