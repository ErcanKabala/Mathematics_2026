# Exercise 9. Composing Transformations

## Question
Let the transformation matrices $S$ and $R$, and the vector $x$, be given by:
$$S = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix}, \quad R = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}, \quad x = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$$

Here, $S$ represents nonuniform scaling and $R$ represents a $90^\circ$ counterclockwise rotation. We are asked to compute $RSx$ and $SRx$, compare the results, and explain geometrically why the order of these transformations matters.

## Solution

### 1. Computing $RSx$ and $SRx$
Using the associativity of matrix multiplication, we can evaluate $RSx = R(Sx)$ and $SRx = S(Rx)$ by applying the rightmost transformation to the vector $x$ first.

* **Computing $RSx$ (Scaling first, then Rotation):**
  First, we apply the scaling matrix $S$ to $x$:
  $$Sx = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 2(1) + 0(2) \\ 0(1) + 1(2) \end{pmatrix} = \begin{pmatrix} 2 \\ 2 \end{pmatrix}$$
  Next, we apply the rotation matrix $R$ to the resulting vector $Sx$:
  $$RSx = R(Sx) = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 2 \\ 2 \end{pmatrix} = \begin{pmatrix} 0(2) + (-1)(2) \\ 1(2) + 0(2) \end{pmatrix} = \begin{pmatrix} -2 \\ 2 \end{pmatrix}$$

* **Computing $SRx$ (Rotation first, then Scaling):**
  First, we apply the rotation matrix $R$ to $x$:
  $$Rx = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 0(1) + (-1)(2) \\ 1(1) + 0(2) \end{pmatrix} = \begin{pmatrix} -2 \\ 1 \end{pmatrix}$$
  Next, we apply the scaling matrix $S$ to the resulting vector $Rx$:
  $$SRx = S(Rx) = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -2 \\ 1 \end{pmatrix} = \begin{pmatrix} 2(-2) + 0(1) \\ 0(-2) + 1(1) \end{pmatrix} = \begin{pmatrix} -4 \\ 1 \end{pmatrix}$$

### 2. Comparison and Geometric Explanation
Comparing the two output vectors shows that **$RSx \neq SRx$**, since $\begin{pmatrix} -2 \\ 2 \end{pmatrix} \neq \begin{pmatrix} -4 \\ 1 \end{pmatrix}$.

**Geometric Explanation:**
The matrix $S$ stretches vectors horizontally along the $x$-axis by a factor of $2$ while keeping the vertical $y$-coordinate unchanged. The matrix $R$ rotates vectors by $90^\circ$ counterclockwise around the origin, mapping any point $(x, y)$ to $(-y, x)$.
* In **$RSx$**, the point $(1, 2)$ is **stretched horizontally first** to $(2, 2)$, and **then rotated $90^\circ$ counterclockwise**. The rotation carries that stretched horizontal length onto the vertical $y$-axis, ending at $(-2, 2)$.
* In **$SRx$**, the point $(1, 2)$ is **rotated $90^\circ$ counterclockwise first** to $(-2, 1)$ (so the original vertical component $y = 2$ now lies along the negative $x$-axis), and **then stretched horizontally** by a factor of $2$, doubling $-2$ to $-4$ and ending at $(-4, 1)$.

Because nonuniform scaling affects the $x$- and $y$-axes differently, rotating before or after scaling changes which component of the vector gets stretched. Geometrically, this explains why composing these transformations in different orders produces different results ($RS \neq SR$).

### Verification
We can verify both calculations by first computing the composite matrices $RS$ and $SR$ directly and then multiplying by $x$:
* **Composite $RS$:**
  $$RS = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 & -1 \\ 2 & 0 \end{pmatrix} \implies (RS)x = \begin{pmatrix} 0 & -1 \\ 2 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} -2 \\ 2 \end{pmatrix}$$
* **Composite $SR$:**
  $$SR = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & -2 \\ 1 & 0 \end{pmatrix} \implies (SR)x = \begin{pmatrix} 0 & -2 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} -4 \\ 1 \end{pmatrix}$$
  Both composite matrix products match our step-by-step vector results.