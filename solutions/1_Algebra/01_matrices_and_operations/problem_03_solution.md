# Exercise 3. When Can Matrices Be Multiplied?

## Question
Given the matrix dimensions:
$$A_{2\times 3}, \quad B_{3\times 4}, \quad C_{4\times 2}, \quad D_{2\times 2}$$

We must determine whether each of the following products is defined:
$$AB, \quad BA, \quad BC, \quad CB, \quad AC, \quad CA, \quad AD, \quad DA$$
For every defined product, we must state the size of the resulting matrix and justify each decision using the dimension compatibility condition.

## Solution

### Dimension Compatibility Condition
For a matrix product $XY$ to be defined, the number of columns in the left matrix $X$ must equal the number of rows in the right matrix $Y$. Specifically, if $X$ has size $m \times n$ and $Y$ has size $p \times q$, the product $XY$ is defined if and only if $n = p$, and the resulting matrix has size $m \times q$.

Applying this condition to each pair:
* **$AB$ ($2\times 3$ and $3\times 4$):** **Defined.** The inner dimensions match ($3 = 3$). The resulting matrix has size **$2 \times 4$**.
* **$BA$ ($3\times 4$ and $2\times 3$):** **Undefined.** The number of columns in $B$ ($4$) does not equal the number of rows in $A$ ($2$).
* **$BC$ ($3\times 4$ and $4\times 2$):** **Defined.** The inner dimensions match ($4 = 4$). The resulting matrix has size **$3 \times 2$**.
* **$CB$ ($4\times 2$ and $3\times 4$):** **Undefined.** The number of columns in $C$ ($2$) does not equal the number of rows in $B$ ($3$).
* **$AC$ ($2\times 3$ and $4\times 2$):** **Undefined.** The number of columns in $A$ ($3$) does not equal the number of rows in $C$ ($4$).
* **$CA$ ($4\times 2$ and $2\times 3$):** **Defined.** The inner dimensions match ($2 = 2$). The resulting matrix has size **$4 \times 3$**.
* **$AD$ ($2\times 3$ and $2\times 2$):** **Undefined.** The number of columns in $A$ ($3$) does not equal the number of rows in $D$ ($2$).
* **$DA$ ($2\times 2$ and $2\times 3$):** **Defined.** The inner dimensions match ($2 = 2$). The resulting matrix has size **$2 \times 3$**.

### Verification
We can verify the defined products by checking that the outer dimensions of each valid pair directly give the result size:
* $(2 \times \mathbf{3})(\mathbf{3} \times 4) \rightarrow 2 \times 4$
* $(3 \times \mathbf{4})(\mathbf{4} \times 2) \rightarrow 3 \times 2$
* $(4 \times \mathbf{2})(\mathbf{2} \times 3) \rightarrow 4 \times 3$
* $(2 \times \mathbf{2})(\mathbf{2} \times 3) \rightarrow 2 \times 3$
  All four defined cases satisfy $n = p$, and the remaining four fail this condition.