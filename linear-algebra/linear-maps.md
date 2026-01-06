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

> *Proposition.*{: .prop}
> $\mathcal{L}(U, V)$ is a vector space over $\mathbb{F}$, with respect to the operations
>
> $$
  (\alpha + \beta)(u) = \alpha(u) + \beta(u)
  $$
>
> and
>
> $$
  (\lambda \alpha)(u) = \lambda(\alpha(u))
  $$
>
> *Proof.*{: .prf}
>
> We have
>
> $$
  (\alpha + \beta)(\lambda u_1 + \mu u_2) = \alpha(\lambda u_1 + \mu u_2) + \beta(\lambda u_1 + \mu u_2) = \lambda (\alpha + \beta)(u_1) + \mu (\alpha + \beta)(u_2)
  $$
>
> so $\alpha + \beta$ is a linear map and $\alpha + \beta$ is well defined.
>
> Similarily,
>
> $$
  (\lambda \alpha)(\mu u_1 + \nu u_2) = \lambda (\alpha (\mu u_1 + \nu u_2)) = \mu (\lambda \alpha)(u_1) + \nu (\lambda \alpha)(u_2)
  $$
>
> so $\lambda \alpha$ is a linear map and $\lambda \alpha$ is well defined.
>
> The linear transformation $0$ that sends each $u \in U$ into $0$ is the additive identity and $(-\alpha)(u) = -(\alpha(u))$ is the additive inverse of $\alpha$.
> We can then see that such construction satisfies all the axioms of vector space.

We will later on see that the $\dim \mathcal{L}(U, V) = \dim U \times \dim V$.

$\mathcal{L}(U, V)$ has one more operation: multiplication of linear maps $\alpha \beta$ which satisfies the associative and distributive laws.
Therefore, $\mathcal{L}(U, V)$ is a _ring_.

## Isomorphism

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

> *Corollary.*{: .cor}
> $\dim \mathcal{L}(U, V) = \dim U \times \dim V$.
>
> *Proof.*{: .prf}
>
> For the $\dim U$ basis vectors of $U$, each of them can be mapped to an arbitrary vector in $V$, which is a linear combination of the $\dim V$ basis vectors of $V$.
> Therefore, each basis vector of $U$ has $\dim V$ free choices of coefficients, and $\dim \mathcal{L}(U, V) = \dim U \times \dim V$.

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

The columns of $A$ are representing the linear combination of each $u_i$ in terms of $v_j$ and that of $B$ are representing the linear combination of each $v_j$ in terms of $w_k$.
The columns of their product $BA$ are representing the linear combination of each $u_i$ in terms of $w_k$.
When looking at a single entry $(BA)_{ki}$ which is the coefficient of the $w_k$ term for $u_i$, we can see that the related entries are obviously the $i$-th column of $A$ ($u_i$) and $k$-th row of $B$ ($w_k$)
and from the above we can conclude that $(BA)\_{ki} = \sum B\_{kj}A\_{ji}$.

## Rank and Nullity

> *Definition.*{: .def}
> Suppose that $\alpha: U \to V$ is a linear map. The **image** of $\alpha$ is defined by
>
> $$
  \text{Im}\, \alpha = \Set{\alpha(u) : u \in U}
  $$
>
> and the **kernel**/**nullspace** of $\alpha$ is defined by
>
> $$
  \ker \alpha = \Set{u \in U : \alpha(u) = 0}
  $$

> *Proposition.*{: .prop}
> A linear map $\alpha$ is injective iff $\ker \alpha = 0$ and surjective iff $\text{Im}\, \alpha = V$.
>
> *Proof.*{: .prf}
>
> If $\ker \alpha = 0$, if $\alpha(v_1) = \alpha(v_2)$, $\alpha(v_1 - v_2) = 0$ and $v_1 = v_2$ so $\alpha$ is injective.
>
> By definition, $\text{Im}\, \alpha = V$ is equivalent to surjectivity.

> *Proposition.*{: .prop}
> Let $\alpha: U \to V$ be a linear map between vector spaces over $\mathbb{F}$.
> Then $\ker \alpha$ is a subspace of $U$ and $\text{Im}\, \alpha$ is a subspace of $V$.
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

> *Theorem.*{: .thm}
> **[First Isomorphism Theorem]**
> A linear map $\alpha: U \to V$ induces an isomorphism $\bar{\alpha}: U / \ker \alpha \to \text{Im}\, \alpha$ given by
>
> $$
  \bar{\alpha}(u + \ker \alpha) = \alpha(u)
  $$
>
> *Proof.*{: .prf}
>
> If $u + \ker \alpha = u' + \ker \alpha \in U / \ker \alpha$, then $u - u' \in \ker \alpha$ and $\alpha(u - u') = 0$ which implies $\alpha(u) = \alpha(u')$ so $\bar{\alpha}$ is well-defined.
>
> $\bar{\alpha}$ is linear since $\bar{\alpha}(\lambda[u_1] + \mu[u_2]) = \alpha(\lambda u_1 + \mu u_2) = \lambda \alpha(u_1) + \lambda \alpha(u_2) = \lambda \bar{\alpha}([u_1]) + \mu \bar{\alpha}([u_2])$.
>
> $\bar{\alpha}(u + \ker \alpha) = 0$ implies $\alpha(u) = 0$ so $u \in \ker \alpha$ and $u + \ker \alpha = 0$. $\ker \bar{\alpha} = 0$ so $\bar{\alpha}$ is injective.
> By construction, $\bar{\alpha}$ is surjective. Hence, $\bar{\alpha}$ is bijective and is an isomorphism.

> *Definition.*{: .def}
> Suppose that $\alpha: U \to V$ is a linear map between finite dimensional vector spaces.
> The **nullity** of $\alpha$ is defined by $n(\alpha) = \dim \ker \alpha$ and **rank** is defined by $r(\alpha) = \dim \text{Im}\, \alpha$.

> *Theorem.*{: .thm}
> **[Rank-Nullity Theorem]**
> If $\alpha: U \to V$ is a linear map between finite dimensional vector spaces over $\mathbb{F}$ then
>
> $$
  r(\alpha) + n(\alpha) = \dim U
  $$
>
> *Proof.*{: .prf}
>
> By the isomorphism theorem, $\dim U / \ker \alpha = \dim \text{Im}\, \alpha = r(\alpha)$.
> For the quotient space $U / \ker \alpha$, $\dim U / \ker \alpha = \dim U - \dim \ker \alpha = \dim U - n(\alpha)$.
> Hence, $\dim U = n(\alpha) + r(\alpha)$.

The rank-nullity theorem is very important and worth of a more direct proof.
This proof relies on the important property that linear map is determined by its effect on the basis vectors and the ability to extend any set of linear independent vectors to a basis.
With that, we can define a basis for the kernel subspace and extend it to a basis for the domain and study how the linear map transform them.

> *Theorem.*{: .thm}
> **[Rank-Nullity Theorem Again]**
> If $\alpha: U \to V$ is a linear map between finite dimensional vector spaces over $\mathbb{F}$
> then there are bases $(e_1, ..., e_n)$ for $U$ and $(f_1, ..., f_m)$ for $V$ such that the matrix representing $\alpha$ is
>
> $$
  \begin{pmatrix}
  I_r & 0 \\
  0 & 0
  \end{pmatrix}
  $$
>
> where $r = r(\alpha)$ and $I_r$ is the identity matrix. In particular, $r(\alpha) + n(\alpha) = \dim U$.
>
> *Proof.*{: .prf}
>
> Let $(e_{r+1}, ..., e_n)$ be a basis for $\ker \alpha$ and extend it to a basis $(e_1, ..., e_n)$ for $U$.
> Then $\alpha(e_i) = 0$ for $r+1 \le i \le n$ and let $f_i = \alpha(e_i)$ for $1 \le i \le r$.
> We have to show that $(f_1, ..., f_r)$ is a basis for $\text{Im}\, \alpha$.
>
> If $\sum_{i=1}^r \lambda_i f_i = 0$, then
>
> $$
  \sum_{i=1}^r \lambda_i \alpha(e_i) = \alpha \left( \sum_{i=1}^r \lambda_i e_i \right) = 0
  $$
>
> Since $\ker \alpha \cap \langle e_1, ..., e_r \rangle = 0$ by construction, it implies $\sum_{i=1}^r \lambda_i e_i = 0$ and $\lambda_i = 0$.
> Therefore, $\Set{f_1, ..., f_r}$ is linearly independent.
>
> For any $v \in \text{Im}\, \alpha$, we have
>
> $$
  v = \alpha \left( \sum_{i=1}^n \lambda_i e_i \right) = \sum_{i=1}^n \lambda_i \alpha(e_i) = \sum_{i=1}^r \lambda_i f_i
  $$
>
> so $\langle f_1, ..., f_r \rangle = \text{Im}\, \alpha$ and $(f_1, ..., f_r)$ is a basis for $\text{Im}\, \alpha$.
> Hence,
>
> $$
  \dim U = n = (n - r) + r = n(\alpha) + r(\alpha)
  $$
>
> We can then extend $\Set{f_1, ..., f_r}$ to a basis $\Set{f_1, ..., f_m}$ for $V$, and
>
> $$
  \alpha(e_i) = \begin{cases}
  f_i & 1 \le i \le r \\
  0 & r+1 \le i \le m
  \end{cases}
  $$
>
> so the matrix representing $\alpha$ with respect to our choice of bases is as in the proposition.

> *Corollary.*{: .cor}
> Suppose that $\alpha: U \to V$ is a linear map between two vector spaces of the same dimension $n$.
> Then the following are equivalent:
>
> + $\alpha$ is injective;
>
> + $\alpha$ is surjective;
>
> + $\alpha$ is an isomorphism.
>
> *Proof.*{: .prf}
>
> $\alpha$ is injective iff $n(\alpha) = 0$ iff $r(\alpha) = n$ iff $\alpha$ is surjective.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 2
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 3
