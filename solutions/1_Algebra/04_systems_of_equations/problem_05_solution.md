# Exercise 5. Row Echelon Form and Number of Solutions

## Question
For the given augmented matrix in row echelon form:
$$\left( \begin{array}{ccc|c} 1 & 2 & -1 & 3 \\ 0 & 1 & 2 & 1 \\ 0 & 0 & 0 & 0 \end{array} \right)$$
we need to determine the number of solutions, write them in parametric form, and explain how we know how many variables may be chosen freely.

## Solution

### 1. Number of Solutions and Number of Free Variables
Let the three unknowns corresponding to the first three columns be $x$, $y$, and $z$.
* **Consistency:** The third row is $\begin{pmatrix} 0 & 0 & 0 \mid 0 \end{pmatrix}$, which represents the trivial identity $0 = 0$. Since there is no contradictory row of the form $\begin{pmatrix} 0 & 0 & 0 \mid c \end{pmatrix}$ with $c \neq 0$, the system is consistent.
* **Counting Free Variables:** There are $n = 3$ unknowns in total, and the row echelon form has $r = 2$ pivot columns (column $1$ and column $2$). The number of free variables equals the number of non-pivot columns:
  $$\text{Number of free variables} = n - r = 3 - 2 = 1$$
  Because the system is consistent and has $1$ free variable that can take any real value, the system has **infinitely many solutions**.

### 2. Writing the Solutions in Parametric Form
Since column $3$ has no pivot, $z$ is the free variable. Setting $z = t$ where $t \in \mathbb{R}$ is an arbitrary real parameter:
* From the second row ($y + 2z = 1$):
  $$y + 2t = 1 \implies y = 1 - 2t$$
* From the first row ($x + 2y - z = 3$):
  $$x + 2(1 - 2t) - t = 3 \implies x + 2 - 4t - t = 3 \implies x + 2 - 5t = 3 \implies x = 1 + 5t$$

Hence, all solutions are given in parametric form by:
$$(x, y, z) = (1 + 5t, \, 1 - 2t, \, t), \quad t \in \mathbb{R} \qquad \text{or} \qquad \begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix} + t \begin{pmatrix} 5 \\ -2 \\ 1 \end{pmatrix}$$

### Verification
We verify the parametric formula by substituting $(x, y, z) = (1 + 5t, 1 - 2t, t)$ back into the equations represented by the augmented matrix for any $t \in \mathbb{R}$:
* **Row 1:** $(1 + 5t) + 2(1 - 2t) - t = 1 + 5t + 2 - 4t - t = 3$ (matches $3$).
* **Row 2:** $(1 - 2t) + 2(t) = 1 - 2t + 2t = 1$ (matches $1$).
* **Row 3:** $0(1 + 5t) + 0(1 - 2t) + 0(t) = 0$ (matches $0$).

The system is satisfied for every real value of $t$.