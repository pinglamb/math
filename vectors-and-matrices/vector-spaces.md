---
layout: base
title: Vector Spaces &#124; Vectors and Matrices
---

# Vector Spaces
{: .page-title}

The essential features of vectors is that we can have a linear combination of vectors which again is a vector.
This idea can be generalized to different kinds of quantities, not just about magnitude and direction.

> *Definition.*{: .def}
> A **vector space** $V$ over the field $\mathbb{F}$ is a set $V$ of vectors, a field $\mathbb{F}$ of scalars,
> and two _binary operations_:
> an _addition_ $a + b$ of vectors $a$ and $b$,
> and a _scalar multiplication_ $\lambda v$ of a scalar $\lambda$ and a vector $v$,
> which together satisfy the following properties/axioms:
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
> + scalar multiplication has an _identity_ element, i.e. there exists an element $1 \in \mathbb{F}$ such that
>
>   $$
    1 a = a
    $$

Base on our study of [vectors](vectors.md) in $\mathbb{R}^2$/$\mathbb{R}^3$, we can see that they form a vector space over $\mathbb{R}$.

## Properties

We generalize properties of vectors in $\mathbb{R}^2$/$\mathbb{R}^3$ and prove them algebraically.

> *Prop.*{: .prop}
> Vector space is an _abelian group_ under vector addition, hence we have
>
> + additive identity $0 \in V$ is unique
>
> + additive inverse $-a \in V$ is unique
>
> *Proof.*{: .prf}
>
> Base on the vector space and abelian group definition.

> *Definition.*{: .def}
> Vector subtraction is defined by addition of additive inverse, i.e.
>
> $$
  a - b = a + (-b)
  $$

> *Prop.*{: .prop}
> Scalar multiplication by $0 \in \mathbb{F}$ yields the additive identity $0_V \in V$.
>
> *Proof.*{: .prf}
>
> Let $a \in V$, we have
>
> $$
  \begin{align*}
  0_{\mathbb{F}} a &= 0_{\mathbb{F}} a + 0_{V} \\
  &= 0_{\mathbb{F}} a + a + (-a) \\
  &= (0_{\mathbb{F}} + 1) a + (-a) \\
  &= a + (-a) \\
  &= 0_{V}
  \end{align*}
  $$

> *Prop.*{: .prop}
> Scalar multiplication by $-1 \in \mathbb{F}$ yields the additive inverse $-a \in V$.
>
> *Proof.*{: .prf}
>
> Let $a \in V$, we have
>
> $$
  \begin{align*}
  (-1)a &= (-1)a + 0_{V} \\
  &= (-1)a + a + (-a) \\
  &= (-1 + 1) a + (-a) \\
  &= 0_{\mathbb{F}}a + (-a) \\
  &= 0_{V} + (-a) \\
  &= -a
  \end{align*}
  $$

> *Prop.*{: .prop}
> Scalar multiplication with zero vector $0\_V$ yields $0\_V$, i.e. $\lambda 0_V = 0_V$.
>
> *Proof.*{: .prf}
>
> Let $a \in V$, we have
>
> $$
  \lambda 0_V + \lambda a = \lambda (0_V + a) = \lambda a
  $$
>
> Hence, $\lambda 0_v$ is a zero vector and from the above zero vector is unique, so $\lambda 0_V = 0_V$.

> *Prop.*{: .prop}
> If $\lambda a = 0_V$, either $\lambda = 0\_{\mathbb{F}}$ or $a = 0\_V$.
>
> *Proof.*{: .prf}
>
> If $\lambda \not = 0_{\mathbb{F}}$, there exists $\lambda^{-1}$ such that
>
> $$
  a = (\lambda^{-1}\lambda)a = \lambda^{-1}(\lambda a) = \lambda^{-1}0_V = 0_V
  $$
>
> If $a \not = 0\_V$, then $\lambda a = 0\_V$ for all other $a \in V$ only when $\lambda = 0_\mathbb{F}$.

> *Prop.*{: .prop}
> Negation commutes freely, i.e.
>
> $$
  (-\lambda)a = \lambda(-a) = -(\lambda a)
  $$
>
> *Proof.*{: .prf}
>
> Let $a \in V$ and $\lambda \in \mathbb{F}$, we have
>
> $$
  \begin{align*}
  (-\lambda)a &= (\lambda(-1))a \\
              &= \lambda((-1)a) \\
              &= \lambda(-a)
  \end{align*}
  $$
>
> and
>
> $$
  \begin{align*}
  (-\lambda)a &= ((-1)\lambda)a \\
              &= (-1)(\lambda a) \\
              &= -(\lambda a)
  \end{align*}
  $$

## Scalar Product

> *Definition.*{: .def}
> For a vector space $V$ over $\mathbb{R}$,
> The scalar/inner product of vectors $a, b \in V$, denoted by $a \cdot b$ or $\langle a \mid b \rangle$,
> is a map $V \times V \to \mathbb{R}$ that satisfies the following properties:
>
> + _Symmetric_, i.e.
>
>   $$
    a \cdot b = b \cdot a
    $$
>
> + _Linearilty_ in the second argument, i.e.
>
>   $$
    a \cdot (\lambda b + \mu c) = \lambda (a \cdot b) + \mu (a \cdot c)
    $$
>
> + _Non-negativity_, with equality holds iff $a = 0_V$, i.e.
>
>   $$
    a \cdot a \ge 0_\mathbb{R}
    $$
>
> + _Non-degeneracy_, the only vector of zero _norm_ should be the zero vector, i.e.
>
>   $$
    \vert a \vert = 0 \implies a = 0_V
    $$

This definition is only for real vector spaces. For complex vector spaces, we have a different set of [axioms](spanning-sets-and-bases.md#complex-space-scalar-product-axioms).

> *Definition.*{: .def}
> The **norm** of a vector, denoted by $\vert a \vert$ or $\Vert a \Vert$, is defined by
>
> $$
  \vert a \vert \equiv \Vert a \Vert = \sqrt{a \cdot a}
  $$

### Cauchy-Schwarz Inequality

> *Theorem.*{: .thm}
> **[Cauchy-Schwarz Inequality]**
> For all $a, b \in V$,
>
> $$
  \vert a \cdot b \vert \le \vert a \vert \vert b \vert
  $$
>
> with equality only when $a = 0_V$, $b = 0_V$ or $a = \lambda b$.
>
> *Proof.*{: .prf}
>
> Consider the expression $\vert a + \lambda b \vert^2$, from the above axioms about scalar product, we have
>
> $$
  \begin{align*}
  \vert a + \lambda b \vert^2 &\ge 0 \\
  (a + \lambda b) \cdot (a + \lambda b) &\ge 0 \\
  \vert a \vert^2 + 2 (a \cdot b) \lambda + \vert b \vert^2 \lambda^2 &\ge 0
  \end{align*}
  $$
>
> If $b = 0_V$, $\vert b \vert = 0$, we have $\vert a \cdot b \vert = \vert a \vert \vert b \vert = 0$.
>
> If $b \not = 0_V$, by viewing the above as a quadratic equation in $\lambda$, as it is always non-negative, it has at most one root. Hence,
>
> $$
  \Delta = (2 a \cdot b)^2 - 4 \vert a \vert^2 \vert b \vert^2 \le 0
  $$
>
> $$
  \vert a \cdot b \vert \le \vert a \vert \vert b \vert
  $$
>
> and equality holds only when $a = -\lambda b$ for some $\lambda$.

## Subspaces

> *Definition.*{: .def}
> For a vector space $V$, a **subspace** of $V$ is a non-empty subset $U$ of the vectors of $V$
> if $U$ is a vector space under the same operations (i.e. vector addition and scalar multiplication) as are used to define $V$.

> *Theorem.*{: .thm}
> A subset $U$ of a vector space $V$ is a subspace of $V$ iff under the operations defined on $V$
>
> + $\forall a, b \in U, a + b \in U$
>
> + $\forall a \in U, \lambda \in \mathbb{F}, \lambda a \in U$
>
> or in short
>
> $$
  \forall a, b \in U, \forall \lambda, \mu \in \mathbb{F}, \lambda a + \mu b \in U
  $$
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) If $U$ is a subspace then it is a vector space, by definition the above conditions hold.
>
> ($\Leftarrow$) If the above holds, most of the axioms of vector space obviously holds as elements of $U$ are also elements of $V$.
> The only non-trivial axioms are the existence of _identity_ and _inverse_ in $U$:
>
> + As $0_F a \in U$ and $0_F a = 0_V$, $0_V \in U$
>
> + As $(-1)a \in U$ and $(-1)a = -a$, $-a \in U$

> *Definition.*{: .def}
> A **proper subspace** is a subspace of $V$ that is not $V$ or $\Set{0\_V}$.

## Reference

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 7
* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter 2](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
