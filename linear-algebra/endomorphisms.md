---
layout: base
title: Endomorphisms &#124; Linear Algebra
---

# Endomorphisms
{: .page-title}

> *Definition.*{: .def}
> An **endomorphism** of $V$ is a linear map $\alpha: V \to V$.
> The vector space of endomorphisms of $V$ is denoted by $\text{End}(V)$ and the identity endomorphism is denoted by $\iota$.

The key difference while considering endomorphisms as matrices is that the same basis will be used for both the domain and the range which leads to some other properties.

## Basis

The standard basis of $\text{Mat}_n(\mathbb{F})$ can be useful sometimes for proving properties of the corresponding endomorphism.

> *Definition.*{: .def}
> The standard basis for $\text{Mat}_n(\mathbb{F})$ consists of $n^2$ matrices $\Set{E\_{ij}}$ in which
>
> $$
  (E_{ij})_{kl} = \begin{cases}
  1 & i = k, j = l \\
  0 & \text{otherwise}
  \end{cases}
  $$

> *Proposition.*{: .prop}
> $E\_{ij} E\_{kl} = \delta_{jk} E_{il}$.
>
> *Proof.*{: .prf}
>
> $$
  (E_{ij} E_{kl})_{pq} = \sum_{r = 1}^n (E_{ij})_{pr} (E_{kl})_{rq}
  $$
>
> $(E\_{ij})\_{pr} = 1$ if $p = i$ and $r = j$ and $(E\_{kl})\_{rq} = 1$ if $q = l$ and $r = k$ so only $(E\_{ij} E\_{kl})_{il}$ can be non-zero provided that $j = k$.

> *Definition.*{: .def}
> The **commutator** of two elements $a$ and $b$ of a ring is the element $[a, b] = ab - ba$.
> The elements $a$ and $b$ are said to **commute** if the commutator is zero, i.e. $ab = ba$.

> *Proposition.*{: .prop}
> Every off-diagonal basis matrices are commutators, specifically $E\_{ij} = E\_{ik}E\_{kj} - E\_{kj}E\_{ik}$ for $i \not= j$.
>
> *Proof.*{: .prf}
>
> $E\_{ik}E\_{kj} = E_{ij}$ and $E\_{kj}E\_{ik} = 0$ when $i \not= j$.

## Invariants

We will first address properties of matrices that are invariant up to similarity.

> *Proposition.*{: .prop}
> Suppose that $(e_1, ..., e_n)$ and $(f_1, ..., f_n)$ are bases for $V$ such that $f_i = \sum P_{ki} e_k$.
> Let $\alpha \in \text{End}(V)$, $A$ be the matrix representing $\alpha$ with respect to $(e_i)$ and $B$ the matrix representing $\alpha$ with respect to $(f_i)$.
> Then $B = P^{-1}AP$.
>
> *Proof.*{: .prf}
>
> $P$ is the identity map from basis $(f_i)$ to $(e_i)$.
> The relation is just a special case of the change of basis formula with $Q = P$.

> *Definition.*{: .def}
> Matrices $A$ and $B$ are **similar** (or **conjugate**) if $B = P^{-1}AP$ for some invertible matrix $P$.

In terms of group theory, recall $\text{GL}_n(\mathbb{F})$ denotes all the invertible matrices
so $\text{GL}_n(\mathbb{F})$ acts on $\text{Mat}_n(\mathbb{F})$ by conjugation and two matrices are similar if they lie in the same orbit, and similarity is an equivalence relation.

> *Definition.*{: .def}
> The **trace** of a matrix $A$ is defined by $\text{tr}: \text{Mat}\_n(\mathbb{F}) \to \mathbb{F}$ such that $\text{tr}\,A = \sum A_{ii}$.

> *Proposition.*{: .prop}
> Suppose that $A \in \text{Mat}\_{n,m}(\mathbb{F})$ and $B \in \text{Mat}\_{m,n}(\mathbb{F})$.
> Then $\text{tr}\,AB = \text{tr}\,BA$.
>
> *Proof.*{: .prf}
>
> $$
  \text{tr}\,AB = \sum_{i=1}^n \left( \sum_{j=1}^m A_{ij} B_{ji} \right)  = \sum_{j=1}^m \left( \sum_{i=1}^n B_{ji} A_{ij} \right) = \text{tr}\,BA
  $$

> *Proposition.*{: .prop}
> Suppose that $f \in \text{Mat}_n(\mathbb{F})^\ast$ such that $f(AB) = f(BA)$ for all $A, B \in \text{Mat}_n(\mathbb{F})$.
> Then $f$ is a scalar multiple of the trace function.
>
> *Proof.*{: .prf}
>
> Since every off-diagonal basis matrices are commutators, for $i \not= j$, $f(E\_{ij}) = f(E\_{ik}E\_{kj} - E\_{kj}E\_{ik}) = 0$.
> For on-diagonal basis matrices, $f(E_{ii}) = f(E\_{ik}E\_{ki} - E\_{ki}E\_{ik}) = 0$ so $f(E_{ii}) = f(E_{kk})$ and all of them have the same scalar value $\lambda$.
> Hence, for any matrix $A$, $f(A) = \sum A_{ii} f(E_{ii}) = \lambda \text{tr}(A)$.

> *Proposition.*{: .prop}
> If matrices $A$ and $B$ are similar. Then
>
> + $\text{tr}\,A = \text{tr}\,B$;
>
> + $\det A = \det B$.
>
> *Proof.*{: .prf}
>
> + $\text{tr}\,B = \text{tr}\,P^{-1}AP = \text{tr}\,AP^{-1}P = \text{tr}\,A$.
>
> + $\det B = \det P^{-1}AP = \det A \det P^{-1} \det P = \det A$.

Since the trace and determinant are independent of the choice of basis, we can define:

> *Definition.*{: .def}
> The **trace** and **determinant** of an endomorphism $\alpha$, i.e. $\text{tr}\,\alpha$ and $\det \alpha$, are defined to be the trace and determinant of any matrix representing $\alpha$ respectively.

> *Proposition.*{: .prop}
> Let $\alpha^\ast \in \text{End}(V^\ast)$ be the dual of $\alpha \in \text{End}(V)$.
> Then $\det \alpha^\ast = \det \alpha$ and $\text{tr}\,\alpha^\ast = \text{tr}\,\alpha$.
>
> *Proof.*{: .prf}
>
> Since $\det A^\intercal = \det A$ and $\text{tr}\,A^\intercal = \text{tr}\,A$.

## References

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 6
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 7
