# Linear Combinations

A **linear combination** is formed by:
- multiplying vectors by numbers (scalars)
- and then adding the results together

So, if we have vectors **v** and **u**,  
any vector of the form:

a·v + b·u

is called a **linear combination** of v and u,  
where **a** and **b** are scalars.

In simple words:  
👉 **scale the vectors and add them.**

---

## Set of All Linear Combinations

Given vectors  
v₁, v₂, ..., vₙ  

the set of all linear combinations consists of all vectors of the form:

a₁v₁ + a₂v₂ + ... + aₙvₙ

This set forms a **region in space**.

What that region looks like depends entirely on **which vectors you choose**.

---

## Span

The **span** of a set of vectors is the collection of **all possible linear combinations** of those vectors.

In other words:

> **Span tells us what part of space we can reach using the vectors.**

### Examples:
- Two linearly independent vectors in ℝ² → span the entire plane  
- Three linearly independent vectors in ℝ³ → span the entire space  
- One non-zero vector → spans only a line  

---

## What You Can Reach Depends on the Vectors You Choose

You can take linear combinations of **any set of vectors**,  
but the **result you can achieve** depends on the set you pick.

---

## 1. Using Basis Vectors — Reaching the Entire Space (“The Map”)

When you use **basis vectors**, you are guaranteed to reach **every point** in the space.

### Why?
- Basis vectors are **linearly independent**
- They **span the entire space**
- No direction is missing

They are like the:
- **North–South**
- **East–West**

of your mathematical world.

### Purpose:
- To define coordinates
- To ensure no part of space is off-limits
- To represent every vector uniquely

> Using basis vectors means you can reach **everything**.

---

## 2. Using Any Arbitrary Set of Vectors — Reaching a Subspace

If the vectors you choose are **not a basis**,  
their linear combinations may only reach a **restricted region** of the space.

This region is called a **subspace**.

### Example:
Imagine a **3D room**, but your vectors only lie on the floor.

- You can move anywhere on the carpet
- You can never reach the ceiling

You are stuck in a **2D plane inside a 3D space**.

> The vectors decide the directions you are allowed to move in.

---

## Linear Independence & Dependence

### Linear Independence

A set of vectors is **linearly independent** if:

The **only way** to get the zero vector using a linear combination  
is by setting **all coefficients equal to zero**.

This is called the **trivial solution**.

If this is the only solution → the vectors are independent.

---

### Linear Dependence

A set of vectors is **linearly dependent** if:

- There exists **at least one non-trivial solution**
- where not all coefficients are zero
- and the result is the zero vector

**Equivalent view:**
> At least one vector can be written as a linear combination of the others.

---

## Trivial vs Non-Trivial Solutions

- **Trivial solution:**  
  All coefficients = 0  

- **Non-trivial solution:**  
  At least one coefficient ≠ 0  

If a **non-trivial solution** gives the zero vector → **dependent**

---

## Quick Checks (Intuition Hacks)

- One vector is a scalar multiple of another → **dependent**
- More vectors than the dimension of space → **dependent**
  - e.g. 3 vectors in ℝ²
- Two vectors in a plane are independent if:
  - neither is zero
  - they are not collinear

---

## Linear Combinations in Machine Learning (Feature Vectors)

In Machine Learning, we **do not usually use standard basis vectors** like (1,0,0).

Instead, we use **feature vectors**, such as:
- size
- age
- income
- number of rooms

These features become the **ingredients** for linear combinations.

### The goal is different:
- We are not trying to reach every possible point in space
- We are trying to reach **one specific point**: the best prediction

The model’s job is to:
- find the correct **weights (scalars)**
- apply them to the **feature vectors**
- so their linear combination matches the target output

---

## Why This Matters in ML

Independent features:
- add new information
- help learning
- improve stability

Dependent features:
- are redundant
- slow learning
- confuse optimization

A good feature set is like a good basis:
- minimal
- independent
- no redundancy

> **You use basis vectors to build the grid,  
but you use feature vectors to find the path to your prediction.**

