# Exercise 8. Row Operations and Their Reversibility

## Question
For the given matrix:
$$A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix}$$

We need to perform the following elementary row operations in order:
1. $R_2 \leftarrow R_2 - 2R_1$,
2. $R_3 \leftarrow R_3 + R_1$,
3. Interchange $R_2$ and $R_3$.

We must write the resulting matrix after each step, and then state an elementary row operation that reverses each of the three operations.

## Solution

### 1. Performing the Row Operations Step-by-Step
We apply each row operation sequentially to the matrix obtained from the preceding step.

* **Step 1 ($R_2 \leftarrow R_2 - 2R_1$):** We subtract $2$ times the first row $2R_1 = \begin{pmatrix} 2 & 4 & -2 \end{pmatrix}$ from the second row $R_2 = \begin{pmatrix} 2 & 4 & 1 \end{pmatrix}$, giving the new second row $\begin{pmatrix} 2 - 2 & 4 - 4 & 1 - (-2) \end{pmatrix} = \begin{pmatrix} 0 & 0 & 3 \end{pmatrix}$:
  $$A_1 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix}$$

* **Step 2 ($R_3 \leftarrow R_3 + R_1$):** Using $A_1$, we add the first row $R_1 = \begin{pmatrix} 1 & 2 & -1 \end{pmatrix}$ to the third row $R_3 = \begin{pmatrix} -1 & 1 & 3 \end{pmatrix}$, yielding the new third row $\begin{pmatrix} -1 + 1 & 1 + 2 & 3 + (-1) \end{pmatrix} = \begin{pmatrix} 0 & 3 & 2 \end{pmatrix}$:
  $$A_2 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix}$$

* **Step 3 (Interchange $R_2$ and $R_3$, denoted $R_2 \leftrightarrow R_3$):** Using $A_2$, we swap the positions of the second and third rows:
  $$A_3 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 2 \\ 0 & 0 & 3 \end{pmatrix}$$

### 2. Reversing Each Operation
Every elementary row operation has a unique inverse operation of the same type that undoes its effect:
1. To reverse **$R_2 \leftarrow R_2 - 2R_1$**, we add $2$ times row $1$ back to row $2$: **$R_2 \leftarrow R_2 + 2R_1$**.
2. To reverse **$R_3 \leftarrow R_3 + R_1$**, we subtract row $1$ from row $3$: **$R_3 \leftarrow R_3 - R_1$**.
3. To reverse **interchanging $R_2$ and $R_3$ ($R_2 \leftrightarrow R_3$)**, we swap the same two rows again: **interchange $R_2$ and $R_3$ ($R_2 \leftrightarrow R_3$)**.

### Verification
We verify both our forward steps and our inverse operations by applying the reverse operations in reverse order (Step 3, then Step 2, then Step 1) to the final matrix $A_3$:
1. Apply $R_2 \leftrightarrow R_3$ to $A_3$:
   $$\begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix} = A_2$$
2. Apply $R_3 \leftarrow R_3 - R_1$ to $A_2$ (row $3$ becomes $\begin{pmatrix} 0 - 1 & 3 - 2 & 2 - (-1) \end{pmatrix} = \begin{pmatrix} -1 & 1 & 3 \end{pmatrix}$):
   $$\begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix} = A_1$$
3. Apply $R_2 \leftarrow R_2 + 2R_1$ to $A_1$ (row $2$ becomes $\begin{pmatrix} 0 + 2 & 0 + 4 & 3 + (-2) \end{pmatrix} = \begin{pmatrix} 2 & 4 & 1 \end{pmatrix}$):
   $$\begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix} = A$$

Since we recover the exact original matrix $A$, both the step-by-step matrices and the inverse operations are verified.