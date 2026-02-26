# Spectral Decomposition Theorem

We saw that self-adjoint (symmetric) matrices:

- Have real eigenvalues
- Have orthonormal eigenvectors
- Can be diagonalized

Now we state this properly.

---

# Spectral Decomposition Theorem (Real Case)

If \( A \) is a real symmetric matrix:

$$
A^T = A
$$

Then:

1. \( A \) has \( n \) real eigenvalues.
2. \( A \) has \( n \) orthonormal eigenvectors.
3. We can write:

$$
A = U \Lambda U^T
$$

This is called the **Spectral Decomposition** of \( A \).

---

# What Does \( A = U Λ U^T \) Mean?

Let’s understand each part clearly.

## 1️⃣ Matrix \( A \)

- Original matrix
- Represents some linear transformation
- Could look complicated

---

## 2️⃣ Matrix \( U \)

- Matrix whose columns are eigenvectors of \( A \)
- These eigenvectors are orthonormal
- So:

$$
U^T U = I
$$

That means:

$$
U^{-1} = U^T
$$

So \( U \) is an **orthogonal matrix**.

Geometrically:
> \( U \) represents a rotation (or change of coordinate system).

---

## 3️⃣ Matrix ( Λ)

- Diagonal matrix
- Contains eigenvalues on the diagonal

Example:

$$
\Lambda =
\begin{bmatrix}
\lambda_1 & 0 & 0 \\
0 & \lambda_2 & 0 \\
0 & 0 & \lambda_3
\end{bmatrix}
$$

Geometrically:
> Λ stretches or shrinks along coordinate axes.

---

# Geometric Interpretation

Applying \( A \) to a vector is the same as:

1️⃣ Apply \( U^T \) → rotate into eigenvector coordinate system  
2️⃣ Apply \( Λ \) → stretch/shrink along perpendicular axes  
3️⃣ Apply \( U \) → rotate back to original coordinate system  

So every symmetric matrix acts like:


Rotate → Stretch → Rotate Back


This is extremely important.

It means symmetric matrices do not randomly distort space.

They:

- Rotate to a special coordinate system
- Stretch along perpendicular directions
- Rotate back

---

# Why Is This Powerful?

Because now we understand the transformation completely:

- Directions = eigenvectors
- Stretch amount = eigenvalues

If we know \( U \) and \( \Λ \),  
we can rebuild the original matrix:

$$
A = U Λ U^T
$$

So eigenvalues + eigenvectors fully describe symmetric matrices.

---

# How To Perform Spectral Decomposition (Practical Steps)

If you are given a matrix \( A \):

### Step 1
Verify it is symmetric:

$$
A^T = A
$$

---

### Step 2
Find eigenvalues:

Solve:

$$
\det(A - λI) = 0
$$

---

### Step 3
Find eigenvectors:

For each eigenvalue \( λ_i \), solve:

$$
(A - λ_i I)v = 0
$$

---

### Step 4
Normalize eigenvectors

Convert each eigenvector \( v_i \) into unit length:

$$
u_i = \frac{v_i}{\|v_i\|}
$$

Because symmetric matrices guarantee orthogonality,  
after normalization they become orthonormal.

---

### Step 5
Construct matrix \( U \)

Place normalized eigenvectors as columns:

$$
U = [u_1 \; u_2 \; \dots \; u_n]
$$

---

### Step 6
Construct diagonal matrix \( Λ \)

Place eigenvalues on diagonal:

$$
\Λ =
\begin{bmatrix}
\λ_1 & 0 & \dots \\
0 & \λ_2 & \dots \\
\vdots & & \ddots
\end{bmatrix}
$$

---

### Step 7
Reconstruct

$$
A = U Λ U^T
$$

Done.

---

# Important Observation

Because eigenvectors are orthonormal:

- They form an orthonormal basis
- They create a new coordinate system
- In that coordinate system, the matrix becomes diagonal

That is the magic of the spectral theorem.

---

# Big Idea

Every real symmetric matrix:

- Has perpendicular eigen-directions
- Stretches along those directions
- Can be written as \( U Λ U^T \)

This result is the foundation for:

- PCA
- Quadratic forms
- Optimization
- SVD (coming next)
