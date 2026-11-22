# Exercise 14. Rotation Matrices

## Question
The matrix for a counterclockwise rotation in $\mathbb{R}^2$ through an angle $\theta$ is given by:
$$R(\theta) = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}$$
We need to compute the product $R(\alpha)R(\beta)$, use the angle-sum formulas for sine and cosine to show that $R(\alpha)R(\beta) = R(\alpha + \beta)$, and explain the result geometrically.

## Solution

### 1. Computing $R(\alpha)R(\beta)$ and Applying Angle-Sum Formulas
We multiply the two $2 \times 2$ rotation matrices using row-by-column multiplication:
$$R(\alpha)R(\beta) = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix} \begin{pmatrix} \cos\beta & -\sin\beta \\ \sin\beta & \cos\beta \end{pmatrix}$$
$$R(\alpha)R(\beta) = \begin{pmatrix} \cos\alpha\cos\beta + (-\sin\alpha)\sin\beta & \cos\alpha(-\sin\beta) + (-\sin\alpha)\cos\beta \\ \sin\alpha\cos\beta + \cos\alpha\sin\beta & \sin\alpha(-\sin\beta) + \cos\alpha\cos\beta \end{pmatrix}$$
$$R(\alpha)R(\beta) = \begin{pmatrix} \cos\alpha\cos\beta - \sin\alpha\sin\beta & -(\sin\alpha\cos\beta + \cos\alpha\sin\beta) \\ \sin\alpha\cos\beta + \cos\alpha\sin\beta & \cos\alpha\cos\beta - \sin\alpha\sin\beta \end{pmatrix}$$

Now we recall the trigonometric angle-sum identities:
$$\cos(\alpha + \beta) = \cos\alpha\cos\beta - \sin\alpha\sin\beta$$
$$\sin(\alpha + \beta) = \sin\alpha\cos\beta + \cos\alpha\sin\beta$$

Substituting these two identities into the entries of the product matrix yields:
$$R(\alpha)R(\beta) = \begin{pmatrix} \cos(\alpha + \beta) & -\sin(\alpha + \beta) \\ \sin(\alpha + \beta) & \cos(\alpha + \beta) \end{pmatrix} = R(\alpha + \beta)$$

### 2. Geometric Explanation
For any vector $v \in \mathbb{R}^2$, the product $R(\alpha)R(\beta)v = R(\alpha)(R(\beta)v)$ represents applying two linear transformations in succession: first rotating $v$ counterclockwise around the origin by angle $\beta$, and then rotating the resulting vector counterclockwise around the origin by angle $\alpha$. Geometrically, performing two consecutive counterclockwise rotations in the plane through angles $\beta$ and $\alpha$ is equivalent to performing a single counterclockwise rotation through the total combined angle $\alpha + \beta$, which is represented by $R(\alpha + \beta)$.

### Verification
We verify the identity with the specific angles $\alpha = \frac{\pi}{2}$ and $\beta = \frac{\pi}{2}$ (so $\alpha + \beta = \pi$):
* Since $\cos\frac{\pi}{2} = 0$ and $\sin\frac{\pi}{2} = 1$, we have $R\left(\frac{\pi}{2}\right) = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$.
* Computing the product directly:
  $$R\left(\frac{\pi}{2}\right)R\left(\frac{\pi}{2}\right) = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 - 1 & 0 + 0 \\ 0 + 0 & -1 + 0 \end{pmatrix} = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$$
* Evaluating $R(\pi)$ directly (since $\cos\pi = -1$ and $\sin\pi = 0$):
  $$R(\pi) = \begin{pmatrix} \cos\pi & -\sin\pi \\ \sin\pi & \cos\pi \end{pmatrix} = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}$$
  Both matrices match, confirming $R(\alpha)R(\beta) = R(\alpha + \beta)$.