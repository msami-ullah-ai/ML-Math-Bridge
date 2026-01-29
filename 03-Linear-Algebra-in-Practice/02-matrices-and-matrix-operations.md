# Matrices, Memory, and Data Layout

## 1. Matrices and Dimensions

A **matrix** is a 2D array of numbers.

Let

$$
A \in \mathbb{R}^{n \times \ell}
$$

where:
- $n$ = number of rows  
- $\ell$ = number of columns  

Let

$$
B \in \mathbb{R}^{\ell \times m}
$$

Then matrix multiplication is defined and the result is:

$$
AB \in \mathbb{R}^{n \times m}
$$

📌 **Key rule**:  
The **inner dimensions must match**.

---

## 2. Matrix–Vector Multiplication (Column View)

Matrix–vector multiplication has a very important geometric interpretation.

Let

$$
A \in \mathbb{R}^{m \times n}
$$

and

$$
x \in \mathbb{R}^{n}
$$

### Column View Interpretation

- Each **column of A** is a building block
- Each **entry of x** is a weight
- The output is a **weighted sum of the columns of A**

\[
Ax = x_1 A_1 + x_2 A_2 + \dots + x_n A_n
\]

### Column Space

The **column space of A** is:
- the set of **all possible outputs** \( Ax \)
- all linear combinations of columns of A

📌 **Important intuition**:  
Matrix–vector multiplication = **linear combination of columns**

---

## 3. How Matrices Are Stored in Memory

### Big Picture

- **Memory is 1D**
- **Matrices are 2D**
- So matrices must be stored as a **single linear list**

The trick is to map a 2D index \((i, j)\) into a 1D index.

---

## 4. Row-Major Ordering (C-order)

Most systems (and NumPy by default) use **row-major ordering**.

### What it means

- Rows are stored **one after another**
- Elements of the same row are **next to each other in memory**

### Index Transformation

For a matrix with `m` columns:

$$
\text{index}(i, j) = i \times m + j
$$

Where:
- `i` = row index
- `j` = column index
- `m` = number of columns

📌 This explains why matrices can be flattened into a single list.

---

## 5. Column-Major Ordering (Fortran-order)

In **column-major ordering**:
- Columns are stored one after another

### Important Property

- Column-major order is the same for a matrix and its transpose

### NumPy Defaults

- Default: `order='C'` → row-major
- Optional: `order='F'` → column-major

---

## 6. Where Does an Element Live in Memory?

For row-major order:


$$
A(i, j) \rightarrow i \times (\text{number of columns}) + j
$$

This mapping explains:
- flattening
- reshaping
- memory efficiency
- performance differences

📌 **Matrix = single list + index formula**

---

## 7. Matrix Multiplication Rules (Again, Practically)

To multiply two matrices:

$$
A \in \mathbb{R}^{m \times n}
$$

and

$$
B \in \mathbb{R}^{n \times p}
$$

The result is:

$$
AB \in \mathbb{R}^{m \times p}
$$

- Inner dimension $n$ must match  
- Output shape is $(m \times p)$


Example:

(3, 4) @ (4, 2) → (3, 2)


---

## 8. Elementwise Multiplication (`*`)

Elementwise multiplication is **not** matrix multiplication.

### Rules

Shapes must be:
- exactly the same, or
- broadcastable

Examples:
- same shape
- one dimension is `1`

📌 This is different from `@` (matrix multiplication).

---

## 9. Reshaping Arrays

Reshaping is allowed **if and only if**:
- total number of elements stays the same

Example:


(2, 6) → (3, 4) ❌
(2, 6) → (3, 4) ❌
(2, 6) → (3, 4) ❌
(2, 6) → (3, 4) ❌


Correct example:


(2, 6) → (3, 4) ❌
(2, 6) → (4, 3) ✅


---

## 10. Horizontal Stacking (`hstack`)

Horizontal stacking places arrays **side by side** (column-wise).

### Rules

- Arrays must have the **same number of rows**
- Columns are joined left to right

📌 Special case:
- If arrays are **1D**, `hstack` just concatenates them

---

## 11. Data Representation in Machine Learning

### Key Principle

> **Every data point is a column vector**

This is emphasized throughout the book.

---

## 12. Batch-Last vs Batch-First

This part is critical and often confusing, so let’s be very clear.

---

### 12.1 Definitions

- **Feature** → one measurable property (e.g., height, age)
- **Sample** → one data point (collection of features)

---

## 12.2 Batch-Last (Features × Samples)

Shape:


(features, samples)


- Each **column** is one sample
- Each **row** is one feature

Example:


X ∈ ℝ^{features × samples}


### Why this is nice

- Weight matrix:


W ∈ ℝ^{outputs × features}


- Clean matrix multiplication:


WX


📌 This gives **very clean math**, which is why the book prefers it.

---

## 12.3 Batch-First (Samples × Features)

Shape:


(samples, features)


- Each **row** is one sample
- Each line of data = one sample

### Why this is common

- Matches how data is stored in files
- Matches CSVs, datasets, pandas DataFrames

📌 This is why many ML libraries use batch-first.

---

## 12.4 Summary Comparison

| Convention | Shape | Sample Location | Common Use |
|-----------|------|-----------------|------------|
| Batch-last | (features, samples) | Column | Math, theory |
| Batch-first | (samples, features) | Row | Data storage, practice |

---

## Final Takeaways

- Matrices are stored as **1D memory**
- Matrix–vector multiplication = **weighted sum of columns**
- Memory layout matters for performance
- Matrix multiplication rules are strict
- Elementwise multiplication is different
- Reshaping must preserve total elements
- **Every data point is a column vector**
- Batch-last = clean math
- Batch-first = practical storage

---
