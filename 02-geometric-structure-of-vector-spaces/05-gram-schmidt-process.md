# Gram–Schmidt Orthogonalization Process

---

## Core Idea (Very Simple)

Gram–Schmidt is a method to:

- remove **overlapping information**
- step by step
- and build **orthogonal (and orthonormal) vectors**

In short:

> **Remove overlap, keep only new directions**

---

## What Gram–Schmidt Does

Gram–Schmidt is used to construct an **orthogonal set of vectors**  
from a given set of **linearly independent vectors**.

Important points:

- input vectors must be linearly independent  
- output vectors are orthogonal  
- if we normalize them, we get an **orthonormal basis**

---

## Big Intuition (Most Important)

Every vector can be split into two parts:

- part **along an existing direction** (overlap → redundant)  
- part **perpendicular to it** (new information)

Gram–Schmidt keeps only the **perpendicular part**.

---

## Step 1: First Vector

Start with the first vector:

e1 = v1

Nothing to remove yet.  
So we keep it as it is.

---

## Step 2: Second Vector (Remove Overlap)

Now take `v2`.

`v2` has two parts:

- part along `e1` (overlap, no new info)
- part perpendicular to `e1` (new direction)

### Projection (overlapping part)

proj_e1(v2) = ( <v2, e1> / <e1, e1> ) · e1

### Remove overlap

e2 = v2 - proj_e1(v2)
Now:

- `e2 ⟂ e1`
- `e2` contains only **new information**

---

## Geometric Meaning (Visualization)

To find `e2`:

1. Place `v2` and `e1` tail-to-tail  
2. Project `v2` onto `e1`  
3. Subtract the projection from `v2`  
4. The leftover arrow is perpendicular to `e1`  

That leftover vector **is `e2`**.

---

## Step 3: Third Vector (Remove All Previous Overlaps)

Now comes `v3`.

`v3` overlaps with:

- `e1`
- `e2`

So `v3` has **three parts**:

1. part along `e1`  
2. part along `e2`  
3. part perpendicular to both  

We only want part (3).

### Overlapping parts

Projection of v3 onto e1 (overlap with e1):

proj_e1(v3) = ( <v3, e1> / <e1, e1> ) · e1


Projection of v3 onto e2 (overlap with e2):

proj_e2(v3) = ( <v3, e2> / <e2, e2> ) · e2

### Total overlap

total_overlap = proj_e1(v3) + proj_e2(v3)

e3 = v3 - total_overlap
Now:

- `e3 ⟂ e1`
- `e3 ⟂ e2`
- `e3` is a **new independent direction**


## In Short (General Rule)

> **Each new orthogonal vector is obtained by subtracting from a vector everything already explained by previous orthogonal vectors.**

Or in simple words:

> Remove overlap.  
> Keep only what is new.

---

## General Gram–Schmidt Formula

For the k-th vector:

ek = vk - sum_{i=1 to k-1} proj_ei(vk)

Where:

proj_ei(vk) = ( <vk, ei> / <ei, ei> ) · ei

Meaning:

> Subtract from `vk` everything already explained by earlier vectors

---

## Final Step: Normalization (Optional but Important)

To get an **orthonormal basis**, normalize each `ek`:

uk = ek / ||ek||

Now:

- all vectors are perpendicular  
- all vectors have length 1  

This is the **Gram–Schmidt orthonormal basis**.

---

## Why Gram–Schmidt Works

Because it:

- repeatedly removes redundancy  
- keeps only new directions  
- ensures no overlap between vectors  

Projection gives **overlapping part**  
Subtraction gives **orthogonal part**

---

## Important Notes

- Input vectors **must be linearly independent**
- If at any step `ek = 0`, it means:
  - the new vector added no new direction
  - vectors are linearly dependent

---

## Why This Is Loved in ML & Math

Gram–Schmidt helps because:

- orthogonal directions don’t interfere  
- projections become simple  
- coefficients are easy to compute  
- information is cleanly separated  

This idea is used in:

- orthonormal bases  
- least squares  
- QR decomposition  
- PCA  

---

## One-Line Summary

> **Each new orthogonal vector is obtained by subtracting from a vector everything already explained by previous ones.**

That is Gram–Schmidt.
