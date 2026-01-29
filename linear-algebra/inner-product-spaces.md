---
layout: base
title: Inner Product Spaces &#124; Linear Algebra
---

# Inner Product Spaces
{: .page-title}

> *Definition.*{: .def}
> An **inner product** on a vector space $V$ over $\mathbf{F}$ is a _positive definite_ _symmetric_/_Hermitian_ form $\phi$ on $V$, denoted by $\langle u, v \rangle$.
> A vector space equipped with an inner product is called an **inner product space**.

> *Definition.*{: .def}
> The **norm** of a vector $v$ of an inner product space $V$ is defined by
>
> $$
  \Vert v \Vert = \langle v, v \rangle^{1/2}
  $$

Note that $\Vert v \Vert \ge 0$ with equality iff $v = 0$. Also, the norm determines the inner product because of the polarization identity.

> *Theorem.*{: .thm}
> **[Cauthy-Schwarz Inequality]**
> Suppose that $V$ is an inner product space. For any $u, v \in V$,
>
> $$
  \vert \langle u, v \rangle \vert \le \Vert u \Vert \Vert v \Vert
  $$
>
> *Proof.*{: .prf}
>
> Suppose that $\Vert u \Vert = \Vert v \Vert = 1$. Then
>
> $$
  \langle u - v, u - v \rangle = \Vert u \Vert^2 + \Vert v \Vert^2 - 2 \langle u, v \rangle \ge 0 \quad \implies \quad \langle u, v \rangle \le 1
  $$
>
> and
>
> $$
  \langle u + v, u + v \rangle = \Vert u \Vert^2 + \Vert v \Vert^2 + 2 \langle u, v \rangle \ge 0 \quad \implies \quad -\langle u, v \rangle \le 1
  $$
>
> Therefore, $\vert \langle u, v \rangle \vert \le 1$.
>
> The result is trivial if either $u$ or $v$ is zero. Therefore, by considering the vectors $u / \Vert u \Vert$ and $v / \Vert v \Vert$, we have
>
> $$
  \left\vert \langle {u \over \Vert u \Vert}, {v \over \Vert v \Vert} \rangle \right\vert \le 1
  $$
>
> so $\vert \langle u, v \rangle \vert \le \Vert u \Vert \Vert v \Vert$.

> *Corollary.*{: .cor}
> **[Triangle Inequality]**
> Suppose that $V$ is an inner product space. For any $u, v \in V$,
>
> $$
  \Vert u + v \Vert \le \Vert u \Vert + \Vert v \Vert
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \Vert u + v \Vert^2 &= \langle u + v, u + v \rangle \\
  &= \Vert u \Vert^2 + \Vert v \Vert^2 + 2 \langle u, v \rangle \\
  &\le \Vert u \Vert^2 + \Vert v \Vert^2 + 2 \Vert u \Vert \Vert v \Vert \\
  &= (\Vert u \Vert + \Vert v \Vert)^2
  \end{align*}
  $$

The law of cosines assets that

$$
\Vert u - v \Vert^2 = \Vert u \Vert^2 + \Vert v \Vert^2 - 2 \Vert u \Vert \Vert v \Vert \cos \theta
$$

which allows us to define the angle $\theta$ between two vectors by inner product.

> *Definition.*{: .def}
> The **angle** $\theta$ between $u, v \in V$ is defined by
>
> $$
  \cos \theta = { \langle u, v \rangle \over \Vert u \Vert \Vert v \Vert }
  $$

## Orthonormal Basis

> *Definition.*{: .def}
> Suppose that $V$ is an inner product space. Then $u, v \in V$ are **orthogonal** if $\langle v, w \rangle = 0$.

> *Definition.*{: .def}
> A set $\Set{v_i}$ is **orthonormal** if $\langle v_i, v_j \rangle = \delta_{ij}$ and an **orthonormal basis** for $V$ is a basis that is orthonormal.

Suppose that $(v_1, ..., v_n)$ is a orthonormal basis. We have $v = \sum \lambda_i v_i$ therefore $\langle v_j, v \rangle = \sum \lambda_i \langle v_j, v_i \rangle = \lambda_j$ and

$$
v = \sum_{i=1}^n \langle v_i, v \rangle v_i
$$

> *Proposition.*{: .prop}
> **[Parseval's Identity]**
> Suppose that $V$ is a finite dimensional inner product space with orthonormal basis $(v_1, ..., v_n)$ then
>
> $$
  \langle u, v \rangle = \sum_{i=1}^n \overline{\langle v_i, u \rangle} \langle v_i, v \rangle
  $$
>
> In particular,
>
> $$
  \Vert v \Vert^2 = \sum_{i=1}^n \vert \langle v_i, u \rangle \vert^2
  $$
>
> *Proof.*{: .prf}
>
> $$
  \langle u, v \rangle = \langle \sum_{i=1}^n \langle v_i, u \rangle v_i, \sum_{j=1}^n \langle v_j, v \rangle v_j \rangle = sum_{i=1}^n \overline{\langle v_i, u \rangle} \langle v_i, v \rangle
  $$

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 8.1
