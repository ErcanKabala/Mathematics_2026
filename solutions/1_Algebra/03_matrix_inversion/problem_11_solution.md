# Exercise 11. Parameter and Invertibility

## Question
For the parameter-dependent $2 \times 2$ matrix:
$$A(t) = \begin{pmatrix} 1 & t \\ t & 1 \end{pmatrix}$$
we need to:
1. Find all values of $t$ for which the matrix $A(t)$ is invertible.
2. Give an explicit formula for $A(t)^{-1}$.
3. Explain what happens to this formula at the excluded values of $t$.

## Solution

### 1. Values of $t$ for Which $A(t)$ Is Invertible
A square matrix is invertible if and only if its determinant is non-zero ($\det A(t) \neq 0$). Computing the determinant of $A(t)$ gives:
$$\det A(t) = (1)(1) - (t)(t) = 1 - t^2$$

Setting $\det A(t) \neq 0$:
$$1 - t^2 \neq 0 \implies t^2 \neq 1 \implies t \neq 1 \quad \text{and} \quad t \neq -1$$

Thus, $A(t)$ is invertible for **all real numbers $t$ except $t = 1$ and $t = -1$** (i.e., $t \in \mathbb{R} \setminus \{-1, 1\}$).

### 2. Formula for $A(t)^{-1}$
For any $t \neq \pm 1$, we apply the $2 \times 2$ inverse formula $A(t)^{-1} = \frac{1}{\det A(t)} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$:
$$A(t)^{-1} = \frac{1}{1 - t^2} \begin{pmatrix} 1 & -t \\ -t & 1 \end{pmatrix} = \begin{pmatrix} \frac{1}{1 - t^2} & -\frac{t}{1 - t^2} \\ -\frac{t}{1 - t^2} & \frac{1}{1 - t^2} \end{pmatrix}$$

### 3. What Happens at the Excluded Values ($t = 1$ and $t = -1$)
At the excluded values $t = 1$ and $t = -1$, the determinant expression $1 - t^2$ in the denominator equals **$0$**, so the formula for $A(t)^{-1}$ involves **division by zero and is completely undefined**. Geometrically and structurally, at these exact parameter values the rows of $A(t)$ become linearly dependent:
* At $t = 1$: $A(1) = \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}$, where $R_1 = R_2$.
* At $t = -1$: $A(-1) = \begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}$, where $R_1 = -R_2$.
  In both cases, $A(t)$ collapses $\mathbb{R}^2$ onto a $1$-dimensional line, so no inverse transformation can exist.

### Verification
We verify our inverse formula for any $t \neq \pm 1$ by computing the product $A(t) A(t)^{-1}$:
$$A(t) A(t)^{-1} = \frac{1}{1 - t^2} \begin{pmatrix} 1 & t \\ t & 1 \end{pmatrix} \begin{pmatrix} 1 & -t \\ -t & 1 \end{pmatrix} = \frac{1}{1 - t^2} \begin{pmatrix} 1(1) + t(-t) & 1(-t) + t(1) \\ t(1) + 1(-t) & t(-t) + 1(1) \end{pmatrix}$$
$$A(t) A(t)^{-1} = \frac{1}{1 - t^2} \begin{pmatrix} 1 - t^2 & 0 \\ 0 & 1 - t^2 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$$
Since the product simplifies to $I_2$, the formula is confirmed.