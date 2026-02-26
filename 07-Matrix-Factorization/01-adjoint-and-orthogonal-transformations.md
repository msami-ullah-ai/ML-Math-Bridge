# Chapter 07 – Matrix Factorization (Foundations)

Before studying matrix factorizations, we need to understand some very important geometric ideas.

---

# 1. Recall: Linear Transformation is Geometric

A linear transformation is a **geometric object**.

We can think of it as:

- Stretch
- Rotate
- Reflect
- Project

Formally:

$$
T : V \rightarrow V
$$

But when we choose a **basis**, this transformation becomes a matrix.

If the matrix is \( A \), then:

$$
T(x) = Ax
$$

Now everything becomes linear algebra.

We can:

- Multiply matrices
- Compute determinants
- Find eigenvalues
- Find eigenvectors
- Study geometry through algebra

---

# 2. Importance of Inner Product

The inner product gives us geometry inside vector spaces.

For vectors x,y in R^n:

$$
\langle x, y \rangle = \sum_{i=1}^{n} x_i y_i
$$

(standard dot product)

---

## 2.1 Angle Between Vectors

The inner product gives a way to compute angle:

$$
\cos\theta =
\frac{\langle x, y \rangle}
{\|x\|\|y\|}
$$

---

## 2.2 Orthogonality

Two vectors are orthogonal if:

$$
\langle x, y \rangle = 0
$$

---

## 2.3 Length (Norm)

Length comes from inner product:

$$
\|x\| = \sqrt{\langle x, x \rangle}
$$

So inner product controls:

- Length
- Angle
- Orthogonality

This is why it is very important.

---

# 3. Adjoint Transformation

Suppose we have a linear transformation:

$$
f : \mathbb{R}^n \rightarrow \mathbb{R}^n
$$

Then there exists another transformation \( f^* \) such that:

$$
\langle f(x), y \rangle = \langle x, f^*(y) \rangle
$$

### Meaning:

Adjoint is just a way to **move the transformation from one side of inner product to the other side**.

Think of it like this:

- First transform \( x \), then take dot product with \( y \)
- OR
- First transform \( y \) (using adjoint), then take dot product with \( x \)

Both give same result.

---

## 3.1 Matrix Form of Adjoint

Let transformation \( f \) be represented by matrix \( A \).

Then:

$$
f(x) = Ax
$$

The matrix of \( f^* \) is:

$$
A^T
$$

So:

$$
f^*(y) = A^T y
$$

Thus:

$$
\langle Ax, y \rangle = \langle x, A^T y \rangle
$$

---

## 3.2 Important Cases

### (1) Symmetric Matrix

If:

$$
A^T = A
$$

Then:

$$
f = f^*
$$

Such transformation is called:

**Self-adjoint transformation**

---

### (2) Orthogonal Matrix

If:

$$
A^T A = I
$$

Then the matrix is **orthogonal**.

We will study this next.

---

# 4. Special Transformations (Inner Product Preserving)

Some transformations preserve inner product.

Meaning:

If we take two vectors \( x, y \) and apply transformation \( f \), then:

A transformation preserves inner product if:

$$
\langle f(x), f(y) \rangle = \langle x, y \rangle
$$

---

## What does this mean geometrically?

After transformation:

- Length stays same
- Angle stays same
- Orthogonality stays same

So geometry is preserved.

---

# 5. Condition for Preserving Inner Product

A matrix preserves inner product **if and only if**:

$$
A^T A = I
$$

or equivalently

$$
A^{-1} = A^T
$$

This means:

> Transpose undoes the transformation.

---

# 6. Orthogonal Transformation

A transformation is orthogonal if:

$$
\langle Ax, Ay \rangle = \langle x, y \rangle
$$

That means:

- Length between vectors is preserved
- Angle between vectors is preserved
- Dot product is preserved

---

## 6.1 What Orthogonal Transformations Do

They do NOT:

- Stretch
- Shrink
- Distort space

They only:

- Rotate
- Reflect
- Change coordinate system

So they preserve geometry.

---

# 7. Summary

- Inner product controls geometry (length, angle, orthogonality).
- Adjoint allows us to move transformation across inner product.
- In R^n the adjoint is the transpose.
- If \( A^T = A \) → symmetric (self-adjoint).
- If \( A^T A = I \) → orthogonal.
- Orthogonal transformations preserve geometry.
- They only rotate or reflect space.

---

This foundation is important before studying:

- Matrix factorization
- Spectral decomposition
- SVD
- PCA
