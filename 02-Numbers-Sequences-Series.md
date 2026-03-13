# Numbers, Sequences, and Series (ML-Math-Bridge Notes)

## Overview

- Introduces **sequences, limits, convergence, and infinite series**
- Forms the mathematical basis for:
  - calculus
  - probability
  - optimization
- Important for understanding **why optimization algorithms converge**

---

# 1. Sequences

## Definition

A **sequence** is an ordered list of numbers.

$$
\{a_n\}_{n=1}^{\infty}
$$

Represents

$$
a_1, a_2, a_3, a_4, \dots
$$

Each term belongs to the real numbers

$$
a_n \in \mathbb{R}
$$

---

## Example

Sequence

$$
a_n = \frac{1}{n}
$$

Terms

```
1, 1/2, 1/3, 1/4, 1/5, ...
```

---

## Sequences as Functions

A sequence can be viewed as a function

$$
a : \mathbb{N} \rightarrow \mathbb{R}
$$

Meaning

```
input  → natural number n
output → sequence value a_n
```

---

# 2. Subsequences

A **subsequence** is obtained by removing elements while preserving order.

Original sequence

```
1,2,3,4,5,6,7,8,...
```

Subsequence

```
2,4,6,8,...
```

Rule

```
order must remain unchanged
```

---

# 3. Convergence of Sequences

A sequence **converges** if it approaches a fixed number.

$$
\lim_{n\to\infty} a_n = a
$$

Meaning

```
sequence approaches value a
```

---

## Example

$$
a_n = \frac{1}{n}
$$

Values

```
1, 0.5, 0.33, 0.25, ...
```

Limit

$$
\lim_{n\to\infty} \frac{1}{n} = 0
$$

---

## Formal Definition

A sequence converges to \(a\) if

$$
|a_n - a| < \varepsilon
$$

for sufficiently large \(n\).

Meaning

```
terms become arbitrarily close to a
```

---

# 4. Divergent Sequences

A sequence is **divergent** if it does not converge.

## Oscillating Divergence

Example

$$
a_n = \sin(n)
$$

```
values oscillate between -1 and 1
```

## Divergence to Infinity

Example

$$
a_n = n
$$

```
1,2,3,4,5,...
```

$$
a_n \to \infty
$$

---

# 5. Famous Convergent Sequences

## Power Sequence

$$
x^n
$$

| x | Limit |
|---|---|
| \(0 \le x < 1\) | 0 |
| \(x = 1\) | 1 |
| \(x > 1\) | ∞ |

---

## Root Sequence

$$
x^{1/n}
$$

$$
\lim_{n\to\infty} x^{1/n} =
\begin{cases}
1 & x>0 \\
0 & x=0
\end{cases}
$$

---

## Important Limit

$$
\lim_{n\to\infty} \sqrt[n]{n} = 1
$$

Idea

$$
n^{1/n} = e^{\frac{\log n}{n}}
$$

Since

$$
\frac{\log n}{n} \to 0
$$

$$
e^0 = 1
$$

---

# 6. Growth Rates of Functions

Hierarchy

```
log n  <<  n  <<  2^n  <<  n!
```

| Function | Growth |
|---|---|
| log n | slow |
| n | moderate |
| 2^n | very fast |
| n! | extremely fast |

---

## Importance in Machine Learning

Applications

- algorithm complexity
- training time
- system scalability

Examples

```
Binary search → O(log n)
Linear search → O(n)
Brute force → O(2^n)
```

---

# 7. Big-O and Small-o Notation

## Big-O

$$
b_n = O(a_n)
$$

Meaning

```
b_n grows at most as fast as a_n
```

Formal definition

$$
|b_n| \le C a_n
$$

Examples

```
5n = O(n)
n + 10 = O(n)
```

---

## Small-o

$$
b_n = o(a_n)
$$

Meaning

```
b_n grows strictly slower than a_n
```

Example

$$
\log n = o(n)
$$

because

$$
\frac{\log n}{n} \to 0
$$

---

# 8. Real Numbers as Limits of Sequences

Sequence

$$
a_n = \left(1+\frac{1}{n}\right)^n
$$

Limit

$$
\left(1+\frac{1}{n}\right)^n \to e
$$

$$
e \approx 2.71828
$$

Observation

```
each term is rational
limit is irrational
```

Conclusion

```
real numbers arise as limits of rational sequences
```

---

# 9. Approximating the Number e

## Limit Definition

$$
e = \lim_{n\to\infty} \left(1+\frac{1}{n}\right)^n
$$

## Series Definition

$$
e = \sum_{n=0}^{\infty} \frac{1}{n!}
$$

---

# 10. Infinite Series

Definition

$$
\sum_{n=1}^{\infty} a_n
$$

Meaning

```
a1 + a2 + a3 + ...
```

---

## Partial Sums

$$
S_N = \sum_{n=1}^{N} a_n
$$

Series value

$$
\sum_{n=1}^{\infty} a_n = \lim_{N\to\infty} S_N
$$

---

# 11. Convergent vs Divergent Series

## Convergent

Example

$$
1 + \frac12 + \frac14 + \frac18 + ...
$$

## Divergent

Example

$$
1 + 1 + 1 + 1 + ...
$$

---

# 12. Geometric Series

Definition

$$
\sum_{n=0}^{\infty} q^n
$$

Example

```
1 + q + q^2 + q^3 + ...
```

## Formula

If

$$
|q| < 1
$$

then

$$
\sum_{n=0}^{\infty} q^n = \frac{1}{1-q}
$$

Example

$$
1 + \frac12 + \frac14 + \frac18 + ...
$$

Sum

$$
= 2
$$

---

# 13. Harmonic Series

$$
\sum_{n=1}^{\infty} \frac{1}{n}
$$

Even though

$$
\frac{1}{n} \to 0
$$

Series **diverges**

Important fact

```
a_n → 0 does NOT guarantee convergence
```

---

# 14. Alternating Series

Example

$$
\sum_{n=1}^{\infty} (-1)^{n+1}\frac{1}{n}
$$

Result

$$
= \log 2
$$

---

# 15. Connection to Machine Learning

## Optimization

Gradient descent sequence

$$
x_{n+1} = x_n - \eta \nabla f(x_n)
$$

Training succeeds when

```
sequence converges
```

---

## Probability

Used in

- Law of Large Numbers
- Central Limit Theorem

---

## Numerical Computation

Functions computed using series

```
exp(x)
sin(x)
log(x)
```

---

# Key Takeaways

- A **sequence** is an ordered list of numbers
- Convergence means approaching a fixed limit
- Some sequences diverge or oscillate
- **Big-O** compares growth rates
- Real numbers arise as limits of rational sequences
- A **series** is a sum of infinitely many terms
- **Geometric series** have closed-form sums
- **Harmonic series diverges**
