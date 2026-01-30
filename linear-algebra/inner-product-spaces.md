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
> A set $\Set{e_i}$ is **orthonormal** if $\langle e_i, e_j \rangle = \delta_{ij}$ and an **orthonormal basis** for $V$ is a basis that is orthonormal.

> *Proposition.*{: .prop}
> Every orthonormal set of vectors is linearly independent.
>
> *Proof.*{: .prf}
>
> Suppose that $(e_1, ..., e_k)$ is a orthonormal set. Then
>
> $$
  \begin{align*}
  \lambda_1 e_1 + \cdots + \lambda_k e_k &= 0 \\
  \langle e_i, \lambda_1 e_1 + \cdots + \lambda_k e_k \rangle &= \langle e_i, 0 \rangle \\
  \lambda_i &= 0
  \end{align*}
  $$
>
> for $i = 1, ..., k$ so $(e_1, ..., e_k)$ is linearly independent.

Suppose that $(e_1, ..., e_n)$ is a orthonormal basis for $V$. Then $v = \sum \lambda_i e_i \in V$ and $\langle e_j, v \rangle = \sum \lambda_i \langle e_j, e_i \rangle = \lambda_j$ so

$$
v = \sum_{i=1}^n \langle e_i, v \rangle e_i
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

> *Theorem.*{: .thm}
> **[Gram-Schmidt Orthogonalization Process]**
> Suppose that $V$ is an inner product space and $v_1, v_2, ...$ are linearly independent vectors.
> Then there is a sequence $e_1, e_2, ...$ of orthonormal vectors such that $\langle e_1, ..., e_k \rangle = \langle v_1, ..., v_k \rangle $ for each $k \ge 0$.
> In particular,
>
> $$
  e_{k+1} = {v \over \Vert v \Vert} \quad \text{where} \quad v = v_{k+1} - \sum_{i = 1}^k (e_i, v_{k+1}) e_i
  $$
>
> *Proof.*{: .prf}
>
> The result is obvious when $k = 0$. Assume we have found $e_1, ..., e_k$ accordingly.
> Since $v_1, ..., v_{k+1}$ are linearly independent, $v$ defined above is non-zero so $\Vert e_{k+1} \Vert = 1$.
> Then for $j \le k$,
>
> $$
  \langle e_j, v \rangle = \langle e_j, v_{k+1} \rangle - \sum_{i=1}^k \langle e_i, v_{k+1} \rangle \langle e_j, e_i \rangle = \langle e_j, v_{k+1} \rangle - \langle e_j, v_{k+1} \rangle = 0
  $$
>
> so $\Set{e_1, ..., e_{k+1}}$ is orthonormal.
> Since $\langle e_1, ..., e_k \rangle = \langle v_1, ..., v_k \rangle$ by induction hypothesis
> and $v_{k+1} \in \langle e_1, ..., e_{k+1} \rangle$ and $e_{k+1} \in \langle v_1, ..., v_{k+1} \rangle$ by construction, $\langle e_1, ..., e_{k+1} \rangle = \langle v_1, ..., v_{k+1} \rangle$.

> *Corollary.*{: .cor}
> Suppose that $V$ is a finite dimensional inner product space.
> Then any orthonormal set $(e_1, ..., e_k)$ can be extended to an orthonormal basis.
>
> *Proof.*{: .prf}
>
> The orthonormal set $(e_1, ..., e_k)$ is linearly independent and can be extend to a basis $(e_1, ..., e_k, v_{k+1}, ..., v_n)$ for $V$.
> By the Gram-Schmidt process, we can obtain an orthonormal basis $(f_1, ..., f_n)$ such that $f_i = e_i$ for $i = 1, ... k$.

## Orthogonal Complements

> *Definition.*{: .def}
> The **orthogonal complement** of a subspace $U \subset V$ of an inner product space $V$, denoted by $U^\perp$, is the subspace of $V$ defined by
>
> $$
  U^\perp = \Set{v \in V : \forall u \in U, \langle u, v \rangle = 0}
  $$

> *Definition.*{: .def}
> Suppose that $V$ is an inner product space and $V_1, V_2$ are subspaces of $V$.
> Then $V$ is _orthogonal (internal) direct sum_ of $V_1$ and $V_2$, denoted by $V = V_1 \perp V_2$, if
>
> + $V = V_1 + V_2$;
>
> + $V_1 \cap V_2 = 0$;
>
> + $\langle v_1, v_2 \rangle = 0$ for all $v_1 \in V_1$ and $v_2 \in V_2$.

> *Proposition.*{: .prop}
> Suppose that $V$ is a finite dimensional inner product space and $U$ is a subspace of $V$. Then
>
> $$
  V = U \perp U^\perp
  $$
>
> *Proof.*{: .prf}
>
> For any $u \in U$ and $u^\perp \in U^\perp$, by definition, $\langle u, u^\perp \rangle = 0$.
> For $v \in U \cap U^\perp$, $\langle v, v \rangle = 0$ so $v = 0$ and $U \cap U^\perp = 0$.
>
> Let $(e_1, ..., e_k)$ be an orthonormal basis for $U$. For any $v \in V$ and $1 \le i \le k$,
>
> $$
  \langle e_i, v - \sum_{j=1}^k \langle e_j, v \rangle e_j \rangle = \langle e_i, v \rangle - \langle e_i, \sum_{j=1}^k \langle e_j, v \rangle e_j \rangle = 0
  $$
>
> Therefore, for all $u = \sum_{i=1}^k \lambda_i e_i \in U$, $\langle u, v - \sum_{j=1}^k \langle e_j, v \rangle e_j = 0$ so
>
> $$
  v - \sum_{j=1}^k \langle e_j, v \rangle e_j \in U^\perp
  $$
>
> and $V = U + U^\perp$.

It implies that orthogonal complements are unique.

> *Definition.*{: .def}
> The _orthogonal (external) direct sum_ of two inner product spaces $V$ and $W$ is the direct sum $V \oplus W$ with the inner product
>
> $$
  \langle (v_1, w_1), (v_2, w_2) \rangle = \langle v_1, v_2 \rangle + \langle w_1, w_2 \rangle
  $$

> *Definition.*{: .def}
> Suppose that $V = U \oplus U'$. The **projection map** $\pi: V \to U$ onto $U$ along $U'$ is given by $\pi(u + u') = u$ for $u \in U$ and $u' \in U'$.
> If $U' = U^\perp$ then $\pi$ is called the **orthogonal projection** onto $U$.

> *Proposition.*{: .prop}
> Suppose that $V$ is a finite dimensional inner product space and $U \subset V$ is a subspace with orthonormal basis $(e_1, ..., e_k)$ and $\pi$ is an orthogonal projection onto $U$.
> Then
>
> + $\pi(v) = \sum_{i=1}^k \langle e_i, v \rangle e_i$ for each $v \in V$;
>
> + $\Vert v - \pi(v) \Vert \le \Vert v - u \Vert$ for all $u \in U$ with equality iff $\pi(v) = u$, i.e. $\pi(v)$ is the closest point to $v$ in $U$.
>
> *Proof.*{: .prf}
>
> Let $u' = \sum_{i=1}^k \langle e_i, v \rangle e_i \in U$. Then
>
> $$
  \langle e_j, v - u' \rangle = \langle e_j, v \rangle - \sum_{i=1}^k \langle e_i, v \rangle \langle e_j, e_i \rangle = 0
  $$
>
> for $1 \le j \le k$ so $v - u' \in U^\perp$. Therefore, $v = u' + (v - u')$ so $\pi(v) = u'$ as required.
>
> Let $u \in U$, consider the vectors $v - \pi(v)$ and $\pi(v) - u$.
> From the above, we have $\pi(v) \in U$ so $\pi(v) - u \in U$. Also, $v - \pi(v) \in U^\perp$ so they are orthogonal to each other.
> Hence,
>
> $$
  \begin{align*}
  \Vert v - u \Vert^2 &= \Vert (v - \pi(v)) + (\pi(v) - u) \Vert^2 \\
  &= \Vert v - \pi(v) \Vert^2 + \Vert \pi(v) - u \Vert^2 + 2 \langle v - \pi(v), \pi(v) - u \rangle \\
  &= \Vert v - \pi(v) \Vert^2 + \Vert \pi(v) - u \Vert^2
  \end{align*}
  $$
>
> and $\Vert v - u \Vert^2 \ge \Vert v - \pi(v) \Vert^2$ with equality iff $\Vert \pi(v) - u \Vert^2 = 0$, i.e. $\pi(v) = u$.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 8.1, 8.2
