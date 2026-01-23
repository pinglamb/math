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

> *Proposition.*{: .prop}
> Suppose that $\phi: V \times V \to \mathbf{F}$ is a bilinear form and $(e_1, ..., e_n)$ is a basis for $V$ and $M$ is the matrix representing $\phi$ with respect to this basis.
> Then $\phi$ is symmetric iff $M$ is symmetric, i.e. $M^\intercal = M$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) If $\phi$ is symmetric then $M_{ij} = \phi(e_i, e_j) = \phi(e_j, e_i) = M_{ji}$ so $M$ is symmetric.
>
> ($\Leftarrow$) If $M$ is symmetric then
>
> $$
  \phi(x, y) = \sum_{i,j=1}^n x_i M_{ij} y_j = \sum_{i,j=1}^n j_i M_{ji} x_i = \phi(y, x)
  $$

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 7
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Section 31
