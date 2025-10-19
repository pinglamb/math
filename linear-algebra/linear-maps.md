---
layout: base
title: Linear Maps &#124; Linear Algebra
---

# Linear Maps
{: .page-title}

In order to compare different mathematical systems of the same type, it is essential to study the functions which preserve the operations of the system.
For vector spaces, linear maps are the functions that preserve the linearity the operations of addition and scalar multiplication.

> *Definition.*{: .def}
> Suppose that $U$ and $V$ are vector spaces over $\mathbb{F}$.
> Then a function $\alpha: U \to V$ is a **linear map** if
>
> + $\alpha(u_1 + u_2) = \alpha(u_1) + \alpha(u_2)$ for all $u_1, u_2 \in U$;
>
> + $\alpha(\lambda u) = \lambda \alpha(u)$ for all $u \in U$ and $\lambda \in \mathbb{F}$.
>
> In short, we can combine the two parts as $\alpha(\lambda u_1 + \mu u_2) = \lambda \alpha(u_1) + \mu \alpha(u_2)$.

> *Definition.*{: .def}
> The set of linear maps from $U$ to $V$ is denoted by $\mathcal{L}(U, V)$.

> *Definition.*{: .def}
> A linear map $\alpha: U \to V$ is an **isomorphism** if there is a linear map $\beta: V \to U$ such that $\beta \alpha = \mathrm{id}_U$ and $\alpha \beta = \mathrm{id}_V$.

> *Proposition.*{: .prop}
> A linear map $\alpha: U \to V$ is an isomorphism iff $\alpha$ is a bijection.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Certainly if $\alpha$ is an isomorphism then it is a bijection since it has an inverse.
>
> ($\Leftarrow$) If $\alpha$ is a bijection, it has inverse $\beta: V \to U$. Then
>
> $$
  \alpha \beta (\lambda v_1 + \mu v_2) = \mathrm{id}_V(\lambda v_1 + \mu v_2) = \lambda \alpha \beta(v_1) + \mu \alpha \beta(v_2) = \alpha (\lambda \beta(v_1) + \mu \beta(v_2))
  $$
>
> Since $\alpha$ is injective, $\beta (\lambda v_1 + \mu v_2) = \lambda \beta(v_1) + \mu \beta(v_2)$ implies $\beta$ is also a linear map and therefore $\alpha$ is an isomorphism.

> *Proposition.*{: .prop}
> Suppose that $\alpha: U \to V$ is a linear map. Then
>
> + If $\alpha$ is _injective_ and $S \subset U$ is linearly independent then $\alpha(S) \subset V$ is linearly independent.
>
> + If $\alpha$ is _surjective_ and $S \subset U$ spans $U$ then $\alpha(S) \subset V$ spans $V$.
>
> + If $\alpha$ is an isomorphism and $S$ is a basis of $U$ then $\alpha(S)$ is a basis of $V$.
>
> *Proof.*{: .prf}
>
> Let $S \subset U$ and $\alpha(S)$ is linearly dependent.
> Then there exists $\lambda_i \in \mathbb{F}$ such that
>
> $$
  \alpha (s_1) = \sum \lambda_i \alpha(s_i) = \alpha \left( \sum \lambda_i s_i \right)
  $$
>
> Since $\alpha$ is injective, $s_1 = \sum \lambda_i s_i$ and $S$ is linearly dependent.
> Contrapositively, if $\alpha$ is injective and $S$ is linearly independent then $\alpha(S)$ is linearly independent.
>
> Suppose that $S \subset U$ spans $U$ and $\alpha$ is surjective.
> Then for any $v \in V$, there exists $u \in U$ such that $\alpha(u) = v$. Thus,
>
> $$
  v = \alpha(u) = \alpha \left( \sum \lambda_i s_i \right) = \sum \lambda_i \alpha(s_i)
  $$
>
> and $\alpha(S)$ spans $V$.
>
> Hence, if $\alpha$ is bijective and $S$ is a basis of $U$, from the above $\alpha(S)$ is a basis of $V$.

> *Corollary.*{: .cor}
> If there exists an isomorphism between two finite dimensional vector spaces $U$ and $V$, then $\dim U = \dim V$.
>
> *Proof.*{: .prf}
>
> If $\alpha$ is an isomorphism and $S$ is a basis of $U$, then $\alpha(S)$ is a basis for $V$.
> Since $\alpha$ is injective, $\vert S \vert = \vert \alpha(S) \vert$.

## Matrix Representation

> *Proposition.*{: .prop}
> Suppose that $U$ and $V$ are finite dimensional vector spaces and $\Set{u_1, ... u_n}$ is a basis of $U$.
> If $\alpha, \beta \in \mathcal{L}(U, V)$ such that $\alpha(u_i) = \beta(u_i)$ for $1 \le i \le n$, then $\alpha = \beta$.
> Moreover, let $v_1, ..., v_n$ be arbitrary vectors in $V$.
> Then there exists one and only one linear transformation $\alpha \in \mathcal{L}(U, V)$ such that $\alpha(u_i) = v_i$.
>
> *Proof.*{: .prf}
>
> Since $\Set{u_1, ..., u_n}$ is a basis of $V$, any vector $u \in U$ can be expressed as $\sum \lambda_i u_i$.
> Therefore, if $\alpha(u_i) = \beta(u_i)$, for all $u \in U$, we have
>
> $$
  \alpha(u) = \alpha \left( \sum_{i=1}^n \lambda_i u_i \right) = \sum_{i=1}^n \lambda_i \alpha(u_i) = \sum_{i=1}^n \lambda_i \beta(u_i) = \beta \left( \sum_{i=1}^n \lambda_i u_i \right) = \beta(u)
  $$
>
> and $\alpha = \beta$.
>
> Given $v_1, ..., v_n \in W$, define a mapping $\alpha: U \to V$ by
>
> $$
  \alpha(u) = \alpha \left( \sum \lambda_i u_i \right) = \sum \lambda_i v_i
  $$
>
> Since $\Set{u_i, ..., u_n}$ is a basis of $U$, the linear combination $u = \sum \lambda_i u_i$ is unique and therefore $\alpha$ is well-defined.
>
> Moreover, we have
>
> $$
  \begin{align*}
  \alpha (\lambda u + \mu u') &= \alpha \left( \lambda \sum \lambda_i u_i + \mu \sum \mu_i u_i \right) \\
  &= \alpha \left( \sum (\lambda \lambda_i + \mu \mu_i) u_i \right) \\
  &= \sum (\lambda \lambda_i + \mu \mu_i) v_i \\
  &= \lambda \sum \lambda_i v_i + \mu \sum \mu_i v_i \\
  &= \lambda \alpha(u) + \mu \alpha(u')
  \end{align*}
  $$
>
> so $\alpha$ is a linear map. By construction, $\alpha(u_i) = v_i$ and its uniqueness is proved above.

It means that linear map is completely determined by its effect on a set of basis vectors.
Conversely, we can define a unique linear map by assigning arbitrary images for a set of basis vectors.

> *Corollary.*{: .cor}
> Suppose that $U$ and $V$ are vector spaces of the same dimension $n$ and $\Set{u_1, ... u_n}$ is a basis of $U$.
> Then there is a bijection $\Phi$ between the set of isomorphisms $U \to V$ and the set of (ordered) bases for $V$
> that sends the isomorphism $\alpha: U \to V$ to the (ordered) basis $(\alpha(u_1), ..., \alpha(u_n))$.
>
> *Proof.*{: .prf}
>
> If $S$ is a basis of $U$ and $\alpha$ is an isomorphism, then $\alpha(S)$ is a basis of $V$ so $\Phi$ is well-defined.
> Conversely, let $\Set{v_1, ..., v_n}$ be a basis of $V$.
> There exists linear maps $\alpha \in \mathcal{L}(U, V)$ such that $\alpha(u_i) = v_i$ and $\beta \in \mathcal{L}(V, U)$ such that $\beta(v_i) = u_i$.
> $\beta$ is the inverse of $\alpha$ and therefore $\alpha$ is an isomorphism.
>
> From the above, $\Phi$ is both injective and surjective so it is bijective.

It can be considered as a special case that if the arbitrary vectors appeared to be a basis of $V$ then the corresponding linear map is an isomorphism.

> *Corollary.*{: .cor}
> If $U$ and $V$ are finite dimensional vector spaces over $\mathbb{F}$ with ordered bases $(e_1, ..., e_m)$ and $(f_1, ..., f_n)$ respectively then there is a bijection
>
> $$
  \mathrm{Mat}_{n, m}(\mathbb{F}) \leftrightarrow \mathcal{L}(U, V)
  $$
>
> that sends a matrix $A$ to the unique linear map $\alpha$ such that $\alpha(e_i) = \sum A_{ji} f_j$.
>
> *Proof.*{: .prf}
>
> Given a linear map $\alpha \in \mathcal{L}(U, V)$, there exists a unique ordered set of vectors $(v_1, ..., v_m)$ in $V$ such that $\alpha(e_i) = v_i$ for each $1 \le i \le m$.
> Since $(f_1, ..., f_n)$ is a basis of $V$, we have $v_i = \sum A_{ji} f_j$ with $A_{ji} \in \mathbb{F}$.
> The $n$-by-$m$ matrix $A = (A\_{ji})$ is therefore uniquely determined by the linear map $\alpha$.

> *Definition.*{: .def}
> If $\alpha \in \mathcal{L}(U, V)$, $(e_1, ..., e_m)$ is a basis for $U$ and $(f_1, ..., f_n)$ is a basis for $V$,
> then the $n$-by-$m$ matrix $A$ such that $\alpha(e_i) = \sum A_{ji} f_j$ is the **matrix representation** of $\alpha$ with respect to bases.

In fact, we can choose to write the coefficients by rows ($m$-by-$n$) or columns ($n$-by-$m$) when we form the matrix.
The reason to have the $i$-th column containing the coefficients of the linear combination of the $i$-th basis vector is that we want to align the result of linear maps composition and matrix multiplication, i.e. $\alpha\beta = (A_{ij})(B_{ij})$.

> *Proposition.*{: .prop}
> Suppose that $U$, $V$, $W$ are finite dimensional vector spaces over $\mathbb{F}$ with bases $R = (u_1, ..., u_r)$, $S = (v_1, ..., v_s)$ and $T = (w_1, ..., w_t)$ respectively,
> and $\alpha \in \mathcal{L}(U, V)$ and $\beta \in \mathcal{L}(V, W)$ represented by matrices $A$ and $B$ respectively (with respect to corresponding bases).
> Then $\beta \alpha$ is the linear map $U \to W$ represented by $BA$ with respect to $R$ and $T$.
>
> *Proof.*{: .prf}
>
> $$
  \beta(\alpha(u_i)) = \beta \left( \sum_j A_{ji} v_j \right) = \sum_j A_{ji} \beta(v_j) = \sum_j A_{ji} \sum_k B_{kj} w_k = \sum_k \left( \sum_j B_{kj} A_{ji} \right) w_k = \sum_k (BA)_{ki} w_k
  $$

## Rank and Nullity

> *Definition.*{: .def}
> Suppose that $\alpha: U \to V$ is a linear map. The **image** of $\alpha$ is defined by
>
> $$
  \text{Im}\, \alpha = \Set{\alpha(u) : u \in U}
  $$
>
> and the **kernel** of $\alpha$ is defined by
>
> $$
  \ker \alpha = \Set{u \in U : \alpha(u) = 0}
  $$

By definition, $\alpha$ is injective iff $\ker \alpha = 0$ and surjective iff $\text{Im}\, \alpha = V$.

> *Theorem.*{: .thm}
> **[First Isomorphism Theorem]**
> Let $\alpha: U \to V$ be a linear map between vector spaces over $\mathbb{F}$.
> Then $\ker \alpha$ is a subspace of $U$ and $\text{Im}\, \alpha$ is a subspace of $V$.
> Moreover $\alpha$ induces an isomorphism $\bar{\alpha}: U / \ker \alpha \to \text{Im}\, \alpha$ given by
>
> $$
  \bar{\alpha}(u + \ker \alpha) = \alpha(u)
  $$
>
> *Proof.*{: .prf}
>
> Since $\alpha(0) = 0$, $0 \in \ker \alpha$. Suppose that $u_1, u_2 \in \ker \alpha$, then
>
> $$
  \alpha(\lambda u_1 + \mu u_2) = \lambda \alpha(u_1) + \mu \alpha(u_2) = 0
  $$
>
> so $\ker \alpha \le U$. Similarily, $0 \in \text{im}\, \alpha$ and for $\alpha(u_1), \alpha(u_2) \in \text{Im}\, \alpha$, we have
>
> $$
  \lambda \alpha(u_1) + \mu \alpha(u_2) = \alpha(\lambda u_1 + \mu u_2) \in \text{Im}\, \alpha
  $$
>
> so $\text{Im}\, \alpha \le V$.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 2
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 3
