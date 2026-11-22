# Exercise 14. A Small Change in the Right-Hand Side

## Question
We are asked to compare the two overdetermined linear systems:
$$\text{System 1:} \quad \begin{cases} x + y = 2, \\ 2x - y = 1, \\ 3x = 3 \end{cases} \qquad \text{and} \qquad \text{System 2:} \quad \begin{cases} x + y = 2, \\ 2x - y = 1, \\ 3x = 3.1. \end{cases}$$

We must check the consistency of each system and explain why a small change in one number on the right-hand side can change the type of the system.

## Solution

### 1. Checking Consistency of System 1
We form the augmented matrix for System 1 and perform Gaussian elimination:
$$\left( \begin{array}{cc\|c} 1 & 1 & 2 \\ 2 & -1 & 1 \\ 3 & 0 & 3 \end{array} \right) \xrightarrow{\substack{R_2 \leftarrow R_2 - 2R_1 \\ R_3 \leftarrow R_3 - 3R_1}} \left( \begin{array}{cc\|c} 1 & 1 & 2 \\ 0 & -3 & -3 \\ 0 & -3 & -3 \end{array} \right) \xrightarrow{R_3 \leftarrow R_3 - R_2} \left( \begin{array}{cc\|c} 1 & 1 & 2 \\ 0 & -3 & -3 \\ 0 & 0 & 0 \end{array} \right)$$

The third row reduces to $0 = 0$ (no contradiction), and back-substitution from the first two rows yields $-3y = -3 \implies y = 1$ and $x + 1 = 2 \implies x = 1$. Therefore, **System 1 is consistent** and has the unique solution **$(x, y) = (1, 1)$**.

### 2. Checking Consistency of System 2
Applying the exact same elementary row operations to the augmented matrix of System 2 gives:
$$\left( \begin{array}{cc\|c} 1 & 1 & 2 \\ 2 & -1 & 1 \\ 3 & 0 & 3.1 \end{array} \right) \xrightarrow{\substack{R_2 \leftarrow R_2 - 2R_1 \\ R_3 \leftarrow R_3 - 3R_1}} \left( \begin{array}{cc\|c} 1 & 1 & 2 \\ 0 & -3 & -3 \\ 0 & -3 & -2.9 \end{array} \right) \xrightarrow{R_3 \leftarrow R_3 - R_2} \left( \begin{array}{cc\|c} 1 & 1 & 2 \\ 0 & -3 & -3 \\ 0 & 0 & 0.1 \end{array} \right)$$

The third row now represents the false equation **$0 = 0.1$**, which is a contradiction. Therefore, **System 2 is inconsistent** and has **no solution**.

### 3. Why a Small Change in One Number Changes the Type of the System
Both systems are **overdetermined** ($3$ equations in only $2$ unknowns). The first two equations ($x + y = 2$ and $2x - y = 1$) represent two non-parallel lines in $\mathbb{R}^2$ that already intersect at a single, uniquely determined point $(1, 1)$.
* For a third equation to be consistent with the first two, its graph must pass through that exact same intersection point $(1, 1)$—algebraically, since $(x + y) + (2x - y) = 3x$, the right-hand side must satisfy the strict compatibility condition $b_3 = b_1 + b_2 = 2 + 1 = 3$.
* In **System 1**, $b_3 = 3$ satisfies this condition, so the third line $x = 1$ passes directly through $(1, 1)$.
* In **System 2**, changing $b_3$ by just $0.1$ (from $3$ to $3.1$) shifts the third vertical line from $x = 1$ to $x = \frac{3.1}{3} = \frac{31}{30}$. Because this line no longer passes through $(1, 1)$, all three lines fail to share a common intersection point, abruptly changing the system from consistent (with a unique solution) to inconsistent (with no solution).

### Verification
We verify both results directly by substitution:
* **System 1 at $(1, 1)$:** $1 + 1 = 2$, $2(1) - 1 = 1$, and $3(1) = 3$ (all three equations hold).
* **System 2:** Adding the first two equations gives $3x = 3 \implies x = 1$, whereas the third equation requires $3x = 3.1 \implies x = \frac{31}{30}$; since $1 \neq \frac{31}{30}$, no pair $(x, y)$ can satisfy all three equations simultaneously.