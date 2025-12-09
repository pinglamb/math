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
