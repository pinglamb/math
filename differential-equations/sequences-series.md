---
layout: base
title: Sequences and Series &#124; Differential Equations
---

# Sequences and Series

## Limit of Sequences

A sequence $\Set{a_n}$ has a limit $L$ and we write

$$
\lim_{n \to \infty} a_n = L
$$

if for every $\varepsilon > 0$ there is a corresponding integer $N$ such that

$$
\forall n > N, \quad |a_n - L| < \varepsilon
$$

It is similar to the definition of limit of a function $f(x)$, therefore

$$
\lim_{x \to \infty} f(x) = L \text{ and } f(n) = a_n \implies \lim_{n \to \infty} a_n = L
$$

The sequence is convergent if the limit exists, otherwise it is divergent.

For sequence diverges to $\infty$, it means for all positive number $M$, there is an integer $N$ such that

$$
\forall n > N, \quad a_n > M
$$

### Properties

For alternating sequence, it might be useful for the fact that

$$
\lim_{n \to \infty} |a_n| = 0 \implies \lim_{n \to \infty} a_n = 0
$$

_Proof_. As

$$
-|a_n| \le a_n \le |a_n| \quad \text{and} \quad \lim_{n \to \infty} |a_n| = \lim_{n \to \infty} -|a_n| = 0
$$

By Squeeze Theorem, $\lim_{n \to \infty} a_n = 0$

For example,

$$
\lim_{n \to \infty} {(-1)^n \over n} = \lim_{n \to \infty} \left| {(-1)^n \over n} \right| = 0
$$

Also, if $\lim_{n \to \infty} a_n = L$ and function $f$ is continuous at $L$, then

$$
\lim_{n \to \infty} f(a_n) = f(L)
$$

_Proof_. As $f$ is continuous at $L$, i.e.

$$
\lim_{x \to L} f(x) = f(L)
$$

Given an $\varepsilon$, there exists $\delta$ such that

$$
0 < |x - L| < \delta \implies |f(x) - f(L)| < \varepsilon
$$

Since $\lim_{n \to \infty} a_n = L$, there exists $N$ such that

$$
n > N \implies |a_n - L| < \delta
$$

Combining the statements, given any $\varepsilon > 0$, we can find $N$ such that whenever $n > N$,

$$
|a_n - L| < \delta
$$

which implies

$$
|f(a_n) - f(L)| < \varepsilon
$$

Hence,

$$
\lim_{n \to infty} f(a_n) = f(L)
$$

### Monotonic and Bounded Sequences

If $a_n < a_{n+1}$ for all $n \ge 1$, $\Set{a_n}$ is called increasing.
If $a_n > a_{n+1}$ for all $n \ge 1$, $\Set{a_n}$ is called decreasing.
A sequence is monotonic if it is either increasing or decreasing.

If $a_n \le M$ for all $n \ge 1$, $\Set{a_n}$ is bounded above.
If $m \le a_n$ for all $n \ge 1$, $\Set{a_n}$ is bounded below.
A sequence is bounded if it is bounded above and below.

Every monotonic, bounded sequence is convergent.

_Proof_. If $\Set{a_n}$ is bounded above, there exists a least upper bound $L$.
Given $\varepsilon > 0$, $L - \varepsilon$ is not an upper bound, hence for some integer $N$

$$
L - \varepsilon < a_N \le L
$$

As $a_n$ is increasing, $a_n ge a_N$ for all $n > N$. Thus,

$$
L - \varepsilon < a_n \le L
$$

Hence,

$$
\lim_{n \to \infty} a_n = L
$$

## Series

A series is the infinite sum of a sequence $a_n$. Let $s_n$ denote its $n$th partial sum

$$
s_n = a_1 + a_2 + ... + a_n
$$

$\Set{s_n}$ is a sequence and $s$ is the sum of the series if the series is convergent and $\lim_{n \to \infty} s_n = s$.

If the series is convergent, it implies the underlying sequence $\Set{a_n}$ has limit $\lim_{n \to \infty} a_n = 0$ as

$$
\lim_{n \to \infty} a_n = \lim_{n \to \infty} (s_n - s_{n-1}) = s - s = 0
$$

The converse is not true though for example the harmonic series has the terms approaching $0$ but the sum is divergent.

The counterpositive can be a test for divergence, i.e. if $\lim_{n \to \infty} a_n \not = 0$, $\Set{s_n}$ is divergent.

### Integral Test

Consider the series

$$
\sum_{n=1}^{\infty} {1 \over n^2} = {1 \over 1^2} + {1 \over 2^2} + {1 \over 3^2} + ...
$$

Geometrically, we can form rectangles under the graph of $y = 1/x^2$, each with a unit width and height eqauls to the value of function.
The sum of the area of the rectangles equals to the sum of the series. Consider all the terms excluding the first one $1/1^2$,
it has to be less than the area under the function from $1$ to $\infty$. Hence,

$$
\sum_{n=1}^{\infty} {1 \over n^2} < {1 \over 1^2} + \int_{1}^{\infty} { 1 \over x^2} \mathrm{d}x = 1 + 1 = 2
$$

As the partial sum $\Set{s_n}$ is increasing and bounded above, the series is convengent.

<p align="center"><img src="../images/integral-test-below.png" alt="" /></p>

On the other hand, we can also form rectangles with tops lie above the curve to show the series is divergent. Consider the series

$$
\sum_{n=1}^{\infty} {1 \over \sqrt{n}} = {1 \over \sqrt{1}} + {1 \over \sqrt{2}} + {1 \over \sqrt{3}} + ...
$$

We have

$$
\sum_{n=1}^{\infty} {1 \over \sqrt{n}} > \int_{1}^{\infty} {1 \over \sqrt{x}} \mathrm{d}x = \infty
$$

So, the series is divergent.

<p align="center"><img src="../images/integral-test-above.png" alt="" /></p>

Therefore, we can conclude that with $f$ being a continuous, positive, decreasing function on $[1, \infty)$ and $f(n) = a_n$,
if $\int_{1}^{\infty} f(x) \mathrm{d}x$ is convengent/divergent, so as $\sum_{n=1}^{\infty} a_n$.

We can also use the integral to estimate the sum, let $R_n$ be the remainder of the partial sum $s_n$, i.e.

$$
R_n = s - s_n = a_{n+1} + a_{n+2} + ...
$$

By forming rectangles with top above and below the curve, we have

$$
\int_{n+1}^{\infty} f(x) \mathrm{d}x \le R_n \le \int_{n}^{\infty} f(x) \mathrm{d}x
$$

Adding $s_n$ to the inequalities, we can find an upper bound and a lower bound for $s$.

$$
s_n + \int_{n+1}^{\infty} f(x) \mathrm{d}x \le s \le s_n + \int_{n}^{\infty} f(x) \mathrm{d}x
$$

### Comparison Test

## References

* James Stewart _Single Variable Calculus_, 2015 - Chapter 11
