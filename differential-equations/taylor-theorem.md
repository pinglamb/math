---
layout: base
title: Differentiability &#124; Differential Equations
---

# Taylor's Theorem

Taylor's Theorem is a higher-order version of the tangent line approximation discussed in [differentiability](differentiability.md).
It states that a function $f$ of class $C^k$ on an interval $I$ containing the point $x = a$ is the sum of a certain polynomial of degree $k$
and a remainder term that vanishes more rapidly than $\|x-a\|^k$ as $x \to a$ (i.e. $o(h^k)$).

## Definition

The $k$-th order _Taylor polynomial_ $P_{a, k}$ for $f$ based at $a$ is defined by

$$
P_{a,k}(h) = \sum_{j=0}^k {f^{(j)}(a) \over j!} h^j
$$

We have $P^{(j)}(0) = f^{(j)}(a)$ for $0 \le j \le k$.

The $k$-th order _Taylor remainder_ $R_{a, k}$ is the difference

$$
R_{a, k}(h) = f(a + h) - P_{a, k}(h) = f(a + h) - \sum_{j=0}^k {f^{(j)}(a) \over j!} h^j
$$

## Integral Remainer I

Suppose that $f$ is of class $C^{k+1}$ on an interval $I \subset \mathbb{R}$ and $a \in I$, i.e. $f^{j}$ exists and is continuous on $I$ for $0 \le j \le k + 1$.
Then the remainder $R_{a,k}$ is given by

$$
R_{a,k}(h) = {h^{k+1} \over k!} \int_0^1 (1 - t)^k f^{k+1}(a + th) dt
$$

From this, we can see that $R_{a,k}(h) = o(h^{k+1})$ if $f^{k+1}$ exists.

## References

* [Gerald B. Folland _Advanced Calculus_, 2022 - Chapter 2.7](http://www.math.washington.edu/~folland/Homepage/AdvCalc24.pdf)
