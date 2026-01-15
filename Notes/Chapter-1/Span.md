# Span

The **span** of a set of vectors is the set of all vectors that can be obtained by taking linear combinations of those vectors.

In simple words:

> **Using these vectors, I can build any vector in the span.**

If the span equals the whole space, then:

> **Span = Space**

This means **every vector in the space can be written as a linear combination of the given vectors.**

---

## Understanding Span Geometrically

When we think about coordinates of a vector as scalars, the basic vectors are the ones those scalars scale.

If vectors are **collinear** or one of them is the **zero vector**,  
they cannot span the entire space — only a straight line.

The span of two vectors **v** and **w** is:

a·v + b·w  
where a and b are real numbers that vary.

So the span tells us **all the locations we can reach** by stretching and adding the vectors.

---

## Important Observations

- Taking span twice does nothing new.
- If one vector in the span is **redundant**, removing it does **not** change the span.
- If a vector **cannot** be written as a linear combination of others, it is **linearly independent** from them.

---

## Generating Set

Take a subset of vectors **S** from a vector space **V**.

If:

Span(S) = V

then **S** is called a **generating set** of the space.

---

## Minimal Generating Set

A generating set that uses the **fewest possible vectors** is called a **minimal generating set**.

It is the most compact version of the whole space —  
the smallest set of vectors needed to rebuild every vector in the space.

---

## Why This Matters in ML

Good features should:
- generate the full data space
- not be redundant
- carry maximum information with minimum size

This is exactly the idea behind good representations in machine learning.
