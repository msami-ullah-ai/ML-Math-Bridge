## 1. Basic Idea

Eigenvector is a vector which maintains its direction after undergoing a linear transformation.

Eigenvalue is the scalar value by which eigenvector gets multiplied during linear transformation.

Mathematically:

$$
Av = \lambda v \quad (v \neq 0)
$$

This means:

When vector **v** is multiplied by matrix **A**,

- it may get stretched  
- it may get shrunk  
- but does NOT change direction

So:

- **v** → eigenvector  
- **λ** → eigenvalue  

Matrix multiplication just scales the vector.

No rotation  
No bending  
No directional change  

---

## 2. Why Eigenvalues are Powerful?

Eigenvalues are powerful because:

> They help turn complicated matrices into diagonal ones.

If basis vectors are eigenvectors then:

- transformation becomes pure scaling along each basis  
- no mixing of directions  
- matrix becomes diagonal  

That is why diagonal matrices are closely related to eigenvectors.

---

## 3. Rewriting the Equation

Start from:

$$
Av = \lambda v
$$

Bring all terms to one side:

$$
Av - \lambda v = 0
$$

But:

- $Av$ → matrix × vector  
- $\lambda v$ → scalar × vector  

We cannot subtract them directly in matrix form.

So rewrite:

$$
\lambda v = (\lambda I)v
$$

where:

$$
\lambda I =
\begin{bmatrix}
\lambda & 0 \\
0 & \lambda
\end{bmatrix}
$$

Now:

$$
Av - (\lambda I)v = 0
$$

Factor:

$$
(A - \lambda I)v = 0
$$

---

## 4. What Does This Mean?

We are looking for:

> A non-zero vector **v** such that  
> the matrix $(A - \lambda I)$ sends it to zero.

i.e.

$$
(A - \lambda I)v = 0
$$

---

## 5. General System Idea

Consider:

$$
Bx = 0
$$

- If $\det(B) \neq 0$  
  → only solution is $x = 0$

- If $\det(B) = 0$  
  → infinitely many solutions exist

Eigenvectors must be non-zero.

So we REQUIRE:

$$
\det(A - \lambda I) = 0
$$

---

## 6. Characteristic Equation

The equation:

$$
\det(A - \lambda I) = 0
$$

gives possible values of λ.

This is called the:

> Characteristic Equation

Define:

$$
p(\lambda) = \det(A - \lambda I)
$$

This is called:

> Characteristic Polynomial

Roots of this polynomial  
= Eigenvalues

---

## 7. After Finding Eigenvalues

For each eigenvalue λ:

Solve:

$$
(A - \lambda I)v = 0
$$

Solutions of this equation are eigenvectors.

---

## 8. Important Fact

A single eigenvalue can be associated with:

> Multiple eigenvectors

Because solutions of $(A - \lambda I)v = 0$ form a space.

---

## 9. Eigenspace

Eigenspace =

> Set of all possible vectors that satisfy  
> the eigenvalue equation for a given λ.

It includes:

- infinitely many vectors  
- zero vector  
- all vectors in same direction

Eigenvectors = non-zero vectors in eigenspace.

---

## 10. Special Case: Diagonal Matrix

For a diagonal matrix:

$$
\begin{bmatrix}
5 & 0 & 0 \\
0 & -4 & 0 \\
0 & 0 & 2
\end{bmatrix}
$$

- Eigenvalues = diagonal entries  
  → 5, −4, 2

- Basis vectors are eigenvectors.

---

## 11. Example

Let:

$$
A =
\begin{bmatrix}
2 & 1 \\
1 & 2
\end{bmatrix}
$$

Take:

$$
u = (1,1)
$$

Then:

$$
Au =
\begin{bmatrix}
3 \\
3
\end{bmatrix}
= 3(1,1)
$$

So:

- u is eigenvector  
- 3 is eigenvalue  

---

## 12. Choosing New Basis as Eigenvectors

Let:

$$
u_1 = (1,1), \quad u_2 = (-1,1)
$$

Then:

$$
Au_1 = 3u_1
$$

$$
Au_2 = 1u_2
$$

Expressed in this new basis:

- first direction scales by 3  
- second direction scales by 1  

So matrix becomes:

$$
\begin{bmatrix}
3 & 0 \\
0 & 1
\end{bmatrix}
$$

Diagonal.

---

## FINAL TAKEAWAY

To simplify (diagonalize) a matrix:

1. Find eigenvalues  
2. Find eigenvectors  
3. Use eigenvectors as basis  

Then:

> The matrix becomes diagonal when written in the coordinate system formed by its eigenvectors.
