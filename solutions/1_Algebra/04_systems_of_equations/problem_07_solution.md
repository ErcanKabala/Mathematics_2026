# Exercise 7. Choosing a Method Deliberately

## Question
We are given three different linear system scenarios:
1. One system with a triangular coefficient matrix:
$$\begin{cases} 2x - y = 3, \\ 4y = 8; \end{cases}$$
2. Three systems $Ax = b_i$ ($i = 1, 2, 3$) with the same invertible matrix $A$, when $A^{-1}$ is already known;
3. One $3 \times 3$ system for which the inverse matrix is not given and the goal is only to find one solution vector.

We must choose the method that best uses the structure of each situation and justify our choice based on the number of right-hand sides and the matrix structure. For case 1, we must carry out the chosen method completely. For cases 2 and 3, we must describe the plan and indicate which part of the computation would be reusable or unnecessary.

## Solution

### 1. Case 1: Triangular Coefficient Matrix
* **Chosen Method:** Direct **back-substitution** (without performing row reduction).
* **Justification:** There is a single right-hand side and the coefficient matrix $\begin{pmatrix} 2 & -1 \\ 0 & 4 \end{pmatrix}$ is already in upper triangular form, so the last equation already contains only one unknown. Performing forward elimination is unnecessary.
* **Complete Execution:**
  1. From the second equation: $4y = 8 \implies y = \frac{8}{4} = 2$.
  2. Substituting $y = 2$ into the first equation: $2x - 2 = 3 \implies 2x = 5 \implies x = \frac{5}{2}$ (or $2.5$).
  * The unique solution is **$(x, y) = \left(\frac{5}{2}, 2\right)$**.

### 2. Case 2: Three Systems $Ax = b_i$ with Known $A^{-1}$
* **Chosen Method:** Direct matrix-vector multiplication **$x_i = A^{-1}b_i$** for each $i = 1, 2, 3$.
* **Plan and Justification:** Because there are multiple ($3$) right-hand side vectors $b_1, b_2, b_3$ sharing the exact same invertible coefficient matrix $A$ and $A^{-1}$ is already available, we compute each solution directly by multiplying $x_1 = A^{-1}b_1$, $x_2 = A^{-1}b_2$, and $x_3 = A^{-1}b_3$.
* **Reusable vs. Unnecessary Computation:** The precomputed inverse matrix **$A^{-1}$ is completely reusable** across all three systems (each solve requires only one matrix-vector multiplication). Re-computing $A^{-1}$ or running Gaussian elimination three separate times from scratch would be completely **unnecessary**.

### 3. Case 3: One $3 \times 3$ System Without $A^{-1}$ Given
* **Chosen Method:** **Gaussian elimination** on the augmented matrix $[A \mid b]$ followed by back-substitution.
* **Plan and Justification:** Since there is only $1$ right-hand side vector and $A^{-1}$ is neither given nor assumed to have a special triangular/diagonal structure, we form the $3 \times 4$ augmented matrix $[A \mid b]$, reduce it to row echelon form using elementary row operations, and recover the single solution vector $x$ via back-substitution.
* **Reusable vs. Unnecessary Computation:** Computing the full $3 \times 3$ inverse matrix $A^{-1}$ (which requires reducing $[A \mid I_3]$, equivalent to solving three systems simultaneously) is **unnecessary**, because there are no additional right-hand side vectors that would reuse $A^{-1}$.

### Verification
For Case 1, substituting $(x, y) = \left(\frac{5}{2}, 2\right)$ back into both original equations confirms the result:
* Equation 1: $2\left(\frac{5}{2}\right) - 2 = 5 - 2 = 3$.
* Equation 2: $4(2) = 8$.