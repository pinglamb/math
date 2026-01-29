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

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 8.1
