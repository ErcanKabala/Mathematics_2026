# Exercise 13. A Recurrence Written in Matrix Form

## Question
Let:
$$F = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix}$$
We need to compute $F^2$, $F^3$, $F^4$, and $F^5$, compare the entries obtained with the sequence $0, 1, 1, 2, 3, 5, 8, \dots$, and describe the observed relationship. Then, we must compute $F \begin{pmatrix} a \\ b \end{pmatrix}$ and explain how this multiplication performs one recurrence step.

## Solution

### 1. Computing $F^2$, $F^3$, $F^4$, and $F^5$
Multiplying successively by $F$ gives:
* **Computing $F^2$:**
  $$F^2 = F \cdot F = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 1(1) + 1(1) & 1(1) + 1(0) \\ 1(1) + 0(1) & 1(1) + 0(0) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}$$

* **Computing $F^3$:**
  $$F^3 = F^2 \cdot F = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 2(1) + 1(1) & 2(1) + 1(0) \\ 1(1) + 1(1) & 1(1) + 1(0) \end{pmatrix} = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix}$$

* **Computing $F^4$:**
  $$F^4 = F^3 \cdot F = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 3(1) + 2(1) & 3(1) + 2(0) \\ 2(1) + 1(1) & 2(1) + 1(0) \end{pmatrix} = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix}$$

* **Computing $F^5$:**
  $$F^5 = F^4 \cdot F = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 5(1) + 3(1) & 5(1) + 3(0) \\ 3(1) + 2(1) & 3(1) + 2(0) \end{pmatrix} = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix}$$

### 2. Relationship with the Sequence $0, 1, 1, 2, 3, 5, 8, \dots$
Denoting the terms of the Fibonacci sequence by $f_0 = 0, f_1 = 1, f_2 = 1, f_3 = 2, f_4 = 3, f_5 = 5, f_6 = 8, \dots$ (where $f_{n+1} = f_n + f_{n-1}$), every entry in $F^n$ is a consecutive Fibonacci number following the exact pattern:
$$F^n = \begin{pmatrix} f_{n+1} & f_n \\ f_n & f_{n-1} \end{pmatrix}$$
Specifically:
* In $F^1 = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix}$, the entries are $f_2 = 1$, $f_1 = 1$, and $f_0 = 0$.
* In $F^2 = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}$, the entries are $f_3 = 2$, $f_2 = 1$, and $f_1 = 1$.
* In $F^3 = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix}$, the entries are $f_4 = 3$, $f_3 = 2$, and $f_2 = 1$.
* In $F^4 = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix}$, the entries are $f_5 = 5$, $f_4 = 3$, and $f_3 = 2$.
* In $F^5 = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix}$, the entries are $f_6 = 8$, $f_5 = 5$, and $f_4 = 3$.

### 3. Computing $F \begin{pmatrix} a \\ b \end{pmatrix}$ and Explaining the Recurrence Step
Multiplying $F$ by a general column vector $\begin{pmatrix} a \\ b \end{pmatrix}$ gives:
$$F \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 1(a) + 1(b) \\ 1(a) + 0(b) \end{pmatrix} = \begin{pmatrix} a + b \\ a \end{pmatrix}$$

**Explanation:** Suppose the input vector $\begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} f_n \\ f_{n-1} \end{pmatrix}$ stores two consecutive terms of the sequence, with $a$ as the current term and $b$ as the previous term. The first row $\begin{pmatrix} 1 & 1 \end{pmatrix}$ of $F$ sums both entries to compute $a + b = f_n + f_{n-1} = f_{n+1}$ (creating the next term in the sequence), while the second row $\begin{pmatrix} 1 & 0 \end{pmatrix}$ selects $a = f_n$ and places it in the lower position (keeping the more recent term so that $\begin{pmatrix} f_{n+1} \\ f_n \end{pmatrix}$ is ready for the next step).

### Verification
Starting with the initial vector $v_1 = \begin{pmatrix} f_1 \\ f_0 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$ and applying $F^5$ directly gives:
$$F^5 \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 8 \\ 5 \end{pmatrix} = \begin{pmatrix} f_6 \\ f_5 \end{pmatrix}$$
Additionally, $\det(F^5) = 8(3) - 5(5) = 24 - 25 = -1$, which matches $(\det F)^5 = (-1)^5 = -1$, confirming our powers of $F$.