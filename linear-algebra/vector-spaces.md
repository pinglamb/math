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

> *Proposition.*{: .prop}
> Suppose that $U$ and $W$ are subspaces of a vector space $V$. Then $U \cap W$ is also a subspace of $V$.
>
> *Proof.*{: .prf}
>
> $U \cap W$ contains $0$ so it is nonempty.
> For all $v_1, v_2 \in U \cap W$, $\lambda v_1 + \mu v_2 \in U$ and $\lambda v_1 + \mu v_2 \in W$ so $\lambda v_1 + \mu v_2 \in U \cap W$.

## Quotient Spaces

> *Definition.*{: .def}
> Suppose that $V$ is a vector space over $\mathbb{F}$ and $U$ is a subspace of $V$.
> Then the **quotient space** $V/U$ is the set $\Set{v + U}$ with addition
>
> $$
  (v_1 + U) + (v_2 + U) = (v_1 + v_2) + U
  $$
>
> and scalar multiplication
>
> $$
  \lambda (v + U) = (\lambda v) + U
  $$

It is easier to understand the above structure by considering the equivalence relation $v_1 \sim v_2$ if $v_1 - v_2 \in U$.
Therefore, the equivalence class of $v$ is defined as

$$
[v] = \Set{v + u : u \in U}
$$

which is denoted as $v + U$ above and $V/U$ is the set containing all the equivalence classes induced by $\sim$ on $U$ with addition $[v_1] + [v_2] = [v_1 + v_2]$ and $\lambda [v] = [\lambda v]$.
Note that all the elements in $U$ are in the equivalence class $[0]$ so the quotient space $V/U$ is obtained by "collapsing" $U$ to zero.

> *Proposition.*{: .prop}
> The quotient space $V/U$ is a vector space over $\mathbb{F}$.
>
> *Proof.*{: .prf}
>
> For $v_1, v_1', v_2, v_2' \in V$ and $u_1, u_2 \in U$ with $[v_1] = [v_1']$ and $[v_2] = [v_2']$, we have
>
> $$
  v_1' + v_2' = (v_1 + u_1) + (v_2 + u_2) = (v_1 + v_2) + (u_1 + u_2)
  $$
>
> so $[v_1' + v_2'] = [v_1 + v_2]$ since $u_1 + u_2 \in U$. Similarily,
>
> $$
  \lambda v_1' = \lambda (v_1 + u_1) = (\lambda v_1) + (\lambda u_1)
  $$
>
> so $[\lambda v_1'] = [\lambda v_1]$.
> Thus, both operations are well-defined, i.e. independent of the choice of representatives.
>
> The axioms are an almost immediate consequence of the fact that the same axioms hold for $V$ and $U$ being a vector space, e.g.
>
> $$
  \lambda (\mu [v]) = [\lambda (\mu v)] = [(\lambda \mu) v] = (\lambda \mu) [v]
  $$

## Direct Sums

> *Definition.*{: .def}
> Suppose that $U$ and $W$ are subspaces of a vector space $V$ over $\mathbb{F}$.
> Then the **sum** of $U$ and $W$ is defined by the set
>
> $$
  U + W = \Set{u + w : u \in U, w \in W}
  $$

> *Proposition.*{: .prop}
> $U + W$ is a subspace of $V$.
>
> *Proof.*{: .prf}
>
> $U + W$ is nonempty since it contains $0$. For all $u_1 + w_1, u_2 + w_2 \in U + W$,
>
> $$
  \lambda (u_1 + w_1) + \mu (u_2 + w_2) = (\lambda u_1 + \mu u_2) + (\lambda w_1 + \mu w_2) \in U + W
  $$

> *Definition.*{: .def}
> $V$ is the **(internal) direct sum** of $U$ and $W$, written $V = U \oplus W$,
> if every element $v \in V$ can be written uniquely as $u + w$ with $u \in U$ and $w \in W$.
> $U$ and $W$ are said to be the **complementary subspaces** in $V$.

> *Proposition.*{: .prop}
> $V = U \oplus W$ iff $V = U + W$ and $U \cap W = \Set{0}$.
>
> *Proof.*{: .prf}
>
> Obviously, $V = U + W$ and if $v \in U \cap W \not= 0$, then $v = 0 + v = v + 0$ which cannot be written uniquely.

> *Definition.*{: .def}
> The **(external) direct sum** $U \oplus W$ of two vector spaces $U$ and $W$ over $\mathbb{F}$ is defined by the set
>
> $$
  U \oplus W = \Set{(u, w) : u \in U, w \in W}
  $$
>
> with the natural coordinate-wise operations.

> *Proposition.*{: .prop}
> $U \oplus W$ is a vector space over $\mathbb{F}$ and is the internal direct sum of the subspaces
>
> $$
  \Set{(u, 0) : u \in U} \quad \text{and} \quad \Set{(0, v) : v \in V}
  $$

More generally, we can make the following definitions.

> *Definition.*{: .def}
> If $U_1, ..., U_n$ are subspaces of $V$ then $V$ is the (internal) direct sum of $U_1, ..., U_n$, denoted by
>
> $$
  V = U_1 \oplus \cdots \oplus U_n = \bigoplus_{i=1}^n U_i
  $$
>
> if every element $v \in V$ can be written uniquely as $v = \sum u_i$ with $u_i \in U_i$.

> *Proposition.*{: .prop}
> $V$ is the direct sum of subspaces $U_1, ..., U_n$ iff
>
> + every vector $v \in V$ can be expressed in at least one way as $v = u_1 + ... + u_n$;
>
> + If $u_1 + ... + u_n = 0$, then $u_1 = ... = u_n = 0$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) If $V = U_1 \oplus \cdots \oplus U_n$ then obviously both are true.
>
> ($\Leftarrow$) Suppose that $u_1 + ... u_n = u_1' + ... + u_n'$, then $(u_1 - u_1') + ... + (u_n - u_n') = 0$ so $u_1 = u_1', ..., u_n = u_n'$ and the expression is unique.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 1.1
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 2.3, 2.4
