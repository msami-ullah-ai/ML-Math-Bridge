# Functions and Their Role in Machine Learning

## 1. Functions in Machine Learning

In machine learning, a **predictive model** can be viewed as a mathematical function.

A model takes **input data** and produces an **output prediction**.

Example models:

- **Linear Regression**

$$
f(x) = Ax
$$

- **Logistic Regression**

$$
f(x) = \sigma(Ax)
$$

- **Neural Networks**

A neural network is essentially a **sequence of functions applied one after another**.

$$
f(x) = f_3(f_2(f_1(x)))
$$

So we can think of ML models as **multivariate parametric functions**.

---

# 2. Training a Model

Training a machine learning model means:

> Finding parameters that **minimize prediction error**.

This optimization is done using **differentiation**.

Derivative definition:

$$
f'(x_0) =
\lim_{x \to x_0}
\frac{f(x) - f(x_0)}{x - x_0}
$$

Differentiation is the key idea behind **Gradient Descent**, which trains neural networks.

### Gradient Descent Idea

1. Start with random parameters
2. Compute prediction error
3. Compute gradient (derivative of error)
4. Move parameters in the direction that reduces error
5. Repeat until convergence

---

# 3. Mathematical Definition of a Function

A function maps elements from one set to another.

$$
f : A \rightarrow B
$$

Meaning:

- Each element in **A (domain)** is assigned
- Exactly **one element in B (codomain)**.

### Formal Definition

A **function** is a relation where every element in the **domain** is paired with **exactly one element in the codomain**.

---

# 4. Important Terminology

### Domain

The **set of all possible inputs**.

Example:

If

$$
f(x) = x^2
$$

then the domain is all real numbers.

---

### Codomain

The **set of values the function could possibly output**.

---

### Range

The **actual set of outputs produced by the function**.

Range is always a **subset of the codomain**.

---

# 5. Types of Functions

## Injective Function (One to One)

A function is **injective** if different inputs produce different outputs.

Mathematically:

$$
f(a) = f(b) \Rightarrow a = b
$$

Meaning:

No two different inputs map to the same output.

---

## Surjective Function (Onto)

A function is **surjective** if every element in the codomain is mapped by some input.

Meaning:

$$
Range = Codomain
$$

---

## Bijective Function

A function is **bijective** if it is:

- Injective (one-to-one)
- Surjective (onto)

This means every input maps to a unique output and every output has a corresponding input.

---

# 6. Inverse Functions

If a function is **bijective**, it has an **inverse function**.

If

$$
f : A \rightarrow B
$$

then

$$
f^{-1} : B \rightarrow A
$$

And

$$
f^{-1}(f(x)) = x
$$

or

$$
f(f^{-1}(x)) = x
$$

---

# 7. Connection to Linear Algebra

A **linear transformation** is a function of the form:

$$
T(x) = Ax
$$

If matrix \(A\) is invertible:

$$
T^{-1}(x) = A^{-1}x
$$

So:

$$
T^{-1}(T(x)) = x
$$

Therefore:

> A linear transformation is invertible **if and only if it is bijective**.

---

# 8. Conditions for Matrix Invertibility

A matrix \(A\) is invertible if:

1. Determinant is non-zero

$$
\det(A) \neq 0
$$

2. Columns are linearly independent

3. Kernel contains only the zero vector

$$
Kernel(A) = \{0\}
$$

4. The transformation is bijective

---

# 9. Function Composition

Applying one function after another is called **composition**.

If we have two functions:

$$
f(x), \quad g(x)
$$

Their composition is:

$$
(f \circ g)(x) = f(g(x))
$$

Process:

1. First apply \(g(x)\)
2. Then apply \(f(x)\)

---

# 10. ReLU Function

One of the most important functions in modern neural networks is **ReLU**.

ReLU stands for **Rectified Linear Unit**.

Definition:

$$
ReLU(x) = \max(0, x)
$$

Piecewise form:

$$
ReLU(x) =
\begin{cases}
0 & x < 0 \\
x & x \ge 0
\end{cases}
$$

### Why ReLU is Important

ReLU:

- Introduces **non-linearity**
- Allows neural networks to learn complex patterns
- Makes training faster

---

# 11. Neural Network Layer

In neural networks, a layer performs:

$$
z = Wx + b
$$

Then applies activation:

$$
a = ReLU(z)
$$

So each layer performs a **transformation of the input features**.

---

# 12. Functions as Transformations

In machine learning:

> Functions transform data from one representation to another.

Example:

Image brightness transformation:

$$
new\_pixel = old\_pixel + c
$$

This modifies the image brightness.

---

# 13. Neural Networks as Chains of Transformations

Neural networks apply many transformations sequentially.

So we can write:

$$
NN(x) = f_3(f_2(f_1(x)))
$$

Each layer modifies the feature representation.

---

# 14. How Images Become Numbers

Neural networks cannot process images directly.

Images must be converted into **numbers**.

### Step 1: Pixels

Images consist of pixels arranged in a grid.

Example:

- width = 100
- height = 100

Total pixels:

```
100 × 100
```

---

### Step 2: Color Channels

Each pixel has color values.

Typically **RGB**:

```
(R, G, B)
```

Example:

| Color | RGB Value |
|------|------|
| Red | (255,0,0) |
| Green | (0,255,0) |
| Blue | (0,0,255) |
| White | (255,255,255) |

---

### Step 3: Image as a Tensor

Images are stored as:

```
Height × Width × Channels
```

Example:

```
100 × 100 × 3
```

Neural networks process images as **numerical tensors**.

---

# 15. Functions as Callable Objects (Python Concept)

In Python, objects can behave like functions using a special method:

```
__call__()
```

Example:

```
class Linear:
    def __init__(self, a, b):
        self.a = a
        self.b = b

    def __call__(self, x):
        return self.a*x + self.b
```

Usage:

```
f = Linear(2, -1)
f(3)
```

Python internally executes:

```
f.__call__(3)
```

---

# 16. Why ML Frameworks Use Callable Objects

Machine learning frameworks prefer **objects instead of simple functions**.

Because objects can store **parameters**.

So a model becomes:

```
model = function + stored parameters
```

This allows models to maintain learned weights.

---

# 17. Composition in Object-Oriented Style

Neural networks are implemented as **function compositions**.

Example:

```
Layer3(Layer2(Layer1(x)))
```

Which mathematically means:

$$
f_3(f_2(f_1(x)))
$$

---

# 18. Implementing Composition in Python

Example:

```
def compose(f, g):

    def func(x):
        return f(g(x))

    return func
```

Usage:

```
h = compose(linear, sigmoid)
h(3)
```

---

# 19. Key Idea

Neural networks are essentially:

> A sequence of functions applied to data.

Each layer transforms the input representation.

So a neural network can be viewed as:

```
NN = chain of transformations
```

---

# Final Summary

Machine learning models can be understood using **functions**.

Key ideas:

- A model is a **function**
- Training uses **differentiation**
- Neural networks are **function compositions**
- Images are converted into **numerical tensors**
- ML frameworks implement functions as **callable objects**

This mathematical perspective helps connect:

- Calculus
- Linear Algebra
- Programming
- Machine Learning
