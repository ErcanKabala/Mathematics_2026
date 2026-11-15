# Exercise 1. Determinant of a 2x2 Matrix

## Question
We are asked to compute the determinants of the following two $2 \times 2$ matrices:
$$\det \begin{pmatrix} 3 & -2 \\ 5 & 4 \end{pmatrix}, \quad \det \begin{pmatrix} 1 & 7 \\ 2 & 14 \end{pmatrix}$$

After computing both values, we need to determine which matrix is invertible and justify our answer.

## Solution

### 1. Computing the Determinants
For a general $2 \times 2$ matrix $M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$, the determinant is given by the formula $\det M = ad - bc$.

* **First Matrix:** Applying the formula yields:
  $$\det \begin{pmatrix} 3 & -2 \\ 5 & 4 \end{pmatrix} = (3)(4) - (-2)(5) = 12 - (-10) = 12 + 10 = 22$$

* **Second Matrix:** Applying the same formula yields:
  $$\det \begin{pmatrix} 1 & 7 \\ 2 & 14 \end{pmatrix} = (1)(14) - (7)(2) = 14 - 14 = 0$$

### 2. Invertibility and Justification
A square matrix is invertible if and only if its determinant is non-zero ($\det M \neq 0$).
* The **first matrix $\begin{pmatrix} 3 & -2 \\ 5 & 4 \end{pmatrix}$ is invertible** because its determinant is $22 \neq 0$.
* The **second matrix $\begin{pmatrix} 1 & 7 \\ 2 & 14 \end{pmatrix}$ is not invertible** (it is singular) because its determinant equals $0$.

### Verification
We can verify both conclusions independently:
* For the first matrix, its explicit inverse is $M_1^{-1} = \frac{1}{22}\begin{pmatrix} 4 & 2 \\ -5 & 3 \end{pmatrix}$, and multiplying gives:
  $$\begin{pmatrix} 3 & -2 \\ 5 & 4 \end{pmatrix} \frac{1}{22}\begin{pmatrix} 4 & 2 \\ -5 & 3 \end{pmatrix} = \frac{1}{22}\begin{pmatrix} 12 + 10 & 6 - 6 \\ 20 - 20 & 10 + 12 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I$$
* For the second matrix, the second row is twice the first row ($R_2 = 2R_1$), confirming linear dependence of the rows and a determinant of $0$.