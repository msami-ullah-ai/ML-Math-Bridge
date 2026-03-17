# 02 - Limits and Continuity

## 1. Limits

### Definition (intuitive)
A limit describes the value a function approaches as `x` gets close to some point `a`.

\[
\lim_{x \to a} f(x) = L
\]

Means: when `x` is near `a`, `f(x)` is near `L`.

---

### Key Idea
- Limit depends on behavior **around** a point
- Not necessary that `f(a) = L`

---

### Important Example
A function can:
- have a limit at `a`
- but be defined differently at `a`

---

### Limit Laws
If limits exist:

- Sum:
  \[
  \lim (f + g) = \lim f + \lim g
  \]

- Product:
  \[
  \lim (fg) = (\lim f)(\lim g)
  \]

- Constant:
  \[
  \lim (c f) = c \cdot \lim f
  \]

- Quotient:
  \[
  \lim \frac{f}{g} = \frac{\lim f}{\lim g}, \quad \text{if } \lim g \neq 0
  \]

---

### Special Limits (useful)
- \[
  \lim_{x \to 0} \frac{\sin x}{x} = 1
  \]

- \[
  \lim_{x \to 0} x \log x = 0
  \]

---

## 2. Continuity

### Definition
A function is continuous at `a` if:

\[
\lim_{x \to a} f(x) = f(a)
\]

---

### Intuition
- No jumps
- No breaks
- Smooth behavior

---

### Equivalent View
If `x → a`, then:
\[
f(x) → f(a)
\]

---

## 3. Properties of Continuous Functions

### Combination Rules
If `f` and `g` are continuous:

- `f + g` is continuous  
- `f * g` is continuous  
- `f / g` is continuous (if denominator ≠ 0)  
- Composition `f(g(x))` is continuous  

---

### Common Continuous Functions
These are continuous everywhere they are defined:

- Polynomials  
- Exponentials  
- Logarithms  
- Trigonometric functions  

---

## 4. Discontinuity

A function is NOT continuous if:
- limit does not exist  
- limit ≠ function value  

---

## 5. Key Takeaways

- Limit = approaching value  
- Limit ≠ actual value (in general)  
- Continuity = limit matches function  
- Continuous functions behave predictably  
- Combining continuous functions keeps continuity  

---
