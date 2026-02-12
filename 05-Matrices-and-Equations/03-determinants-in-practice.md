# Determinants in Practice

## 1. Why Determinants Matter

The determinant of a square matrix

$$
A \in \mathbb{R}^{n \times n}
$$

measures how the linear transformation

$$
x \mapsto Ax
$$

changes volume.

- In 2D → it scales area  
- In 3D → it scales volume  
- In n-dimensions → it scales n-volume  

### Geometric Meaning

If

$$
\det(A) = 0
$$

→ space collapses → matrix is not invertible  

If

$$
\det(A) > 0
$$

→ orientation preserved  

If

$$
\det(A) < 0
$$

→ orientation flipped  

If

$$
|\det(A)|
$$

is large → volume expansion  

If

$$
|\det(A)|
$$

is small → volume contraction  

Determinants are therefore not just algebraic expressions — they describe geometric distortion.

---

## 2. Classical Way #1 — Permutation Formula

The theoretical definition of the determinant is:

$$
\det(A) =
\sum_{\sigma \in S_n}
\text{sign}(\sigma)\,
a_{1\sigma(1)}
a_{2\sigma(2)}
\cdots
a_{n\sigma(n)}
$$


### What This Means

To compute the determinant:

- Choose one element from each row  
- Choose one element from each column  
- Multiply them  
- Add or subtract depending on the permutation sign  

There are

$$
n!
$$

such combinations.

### Problem

Factorial growth explodes extremely fast.

Example:

$$
5! = 120
$$

$$
10! = 3,628,800
$$

$$
20!
$$

is astronomically large.

This makes the permutation formula computationally useless for large matrices.

---

## 3. Classical Way #2 — Recursive (Cofactor Expansion)

Instead of summing over all permutations, we use:

$$
\det(A) =
\sum_{j=1}^{n}
(-1)^{1+j}
a_{1j}
\det(A_{1j})
$$

where \( A_{1j} \) is the matrix obtained by deleting:

- Row 1  
- Column \( j \)

### How It Works

For an \( n x n \) matrix:

- Expand along the first row  
- Compute \( n \) determinants of size \( (n-1) x (n-1) \)  
- Repeat recursively  

Eventually we reach a \( 1 x 1 \) matrix, which stops the recursion.

---

## 4. Why the Recursive Method Is Slow

For an \( n x n \) matrix:

We compute \( n \) determinants of size \( (n-1) x (n-1) \).

If \( a_n \) denotes the time complexity:

$$
a_n = n a_{n-1}
$$

Expanding this gives:

$$
a_n = n(n-1)(n-2)\cdots 1 = n!
$$

This is factorial time complexity.

### Practical Example

For a \( 10 x 10 \) matrix:

Recursive method took about:

63.98 seconds

This is extremely slow for such a small matrix.

Factorial growth makes this approach unusable in practice.

---

## 5. The Key Idea — Use Structure

Instead of breaking the matrix into millions of smaller determinants, we use matrix factorization.

Specifically:

$$
A = LU
$$

where:

- \( L \) is lower triangular  
- \( U \) is upper triangular  

---

## 6. Determinant of a Product

A fundamental property of determinants:

$$
\det(AB) = \det(A)\det(B)
$$

Therefore:

$$
\det(A) = \det(LU) = \det(L)\det(U)
$$

---

## 7. Determinant of a Triangular Matrix

If a matrix is triangular (upper or lower), then:

$$
\det(A) = a_{11} a_{22} \cdots a_{nn}
$$

That is, simply multiply diagonal elements.

### Why This Works

When expanding along the first row of a triangular matrix:

- All off-diagonal elements are zero  
- Only the diagonal term survives  

This repeats recursively, producing the product of diagonal entries.

---

## 8. Why LU Makes Determinants Fast

In standard LU decomposition:

The diagonal of \( L \) consists of 1's.

Therefore:

$$
\det(L) = 1
$$

So:

$$
\det(A) = \det(U)
$$

And since \( U \) is triangular:

$$
\det(A) = u_{11} u_{22} \cdots u_{nn}
$$

### Complexity

Computing LU decomposition requires roughly:

$$
\mathcal{O}(n^3)
$$

operations.

This is dramatically better than:

$$
\mathcal{O}(n!)
$$

---

## 9. Performance Comparison

For a \( 10 x 10 \) matrix:

Recursive determinant:

63.98 seconds  

LU-based determinant:

0.000845 seconds  

Performance improvement:

$$
\approx 75{,}646
$$

times faster.

This is not a small improvement — it is a paradigm shift.

---

## 10. Why This Matters in Machine Learning

Determinants appear in:

- Multivariate Gaussian distributions  
- Log-likelihood computations  
- Covariance matrices  
- Normalizing flows (Jacobian determinants)  

In practice, matrices can be:

$$
100 \times 100
$$

$$
1000 \times 1000
$$

Even larger.

Factorial-time algorithms are impossible to use.

Modern ML libraries rely on:

- LU decomposition  
- LAPACK implementations  
- Optimized numerical linear algebra  

---

## 11. Core Lessons

- A formula being correct does not mean it is computationally practical.  
- Understanding algorithmic complexity is essential in ML.  
- Gaussian elimination is not old theory — it powers modern machine learning.  
- Simple linear algebra ideas can produce massive performance gains.
