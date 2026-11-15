# Exercise 10. Inverse of a Diagonal Matrix

## Question
Given the two diagonal matrices:
$$D = \begin{pmatrix} 2 & 0 & 0 \\ 0 & -3 & 0 \\ 0 & 0 & 5 \end{pmatrix}, \quad E = \begin{pmatrix} 2 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 5 \end{pmatrix}$$
we must decide, without using Gauss–Jordan elimination, which matrix is invertible. For the invertible matrix, we need to state its inverse and verify the result by multiplication.

## Solution

### 1. Deciding Invertibility
The determinant of a diagonal matrix is the product of its main diagonal entries. Therefore, a diagonal matrix is invertible if and only if **every entry on its main diagonal is non-zero**.
* **Matrix $D$:** Its main diagonal entries are $2$, $-3$, and $5$, all of which are non-zero ($\det D = 2 \cdot (-3) \cdot 5 = -30 \neq 0$). Thus, **$D$ is invertible**.
* **Matrix $E$:** Its second diagonal entry is $0$ ($\det E = 2 \cdot 0 \cdot 5 = 0$, and the entire second row consists of zeros). Thus, **$E$ is not invertible**.

### 2. Finding $D^{-1}$
The inverse of an invertible diagonal matrix is simply the diagonal matrix formed by taking the reciprocals of its main diagonal entries:
$$D^{-1} = \begin{pmatrix} \frac{1}{2} & 0 & 0 \\ 0 & -\frac{1}{3} & 0 \\ 0 & 0 & \frac{1}{5} \end{pmatrix}$$

### Verification
We verify $D^{-1}$ by computing the product $D D^{-1}$:
$$D D^{-1} = \begin{pmatrix} 2 & 0 & 0 \\ 0 & -3 & 0 \\ 0 & 0 & 5 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 & 0 \\ 0 & -\frac{1}{3} & 0 \\ 0 & 0 & \frac{1}{5} \end{pmatrix} = \begin{pmatrix} 2\left(\frac{1}{2}\right) & 0 & 0 \\ 0 & (-3)\left(-\frac{1}{3}\right) & 0 \\ 0 & 0 & 5\left(\frac{1}{5}\right) \end{pmatrix} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} = I_3$$
Since $D D^{-1} = D^{-1} D = I_3$, the inverse is verified.