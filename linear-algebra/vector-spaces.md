---
layout: base
title: Vector Spaces &#124; Linear Algebra
---

# Vector Spaces
{: .page-title}

In [Vectors and Matrices](../vectors-and-matrices/vector-spaces.md) we have briefly addressed the idea of _Vector Space_.
Vector space is like an abstraction of linear systems by only relying on axioms for definition and develop the theory base on that.
In this way, any systems that match the axioms are considered as vector space and the theories can then be applied.
Linear algebra can then be summarised as the study of vector spaces and linear maps between them.

> *Definition.*{: .def}
> Let $\mathbb{F}$ be an arbitrary field.
> A **vector space** $V$ over $\mathbb{F}$ or $\mathbb{F}$-vecor space is a non-empty set of _vectors_, a field $\mathbb{F}$ of _scalars_,
> together with two binary operations: an _addition_ $a + b$ of vectors $a$ and $b$ and a _scalar multiplication_ $\lambda v$ of a scalar $\lambda$ and a vector $v$.
> The operations are assumed to satisfy the following axioms:
>
> + $V$ is _closed_ under addition, i.e.
>
>   $$
    \forall a, b \in V \implies a + b \in V
    $$
>
> + addition is _commutative_, i.e. for all $a, b \in V$
>
>   $$
    a + b = b + a
    $$
>
> + addition is _associative_, i.e. for all $a, b, c \in V$
>
>   $$
    a + (b + c) = (a + b) + c
    $$
>
> + addition has an _identity_ element, i.e. there exists an element $0 \in V$ such that
>
>   $$
    a + 0 = a
    $$
>
> + for all $a \in V$, there exists an _additive inverse_ $a' \in V$ such that
>
>   $$
    a + a' = 0
    $$
>
> + $V$ is _closed_ under scalar multiplication, i.e.
>
>   $$
    \forall \lambda \in F, \forall a \in V \implies \lambda a \in V
    $$
>
> + scalar multiplication is _distributive over scalar addition_, i.e. for all $\lambda, \mu \in \mathbb{F}$ and $a \in V$
>
>   $$
    (\lambda + \mu)a = \lambda a + \mu a
    $$
>
> + scalar multiplication is _distributive over vector addition_, i.e. for all $\lambda \in \mathbb{F}$ and $a, b \in V$
>
>   $$
    \lambda (a + b)= \lambda a + \lambda b
    $$
>
> + scalar multiplication is "associative", i.e. for all $\lambda, \mu \in \mathbb{F}$ and $a \in V$
>
>   $$
    \lambda (\mu a) = (\lambda \mu) a
    $$
>
> + scalar multiplication has an _identity_ element, i.e. there exists an element $1 \in \mathbb{F}$ such that
>
>   $$
    1 a = a
    $$

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 1
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 2
