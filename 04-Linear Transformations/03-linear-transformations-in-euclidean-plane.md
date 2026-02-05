# Linear Transformations in the Euclidean Plane (2D)

## What is a Linear Transformation?

Forget matrices for a moment.

A **linear transformation** is simply a rule that **moves vectors**, but in a very structured way.

The structure is:

- Straight lines stay straight  
- Parallel lines stay parallel  
- The origin stays fixed  

If a rule breaks **any** of these, it is **not linear**.

---

## Why does the book talk about “basis” so much?

Because this is the most important fact:

> If you know where the **basis vectors** go, you know where **everything** goes.

In 2D, the standard basis vectors are:

- e₁ → right direction  
- e₂ → up direction  

These two vectors:

- create a grid  
- and the entire plane is made from copies of this grid  

So think of it like this:

**Basis = grid generator**

---

## What does a Linear Transformation REALLY do?

A linear transformation does **not** move points one by one.

Instead:

- it grabs the **entire grid**
- and reshapes it

The grid can be:

- stretched  
- tilted  
- rotated  
- flipped  

Once the grid changes, **every point automatically moves with it**.

---

## Why matrices describe transformations

A matrix is **not numbers doing magic**.

A matrix is just a storage box that says:

- Column 1 = where the first basis vector goes  
- Column 2 = where the second basis vector goes  

That’s all a matrix is doing.

---

## Core Idea 6: Why this matters in Computer Vision

Images are:

- grids of pixels  

Linear transformations:

- rotate images  
- stretch images  
- flip images  
- shear images  

When you apply a matrix to an image, you are literally **distorting the pixel grid**.

That’s why data augmentation works.

---

## Final Summary (Memorize This)

- A linear transformation reshapes the grid  
- Basis vectors generate the grid  
- Knowing where basis vectors go is enough  
- Squares turn into parallelograms, but structure is preserved  

---
