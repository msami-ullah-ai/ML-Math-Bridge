# Row Echelon Form, Rank & Solving Linear Systems  

A matrix is in **Row Echelon Form (REF)** if the following rules are satisfied:

- All rows that are completely zero must be at the **bottom**
- The **first non-zero entry** in each non-zero row is called a **pivot**
- Each pivot must appear **to the right** of the pivot in the row above
- All entries **below a pivot** must be zero

Important note:

- In REF, the pivot **does NOT have to be 1**
- Any **non-zero number** is acceptable as a pivot

REF is an **intermediate form** used during elimination.

---

## 2. Reduced Row Echelon Form (RREF)

A matrix is in **Reduced Row Echelon Form (RREF)** if:

- It satisfies **all conditions of REF**
- Every pivot is exactly **1**
- All other entries in the pivot column are **0**  
  (both above and below the pivot)

RREF is the **final clean form** of a matrix.

---

## 3. Singular vs Non-Singular Matrix

A matrix is **non-singular (invertible)** if **any one** of the following is true:

- The system of equations is **complete** (no missing info)
- The equations are **not redundant**
- The equations are **not contradictory**
- Rows (or columns) are **linearly independent**
- The **determinant is non-zero**
- The matrix has **full rank**
- In RREF:
  - All diagonal entries are **1**
  - There are **no zero rows**

If these fail, the matrix is **singular**.

---

## 4. Core Elimination Strategy 

> Make pivots 1, kill entries below them, then move right and down.

This single rule drives the entire elimination process.

---

## 5. Elimination Method 

Suppose variables are `a, b, c`.

Step-by-step idea:

1. Normalize the pivot of `a` so its coefficient becomes 1
2. Use that row to eliminate all `a` terms below it
3. Move to `b`, normalize its pivot, eliminate `b` below it
4. Repeat for `c`
5. Solve the **last variable first**, then substitute upward

Example system:

a + b + 2c = 12  
3a − 3b − c = 3  
2a − b + 6c = 24  

You always eliminate in the order: **a → b → c**

---

## 6. Elementary Row Operations  
(These preserve the solution structure)

Allowed operations:

- Swap two rows
- Add a multiple of one row to another
- Multiply a row by a non-zero scalar

These operations do **not** change:
- Rank
- Singularity
- Solution type

---

## 7. Rank of a Matrix

Definition:

> Rank = the largest number of linearly independent rows or columns

Interpretation:

- Each independent row adds **new information**
- Redundant rows do not increase rank

How to compute rank:

- Convert the matrix to **REF**
- Count the number of **non-zero rows**

Equivalent statement:

> Rank = number of pivot positions

---

## 8. REF vs RREF 
- During elimination → matrix passes through **REF**
- After cleanup and back substitution → **RREF**

REF = working stage  
RREF = final answer stage

---

## 9. Gaussian Elimination

### Phase 1 — Setup
- Write system as an **augmented matrix**
- Ensure top-left entry is non-zero
- If zero → swap with a row below
- Tip: If a row already starts with 1, move it to the top

---

### Phase 2 — Forward Elimination
- Use pivot row to eliminate entries **below**
- Row operation rule:

New row = Current row − (multiplier × Pivot row)

- Move diagonally:
  - Down one row
  - Right one column
- Repeat for all columns

---

### Phase 3 — Rank & Consistency Check
- Move any all-zero rows to the bottom
- Count non-zero rows → **Rank**
- If a row looks like:

0 0 0 | non-zero  

→ **STOP** — no solution

---

### Phase 4 — Back Substitution
- Start from the last non-zero row
- Solve its variable
- Substitute upward
- Convert to RREF if needed

---

## 10. Three Possible Outcomes of a Linear System

1. **No solution**  
   Equations contradict each other

2. **Exactly one solution**  
   Equations intersect at one point  
   Happens when:
   - Matrix is invertible
   - Determinant ≠ 0  
   Solution can be written as:
   x = A⁻¹b

3. **Infinitely many solutions**  
   Equations are redundant  
   Free variables exist

---

## 11. Determinant Connection 

- det(A) ≠ 0  
  → Matrix is invertible  
  → Exactly one solution

- det(A) = 0  
  → Matrix is singular  
  → Either no solution or infinitely many solutions

---

## Final One-Line Lock 

REF reveals structure, RREF gives answers, rank counts information, and determinant decides uniqueness.
