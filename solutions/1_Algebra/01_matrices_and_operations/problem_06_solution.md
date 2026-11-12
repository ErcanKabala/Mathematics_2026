## Exercise 6: Transpose

### Computations
* $A^T = \begin{pmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{pmatrix}$[cite: 9]

* $B^T = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 3 \end{pmatrix}$[cite: 9]

* $AB = \begin{pmatrix} 1(1)+2(2)+3(-1) & 1(0)+2(1)+3(3) \\ 4(1)+5(2)+6(-1) & 4(0)+5(1)+6(3) \end{pmatrix} = \begin{pmatrix} 2 & 11 \\ 8 & 23 \end{pmatrix}$[cite: 9]

### Verification of $(AB)^T = B^T A^T$
* $(AB)^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}$[cite: 9]

* $B^T A^T = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 3 \end{pmatrix} \begin{pmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{pmatrix} = \begin{pmatrix} 1+4-3 & 4+10-6 \\ 0+2+9 & 0+5+18 \end{pmatrix} = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}$[cite: 9]

* Result: $(AB)^T = B^T A^T$ holds true.[cite: 9]