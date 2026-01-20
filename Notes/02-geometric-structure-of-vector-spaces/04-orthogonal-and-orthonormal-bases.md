# Orthogonal and Orthonormal Bases

---

## Orthogonal Basis

An **orthogonal basis** consists of vectors that are:

- pairwise orthogonal  
- dot product between any two different vectors is zero  
- vectors can have **any length**

In simple words:

Orthogonal basis vectors are at right angles to each other.

⟨v_i , v_j⟩ = 0 for i ≠ j
---

## Orthonormal Basis

An **orthonormal basis** is:

- orthogonal  
- and **normalized**

That means:

- vectors are perpendicular  
- each vector has length **1**

So:

Orthogonal + Normalized = Orthonormal

⟨v_i , v_j⟩ = 0 for i ≠ j
⟨v_i , v_i⟩ = 1
---

## What Does Normalized Mean?

A vector is **normalized** if its length is 1.

Normalization is done by:

v_normalized = v / ||v||
Important intuition:

- direction stays the same  
- magnitude (size) is removed  

Normalization **keeps direction, removes scale**.

---

## Sideways Intuition

Orthogonal vectors are like **sideways directions**.

- one direction does not interfere with another  
- no overlap  
- no repetition of information  

---

## Why Orthonormal Bases Are Special

If a basis is **orthonormal**, then:

To find how much of a vector goes in a basis direction,  
we just take a **dot product**.

coefficient = ⟨x , basis_vector⟩

No solving equations.  
No interference from other directions.

---

## Why Orthogonal Bases Are Loved

Orthogonal bases are loved because:

- they separate information clearly  
- no overlap  
- no redundancy  
- no repetition  

Each direction carries **independent information**.

---

## Projection in an Orthogonal Basis

In an orthogonal basis:

- projection onto one direction depends only on that direction  
- other axes do **not interfere**

So to find how much of a direction exists in a vector:

Just project onto it.

---

## Normalization in Machine Learning

Normalization is used in ML to remove scale effects.

Example (Min–Max Scaling):

x_norm = (x - x_min) / (x_max - x_min)

Purpose:

- removes size / magnitude bias  
- keeps relative behavior  

---

## Why Normalization Is Important in ML

Normalization helps because:

- distance-based models (like KNN) compare behavior, not size  
- large-valued features stop dominating  
- similarity becomes fair  

Normalization removes **scale bias**.

---

## L2 Normalization (Very Common)

L2 normalization scales vectors to **unit length**:

x_normalized = x / ||x||

After this:

- similarity depends only on direction  
- magnitude does not matter  

This is what cosine similarity uses.

---

## Without Normalization

If data is **not normalized**:

- large-scale features dominate  
- distance measures size, not behavior  
- model becomes biased  
- model confuses intensity with similarity  

---

## After Normalization

After normalization:

- similarity depends purely on angle  
- cosine similarity becomes meaningful  
- comparison between data points is fair  

The model asks:

Do these points share the same **pattern**?  
Not: who has larger values?

---

## Practical Example

Suppose we compare users using two features:

- Age: 18–60  
- Annual Income: 20k–200k  

Users:

- User A → (25, 30k)  
- User B → (26, 120k)

### Without Normalization

- income dominates distance  
- model thinks users are very different  
- behavior similarity is ignored  

### With Normalization

- age and income contribute equally  
- similarity reflects real behavior  
- comparison becomes meaningful  

---

## Final Takeaway

Normalization removes scale effects so ML models:

- measure real similarity  
- focus on direction (pattern)  
- avoid bias from large values  

Orthonormal bases make computation simple:

- projections are easy  
- coefficients are dot products  
- information is cleanly separated  

This is why orthonormal bases are everywhere in linear algebra and machine learning.
