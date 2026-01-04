---
layout: base
title: Polynomials &#124; Linear Algebra
---

# Polynomials
{: .page-title}

A prerequisite for understanding the deeper theorems about linear maps is a knowledge of factorization of polynomials as products of prime polynomials.

> *Definition.*{: .def}
> A **polynomial** with coefficients in $\mathbf{F}$ is by definition a sequence
>
> $$
  f = \Set{a_0, a_1, a_2, ... }, \qquad a_i \in \mathbf{F}
  $$
>
> such that for some positive integer $M$ depending on $f$, $a_M = a\_{M+1} = ... = 0$.
> Two polynomials $f = \Set{a_i}$ and $g = \Set{b_i}$ are equal, i.e. $f = g$, iff $a_0 = b_0$, $a_1 = b_1$, etc.
> Addition is the same as for vectors, i.e.
>
> $$
  f + g = \Set{a_0 + b_0, a_1 + b_1, ...}
  $$
>
> and multiplication is defined by the rule
>
> $$
  fg = \Set{c_0, c_1, ...} \quad \text{where} \quad c_k = \sum_{i + j = k} a_i b_j = a_0 b_k + a_1 b_{k-1} + ... + a_k b_0
  $$

Let $\mathbf{F}'$ be the set of all polynomials of the form

$$
a = \Set{a, 0, 0, ...}
$$

and $x^i$ be the polynomial with $1$ at the $i$-th position, i.e.

$$
x^i = \Set{0, ..., 1, ...}
$$

then we have

$$
ax^i = \Set{a, 0, 0, ...}\Set{0, ..., 1, ...} = \Set{0, ..., a, ...}
$$

and therefore an arbitrary polynomial $f$ can be expressed uniquely in the form

$$
f = a_0 + a_1 x + a_2 x^2 + ...
$$

> *Definition.*{: .def}
> The set of polynomials with coefficients in $\mathbf{F}$ is denoted by $\mathbf{F}[x]$.

## References

* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Section 20
