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
    (\forall a, b \in V)\; a + b \in V
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
    (\forall \lambda \in F)(\forall a \in V)\; \lambda a \in V
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

Note that $(V, +)$ is an abelian group and therefore the additive identity and inverse are unique.
Some of the other properties are proved in [Vectors and Matrices](../vectors-and-matrices/vector-spaces.md#properties).

## Subspaces

> *Definition.*{: .def}
> A nonempty subset $U \subset V$ is a **subspace** if
>
> + $U$ is _closed_ under addition, i.e.
>
>   $$
    (\forall u_1, u_2 \in U)\; u_1 + u_2 \in U
    $$
>
> + $U$ is _closed_ under scalar multiplication, i.e.
>
>   $$
    (\forall \lambda \in F)(\forall u \in U)\; \lambda u \in U
    $$
>
> In short, $U \subset V$ is a subspace iff $U \not= \emptyset$ and
>
> $$
  (\forall u_1, u_2 \in U)(\lambda, \mu \in \mathbb{F})\; \lambda u_1 + \mu u_2 \in U
  $$

> *Definition.*{: .def}
> Suppose that $U$ and $W$ are subspaces of a vector space $V$ over $\mathbb{F}$.
> Then the **sum** of $U$ and $W$ is the set
>
> $$
  U + W = \Set{u + w : u \in U, w \in W}
  $$

> *Proposition.*{: .prop}
> Suppose that $U$ and $W$ are subspaces of a vector space $V$ over $\mathbb{F}$.
> Then $U \cap W$ and $U + W$ are also subspaces of $V$.
>
> *Proof.*{: .prf}
>
> $U \cap W$ and $U + W$ is nonempty since $0$ is in them.
>
> For $U \cap W$, for all $v_1, v_2 \in U \cap W$,
> $\lambda v_1 + \mu v_2 \in U$ and $\lambda v_1 + \mu v_2 \in W$ so $\lambda v_1 + \mu v_2 \in U \cap W$.
>
> For $U + W$, for all $u_1 + w_1, u_2 + w_2 \in U + W$,
>
> $$
  \lambda (u_1 + w_1) + \mu (u_2 + w_2) = (\lambda u_1 + \mu u_2) + (\lambda w_1 + \mu w_2) \in U + W
  $$

## Quotient Spaces

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 1
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 2
