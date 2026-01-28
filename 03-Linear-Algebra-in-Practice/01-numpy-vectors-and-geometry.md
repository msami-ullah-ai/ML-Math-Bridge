# NumPy Vectors & Geometric Structure

> ## 1. Why Exact Equality Fails for Floats

In theory, numbers are exact. On a computer, **most real numbers are approximations**.

So comparing floats using `==` is dangerous.

```python
0.1 + 0.2 == 0.3   # False
```

That’s why we **compare with tolerance**, not strict equality.

---

## 2. Tolerance-Based Comparison (`np.isclose`)

Instead of asking:

> “Are these numbers exactly equal?”

We ask:

> “Are they close enough that I can ignore the difference?”

### What is tolerance?

Tolerance = *how much error I’m willing to ignore*.

### Formula used by NumPy

```text
|a - b| ≤ atol + rtol × |b|
```

* `atol` → absolute tolerance
* `rtol` → relative tolerance

### NumPy example

```python
np.isclose(a, b)
```

Returns `True` if values are **close enough**, not exactly equal.

Use this **everywhere** in ML and numerical linear algebra.

---

## 3. Vectors in NumPy (Elementwise Behavior)

In NumPy:

```python
+   *   **
```

are applied **element by element**.

```python
import numpy as np

x = np.array([1, 2, 3])
y = np.array([4, 5, 6])

x + y   # [5, 7, 9]
x * y   # [4, 10, 18]
```

### Important

* NumPy arrays support **elementwise operations by default**
* Python’s `math` functions work only on **scalars**, not arrays

---

## 4. Vectorization (Why NumPy Is Fast)

### Vectorized operations mean:

* Apply one operation to **many numbers at once**
* No explicit `for` loops

```python
# BAD (slow)
for i in range(len(x)):
    x[i] = x[i] ** 2

# GOOD (fast)
x = x ** 2
```

---

## 5. Universal Functions (ufuncs)

**ufuncs** are NumPy’s built-in vectorized functions.

They:

* Work on entire arrays
* Apply operations element-by-element
* Run in **C**, not Python (very fast)

Examples:

```python
np.sqrt(x)
np.exp(x)
np.log(x)
```

### Rule of thumb

> ❌ Never use loops if a NumPy ufunc exists

---

## 6. Naive vs Overhead Cost

* **Naive code** → simple, readable, but slow
* **Overhead** → fixed cost paid every time a function runs

Vectorized code wins because overhead is paid **once**, not per element.

---

## 7. Measuring Speed (`timeit`)

If a variable appears inside `timeit`, it must be created in `setup`.

```python
%timeit x ** 2
```

Setup runs **once**, timing runs **many times**.

---

## 8. Vector Norms

### Euclidean norm (length of vector)

```python
np.linalg.norm(x)
```

By default:

```text
‖x‖₂  (L2 norm)
```

---

## 9. Inner Product (Dot Product)

### Definition

Multiply elementwise, then sum.

```python
np.dot(x, y)
```

### Shape rule

Vectors must have the **same shape**.

---

## 10. Broadcasting (Automatic Shape Matching)

Broadcasting is NumPy’s way to make shapes compatible.

### Rules

1. Compare shapes **from right to left**
2. At each position:

   * sizes must be equal **OR**
   * one of them must be `1`
3. Otherwise → ❌ error

### Result shape

Take the **maximum** size at each dimension.

### Examples

```text
(4,1) and (1,2) → (4,2)
(n,1) and (1,m) → (n,m)
(4,1) and (4,3) → (4,3)
```

---

## 11. Elementwise Math vs Linear Algebra

* Elementwise math → broadcasting is OK
* Linear algebra → use `dot`, `@`, `np.matmul`

```python
x * y      # elementwise
x @ y      # linear algebra
```

---

## 12. Vector Shapes (Important Concept)

```python
x.shape == (4,)
```

Means:

* A **1D vector**
* Element of ℝ⁴
* NOT a row or column matrix

---

## 13. Projection Onto a Single Vector

### Formula

```text
projₑ(n) = (n·e) / (e·e) × e
```

### NumPy implementation

```python
def proj_on_one(n, e):
    return np.dot(n, e) / np.dot(e, e) * e
```

---

## 14. Projection Onto Multiple Vectors

```python
def proj_onto_many(n, vectors):
    p = np.zeros_like(n)
    for v in vectors:
        p += proj_on_one(n, v)
    return p
```

---

## 15. Orthonormalization

### Normalize a vector

```python
def normalize(v):
    return v / np.linalg.norm(v)
```

---

## 16. Gram–Schmidt Orthogonalization

### Goal

Turn **linearly independent vectors** into an **orthonormal set**.

### Core idea

From each new vector:

* Remove components in directions we already used
* Normalize what remains

### Algorithm

```python
def gram_schmidt(vectors):
    ortho = []
    for v in vectors:
        v_ortho = v - proj_onto_many(v, ortho)
        ortho.append(normalize(v_ortho))
    return ortho
```

---

## 17. Geometric Intuition (Very Important)

* Projection = **part of vector in a direction**
* Removing projection = making vectors **perpendicular**

### Verification

```python
np.allclose(np.dot(e, n - proj_on_one(n, e)), 0.0)
```

If dot product is zero → vectors are orthogonal ✅

---

## 18. Key Takeaways

* Never compare floats with `==`
* Use `np.isclose`
* Prefer vectorized operations
* Broadcasting is for elementwise math
* Dot product is for linear algebra
* Gram–Schmidt builds orthonormal bases step by step

---
