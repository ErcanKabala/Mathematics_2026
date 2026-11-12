## Exercise 4: Gauss-Jordan

Matrix $A = \begin{pmatrix} 1 & 2 \\ 3 & 5 \end{pmatrix}$[cite: 13]

### Row Operations
Start with the augmented matrix $[A | I]$:[cite: 13]
$$ \left( \begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 3 & 5 & 0 & 1 \end{array} \right) $$

Step 1: $R_2 \to R_2 - 3R_1$[cite: 13]
$$ \left( \begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & -1 & -3 & 1 \end{array} \right) $$

Step 2: $R_2 \to -1 \cdot R_2$[cite: 13]
$$ \left( \begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & 1 & 3 & -1 \end{array} \right) $$

Step 3: $R_1 \to R_1 - 2R_2$[cite: 13]
$$ \left( \begin{array}{cc|cc} 1 & 0 & -5 & 2 \\ 0 & 1 & 3 & -1 \end{array} \right) $$

Result: $A^{-1} = \begin{pmatrix} -5 & 2 \\ 3 & -1 \end{pmatrix}$[cite: 13]
