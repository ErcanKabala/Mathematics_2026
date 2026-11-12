## Exercise 7: Identity Matrix, Zero Matrix, and Powers

### Computations
* $AI = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A$[cite: 9]

* $IA = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A$[cite: 9]

* $A + 0 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} + \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A$[cite: 9]

* $A^2 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix}$[cite: 9]

* $A^3 = A^2 A = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}$[cite: 9]

### Roles and Pattern
* **Role of $I$:** Multiplicative identity (multiplying by $I$ does not change the matrix).[cite: 9]
* **Role of $0$:** Additive identity (adding $0$ does not change the matrix).[cite: 9]
* **Pattern in $A^n$:** The diagonal entries are $2^n$, the bottom-left entry stays $0$, and the top-right entry follows the pattern $n \cdot 2^{n-1}$.[cite: 9]