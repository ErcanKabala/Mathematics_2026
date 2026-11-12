## Exercise 7: Choosing a Method Deliberately

### 1. Triangular matrix system
* **Method:** Back-substitution.[cite: 16] (Since it's already triangular, elimination is not needed).[cite: 16]
* **Solution:** 
  * $4y = 8 \implies y = 2$[cite: 16]
  * $2x - 2 = 3 \implies 2x = 5 \implies x = 2.5$[cite: 16]
  * Result: $(2.5, 2)$[cite: 16]

### 2. Three systems $Ax = b_i$ with known $A^{-1}$
* **Plan:** Compute $x_i = A^{-1} b_i$ for each system.[cite: 16] 
* **Reusable part:** We just multiply the already known $A^{-1}$ by different $b$ vectors.[cite: 16] We avoid Gaussian elimination entirely.

### 3. One $3\times3$ system to find one solution vector
* **Plan:** Use Gaussian elimination.[cite: 16] 
* **Unnecessary part:** Calculating the full $A^{-1}$ takes a lot of time and is unnecessary when we only need to solve the system for a single right-hand side. Elimination is much faster for a single problem.[cite: 16]