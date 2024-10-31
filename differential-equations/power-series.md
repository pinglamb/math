---
layout: base
title: Power Series &#124; Differential Equations
---

# Power Series

A power series in $(x - a)$ or a power series centered at $a$ or a power series about $a$ is of the form

$$
\sum_{n=0}^{\infty} c_n (x - a)^n = c_0 + c_1 (x - a) + c_2 (x - a)^2 + ...
$$

## Convergence

As it is an infinite sum, the domain of it is the interval of $x$ where the series converges.

For a given power series about $a$, there are only three possibilities

1. The series converges only when $x = a$

2. The series converges for all $x$

3. There is a postiive number $R$ such that the series converges if $\|x - a\| < R$ and diverges if $\|x - a\| > R$

For (3), $R$ is called the radius of convergence (therefore the power series is said to be about $a$).

For the edge case when $x - a = \pm R$, the convergence check has to be done separately.

## Representation of functions

Power series can be used to represent functions, for example

$$
{1 \over 1 - x} = 1 + x + x^2 + ... = \sum_{n=0}^{\infty} x^n
$$

with domain $\|x\| < 1$.

Base on that, we can derive the power series for some functions, such as

$$
{1 \over x+2} = \sum {1 \over 2\left[1 - \left(-{x \over 2}\right) \right]} = {1 \over 2} \sum_{n=0}^{\infty} \left(-{x \over 2}\right)^n = \sum_{n=0}^{\infty} {(-1)^n \over 2^{n+1}}x^n
$$

which converges if $\|-x/2\| < 1$, meaning $\|x\| < 2$.

## Differentiation and Integration

We can differentiate and integrate a power series term-by-term to obtain another power series, which has the same radii of convergence as the original power series.

With this, we can derive the power series for some functions, for example, as

$$
\begin{align*}
{1 \over (1-x)^2} &= {\mathrm{d} \over \mathrm{d}x} {1 \over 1-x} \\
&= 1 + 2x + 3x^2 + ... \\
&= \sum_{n=0}^{\infty} (n+1)x^n
\end{align*}
$$

and it has the same radius of convergence $R = 1$.

On the other hand, we have

$$
\begin{align*}
\ln(1+x) &= \int {1 \over 1+x} \mathrm{d}x = \int (1 - x + x^2 - x^3 + ...) \mathrm{d}x \\
&= x - {x^2 \over 2} + {x^3 \over 3} - {x^4 \over 4} + ... + C \\
&= \sum_{n=1}^{\infty} {(-1)^{n - 1} \over n} x^n + C
\end{align*}
$$

Substitude $x = 0$, we have $C = \ln 1 = 0$ and the radius of convergence is $R = 1$.

## Taylor's Theorem

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
