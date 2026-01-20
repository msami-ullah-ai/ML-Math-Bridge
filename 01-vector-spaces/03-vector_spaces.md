# Vector Spaces

In machine learning, almost everything is about turning data into vectors and working inside a space where math becomes easy.

A **vector space** is that place.

---

## Motivation

All ML is about treating data as points in mathematical space and reshaping that space until predicting labels becomes easy.

Each data point lives in a vector space.

If iris flower has 4 features, then each point lies in **4-D space**.  
That space is called the **vector space**.

When we subtract mean, divide by standard deviation, scale features —  
we are **transforming the space**.  
These are called **data transformations**.

Model’s job is to find transformations of vector space where labels become easy to separate.

---

## What Is a Vector Space?

A vector space is a set of vectors where we can:
- add vectors
- multiply a vector by a number (scalar)
- and the result always stays in the same space

In short:  
**A vector space is the world where our data lives and moves.**

---

## Vectors as Data Points

A vector is just an arrow from the origin.  
Its direction and length represent a data point.


## Operations in Vector Space

### Vector Addition

(2, 3) + (1, 2) = (3, 5)

This means moving the point.

### Scalar Multiplication

(2, 3) \times 2 = (4, 6)

This means stretching or shrinking the space.

Scaling is just moving points by stretching/shrinking the vector space.

---

## Why Vector Space Matters in ML

Feature scaling, normalization, standardization, PCA —  
all of them change the geometry of the vector space.

ML models learn by:
1. Viewing data as points in space
2. Applying transformations to the space
3. Finding a version of space where labels are easy to predict

So ML is really **learning inside vector spaces**.

---

## Final Definition (In Simple Words)

A vector space is a dimensional space where:
- vectors (data points) live
- vector addition and scalar multiplication are allowed
- results always stay inside the same space

That is why almost all of machine learning is built on linear algebra.

---

## Many Representations, One Idea

We can represent vectors as:
- arrows
- points
- lists of numbers

But they all describe the same thing:  
**a location in vector space.**
