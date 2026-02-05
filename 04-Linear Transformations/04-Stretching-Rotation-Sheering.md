# Stretching (Scaling)

## Core Idea 

> scaling the x-direction and y-direction **independently**


---

## Start from the standard basis

Standard basis vectors:

- e₁ = (1, 0) → right  
- e₂ = (0, 1) → up  

They form:

- a unit square  
- width = 1  
- height = 1  

This is the square the book keeps drawing.

---

## What does a stretching matrix mean?

A stretching matrix looks like this :

- one value controls x-direction  
- one value controls y-direction  

Interpretation:

- c₁ → how much x stretches  
- c₂ → how much y stretches  

No mixing.  
No rotation.  
Just straight stretching.

---

<img width="269" height="232" alt="image" src="https://github.com/user-attachments/assets/3708d928-0cbc-4111-8880-560e5e73c883" />

---


##  What happens to basis vectors?

- e₁ becomes longer or shorter, stays on x-axis  
- e₂ becomes longer or shorter, stays on y-axis  

So:

- directions stay the same  
- only lengths change  

---

## What happens to the unit square?

Originally:

- width = 1  
- height = 1  

After stretching:

- width = c₁  
- height = c₂  

So the square becomes a **rectangle**.

---

## What happens to the entire grid?

Remember:

- the grid is made from copies of the unit square  

So:

- every square stretches the same way  
- the whole grid stretches uniformly  
- straight lines stay straight  

---

## Special cases 

- c₁ > 1 → stretch horizontally  
- 0 < c₁ < 1 → squash horizontally  
- c₁ < 0 → flip + stretch  

Same logic for vertical direction.

---


# Rotation

## Core Idea 

Rotation turns the entire grid by an angle α **without changing lengths or shapes**.

Only direction changes.

---

## Step 1: What does rotation mean geometrically?

- origin is pinned  
- everything rotates counter-clockwise by angle α  

What stays the same:

- lengths  
- angles  
- square shapes  

Rotation is a **rigid motion**.

---

## Columns = rotated basis vectors

For rotation:

- Column 1 = rotated e₁  
- Column 2 = rotated e₂  

Find these two → matrix is done.

---

## Rotate the basis vectors

- e₁ rotates to (cosα, sinα)  
- e₂ rotates to (−sinα, cosα)  

These two vectors become the columns of the rotation matrix.

This is **not a formula to memorize** —  
it comes directly from geometry.

---

<img width="534" height="225" alt="image" src="https://github.com/user-attachments/assets/536f4d21-e0a7-4f35-a449-abfaf2a34102" />

---

## Step 4: What happens to the grid?

- grid rotates  
- squares stay squares  
- orientation changes  

Nothing stretches or squashes.

---

## Key Properties 

- preserves lengths  
- preserves angles  
- determinant = 1  
- inverse = rotation by −α  


---

# Shearing

## Core Idea 

Shearing slants the grid:

> one direction stays fixed, the other slides sideways

---

## Physical intuition

Imagine:

- a stack of papers  
- bottom fixed  
- top pushed sideways  

Result:

- vertical lines tilt  
- squares become parallelograms  

That’s shearing.

---

## Step 2: What moves, what stays?

- one basis vector stays unchanged  
- the other shifts by some amount  

Origin stays fixed.  
Still linear.

---

## X-direction shear

- x-axis stays fixed  
- y-direction slides sideways  

Vertical lines tilt.

---

## Y-direction shear

- y-axis stays fixed  
- x-direction tilts upward  

Same idea, opposite roles.

---

<img width="326" height="226" alt="image" src="https://github.com/user-attachments/assets/1672a57b-4ce2-417b-a996-a54890332488" />

---

## Step 5: What happens to the unit square?

- bottom stays flat  
- top slides sideways  

Square → parallelogram

---

## Key Differences 

- Stretching → changes lengths  
- Rotation → changes directions  
- Shearing → changes angles  

Shearing does **not** preserve angles.

---

## Key Points

- Diagonal matrix → stretching  
- Cos–sin pattern → rotation  
- Ones on diagonal + off-diagonal value → shearing  

---

## Final One-Line Summary

Linear transformations reshape the grid.  
Stretching changes lengths, rotation changes direction, and shearing slants the grid — but all preserve straight lines and the origin.
