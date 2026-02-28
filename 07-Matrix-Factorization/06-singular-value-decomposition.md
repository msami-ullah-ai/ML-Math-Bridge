# Singular Value Decomposition (SVD)

## 1. What Is SVD?

Every \( m \times n \) matrix can be factorized into three matrices:

$$
A = U \Sigma V^T
$$

Where:

- \( U \) → Orthogonal matrix (left singular vectors)
- \( \Sigma \) → Diagonal matrix (singular values)
- \( V \) → Orthogonal matrix (right singular vectors)

So SVD breaks a matrix into:

> Rotate → Stretch → Rotate

---

## 2. What Do These Matrices Represent?

### (1) Matrix \( V \)

- Orthogonal matrix
- Columns are orthonormal eigenvectors of:

$$
A^T A
$$

- Represents **input directions** (in domain)
- These are directions that get stretched or compressed by \( A \)

These vectors are called:

> Right singular vectors

---

### (2) Matrix \( U \)

- Orthogonal matrix
- Columns are orthonormal eigenvectors of:

$$
A A^T
$$

- Represents **output directions** (in codomain)
- Shows where the stretched vectors land

These vectors are called:

> Left singular vectors

---

### (3) Matrix \( \Sigma \)

- Diagonal matrix
- Contains singular values:

$$
\sigma_1, \sigma_2, \sigma_3, \dots
$$

arranged in decreasing order:

$$
\sigma_1 \ge \sigma_2 \ge \sigma_3 \ge \dots \ge 0
$$

Singular values are:

$$
\sigma_i = \sqrt{\lambda_i}
$$

where \( \lambda_i \) are eigenvalues of \( A^T A \).

---

## 3. Geometric Meaning

Applying matrix \( A \) to a vector is equivalent to:

1. Apply \( V^T \) → Rotate into special input coordinate system  
2. Apply \( \Sigma \) → Stretch/compress along axes  
3. Apply \( U \) → Rotate to output space  

So:

$$
A = U \Sigma V^T

Meaning:

Any linear transformation = rotate → stretch → rotate

4. Important Properties

𝑈
𝑇
𝑈
=
𝐼
U
T
U=I

𝑉
𝑇
𝑉
=
𝐼
V
T
V=I

Columns of 
𝑈
U and 
𝑉
V are orthonormal

Singular values are always non-negative

Works for any matrix (square or rectangular)

This is why SVD is more powerful than eigen-decomposition.

5. How To Compute SVD (Step-by-Step)

Given matrix 
𝐴
A:

Step 1: Compute 
𝐴
𝑇
𝐴
A
T
A

This matrix is:

Symmetric

Positive semi-definite

Step 2: Find Eigenvalues of 
𝐴
𝑇
𝐴
A
T
A

Solve:

det
⁡
(
𝐴
𝑇
𝐴
−
𝜆
𝐼
)
=
0
det(A
T
A−λI)=0

These eigenvalues are:

𝜆
1
,
𝜆
2
,
…
λ
1
	​

,λ
2
	​

,…
Step 3: Compute Singular Values
𝜎
𝑖
=
𝜆
𝑖
σ
i
	​

=
λ
i
	​

	​


Arrange them in decreasing order.

Step 4: Find Eigenvectors of 
𝐴
𝑇
𝐴
A
T
A

These eigenvectors form matrix 
𝑉
V.

Normalize them so they have length 1.

Step 5: Compute 
𝑈
U

For each singular value 
𝜎
𝑖
σ
i
	​

:

𝑢
𝑖
=
1
𝜎
𝑖
𝐴
𝑣
𝑖
u
i
	​

=
σ
i
	​

1
	​

Av
i
	​


These form matrix 
𝑈
U.

6. Why Is SVD Important?
(1) First columns matter most

The first columns of:

𝑈
U

𝑉
V

Largest singular value in 
Σ
Σ

contain the most important information.

The first few singular values usually dominate.

(2) Low-Rank Approximation

We can approximate matrix 
𝐴
A using only first 
𝑘
k singular values:

𝐴
𝑘
=
𝑈
𝑘
Σ
𝑘
𝑉
𝑘
𝑇
A
k
	​

=U
k
	​

Σ
k
	​

V
k
T
	​


This keeps most information but reduces complexity.

Used in:

PCA

Image compression

Recommendation systems

NLP embeddings

7. Connection to PCA

In PCA, we decompose:

𝐶
=
𝑋
𝑇
𝑋
C=X
T
X

Using SVD:

𝑋
=
𝑈
Σ
𝑉
𝑇
X=UΣV
T

Principal components correspond to:

Right singular vectors

Largest singular values

So PCA is basically SVD applied to data matrix.

8. Big Picture Summary

SVD says:

Any matrix can be decomposed into orthogonal rotations and pure stretching.

It reveals:

Important directions

Magnitude of stretching

Structure of data

Final Insight

Eigen-decomposition works only for square matrices.

SVD works for any matrix.

That’s why SVD is one of the most important tools in Machine Learning.


---

This is now:

- Structured
- Clean
- Conceptually layered
- Computation included
- ML connection included
- Matches your tone

If you want, next we can:

- Add a small numeric example
- Add visual geometric explanation
- Or refine the PCA connection deeper

Your matrix-factorization chapter is becoming very strong now.
