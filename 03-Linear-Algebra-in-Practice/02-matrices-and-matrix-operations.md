# Matrices, Matrix Operations, and Data Representation

## 1. Matrices and Dimensions

A **matrix** is a 2D array of numbers.

Let:
- \( A \in \mathbb{R}^{n \times \ell} \)
- \( B \in \mathbb{R}^{\ell \times m} \)

Then matrix multiplication is defined as:
\[
AB \in \mathbb{R}^{n \times m}
\]

### Dimension Rule
> Matrix multiplication is valid **only if**  
> the number of columns of the first matrix equals the number of rows of the second matrix.

---

## 2. Matrix–Vector Multiplication (Column View)

Matrix–vector multiplication can be understood as a **linear combination of columns**.

Let:
- \( A \in \mathbb{R}^{m \times n} \)
- \( x \in \mathbb{R}^{n} \)

Then:
\[
Ax = x_1 a_1 + x_2 a_2 + \dots + x_n a_n
\]

Where:
- \( a_i \) are the **columns of matrix \( A \)**
- Entries of vector \( x \) act as **weights**
- The output is a **weighted sum of columns**

### Important Intuition
- Columns of \( A \) are the **building blocks**
- The **column space of \( A \)** is the set of all possible outputs of \( Ax \)

> In column view, matrix–vector multiplication is simply a linear combination of columns of \( A \).

---

## 3. Matrix Multiplication (General Case)

Let:
- \( A \in \mathbb{R}^{m \times n} \)
- \( B \in \mathbb{R}^{n \times p} \)

Then:
\[
AB \in \mathbb{R}^{m \times p}
\]

### Inner Dimension Rule
- The inner dimensions \( n \) **must match**

### Fixing Dimension Mismatch
- Transpose:
  \[
  A B^\top \quad \text{if dimensions allow}
  \]
- Reshape:
  - Allowed **only if** the total number of elements stays the same

---

## 4. Elementwise Multiplication (`*`)

Elementwise multiplication is **not** matrix multiplication.

### Rules
- Shapes must be:
  - Exactly the same  
  **or**
  - Broadcastable

Broadcasting examples:
- Same shape
- One dimension is 1 (row or column broadcasting)

---

## 5. Memory Layout and Row-Major Ordering

Computers store data in **1D memory**, even for matrices.

### Row-Major Ordering
- Rows are stored one after another
- Elements of a row are contiguous in memory

#### Index Mapping
For a matrix \( A \in \mathbb{R}^{n \times m} \):

\[
\text{Index}(i, j) = i \cdot m + j
\]

Where:
- \( i \) = row index
- \( j \) = column index
- \( m \) = number of columns

> A matrix is flattened into a single list using this rule.

---

## 6. Column-Major Ordering

- Columns are stored contiguously
- A matrix and its transpose share the same memory order

### NumPy Defaults
- `order='C'` → Row-major (default)
- `order='F'` → Column-major (Fortran-style)

---

## 7. Big Picture: How Matrices Are Stored

- Memory is **1D**
- Matrices are conceptually **2D**
- Trick:
  - Store everything in a list
  - Use a formula to map \((i, j)\) → memory index

> A matrix is stored as a **single linear list**, with indexing rules giving the 2D illusion.

---

## 8. Horizontal Stacking (`hstack`)

Horizontal stacking places arrays **side by side** (column-wise).

### Rules
- Arrays must have the **same number of rows**
- Columns are joined from left to right

### Special Case (1D Arrays)
- `hstack` simply concatenates arrays

---

## 9. Shape Example in Matrix Multiplication

\[
(3, 4) \; @ \; (4, 2) \;\rightarrow\; (3, 2)
\]

---

## 10. Machine Learning Convention

### Key Principle
> **Every data point is a column vector**

This convention is emphasized throughout *Mathematics for Machine Learning*.

---

## 11. Batch-First vs Batch-Last Data Representation

### Definitions
- **Feature** → an individual measurable value
- **Sample (data point)** → a collection of features

---

## Batch-Last Representation (Features × Samples)

### Shape
\[
X \in \mathbb{R}^{(\text{features} \times \text{samples})}
\]

### Interpretation
- Each **column** represents one sample
- Each **row** represents one feature across all samples

Example:
\[
X =
\begin{bmatrix}
x_1^{(1)} & x_1^{(2)} & \dots & x_1^{(n)} \\
x_2^{(1)} & x_2^{(2)} & \dots & x_2^{(n)} \\
\vdots & \vdots & \ddots & \vdots
\end{bmatrix}
\]

---

### Why Batch-Last Is Preferred in the Book

Let:
- Input features = \( d \)
- Output dimension = \( k \)

Weight matrix:
\[
W \in \mathbb{R}^{k \times d}
\]

Forward pass:
\[
Y = W X
\]

Where:
- \( X \in \mathbb{R}^{d \times n} \)
- \( Y \in \mathbb{R}^{k \times n} \)

Each column of \( Y \) corresponds to the output for one sample.

> Batch-last aligns perfectly with linear algebra and avoids unnecessary transposes.

---

## Batch-First Representation (Samples × Features)

### Shape
\[
X \in \mathbb{R}^{(\text{samples} \times \text{features})}
\]

### Interpretation
- Each **row** is one sample
- Common in CSV files and datasets

To compute outputs:
\[
Y = X W^\top
\]

An extra transpose is required.

---

## 12. Comparison Summary

| Aspect | Batch-Last | Batch-First |
|------|-----------|-------------|
| Shape | (features, samples) | (samples, features) |
| Sample stored as | Column | Row |
| Linear algebra | Very clean | Needs transpose |
| Book preference | Yes | No |
| Data storage | Less common | Very common |

---

## 13. Final Takeaways

- Matrix multiplication depends on **dimension alignment**
- Matrix–vector multiplication = **weighted sum of columns**
- Memory is **1D**, matrices are an abstraction
- Elementwise operations are different from matrix multiplication
- ML math treats **every data point as a column vector**
- Batch-last is best for theory and clean math
- Batch-first is best for storage and data handling
