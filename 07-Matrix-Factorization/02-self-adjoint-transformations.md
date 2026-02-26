# Self-Adjoint Transformations

This is the second special case of the Adjoint Transformation theorem  
(after Orthogonal transformations).

We already know:

For every linear transformation \( f \), there exists another transformation \( f^* \) such that

$$
\langle f(x), y \rangle = \langle x, f^*(y) \rangle
$$

In matrix form, if

$$
f(x) = Ax
$$

then

$$
f^*(x) = A^T x
$$

So in R^n, the adjoint is simply the transpose.

---

# What is a Self-Adjoint Transformation?

A transformation is **self-adjoint** if it equals its own adjoint.

That means:

$$
f^* = f
$$

Using matrix form:

$$
A^T = A
$$

So the matrix must be **symmetric**.

Therefore:

> Self-Adjoint = Symmetric (in real vector spaces)

---

# Meaning in Terms of Inner Product

For a self-adjoint transformation:

$$
\langle Ax, y \rangle = \langle x, Ay \rangle
$$

This means the transformation can move across the inner product  
without changing anything — because it equals its own transpose.

---

# Difference from Orthogonal Transformations

Let’s compare clearly:

## Orthogonal Transformation

Condition:

$$
A^T A = I
$$

Meaning:
- Preserves inner product
- Preserves length
- Preserves angles
- Only rotates or reflects space
- No stretching or shrinking

---

## Self-Adjoint Transformation

Condition:

$$
A^T = A
$$

Meaning:
- Does NOT necessarily preserve length
- Does NOT necessarily preserve angles
- Does NOT rotate space like orthogonal matrices
- Instead, it stretches or shrinks along special directions

So:

> Orthogonal = Rotate / Reflect  
> Self-Adjoint = Stretch / Shrink along special directions

---

# Geometric Meaning of Self-Adjoint Transformations

Self-adjoint transformations act along special perpendicular directions.

They do NOT randomly distort space.

Instead:

- There exist special directions
- If a vector lies in one of those directions
- After transformation, it stays in the same direction
- Only its length changes

Those special directions are called:

> **Eigenvectors**

And the amount of stretching or shrinking is called:

> **Eigenvalue**

---

# Key Properties of Self-Adjoint (Symmetric) Matrices

If \( A \) is a real symmetric matrix, then:

- It has **real eigenvalues**
- It has **orthonormal eigenvectors**
- It can be diagonalized
- Its eigenvectors form an orthonormal basis

This is extremely powerful.

Because it means we can fully understand the transformation  
by understanding its eigenvectors and eigenvalues.

---

# Intuition Summary

A self-adjoint transformation:

- Does not rotate space
- Does not preserve length like orthogonal matrices
- Instead, it finds special perpendicular directions
- Along those directions, it stretches or shrinks
- These directions are eigenvectors
- The stretching factor is the eigenvalue

So geometrically, every self-adjoint matrix behaves like:

Stretch along perpendicular axes.

This idea leads directly to the:

> Spectral Decomposition Theorem

Which we study next.
