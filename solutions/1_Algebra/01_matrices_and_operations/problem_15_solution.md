# Exercise 15. Associativity of Multiplication and Different Calculation Paths

## Question
Given the matrices:
$$A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}, \quad B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}, \quad C = \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix}$$
we need to compute $(AB)C$ and $A(BC)$, compare both the final results and the number of intermediate arithmetic operations, and explain what associativity of matrix multiplication means in this example.

## Solution

### 1. Path 1: Computing $(AB)C$
Here, $A$ is $2 \times 3$, $B$ is $3 \times 2$, and $C$ is $2 \times 2$.
* **Step 1 (Compute $AB$, size $2 \times 2$):**
  $$AB = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix} = \begin{pmatrix} 1(1) + 2(2) + 0(-1) & 1(0) + 2(1) + 0(3) \\ 0(1) + 1(2) + 1(-1) & 0(0) + 1(1) + 1(3) \end{pmatrix} = \begin{pmatrix} 5 & 2 \\ 1 & 4 \end{pmatrix}$$
  *Intermediate operations:* $AB$ has $2 \times 2 = 4$ entries, and each entry requires $3$ scalar multiplications and $2$ additions, giving **$12$ multiplications and $8$ additions** ($20$ operations).

* **Step 2 (Compute $(AB)C$, size $2 \times 2$):**
  $$(AB)C = \begin{pmatrix} 5 & 2 \\ 1 & 4 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix} = \begin{pmatrix} 5(2) + 2(0) & 5(1) + 2(-1) \\ 1(2) + 4(0) & 1(1) + 4(-1) \end{pmatrix} = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}$$
  *Intermediate operations:* $(AB)C$ has $2 \times 2 = 4$ entries, and each entry requires $2$ scalar multiplications and $1$ addition, giving **$8$ multiplications and $4$ additions** ($12$ operations).

* **Total for $(AB)C$:** $12 + 8 = \mathbf{20}$ scalar multiplications and $8 + 4 = \mathbf{12}$ additions (**$32$** total operations).

### 2. Path 2: Computing $A(BC)$
* **Step 1 (Compute $BC$, size $3 \times 2$):**
  $$BC = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix} = \begin{pmatrix} 1(2) + 0(0) & 1(1) + 0(-1) \\ 2(2) + 1(0) & 2(1) + 1(-1) \\ -1(2) + 3(0) & -1(1) + 3(-1) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 4 & 1 \\ -2 & -4 \end{pmatrix}$$
  *Intermediate operations:* $BC$ has $3 \times 2 = 6$ entries, and each entry requires $2$ scalar multiplications and $1$ addition, giving **$12$ multiplications and $6$ additions** ($18$ operations).

* **Step 2 (Compute $A(BC)$, size $2 \times 2$):**
  $$A(BC) = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 4 & 1 \\ -2 & -4 \end{pmatrix} = \begin{pmatrix} 1(2) + 2(4) + 0(-2) & 1(1) + 2(1) + 0(-4) \\ 0(2) + 1(4) + 1(-2) & 0(1) + 1(1) + 1(-4) \end{pmatrix} = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}$$
  *Intermediate operations:* $A(BC)$ has $2 \times 2 = 4$ entries, and each entry requires $3$ scalar multiplications and $2$ additions, giving **$12$ multiplications and $8$ additions** ($20$ operations).

* **Total for $A(BC)$:** $12 + 12 = \mathbf{24}$ scalar multiplications and $6 + 8 = \mathbf{14}$ additions (**$38$** total operations).

### 3. Comparison and Meaning of Associativity
* **Comparison:** Both grouping paths yield the exact same $2 \times 2$ result matrix $\begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}$. However, computing $(AB)C$ requires fewer operations ($20$ multiplications and $12$ additions, or $32$ total operations) than computing $A(BC)$ ($24$ multiplications and $14$ additions, or $38$ total operations), because forming $AB$ first compresses the $3$-dimensional intermediate dimension into a smaller $2 \times 2$ matrix before multiplying by $C$.
* **Meaning of Associativity:** Associativity of matrix multiplication states that $(AB)C = A(BC)$ whenever the dimensions are compatible, meaning that while the **left-to-right order** of the matrices cannot be changed, the **parenthesization (grouping)** of intermediate products does not affect the final matrix—allowing us to choose the grouping that minimizes computational work.

### Verification
We verify the final product matrix by applying the three transformations $A$, $B$, and $C$ sequentially to the standard basis vector $e_1 = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$:
$$Ce_1 = \begin{pmatrix} 2 \\ 0 \end{pmatrix} \implies B(Ce_1) = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix} \begin{pmatrix} 2 \\ 0 \end{pmatrix} = \begin{pmatrix} 2 \\ 4 \\ -2 \end{pmatrix} \implies A(B(Ce_1)) = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 2 \\ 4 \\ -2 \end{pmatrix} = \begin{pmatrix} 2 + 8 + 0 \\ 0 + 4 - 2 \end{pmatrix} = \begin{pmatrix} 10 \\ 2 \end{pmatrix}$$
This matches the first column of $\begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}$, confirming our result.