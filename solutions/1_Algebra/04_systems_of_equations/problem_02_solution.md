## Exercise 2: Gaussian Elimination — One Solution

### Augmented Matrix
$$ \left( \begin{array}{ccc|c} 1 & 1 & 1 & 6 \\ 2 & -1 & 1 & 3 \\ 1 & 2 & -1 & 2 \end{array} \right) $$[cite: 14]

### Elimination Steps
1. $R_2 \to R_2 - 2R_1$ and $R_3 \to R_3 - R_1$[cite: 14]
   $$ \left( \begin{array}{ccc|c} 1 & 1 & 1 & 6 \\ 0 & -3 & -1 & -9 \\ 0 & 1 & -2 & -4 \end{array} \right) $$[cite: 14]
2. Swap $R_2$ and $R_3$[cite: 14]
   $$ \left( \begin{array}{ccc|c} 1 & 1 & 1 & 6 \\ 0 & 1 & -2 & -4 \\ 0 & -3 & -1 & -9 \end{array} \right) $$[cite: 14]
3. $R_3 \to R_3 + 3R_2$[cite: 14]
   $$ \left( \begin{array}{ccc|c} 1 & 1 & 1 & 6 \\ 0 & 1 & -2 & -4 \\ 0 & 0 & -7 & -21 \end{array} \right) $$[cite: 14]

### Solving
* $-7z = -21 \implies z = 3$[cite: 14]
* $y - 2(3) = -4 \implies y = 2$[cite: 14]
* $x + 2 + 3 = 6 \implies x = 1$[cite: 14]
  **Solution:** $x=1, y=2, z=3$[cite: 14]

### Consistency Check
* Eq 1: $1 + 2 + 3 = 6$ (True)[cite: 14]
* Eq 2: $2(1) - 2 + 3 = 3$ (True)[cite: 14]
* Eq 3: $1 + 2(2) - 3 = 2$ (True)[cite: 14]