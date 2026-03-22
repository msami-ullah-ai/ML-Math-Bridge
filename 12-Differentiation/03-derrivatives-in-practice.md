# Derivatives in Practice

Now that we understand **what derivatives are**, it’s time to see how they are actually **used in real problems**, especially in **Machine Learning**.

This section is extremely important because:
> This is where differentiation becomes actual **useful**, not just theoretically.

---

# 1. Why We Need Practical Differentiation

Using the definition:

$$
f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}
$$

is:

- Slow  
- Complicated  
- Not practical  

---

## So what do we do?

We use:

> **Rules of differentiation**

---

# 2. Basic Derivative Rules (Toolbox)

---

## Power Rule

$$
\frac{d}{dx}(x^n) = nx^{n-1}
$$

---

## Trigonometric Functions

$$
\frac{d}{dx}(\sin x) = \cos x
$$

$$
\frac{d}{dx}(\cos x) = -\sin x
$$

---

## Exponential Function

$$
\frac{d}{dx}(e^x) = e^x
$$

---

## Logarithmic Function

$$
\frac{d}{dx}(\log x) = \frac{1}{x}
$$

---

# 3. Combining Functions

Real-world functions are not simple.  
They are made by combining smaller functions.

---

## Sum Rule

$$
(f + g)' = f' + g'
$$

---

## Product Rule

$$
(fg)' = f'g + fg'
$$

---

## Chain Rule (MOST IMPORTANT)

$$
(f \circ g)'(x) = f'(g(x)) \cdot g'(x)
$$

---

# 4. Understanding the Chain Rule

---

## What is happening?

If:

$$
y = f(g(x))
$$

Then:

- \( g(x) \) = inner function  
- \( f(x) \) = outer function  

---

## Rule

> Derivative = outer derivative × inner derivative

---

## Example

$$
y = (x^2 + 1)^3
$$

---

### Step 1: Identify

- Inner = \( x^2 + 1 \)  
- Outer = \( u^3 \)

---

### Step 2: Differentiate

$$
= 3(x^2 + 1)^2 \cdot 2x
$$

---

### Final Answer

$$
= 6x(x^2 + 1)^2
$$

---

# 5. Function Composition

---

## Definition

$$
(f \circ g)(x) = f(g(x))
$$

---

## Meaning

> Output of one function becomes input of another

---

## Example

- \( g(x) = x + 2 \)  
- \( f(x) = x^2 \)

$$
f(g(x)) = (x+2)^2
$$

---

# 6. Neural Networks = Function Composition

---

## Key Insight

A neural network is just:

$$
f(x) = f_3(f_2(f_1(x)))
$$

---

## Each layer is a function

- Layer 1 → \( f_1 \)  
- Layer 2 → \( f_2 \)  
- Layer 3 → \( f_3 \)

---

## This is exactly:

> Function composition

---

# 7. Chain Rule in Neural Networks

---

## Important

To train a model, we compute:

$$
\frac{d(\text{output})}{d(\text{input})}
$$

---

## Using chain rule:

$$
f_3'(f_2(f_1(x))) \cdot f_2'(f_1(x)) \cdot f_1'(x)
$$

---

## Meaning

> Multiply derivatives layer by layer

---

# 8. Backpropagation (Core ML Concept)

---

## Definition

> Backpropagation = applying chain rule backward

---

## Process

### Forward pass:

x → f1 → f2 → f3 → output

---

### Backward pass:

f3' × f2' × f1'


---

## Purpose

- Find how each parameter affects output  
- Update weights  

---

# 9. Activation Functions

---

## Sigmoid

$$
\sigma(x) = \frac{1}{1 + e^{-x}}
$$

---

### Derivative

$$
\sigma'(x) = \sigma(x)(1 - \sigma(x))
$$

---

## Insight

- Large in middle → fast learning  
- Small at edges → slow learning  

---

---

## ReLU

$$
\text{ReLU}(x) =
\begin{cases}
x & x > 0 \\
0 & x \le 0
\end{cases}
$$

---

### Derivative

$$
\text{ReLU}'(x) =
\begin{cases}
1 & x > 0 \\
0 & x < 0
\end{cases}
$$

---

## Insight

- Positive → learning happens  
- Negative → neuron inactive  

---

# 10. Numerical Differentiation

---

## When used?

- When exact derivative is unknown  

---

## Forward Difference

$$
\frac{f(x+h) - f(x)}{h}
$$

---

## Backward Difference

$$
\frac{f(x) - f(x-h)}{h}
$$

---

## Symmetric Difference (BEST)

$$
\frac{f(x+h) - f(x-h)}{2h}
$$

---

## Insight

> Using both sides gives better approximation

---

# 11. Big Picture

---

### Functions → combined → composition  
### Composition → chain rule  
### Chain rule → backpropagation  
### Backpropagation → training neural networks  

---

# Final Takeaway

---

> Differentiation is not just math…

It is the **engine behind learning in AI**.

---

## One line to remember

> Neural networks learn because we can compute derivatives.
