# Differentiation and Continuity

This section builds the **foundation of differentiation** — before jumping into rules and neural network applications.

We will understand:
- What is continuity
- What is differentiation
- How they are connected
- Why they matter in Machine Learning

---

# 1. What is Continuity?

## Intuition

A function is **continuous** if you can draw its graph **without lifting your pen**.

No jumps  
No breaks  
No sudden gaps  

---

## Formal Definition

A function \( f(x) \) is continuous at \( x = a \) if:

$$
\lim_{x \to a} f(x) = f(a)
$$

---

## Meaning

For continuity, three things must be true:

1. \( f(a) \) is defined  
2. Limit exists  
3. Limit equals function value  

---

## Example of NOT continuous

A function with a jump:

$$
f(x) =
\begin{cases}
1 & x < 0 \\
2 & x \ge 0
\end{cases}
$$

At \( x = 0 \), left and right values differ → NOT continuous

---

## Example of continuous

$$
f(x) = x^2
$$

- Smooth curve  
- No breaks  

---

# 2. What is Differentiation?

## Core Idea

> Differentiation tells us **how fast something is changing**

---

## Geometric Meaning

Derivative = **slope of tangent line**

---

## Physical Meaning

Derivative = **rate of change**

Example:
- Position → derivative = velocity  
- Velocity → derivative = acceleration  

---

## Formal Definition

$$
f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}
$$

---

## Meaning of Formula

- Take a small step \( h \)  
- Measure change in output  
- Divide by change in input  

Gives slope at a point

---

# 3. Continuity vs Differentiability

## Important Relationship

> If a function is differentiable → it is continuous  
> But if a function is continuous → it may NOT be differentiable

---

## Example (Continuous but NOT differentiable)

$$
f(x) = |x|
$$

At \( x = 0 \):

- Continuous  
- Not differentiable  

---

## Why?

Left slope ≠ Right slope  

---

# 4. Intuition Behind Derivative

## Think like this

Derivative answers:

> “If I change input slightly, how much does output change?”

---

## Example

$$
f(x) = x^2
$$

At \( x = 2 \):

$$
f'(x) = 2x = 4
$$

Meaning:

- At \( x = 2 \), function is increasing at rate **4**

---

# 5. Small Change Interpretation

Let small change be \( h \):

$$
f'(x) \approx \frac{f(x+h) - f(x)}{h}
$$

---

## Meaning

> Derivative measures **local behavior**

---

# 6. Linear Approximation (VERY IMPORTANT)

A function near a point behaves like a line:

$$
f(x) \approx f(x_0) + f'(x_0)(x - x_0)
$$

---

## Meaning

- Complex function ≈ straight line locally  
- Makes analysis easier  

---

## Why important?

Used in:
- Optimization  
- Gradient descent  
- Neural networks  

---

# 7. Taylor Expansion (Basic Idea)

A function can be approximated as:

$$
f(x) = \sum_{k=0}^{n} \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k + o(|x-x_0|^n)
$$

---

## Meaning

- Functions ≈ polynomials  
- Helps simplify complex functions  

---

# 8. Why Differentiation Matters in ML

## Key Idea

Machine Learning = **optimization**

---

## Goal

Minimize error by adjusting parameters

---

## How?

We ask:

> “How does output change if we change parameters?”

---

## Answer

Derivative!

---

## Core ML Idea

- Derivative tells **direction to move**
- Used in:
  - Gradient Descent  
  - Backpropagation  

---

# 9. Two Ways to Compute Derivatives

---

## Method 1: Analytical (Exact)

Using rules:

- Power rule  
- Chain rule  
- Product rule  

---

## Method 2: Numerical (Approximate)

$$
\frac{f(x+h) - f(x)}{h}
$$

---

## When used?

- When formula unknown  
- For gradient checking  

---

# Final Summary

---

### Continuity
- No breaks in function  

---

### Differentiation
- Measures rate of change  

---

### Key Formula

$$
f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}
$$

---

### Differentiable ⇒ Continuous

---

### Derivative = sensitivity

---

### Local linearity

$$
f(x) \approx f(x_0) + f'(x_0)(x - x_0)
$$

---

### ML Connection

- Learning = adjusting parameters  
- Adjustment guided by derivatives  

---
