## Geometry intuition of vector space

Vectors can be represented as **points in space** using geometry (plots).

Even without labels on data points, by **seeing the distance between different clusters**, we can guess that they belong to **different classes**.

---

## Norm

A **norm** is a measure of **vector length**.

* Norm tells the **size or length of a vector**
* It is written as:
||x||

---

## Distance between two vectors

Distance between two vectors is defined as the **norm of their difference**.

Distance between two vectors = || X-Y ||

This is a **generalization of the hypotenuse concept**.

---

## Euclidean Norm (L2 Norm)

Euclidean norm is the **most commonly used norm**.

For a vector
For a vector $x = (x_1, x_2, \dots, x_n)$

$|x| = \sqrt{x_1^2 + x_2^2 + \dots + x_n^2}$


---

### Euclidean Norm in Different Dimensions

- **2D norm**

$$
|x| = \sqrt{x_1^2 + x_2^2}
$$

- **3D norm**

$$
|x| = \sqrt{x_1^2 + x_2^2 + x_3^2}
$$

---

## Meaning of Euclidean Norm

Euclidean norm gives the **length of a vector from the origin**.

* It measures the **shortest distance**
* It represents the **actual length of the vector**
* It is different from Manhattan distance

---

## Manhattan Norm (L1 Norm)

Manhattan norm is also called **L1 norm**.

It measures distance by **moving along coordinate axes** and is also known as **city block distance**.

---

### Definition

For a vector  

x = (x_1, x_2 ...., x_n)

the **Manhattan (L1) norm** is defined as:

$$
\|x\|_1 = |x_1| + |x_2| + \dots + |x_n|
$$

---

## Manhattan Distance

The Manhattan distance between two vectors is the **L1 norm of their difference**.

For vectors \(x\) and \(y\):

$$
d_1(x, y) = \|x - y\|_1
$$

$$
d_1(x, y) = |x_1 - y_1| + |x_2 - y_2| + \dots + |x_n - y_n|
$$

---

## Comparison with Euclidean Norm

- **L1 norm (Manhattan norm)** measures distance by **horizontal and vertical movements**
- **L2 norm (Euclidean norm)** measures the **straight-line distance**
- Manhattan distance is **not the shortest distance**
- Euclidean distance is the **shortest distance**

---

## When Manhattan Norm is Useful

- When movement is **restricted to axes**
- In grid-based problems
- In machine learning for **sparse data**
- Used in **L1 regularization** to promote sparsity

---

## Properties of a Norm

A function $\|\cdot\|$ is called a **norm** if it satisfies the following properties:

### 1. Non-negativity

$$
\|x\| \ge 0
$$

---

### 2. Zero Vector Property

$$
\|x\| = 0 \iff x = 0
$$

---

### 3. Triangle Inequality

$$
\|x + y\| \le \|x\| + \|y\|
$$

---

## Norm of Difference of Two Vectors

The norm of difference of two vectors is:

$$
\|x - y\| = \sqrt{(x_1 - y_1)^2 + (x_2 - y_2)^2 + \dots + (x_n - y_n)^2}
$$

This value represents the **distance between two vectors**.

---

## Distance Function

Distance function is defined as:

$$
d(x, y) = \|x - y\|
$$

---

## Properties of Distance Function

1. **Distance is non-negative**

$$
d(x, y) \ge 0
$$

2. **Distance is symmetric**

$$
d(x, y) = d(y, x)
$$

3. **Distance is zero if and only if both vectors are equal**

$$
d(x, y) = 0 \iff x = y
$$

