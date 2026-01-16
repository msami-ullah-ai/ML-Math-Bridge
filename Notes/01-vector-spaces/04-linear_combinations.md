# Linear Combinations

A **linear combination** is made by:
- stretching a vector by a number
- stretching another vector by another number
- and then adding the results

So if we have two vectors **a** and **b**,  
any vector of the form:

a·v + b·u

is a linear combination of v and u  
where a and b are scalars.

In simple words:  
**scale the vectors and add them.**

---

## Set of All Linear Combinations

The set of all linear combinations of vectors  
v₁, v₂, ..., vₙ consists of all vectors of the form:

a₁v₁ + a₂v₂ + ... + aₙvₙ

This set forms a region in space.

---

## Span

The **span** of a set of vectors is the collection of **all possible linear combinations** of those vectors.

If two vectors are linearly independent in the plane,  
their span fills the entire plane ℝ².

If three vectors are linearly independent in space,  
their span fills ℝ³.

So:

> **Span tells us what part of space we can reach using the vectors.**

---

## Linear Independence & Dependence

### Linear Independence

A set of vectors is **linearly independent** if:

The only way to get the zero vector using a linear combination  
is by setting **all coefficients equal to zero**.

This is called the **trivial solution**.

If this is the only solution, the vectors are independent.

---

### Linear Dependence

If we can find **even one non-trivial solution**  
(where at least one coefficient is not zero)  
that produces the zero vector,  
then the vectors are **linearly dependent**.

That means one vector can be written using the others.

---

## Trivial vs Non-Trivial Solutions

**Trivial solution:**  
All coefficients = 0

**Non-trivial solution:**  
At least one coefficient ≠ 0

If a non-trivial solution gives the zero vector → **dependent**

---

## Simple Checks (Hacks)

- If one vector is a scalar multiple of another → **dependent**
- If only way to get 0 vector is using Trivial Solution → **Independent**
- If number of vectors > dimension of space  
  (e.g. 3 vectors in ℝ²) → **dependent**
- Two vectors in a plane are independent  
  if they are not collinear and neither is zero
  

---

## Why This Matters in ML

Independent vectors bring new information.  
Dependent vectors are redundant.

A good feature set is like a good basis:
- minimal
- independent
- no redundancy

This makes learning faster and more stable.
