---
layout: base
title: Quadratic Forms &#124; Linear Algebra
---

# Quadratic Forms
{: .page-title}

Similar to endomorphisms, we can restrict bilinear forms on a single vector space and choose the same basis for both sides.

> *Proposition.*{: .prop}
> Suppose that $V$ is a finite-dimensional vector space over $\mathbf{F}$ and $\phi: V \times V \to \mathbf{F}$ is a bilinear form
> and $(e_1, ..., e_n)$ and $(f_1, ..., f_n)$ are two bases of $V$ such that $f_i = \sum P_{ki} e_k$.
> If $A$ represents $\phi$ with respect to $(e_i)$ and $B$ represents $\phi$ with respect to $(f_i)$ then
>
> $$
  B = P^\intercal AP
  $$

> *Definition.*{: .def}
> The square matrices $A$ and $B$ are **congruent** if there is an invertible matrix $P$ such that $B = P^\intercal AP$.

> *Definition.*{: .def}
> A bilinear form $\phi: V \times V \to \mathbf{F}$ is **symmetric** if $\phi(v_1, v_2) = \phi(v_2, v_1)$ for all $v_1, v_2 \in V$.
