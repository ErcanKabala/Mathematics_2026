# Exercise 12. Formula for a Matrix Power

## Question
Let:
$$A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$$
We need to compute $A^2$, $A^3$, and $A^4$, use them to formulate a conjecture for $A^n$, and then prove the formula by induction: assume the formula holds for $n$, multiply by $A$, and explain why we obtain the exact formula for $n + 1$.

## Solution

### 1. Computing $A^2$, $A^3$, and $A^4$
We compute each successive power by multiplying the previous power by $A$:
* **Computing $A^2$:**
  $$A^2 = A \cdot A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 1(0) & 1(1) + 1(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}$$

* **Computing $A^3$:**
  $$A^3 = A^2 \cdot A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 2(0) & 1(1) + 2(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix}$$

* **Computing $A^4$:**
  $$A^4 = A^3 \cdot A = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 3(0) & 1(1) + 3(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 4 \\ 0 & 1 \end{pmatrix}$$

### 2. Conjecture for $A^n$
Observing $A^1 = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$, $A^2 = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}$, $A^3 = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix}$, and $A^4 = \begin{pmatrix} 1 & 4 \\ 0 & 1 \end{pmatrix}$, we formulate the conjecture that for every positive integer $n \ge 1$:
$$A^n = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}$$

### 3. Inductive Step from $n$ to $n + 1$
Assume that the formula holds for a fixed integer $n \ge 1$, meaning $A^n = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}$. To obtain $A^{n+1}$, we multiply $A^n$ on the right by $A$:
$$A^{n+1} = A^n \cdot A = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + n(0) & 1(1) + n(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & n + 1 \\ 0 & 1 \end{pmatrix}$$

**Explanation:** When multiplying $A^n$ by $A$, the diagonal entries remain $1(1) + n(0) = 1$ and $0(1) + 1(1) = 1$, and the bottom-left entry remains $0(1) + 1(0) = 0$. In the top-right position, the dot product of the first row $\begin{pmatrix} 1 & n \end{pmatrix}$ of $A^n$ with the second column $\begin{pmatrix} 1 \\ 1 \end{pmatrix}$ of $A$ evaluates to $1 \cdot 1 + n \cdot 1 = n + 1$. Thus, multiplying by $A$ increments the upper-right entry by $1$, producing the exact formula for $n + 1$. Since the base case $n = 1$ holds, the formula is proven for all positive integers $n$.

### Verification
We can verify $A^4$ using the associative property $A^4 = A^2 \cdot A^2$:
$$A^2 \cdot A^2 = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 + 0 & 2 + 2 \\ 0 + 0 & 0 + 1 \end{pmatrix} = \begin{pmatrix} 1 & 4 \\ 0 & 1 \end{pmatrix}$$
This matches both our sequential multiplication and the general formula for $n = 4$.