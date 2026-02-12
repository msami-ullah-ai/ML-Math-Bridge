# LU Decomposition 

## 1. Why LU Decomposition Exists

In many machine learning problems (for example, linear regression), training eventually reduces to solving a linear system of equations:

\[
Ax = b
\]

Here:
- \(A\) is a square matrix built from the data
- \(x\) is the unknown vector (model weights)
- \(b\) is a known vector

Although one could write \(x = A^{-1}b\), computing a matrix inverse is:
- computationally expensive
- numerically unstable

LU decomposition provides a **safe and efficient way to solve \(Ax=b\)** without computing \(A^{-1}\).

---

## 2. What LU Decomposition Is 

LU decomposition is nothing more than **Gaussian elimination written in a structured way**.

On paper, when we solve a system:
1. We take the matrix \(A\)
2. Perform row operations to make all entries **below the diagonal equal to zero**
3. We keep track of the **multipliers** used during elimination

LU decomposition formalizes this process by writing:

\[
A = LU
\]

where:
- \(U\) is the matrix obtained after elimination (upper-triangular)
- \(L\) stores the elimination multipliers (lower-triangular with ones on the diagonal)

---

## 3. How L and U Are Built (Exactly Like on Paper)

### Step 1: Initialize
- Set \(U = A\)
- Set \(L = I\) (identity matrix)

### Step 2: Elimination

For each pivot column `k`:

1. **Compute the multiplier**

   For each row `i` below the pivot row:
m(i,k) = U[i,k] / U[k,k]


3. **Use the multiplier to eliminate the entry below the pivot**

Update row `i` as:
R_i ← R_i − m(i,k) · R_k


3. **Store the multiplier in L**

Save the multiplier in the lower triangular matrix:
L[i,k] = m(i,k)


### Step 3: Finish
- After all eliminations:
  - \(U\) is upper-triangular
  - \(L\) contains all multipliers
- The original matrix satisfies:
  \[
  A = LU
  \]

This is **exactly the same process used on paper**, just written in matrix form.

---

## 4. Solving a System Using LU

Once we have:
\[
A = LU
\]

we can solve:
\[
Ax = b
\]

by substitution:

\[
LUx = b
\]

Instead of solving this all at once, we break it into two simple steps:

1. **Forward substitution**
   \[
   Ly = b
   \]
2. **Back substitution**
   \[
   Ux = y
   \]

The vector \(y\) is just a temporary variable to make the solve easy.

---

## 5. Why This Is Better Than Matrix Inversion

- No matrix inverse is computed
- Triangular systems are fast to solve
- Numerical stability is much better
- Same result as \(A^{-1}b\), but safer

This is why LU decomposition is used in numerical linear algebra libraries and machine learning systems.

---

## 6. LU Decomposition in Machine Learning Context

In linear regression training:
1. Minimizing mean squared error leads to the normal equations:
   \[
   (X^T X)w = X^T y
   \]
2. This has the form:
   \[
   Ax = b
   \]
3. LU decomposition is used to efficiently solve for \(w\)

Once the weights are found:
- Training is complete
- LU decomposition is **not used during prediction**

---

## 7. Key Takeaways

- LU decomposition is **Gaussian elimination with memory**
- \(L\) stores how rows were combined
- \(U\) is the eliminated matrix
- Solving \(Ax=b\) becomes two easy substitution steps
- LU avoids matrix inversion and improves numerical stability

> **LU decomposition does not change the problem — it only changes how we solve it.**
