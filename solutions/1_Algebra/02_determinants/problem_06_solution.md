# Exercise 6. Parameter and Invertibility

## Question
For the parameter-dependent matrix:
$$A(t) = \begin{pmatrix} t & 1 \\ 2 & t \end{pmatrix}$$

We need to find all values of $t$ for which the matrix is not invertible, and explain how our answer is related to the determinant being zero.

## Solution

### 1. Computing the Determinant and Finding Noninvertible Values
We compute the determinant of the $2 \times 2$ matrix $A(t)$ in terms of the parameter $t$:
$$\det A(t) = (t)(t) - (1)(2) = t^2 - 2$$

A square matrix is noninvertible (singular) if and only if its determinant equals zero. Setting $\det A(t) = 0$ gives:
$$t^2 - 2 = 0 \implies t^2 = 2 \implies t = \sqrt{2} \quad \text{or} \quad t = -\sqrt{2}$$

Thus, $A(t)$ is not invertible for **$t = \sqrt{2}$** and **$t = -\sqrt{2}$**.

### 2. Relation to the Determinant Being Zero
For a $2 \times 2$ matrix, the explicit inverse formula is $A(t)^{-1} = \frac{1}{\det A(t)} \begin{pmatrix} t & -1 \\ -2 & t \end{pmatrix}$, which requires dividing by $\det A(t)$. When $t = \pm\sqrt{2}$, we have $\det A(t) = 0$, making division by zero impossible. Equivalently, $\det A(t) = 0$ means the two rows become scalar multiples of one another ($R_1 = \frac{t}{2} R_2$, since $\frac{t}{2} = \frac{1}{t}$ holds precisely when $t^2 = 2$), so the matrix collapses $2\text{D}$ space onto a line and cannot be inverted.

### Verification
We substitute both values back into $A(t)$ and evaluate the determinant directly:
* For $t = \sqrt{2}$: $\det A(\sqrt{2}) = \det \begin{pmatrix} \sqrt{2} & 1 \\ 2 & \sqrt{2} \end{pmatrix} = (\sqrt{2})^2 - 2 = 2 - 2 = 0$.
* For $t = -\sqrt{2}$: $\det A(-\sqrt{2}) = \det \begin{pmatrix} -\sqrt{2} & 1 \\ 2 & -\sqrt{2} \end{pmatrix} = (-\sqrt{2})^2 - 2 = 2 - 2 = 0$.
  Both values yield a zero determinant, confirming the solution.