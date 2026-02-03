# Linear Transformations — Intuition to Matrix Form

## 1. What is a Linear Transformation?

A **linear transformation** is just a function between two vector spaces.

$$
L : V \rightarrow W
$$

- \(V\) = domain  
- \(W\) = codomain  

Key idea:

> A linear transformation **preserves linear combinations**.

---

## 2. What does “preserves linear combinations” mean?

There are **two paths**, and both must give the **same result**.

### Path 1
- Take vectors  
- Scale them  
- Add them  
- Apply the transformation  

Result → \(R_1\)

### Path 2
- Transform each vector first  
- Scale them  
- Add them  

Result → \(R_2\)

✅ For linearity:

R_1 = R_2


---

### Mathematical form

$$
L(c_1 v_1 + c_2 v_2) = c_1 L(v_1) + c_2 L(v_2)
$$

This equation **defines** linear transformations.

---

## 3. Two Rules for Linearity

A transformation \(L\) is linear **if and only if**:

### Rule 1 — Scalar multiplication behaves nicely
$$
L(c v) = c L(v)
$$

### Rule 2 — Vector addition behaves nicely
$$
L(v + w) = L(v) + L(w)
$$

### Combined form
$$
L(a x + b y) = a L(x) + b L(y)
$$

---

## 4. Think of a Matrix the Right Way

> A matrix is **not just numbers**.  
> A matrix is a **machine built out of vectors**.

It tells the coordinate system **how to move**.

---

## 5. Standard Basis Vectors

In 2D space (R²):

$$
e_1 = (1,0), \quad e_2 = (0,1)
$$

Every vector can be written as a linear combination:

$$
(x,y) = x e_1 + y e_2
$$

---

## 6. How a Matrix is Built (Key Construction)

To build the matrix of a linear transformation:

1. See where the transformation sends \(e_1\)  
2. See where it sends \(e_2\)  
3. Put those results as **columns**

$$
A =
\begin{bmatrix}
| & | \\
L(e_1) & L(e_2) \\
| & |
\end{bmatrix}
$$

---

## 7. Why This Works

Because every vector is built from basis vectors:

$$
(x,y) = x(1,0) + y(0,1)
$$

Apply \(L\):

$$
L(x,y) = xL(1,0) + yL(0,1)
$$

Matrix multiplication **rebuilds this linear combination automatically**.

So:

$$
L(x) = Ax
$$

---

## 8. Complete Example (Linear Combination)

### Step 1 — Define vectors
$$
v_1 = (1,0), \quad v_2 = (0,1), \quad v_3 = (1,1)
$$

### Step 2 — Scalars
$$
a = 2, \quad b = -1, \quad c = 3
$$

### Step 3 — Form linear combination
$$
2v_1 - v_2 + 3v_3
$$

$$
= 2(1,0) + (0,-1) + 3(1,1)
$$

$$
= (2,0) + (0,-1) + (3,3)
$$

$$
= (5,2)
$$

---

## 9. Apply a Linear Transformation

Define:

L(x,y) = (3x + 6y, 2x + 9y)

Apply to \((5,2)\):

$$
L(5,2) = (27,28)
$$

---

## 10. Build the Matrix

Apply \(L\) to basis vectors:

$$
L(1,0) = (3,2)
$$

$$
L(0,1) = (6,9)
$$

Put them as columns:

$$
A =
\begin{bmatrix}
3 & 6 \\
2 & 9
\end{bmatrix}
$$

---

## 11. Verify Using Matrix Multiplication

Multiply matrix A with vector v:

$$
A =
\begin{bmatrix}
3 & 6 \\
2 & 9
\end{bmatrix}
$$

$$
v =
\begin{bmatrix}
5 \\
2
\end{bmatrix}
$$

Now compute:

$$
Av =
\begin{bmatrix}
27 \\
28
\end{bmatrix}
$$


✔ Same result.

---

## 12. Rotation Example (Geometric View)

Rotation by angle \(\theta\):

$$
e_1 = (1,0) \rightarrow (\cos\theta,\sin\theta)
$$

$$
e_2 = (0,1) \rightarrow (-\sin\theta,\cos\theta)
$$

Matrix:

$$
A =
\begin{bmatrix}
\cos\theta & -\sin\theta \\
\sin\theta & \cos\theta
\end{bmatrix}
$$

Again: **columns = where basis vectors go**.

---

## 13. What is NOT a Linear Transformation?

### Translation
$$
f(x) = x + w
$$

Fails because:
$$
f(0) \neq 0
$$

❌ So translation is **not linear**.

---

## Final Intuition (Read This Twice)

- Linear transformation = structure preserved  
- Matrix = transformation written in numbers  
- Columns = images of basis vectors  
- Matrix multiplication = rebuilding linear combinations  
