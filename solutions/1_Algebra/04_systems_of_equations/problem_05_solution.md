## Exercise 5: Row Echelon Form and Number of Solutions

Augmented matrix:[cite: 15]
$$ \left( \begin{array}{ccc|c} 1 & 2 & -1 & 3 \\ 0 & 1 & 2 & 1 \\ 0 & 0 & 0 & 0 \end{array} \right) $$[cite: 15]

### Number of Solutions
There are infinitely many solutions.[cite: 15] We know this because the last row is all zeros (no contradiction) and there are 3 variables but only 2 pivots (leading 1s).[cite: 15]

### Parametric Form
Variables: $x, y, z$. The pivot columns are 1 and 2.[cite: 15] The 3rd column has no pivot, so $z$ is the free variable ($z = t$).[cite: 15]
* $y + 2t = 1 \implies y = 1 - 2t$[cite: 15]
* $x + 2(1 - 2t) - t = 3 \implies x + 2 - 5t = 3 \implies x = 1 + 5t$[cite: 15]
  **Solution:** $(1+5t, 1-2t, t)$[cite: 15]