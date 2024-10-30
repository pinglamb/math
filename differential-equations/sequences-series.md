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

### Comparison Test

## References

* James Stewart _Single Variable Calculus_, 2015 - Chapter 11
