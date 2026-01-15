# Basis

A **basis** is the smallest set of “building block” vectors from which we can construct every vector in the space.

Basis vectors are the **rulers of the space**.

Using only basis vectors and the operations of addition and scaling,  
we can reach every vector in the space.

---

## Core Idea

A basis is the **minimal set of vectors** that can build any vector in the space.  
The coordinates of a vector **depend on the basis you choose**.

Different bases give different coordinates,  
but the actual vector itself stays the same.

---

## What Makes a Basis?

Let:
- **V** = the whole vector space  
- **S** = some vectors chosen from V  

S is a basis of V **if and only if**:

### 1) S is linearly independent
- No vector in S is useless  
- Each one adds new information  
- None of them can be built using the others  

### 2) Span(S) = V
Using only vectors from S,  
we can build every desired vector in V.

So:

> **A basis is the smallest possible set of linearly independent vectors that spans the entire space.**

---

## Choosing a Basis

Which vectors we choose as basis is **flexible**,  
as long as they are independent and span the space.

Different choices give different coordinate systems.

---

## Key Points

- Bases are not unique, but the **number of vectors** in any basis of the same space is always the same.
- The number of vectors in a basis is called the **dimension** of the space.
- All bases of a space have the same size.
- Every vector space is guaranteed to have a basis.

---

## Subspaces

A **subspace** is a smaller space inside a bigger vector space  
that behaves like a full vector space on its own.

U is a subspace of V if:
- it is closed under vector addition
- it is closed under scalar multiplication

That means:
If we take any vectors from U and add them or scale them,  
the result must stay inside U.

### Trivial Subspaces
- {0} (just the origin)
- V itself

### Proper Subspace
Any subspace smaller than V but not {0}.
