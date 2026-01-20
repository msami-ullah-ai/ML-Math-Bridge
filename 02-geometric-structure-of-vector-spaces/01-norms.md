# Geometry intuition of vector spaces

Vectors can be represented as **points in space** using geometry (plots).

Even without labels on data points, by **looking at distances between clusters**, we can often guess that they belong to different classes.
This geometric idea is the foundation of many machine learning algorithms.

To talk about *length*, *distance*, and *geometry*, we need the concept of a **norm**.

---

## Norm (idea)

A **norm** is a measure of the **size or length of a vector**.

* Norm tells *how big* a vector is
* It is written as: `||x||`
* Length can never be negative

---

## Norm (formal definition)

A norm is a **function** that:

* takes a vector from a vector space
* returns a **non-negative real number**

Mathematically:

```
|| · || : V → [0, ∞)
```

---

## Properties of a norm

A function is called a **norm** if it satisfies the following properties:

### 1. Positive definiteness

```
||x|| ≥ 0
||x|| = 0  ⇔  x = 0
```

Length cannot be negative, and only the **zero vector** has zero length.

---

### 2. Positive homogeneity (scaling property)

```
||αx|| = |α| ||x||
```

Scaling a vector scales its length by the **same absolute factor**.

Example:
If `||x|| = 5`, then `||-3x|| = 15`

---

### 3. Triangle inequality

```
||x + y|| ≤ ||x|| + ||y||
```

This means the **shortest path** between two points is a **straight line**.

---

## Distance between two vectors

Distance between two vectors is defined using a norm.

```
Distance(x, y) = ||x − y||
```

This is a **generalization of the hypotenuse concept** from geometry.

---

## Euclidean norm (L2 norm)

The **Euclidean norm** is the most commonly used norm.

For a vector:

```
x = (x₁, x₂, …, xₙ)
```

The L2 norm is:

```
||x||₂ = √(x₁² + x₂² + … + xₙ²)
```

### In different dimensions

* **2D**

```
||x||₂ = √(x₁² + x₂²)
```

* **3D**

```
||x||₂ = √(x₁² + x₂² + x₃²)
```

---

### Meaning of L2 norm

* Gives length of the vector from the **origin**
* Measures **straight-line distance**
* Represents the **actual geometric length**
* Most commonly used in ML

Used in:

* Gradient Descent
* Loss functions
* Neural Networks

---

## Manhattan norm (L1 norm)

The **Manhattan norm** (or L1 norm) measures distance by moving **along coordinate axes**.

```
||x||₁ = |x₁| + |x₂| + … + |xₙ|
```

It is also called **city-block distance**.

---

### Manhattan distance between two vectors

```
d₁(x, y) = ||x − y||₁
         = |x₁ − y₁| + |x₂ − y₂| + … + |xₙ − yₙ|
```

---

### Comparison: L1 vs L2

* **L1 norm**:

  * Horizontal + vertical movement
  * Encourages sparsity
* **L2 norm**:

  * Straight-line distance
  * Smooth and stable learning

Euclidean distance is shortest in **continuous space**,
Manhattan distance is shortest when movement is **restricted to axes**.

---

### When L1 norm is useful

* Many features are irrelevant
* Simple model is desired
* Feature selection matters more

Used in:

* **Lasso Regression**

L1 basically says:

> “Use only what you really need.”

---

## L∞ norm (Max norm)

The **L∞ norm** selects the **largest absolute component** of a vector.

```
||x||∞ = max(|x₁|, |x₂|, …, |xₙ|)
```

It answers the question:

> “How bad is the worst component?”

### When to use

* Worst-case error matters
* Safety and robustness problems
* Nothing is allowed to go out of control

---

## How to choose a norm

* Remove features → **L1**
* Smooth, stable learning → **L2**
* Fear extreme values → **L∞**

---

## p-Norm (general norm)

Different values of `p` give different norms.

```
||x||ₚ = ( Σ |xᵢ|ᵖ )^(1/p)   ,   p ∈ [1, ∞)
```

Steps:

1. Take absolute value of each component
2. Raise to power `p`
3. Add all
4. Take `p`-th root

Special cases:

* `p = 1` → L1 (Manhattan)
* `p = 2` → L2 (Euclidean)
* `p → ∞` → L∞ (Max norm)

---

## Mean Squared Error (MSE)

MSE is a **loss function** used in ML.

It is simply the **squared L2 norm of the error vector**, divided by number of samples.

Error vector:

```
e = y − ŷ
```

MSE:

```
MSE = (1/n) Σ (errorᵢ)²
```

Meaning:

1. Take L2 norm of error
2. Square it
3. Divide by `n`

---

## Norms and model complexity

Let model parameters be:

```
θ = (θ₀, θ₁, θ₂, …)
```

* Large parameter norms → complex model
* Small parameter norms → smooth model
* Large norms often cause **overfitting**

Norms help us **control model complexity**.

---

## Regularized loss function

Final loss used in ML:

```
Loss = MSE + λ ||θ||ₚ
```

* `MSE` → prediction error
* `||θ||ₚ` → model complexity
* `λ` → controls strength of regularization
* `p` → type of simplicity enforced

Large parameter norm ⇒ model may overfit training data.

---

## Metric and norm-induced distance

A **metric** defines distance between two points.

When distance is defined using a norm:

```
d(x, y) = ||x − y||
```

This is called a **norm-induced metric**.

It gives geometry to vector spaces.

---

## Final takeaway

Norms help us:

* Measure vector size
* Define distance
* Measure prediction error
* Control model complexity

Used everywhere in ML:

* KNN
* Loss functions
* Regularization
* Optimization

