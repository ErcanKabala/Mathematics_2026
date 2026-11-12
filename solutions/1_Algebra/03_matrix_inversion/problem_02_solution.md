## Exercise 2: Formula for a 2x2 Matrix

For $A = \begin{pmatrix} 3 & 2 \\ 5 & 4 \end{pmatrix}$:[cite: 13]

### Using the Formula
* $\det A = (3)(4) - (2)(5) = 12 - 10 = 2$[cite: 13]
* $A^{-1} = \frac{1}{\det A} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 4 & -2 \\ -5 & 3 \end{pmatrix} = \begin{pmatrix} 2 & -1 \\ -5/2 & 3/2 \end{pmatrix}$[cite: 13]

### Verification
* $A A^{-1} = \begin{pmatrix} 3 & 2 \\ 5 & 4 \end{pmatrix} \begin{pmatrix} 2 & -1 \\ -5/2 & 3/2 \end{pmatrix} = \begin{pmatrix} 6 - 5 & -3 + 3 \\ 10 - 10 & -5 + 6 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I$[cite: 13]
  The result is correct.