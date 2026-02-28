# Singular Value Decomposition (SVD)

## 1. What is SVD?

Singular Value Decomposition (SVD) says that **every** \( m \times n \) matrix can be written as a product of three matrices:

$$
A = U Λ V^T
$$

Where:

- \( U \) → orthogonal matrix (left singular vectors)
- \( Λ \) → diagonal matrix (singular values)
- \( V \) → orthogonal matrix (right singular vectors)

So SVD breaks a matrix into:

> Rotate → Stretch → Rotate

It works for **any matrix** (square or rectangular).

---

## 2. Meaning of Each Matrix

### Matrix \( V \)

- Orthogonal matrix
- Columns are orthonormal eigenvectors of:

$$
A^T A
$$

These represent the **input directions** in the domain that get stretched or compressed.

They are called:

> Right singular vectors

---

### Matrix \( U \)

- Orthogonal matrix
- Columns are orthonormal eigenvectors of:

$$
A A^T
$$

These represent the **output directions** in the codomain after transformation.

They are called:

> Left singular vectors

---

### Matrix \( Λ \)

- Diagonal matrix
- Contains singular values:

$$
\sigma_1 \ge \sigma_2 \ge \sigma_3 \ge \dots \ge 0
$$

Singular values are:

$$
\sigma_i = \sqrt{\lambda_i}
$$

where \( λ \) are eigenvalues of \( A^T A \).

They tell us **how much stretching** happens along special directions.

---

## 3. Geometric Interpretation

Applying matrix \( A \) to a vector is equivalent to:

1. Apply \( V^T \) → rotate into special input coordinate system  
2. Apply \(Λ \) → stretch or compress along coordinate axes  
3. Apply \( U \) → rotate into output space  

So:

$$
A = U Λ V^T
$$

means:

> Any linear transformation = rotation + scaling + rotation

---

## 4. Important Properties

- \( U^T U = I \)
- \( V^T V = I \)
- Columns of \( U \) and \( V \) are orthonormal
- Singular values are always non-negative
- Works for non-square matrices

SVD is more general than eigen-decomposition.

---

## 5. Steps to Compute SVD

Given matrix \( A \):

### Step 1: Compute \( A^T A \)

This matrix is symmetric and positive semi-definite.

---

### Step 2: Find eigenvalues of \( A^T A \)

Solve:

$$
\det(A^T A - \lambda I) = 0
$$

Get eigenvalues:

$$
\lambda_1, \lambda_2, \dots
$$

---

### Step 3: Compute singular values

$$
\sigma_i = \sqrt{\lambda_i}
$$

Arrange them in decreasing order.

---

### Step 4: Find eigenvectors of \( A^T A \)

These eigenvectors form matrix \( V \).

Normalize each eigenvector to unit length.

---

### Step 5: Compute \( U \)

For each singular value \( σ_i \):

$$
u_i = \frac{1}{\sigma_i} A v_i
$$

These vectors form matrix \( U \).

---

## 6. Importance of SVD

### First columns matter most

The first columns of:

- \( U \)
- \( V \)
- Largest singular values in \( Λ \)

contain the most important information about matrix \( A \).

Usually first few singular values dominate.

---

### Low-Rank Approximation

We can approximate matrix \( A \) using only first \( k \) singular values:

$$
A_k = U_k \Sigma_k V_k^T
$$

This keeps most important information but reduces size.

Used in:

- PCA
- Image compression
- Recommendation systems
- NLP embeddings

---

## 7. Connection to PCA

In PCA, we decompose covariance matrix:

$$
C = X^T X
$$

Using SVD:

$$
X = U \Sigma V^T
$$

Principal components correspond to:

- Right singular vectors
- Largest singular values

So PCA is essentially SVD applied to data matrix.

---

## 8. Big Picture Summary

SVD shows that:

- Every matrix hides special directions
- Along those directions, transformation becomes pure stretching
- Rotations handle coordinate changes
- Singular values measure importance

Eigen-decomposition works only for square matrices.

SVD works for **any matrix**.

That is why SVD is one of the most powerful tools in Machine Learning.
