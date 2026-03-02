# Power Iteration Algorithm

## 1. Goal

We want to compute the **eigenvector corresponding to the largest eigenvalue** (dominant eigenvalue) of a real symmetric matrix.

Instead of solving:

$$
\det(A - \lambda I) = 0
$$

we use an **iterative method**.

---

## 2. Why Not Solve the Characteristic Polynomial?

Traditional approach:

1. Solve  
   det(A−λI) = 0
   to get eigenvalues.

2. Then solve  
   (A−λI)x = 0
   to get eigenvectors.

Problems:

- Computationally expensive
- Determinants cost about \( O(n^3) \)
- No general closed-form solution for degree ≥ 5
- Numerically unstable
- Impractical for large matrices

So instead, we use **Power Iteration**.

---

## 3. Special Properties of Real Symmetric Matrices

If \( A \) is real and symmetric:

- All eigenvalues are real.
- Eigenvectors corresponding to different eigenvalues are orthogonal.
- We can form an orthonormal basis of eigenvectors:

$$
\{u_1, u_2, \dots, u_n\}
$$

Every vector in the space can be written as:

$$
x = n_1 u_1 + n_2 u_2 + \dots + n_n u_n
$$

This is spectral decomposition idea.

---

## 4. Key Intuition Behind Power Iteration

Assume eigenvalues are ordered:

$$
|\lambda_1| > |\lambda_2| > \dots > |\lambda_n|
$$

Write any starting vector as:

$$
x = n_1 u_1 + n_2 u_2 + \dots
$$

Now apply \( A \) once:

$$
Ax = n_1 \lambda_1 u_1 + n_2 \lambda_2 u_2 + \dots
$$

Apply \( A \) twice:

$$
A^2 x = n_1 \lambda_1^2 u_1 + n_2 \lambda_2^2 u_2 + \dots
$$

Apply \( A^k \):

$$
A^k x = n_1 \lambda_1^k u_1 + n_2 \lambda_2^k u_2 + \dots
$$

Since λ is largest:

$$
|\lambda_1|^k \text{ dominates}
$$

So as k approaches infinity:

$$
A^k x \approx n_1 \lambda_1^k u_1
$$

Meaning:

> Repeated multiplication amplifies the dominant eigenvector direction.

---

## 5. Extracting Direction Using Limits

We only care about **direction**, not magnitude.

Start with:

A^kx = n1​λ1^k​u1​ +n 2​λ2^k​u2​+…

<img width="476" height="250" alt="image" src="https://github.com/user-attachments/assets/d60a59c0-42e6-4a76-bd9e-f3bda5ace70f" />


---

## 6. Removing Need to Know λ

We don’t know λ in advance.

Instead of dividing by λ, we normalize at every step.

Algorithm step becomes:

$$
x_{k+1} = \frac{A x_k}{\|A x_k\|}
$$

Why normalize?

Because multiplication by \( A \) makes magnitude grow exponentially.

Normalization keeps size controlled while preserving direction.

After many iterations:

$$
x_k \to u_1
$$

---

## 7. Formal Convergence Condition

Power iteration works if:

- λ_1 > λ_2
- Starting vector has non-zero component in direction \( u_1 \)

Meaning:

$$
n_1 \neq 0
$$

Random starting vectors almost always satisfy this.

If \( n_1 = 0 \), convergence to \( u_1 \) is impossible.

---

## 8. What If \( n_1 = 0 \)?

If starting vector has no component in \( u_1 \):

$$
x = n_2 u_2 + n_3 u_3 + \dots
$$

Then power iteration converges to \( u_2 \).

So we must ensure initial vector is not orthogonal to dominant eigenvector.

---

## 9. Power Iteration Algorithm (Step-by-Step)

Given symmetric matrix \( A \):

### Step 1
Choose random starting vector \( x_0 \)

### Step 2
Repeat:

$$
x_{k+1} = \frac{A x_k}{\|A x_k\|}
$$

### Step 3
Stop when:

$$
\|x_{k+1} - x_k\| \text{ is small}
$$

Then \( x_k \) approximates dominant eigenvector.

---

## 10. Computing Second and Third Eigenvectors (Deflation)

After finding \( u_1 \), remove its influence.

Projection of \( x \) onto \( u_1 \):

$$
\text{Proj}_{u_1}(x) = \langle x, u_1 \rangle u_1
$$

Remove it:

$$
x^* = x - \langle x, u_1 \rangle u_1
$$

In matrix form:

$$
x^* = (I - u_1 u_1^T)x
$$

This removes component along \( u_1 \).

Now power iteration on modified vector converges to \( u_2 \).

For third eigenvector:

$$
x^* = (I - u_1 u_1^T - u_2 u_2^T)x
$$

This process is called:

> Deflation

---

## 11. Summary

Power iteration:

- Repeatedly multiplies by matrix
- Dominant eigenvalue direction grows fastest
- Normalize each step
- Converges to largest eigenvector
- Requires non-zero initial component
- Use deflation for next eigenvectors

It is simple, efficient, and widely used in large-scale problems.
