# Reflection — Linear Transformations in the Euclidean Plane

## What we always start with

A vector before any transformation is simply:

[ x
  y ]

Meaning:

- move x units left or right  
- move y units up or down  

A **matrix** tells us how this vector changes.

That’s all linear transformations are.

---

## What is reflection 

Reflection = **mirror**

Just like looking at your face in a mirror:

- left becomes right  
- up becomes down  

Important:

- no stretching  
- no rotation  
- no bending  

Reflection only **flips**.

---

## Reflection across the Y-axis

This reflection flips left ↔ right.

### What happens to a general vector?

[ x
  y ]  →  [ -x
              y ]

Meaning:

- x changes sign  
- y stays the same  

### Geometric meaning

- points on the right move to the left  
- points on the left move to the right  
- height does not change  

👉 This is reflection across the **Y-axis**.

### What happens to basis vectors?

- e₁ = (1, 0) → (−1, 0)  
- e₂ = (0, 1) → (0, 1)  

That’s exactly what the book’s figure shows.

---

## Part 3: Reflection across the X-axis

This reflection flips up ↔ down.

### Apply to a general vector

[ x
  y ]  →  [  x
            -y ]

Meaning:

- x stays the same  
- y changes sign  

👉 Up becomes down  
👉 Down becomes up  

This is reflection across the **X-axis**.

---

## Very important idea (why basis vectors matter)

The book keeps drawing arrows for e₁ and e₂ because:

> If you know what happens to the basis vectors,  
> you know what happens to the entire plane.

That’s why every picture focuses on basis vectors first.

---

## Swapping e₁ and e₂ (confusing part, now easy)

Now the book does something different.

Instead of just flipping signs, it **swaps x and y**.

### What does that mean?

[ x
  y ]  →  [ y
            x ]

Example:

- (2, 5) → (5, 2)

This is a mirror along the line **y = x**.

### What happens to basis vectors?

- e₁ = (1, 0) → (0, 1) = e₂  
- e₂ = (0, 1) → (1, 0) = e₁  

That’s why the book says:

> “Swapping e₁ and e₂”

And that’s exactly what the picture shows.

---

## Why does the book mention rotation here?

Reflection alone can:

- flip left ↔ right  
- flip up ↔ down  

But reflection alone **cannot swap axes**.

So the book explains:

> rotation + reflection can swap basis vectors

This is **extra insight**, not a new concept.

You don’t need it to understand reflection itself.

Core idea remains:

- matrix flips coordinates  
- look at what changes sign or position  

---

## Reflection in 3D 

In 3D, reflection works the same way.

Example: flip the z-direction.

[ x
  y
  z ]  →  [ x
             y
            -z ]

Meaning:

- x stays same  
- y stays same  
- z flips  

 This is exactly how a real mirror works in 3D.

---

## Multiple reflections

You can flip more than one axis.

Example:

- flip y  
- flip z  

Still a linear transformation.  
Still origin stays fixed.

The book mentions this to prepare you for determinants later.

---

## Final Mental Summary 

- Reflection = mirror  
- −1 means flip  
- swapping x and y = mirror along y = x  
- basis vectors show everything  
- shapes don’t stretch — only flip  

