# Exercise 11. When Do Matrices Commute?

## Question
Given the $2 \times 2$ matrices:
$$A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$$
we need to find the conditions on $a, b, c, d$ under which $AB = BA$, and describe the general form of all such matrices $B$.

## Solution

### 1. Computing $AB$ and $BA$
We compute both products in terms of the unknown entries $a, b, c, d$:

* **Product $AB$:**
  $$AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} a & b \\ c & d \end{pmatrix} = \begin{pmatrix} 1(a) + 1(c) & 1(b) + 1(d) \\ 0(a) + 1(c) & 0(b) + 1(d) \end{pmatrix} = \begin{pmatrix} a + c & b + d \\ c & d \end{pmatrix}$$

* **Product $BA$:**
  $$BA = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} a(1) + b(0) & a(1) + b(1) \\ c(1) + d(0) & c(1) + d(1) \end{pmatrix} = \begin{pmatrix} a & a + b \\ c & c + d \end{pmatrix}$$

### 2. Finding the Commutativity Conditions
For $AB = BA$ to hold, every corresponding entry of the two matrices must be equal:
$$\begin{pmatrix} a + c & b + d \\ c & d \end{pmatrix} = \begin{pmatrix} a & a + b \\ c & c + d \end{pmatrix}$$

Equating the entries position by position gives:
* $(1,1)$-entry: $a + c = a \implies c = 0$
* $(1,2)$-entry: $b + d = a + b \implies d = a$
* $(2,1)$-entry: $c = c$ (always satisfied)
* $(2,2)$-entry: $d = c + d \implies c = 0$

Thus, $AB = BA$ if and only if **$c = 0$** and **$a = d$**, with no restriction on $b$.

### 3. General Form of All Matrices $B$
Substituting $c = 0$ and $d = a$ into $B$ shows that every matrix commuting with $A$ has the upper triangular form:
$$B = \begin{pmatrix} a & b \\ 0 & a \end{pmatrix} = a \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} + b \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = aI_2 + bN$$
where $a, b \in \mathbb{R}$ are arbitrary real numbers and $N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$.

### Verification
We verify the general form with a concrete choice of parameters, say $a = d = 3$, $b = -2$, and $c = 0$, so $B = \begin{pmatrix} 3 & -2 \\ 0 & 3 \end{pmatrix}$:
* $AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & -2 \\ 0 & 3 \end{pmatrix} = \begin{pmatrix} 3 + 0 & -2 + 3 \\ 0 + 0 & 0 + 3 \end{pmatrix} = \begin{pmatrix} 3 & 1 \\ 0 & 3 \end{pmatrix}$
* $BA = \begin{pmatrix} 3 & -2 \\ 0 & 3 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 3 + 0 & 3 - 2 \\ 0 + 0 & 0 + 3 \end{pmatrix} = \begin{pmatrix} 3 & 1 \\ 0 & 3 \end{pmatrix}$
  Since $AB = BA$, the conditions and general form are verified.