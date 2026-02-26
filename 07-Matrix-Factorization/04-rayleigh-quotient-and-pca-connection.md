# Rayleigh Quotient and PCA Connection

Now we connect spectral decomposition to optimization and PCA.

This is where everything becomes powerful.

---

# 1. The Expression \( x^T A x \)

Let:

- \( A \) be a symmetric matrix
- \( x \) be a vector

Consider the quantity:

$$
x^T A x
$$

What does this mean?

Step by step:

1. Multiply \( A x \) → transforms vector \( x \)
2. Multiply \( x^T (Ax) \) → gives a single number (scalar)

So:

> \( x^T A x \) measures how vector \( x \) behaves under transformation \( A \).

It tells us how much the transformation stretches \( x \) in its own direction.

---

# 2. Restrict to Unit Vectors

Now suppose we only look at vectors of length 1:

$$
\|x\| = 1
$$

Then we study:

$$
\max_{\|x\| = 1} x^T A x
$$

Meaning:

- Try all unit vectors
- Plug them into \( x^T A x \)
- See which direction makes this value largest

This is an optimization problem.

---

# 3. Important Result

If \( A \) is symmetric, then:

- The maximum value of \( x^T A x \)
- Over all unit vectors

is equal to:

> The largest eigenvalue of \( A \)

And the vector that achieves this maximum (argmax) is:

> The eigenvector corresponding to the largest eigenvalue

So:

$$
\max_{\|x\|=1} x^T A x = \lambda_1
$$

and

$$
\arg\max_{\|x\|=1} x^T A x = u_1
$$

where:

- \( \lambda_1 \) = largest eigenvalue  
- \( u_1 \) = corresponding eigenvector  

---

## 4. Why Does This Happen?

Suppose:

$$
A u = \lambda u
$$

Then:

$$
u^T A u = u^T (\lambda u) = \lambda (u^T u)
$$

If \( u \) is a unit vector, then:

$$
u^T u = 1
$$

So:

$$
u^T A u = \lambda
$$

That means along eigenvector directions,  
\( x^T A x \) equals the eigenvalue.

The largest eigenvalue gives the maximum stretch.

---

# 5. Geometric Meaning

The quadratic form:

$$
x^T A x
$$

tells us:

> How much space spreads (or stretches) along direction \( x \).

So:

- Largest eigenvalue → maximum stretching direction
- Corresponding eigenvector → best direction

---

# 6. Connection to PCA

Now comes the Machine Learning connection.

In PCA, we take:

$$
C = X^T X
$$

(or covariance matrix of data)

Important:

- \( C \) is symmetric
- So spectral theorem applies
- So it has orthonormal eigenvectors
- And real eigenvalues

---

# 7. Variance Interpretation

In PCA, we want:

> The direction where data varies the most.

It turns out:

Variance along direction \( x \) is:

$$
x^T C x
$$

So PCA solves:

$$
\max_{\|x\|=1} x^T C x
$$

From earlier result:

- Maximum value = largest eigenvalue of \( C \)
- Direction that achieves it = corresponding eigenvector

---

# 8. First Principal Component

Definition:

> The first principal component is the eigenvector of the covariance matrix corresponding to the largest eigenvalue.

And:

- That eigenvalue represents the amount of variance captured.

So:

- Direction = eigenvector
- Variance amount = eigenvalue

---

# 9. Big Picture Summary

If you want the direction that captures most information in data:

1. Compute covariance matrix \( C \)
2. Compute eigenvalues and eigenvectors
3. Choose eigenvector with largest eigenvalue

That eigenvector:

- Maximizes \( x^T C x \)
- Captures maximum variance
- Is the first principal component

And remember:

> Variance ∝ Information

So PCA is simply:

Find the eigenvector that maximizes variance.

---

# Final Understanding

Because symmetric matrices can be written as:

$$
C = U \Lambda U^T
$$

The optimization becomes simple.

Spectral theorem guarantees:

- Orthogonal directions
- Clean diagonal structure
- Clear maximum direction

So PCA works because:

> Symmetric matrices have eigenvectors that solve the maximum variance problem.
