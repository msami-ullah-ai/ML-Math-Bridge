# Invertible Linear Transformations

## 1. What does “inverting” a linear transformation mean?

A linear transformation (LT) can be **undone** only if it is **invertible**.

Undoing a transformation means:
- finding **another linear transformation**
- that takes the output **back to the original input**

This new transformation is called the **inverse transformation**.

---

## 2. Inverse Transformation (Intuition)

If a transformation is \(T\), then its inverse is written as \(T^{-1}\).

What it does:
- \(T\) sends input → output  
- \(T^{-1}\) sends output → original input  

So:

- going **forward then backward** gives original vector
- going **backward then forward** also gives original vector

---

## 3. Core Definition (Undo & Redo)

A linear transformation  
T : v -> w  
is **invertible** if there exists a unique transformation  

T^{-1} : w -> v

such that:

### Undo
$$
T^{-1}(T(v)) = v
$$

### Redo
$$
T(T^{-1}(w)) = w
$$

If both work, the transformation is perfectly reversible.

---

## 4. Big Intuition 

> A transformation is invertible **if and only if no information is lost**.

So:

- If two different inputs map to the same output   
- Or everything collapses to zero   
→ No inverse exists.

An invertible LT can be **perfectly undone**.

---

## 5. One-to-One and Onto

For a linear transformation to be invertible, it **must** be:

- **One-to-one (injective)**  
  → different inputs give different outputs  

- **Onto (surjective)**  
  → every output vector is reached  

 Both are required.

---

## 6. Matrix Conditions for Invertibility

If a linear transformation is represented by a matrix \(A\), then:

A is invertible **iff**:

- Matrix is **square**
- Columns are **linearly independent**
- Determinant is **non-zero**
- Matrix is **non-singular**

All of these say the same thing in different words.

---

## 7. Determinant Connection

> The inverse of a linear transformation exists **iff**  
> the determinant of its matrix is **not zero**.

So:
- det(A) ≠ 0 → inverse exists  
- det(A) = 0 → no inverse  

---

## 8. Matrix View of Inverse Transformation

### Core idea:
If a linear transformation is represented by matrix \(A\), then:

- The inverse transformation is represented by \(A^{-1}\)
- Applying \(A^{-1}\) **undoes** what \(A\) did

So:
```text
Transformation → Matrix A
Inverse transformation → Matrix A⁻¹
````

---

## 9. How Inverse Transformation Works (Step by Step)

1. Start with a vector (x)
2. Apply the transformation:

   ```
   y = A x
   ```
3. To recover the original vector:

   ```
   x = A⁻¹ y
   ```

That’s the whole idea.

---

## 10. Matrix Definition of Invertibility

If a linear transformation gives a square matrix (A), then the transformation is invertible **iff** there exists a matrix (A^{-1}) such that:

$$
A^{-1}A = I \quad \text{and} \quad AA^{-1} = I
$$

Where (I) is the identity matrix.

---

## 11. Complete Worked Example

### Step 1 — Define the transformation

$$
T(x,y) = (2x + y,; x + y)
$$

### Step 2 — Use standard basis

$$
e_1 = (1,0), \quad e_2 = (0,1)
$$

### Step 3 — Apply transformation to basis vectors

$$
T(e_1) = (2,1)
$$
$$
T(e_2) = (1,1)
$$

### Step 4 — Build the matrix

$$
A =
\begin{bmatrix}
2 & 1 \
1 & 1
\end{bmatrix}
$$

So:

```
T(x) = A x
```

---

## 12. Apply the Transformation

Let the input vector be:

$$
x =
\begin{bmatrix}
1 \\
2
\end{bmatrix}
$$

Apply the transformation using matrix \(A\):

$$
Ax =
\begin{bmatrix}
4 \\
3
\end{bmatrix}
$$

This is the transformed vector.
## 13. Find the Inverse Matrix

The matrix of the transformation is:

$$
A =
\begin{bmatrix}
2 & 1 \\
1 & 1
\end{bmatrix}
$$

Its inverse is:

$$
A^{-1} =
\begin{bmatrix}
1 & -1 \\
-1 & 2
\end{bmatrix}
$$
## 14. Apply the Inverse (Undo)

We already know the transformed vector:

Ax = [ 4
       3 ]

Now apply the inverse matrix to undo the transformation.

A⁻¹ · [ 4
        3 ]
      = [ 1
          2 ]

✔ Original vector recovered.

This confirms that applying the inverse undoes the transformation:

A⁻¹(Ax) = x


## 15. What is NOT Invertible?

Not all linear transformations are invertible.

Example:

* A transformation that maps **every vector to zero**
* A transformation that squashes space into a line

Why?

* Information is lost
* Determinant becomes zero
* No inverse exists

---

