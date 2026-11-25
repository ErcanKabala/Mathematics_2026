# Exercise 13. Undoing a Composite Transformation

## Question
The matrices:
$$S = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix}, \quad H = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$$
describe nonuniform scaling and horizontal shear, respectively. For the composite transformation $T = HS$, we need to:
1. Find $T^{-1}$ in two ways:
   * Method 1: First compute $T$, then find its inverse.
   * Method 2: Use the product inverse formula $(HS)^{-1} = S^{-1}H^{-1}$.
2. Compare the two results.
3. Compute $H^{-1}S^{-1}$ and verify that the incorrect order yields a different matrix.
4. Explain the rule: *"when undoing a composition of operations, we undo them from the end."*

## Solution

### 1. Finding $T^{-1}$ in Two Ways

* **Method 1 (Computing $T = HS$ first, then inverting $T$):**
First, we multiply $H$ and $S$:
$$T = HS = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(2) + 1(0) & 1(0) + 1(1) \\ 0(2) + 1(0) & 0(0) + 1(1) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 1 \end{pmatrix}$$
Since $\det T = (2)(1) - (1)(0) = 2$, applying the $2 \times 2$ inverse formula gives:
$$T^{-1} = \frac{1}{2} \begin{pmatrix} 1 & -1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix}$$

* **Method 2 (Using $(HS)^{-1} = S^{-1}H^{-1}$):**
First, we find $S^{-1}$ (with $\det S = 2$) and $H^{-1}$ (with $\det H = 1$) separately:
$$S^{-1} = \frac{1}{2} \begin{pmatrix} 1 & 0 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 1 \end{pmatrix}, \qquad H^{-1} = \frac{1}{1} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}$$
Now we multiply $S^{-1}$ by $H^{-1}$:
$$S^{-1}H^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} \frac{1}{2}(1) + 0(0) & \frac{1}{2}(-1) + 0(1) \\ 0(1) + 1(0) & 0(-1) + 1(1) \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix}$$

### 2. Comparing the Results and Checking $H^{-1}S^{-1}$
* **Comparison:** Both Method 1 and Method 2 produce the exact same matrix $\begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix}$, confirming $(HS)^{-1} = S^{-1}H^{-1}$.
* **Computing $H^{-1}S^{-1}$ (Incorrect Order):**
$$H^{-1}S^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1\left(\frac{1}{2}\right) + (-1)(0) & 1(0) + (-1)(1) \\ 0\left(\frac{1}{2}\right) + 1(0) & 0(0) + 1(1) \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -1 \\ 0 & 1 \end{pmatrix}$$
Because $-\frac{1}{2} \neq -1$ in the top-right entry, we see that $H^{-1}S^{-1} \neq T^{-1}$.

### 3. Explaining the Rule: "When Undoing a Composition of Operations, We Undo Them from the End"
When the composite transformation $T = HS$ acts on a vector $x$, matrix multiplication works from right to left: $Tx = H(Sx)$. This means the operation $S$ (stretching the $x$-coordinate by $2$) is applied **first**, and the operation $H$ (adding the $y$-coordinate to the already stretched $x$-coordinate) is applied **second (at the end)**.

To return to the original vector $x$, we must reverse these steps in reverse chronological order—starting from the last operation performed:
1. First, we apply $H^{-1}$ to undo the final shear operation $H$ and recover $Sx$.
2. Second, we apply $S^{-1}$ to undo the initial scaling operation $S$ and recover $x$.

Writing this two-step reversal from right to left gives the matrix product $S^{-1}H^{-1}$, because $H^{-1}$ stands on the right (acting first on $Tx$) and $S^{-1}$ stands on the left (acting second):
$$(S^{-1}H^{-1})(HSx) = S^{-1}(H^{-1}H)Sx = S^{-1}I_2Sx = S^{-1}Sx = x$$
If we instead applied $H^{-1}S^{-1}$, we would mistakenly divide the sheared $x$-coordinate by $2$ before subtracting $y$, failing to restore the original vector.

### Verification
We verify that $T^{-1}$ undoes $T$ on the test vector $v = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$:
* Applying $T = HS$: $Sv = \begin{pmatrix} 2 \\ 2 \end{pmatrix}$, then $Tv = H(Sv) = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}\begin{pmatrix} 2 \\ 2 \end{pmatrix} = \begin{pmatrix} 4 \\ 2 \end{pmatrix}$.
* Applying $T^{-1}$: $T^{-1}(Tv) = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix}\begin{pmatrix} 4 \\ 2 \end{pmatrix} = \begin{pmatrix} 2 - 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 1 \\ 2 \end{pmatrix} = v$.
* By contrast, applying $H^{-1}S^{-1}$ gives $\begin{pmatrix} \frac{1}{2} & -1 \\ 0 & 1 \end{pmatrix}\begin{pmatrix} 4 \\ 2 \end{pmatrix} = \begin{pmatrix} 2 - 2 \\ 2 \end{pmatrix} = \begin{pmatrix} 0 \\ 2 \end{pmatrix} \neq v$, confirming why the reversed order is required.