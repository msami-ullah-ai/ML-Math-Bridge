## 1. What is an Eigenvector?

An **eigenvector** is a vector that:

> maintains its direction after undergoing a linear transformation.

This means:

When a vector **v** is multiplied by matrix **A**,

- it may get stretched  
- it may get shrunk  
- but it does **not change direction**

Mathematically:

$$
Av = \lambda v \quad (v \neq 0)
$$

---

## 2. What is an Eigenvalue?

The **scalar value** by which the eigenvector gets stretched or shrunk is called the:

> **Eigenvalue (λ)**

So in:

$$
Av = \lambda v
$$

- **v** → eigenvector  
- **λ** → eigenvalue  

This equation says:

Matrix multiplication **just scales the vector**  
(No rotation ❌ No bending ❌ No direction change ❌)

---

## 3. Why Are Eigenvalues Important?

Because they help:

> Turn complicated matrices into diagonal ones.

If the basis vectors of a coordinate system are eigenvectors of a matrix:

- Transformation becomes **pure scaling**
- No mixing of directions
- Matrix becomes **diagonal**

---

## IMPORTANT IDEA

A matrix becomes diagonal **when it is written in a coordinate system formed by its eigenvectors**.

Diagonal matrix means:

- Each direction is scaled independently
- No direction affects the other
- No mixing of coordinates

---

## 4. Rewriting the Eigenvalue Equation

Start with:

$$
Av = \lambda v
$$

Bring all terms to one side:

$$
Av - \lambda v = 0
$$

To make operations compatible  
(matrix − matrix), rewrite:

$$
\lambda v = (\lambda I)v
$$

So:

$$
Av - (\lambda I)v = 0
$$

Factor:

$$
(A - \lambda I)v = 0
$$

---

## 5. What Does This Mean?

We are looking for:

> A non-zero vector **v** such that  
> the matrix \(A - λ I\) sends it to zero.

i.e.

$$
(A - \lambda I)v = 0
$$

---

## 6. When Does This Have Non-Zero Solution?

Consider general system:

$$
Bx = 0
$$

- If $$\det(B) \neq 0$$  
  → only solution is $$x = 0$$

- If $$\det(B) = 0$$  
  → infinitely many solutions (non-zero exist)

Eigenvectors must be non-zero.

So we REQUIRE:

$$
\det(A - \lambda I) = 0
$$

---

## 7. Characteristic Equation

The equation:

$$
\det(A - \lambda I) = 0
$$

is called the:

> **Characteristic Equation**

Its solutions give:

> **Possible values of λ (Eigenvalues)**

Define:

$$
p(\lambda) = \det(A - \lambda I)
$$

This is called the:

> **Characteristic Polynomial**

Roots of this polynomial  
= Eigenvalues

---

## 8. After Finding Eigenvalues — Find Eigenvectors

For each eigenvalue λ:

Solve:

$$
(A - \lambda I)v = 0
$$

All solutions of this equation form the:

> **Eigenspace**

---

## 9. Eigenspace

Eigenspace =

> Set of all vectors that satisfy  
> the eigenvalue equation for a given λ

It contains:

- infinitely many vectors  
- all pointing in the same direction  
- including zero vector

But:

Eigenvectors = **non-zero vectors** inside this space.

---

## 10. Important Fact

A single eigenvalue can have:

> Multiple eigenvectors

(because eigenspace contains infinitely many vectors)

---

## 11. Special Case: Diagonal Matrix

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

- Standard basis vectors are eigenvectors

---

## 12. Example

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

- **u** is eigenvector  
- **λ = 3** is eigenvalue

---

## 13. Choosing New Basis as Eigenvectors

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

So in this new basis:

- First direction scales by 3
- Second direction scales by 1

Matrix becomes:

$$
\begin{bmatrix}
3 & 0 \\
0 & 1
\end{bmatrix}
$$

Diagonal!

---

## FINAL TAKEAWAY

To simplify (diagonalize) a matrix:

- Find eigenvalues  
- Find eigenvectors  
- Use eigenvectors as basis  

Then:

> The matrix becomes diagonal in that coordinate system.
