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
