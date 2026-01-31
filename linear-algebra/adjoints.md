---
layout: base
title: Adjoints &#124; Linear Algebra
---

# Adjoints
{: .page-title}

Adjoint is the analog of the transpose of a linear map for inner product spaces.

> *Definition.*{: .def}
> Suppose that $V$ and $W$ are finite dimensional inner product spaces and $\alpha: V \to W$ is linear.
> An **adjoint** of $\alpha$ is the linear map $\alpha^\ast: W \to V$ such that $\langle \alpha(v), w \rangle = \langle v, \alpha^\ast(w) \rangle$ for all $v \in V$ and $w \in W$.

> *Proposition.*{: .prop}
> Suppose that $V$ and $W$ are finite dimensional inner product spaces and $\alpha: V \to W$ is linear. Then $\alpha$ has a uniquely determined adjoint $\alpha^\ast$.
> If the matrix of $\alpha$ with respect to an orthonormal basis is $A$ then the matrix of $\alpha^\ast$ is $A^\dagger$.
>
> *Proof.*{: .prf}
>
> Let $(e_1, ..., e_m)$ be an orthonormal basis for $V$ and $(f_1, ..., f_n)$ be an orthonormal basis for $W$.
> Let $\alpha: V \to W$ be represented by $A$ and $\alpha^\ast: W \to V$ be represented by $B$.
> Then
>
> $$
  \langle e_i, \alpha^\ast(f_j) \rangle = \left\langle e_i, \sum_k B_{kj} e_j \right\rangle = \sum_k B_{kj} \langle e_i, e_k \rangle = B_{ij}
  $$
>
> and
>
> $$
  \langle e_i, \alpha^\ast(f_j) \rangle = \langle \alpha(e_i), f_j \rangle = \left\langle \sum_k A_{ki} f_k, f_j \right\rangle = \sum_k \overline{A_{ki}} \langle f_k, f_j \rangle = \overline{A_{ji}}
  $$
>
> so $B = A^\dagger$ is unique if it exists.
>
> But now we can assume $\alpha^\ast$ be the linear map represented by $A^\dagger$ and for any $v \in V$ and $w \in W$,
>
> $$
  \langle \alpha(v), w \rangle = \left\langle \alpha \left( \sum_i \lambda_i e_i \right), \sum_j \mu_j f_j \right\rangle
  = \sum_{i,j} \overline{\lambda_i} \mu_j \left\langle \sum_k A_{ki} f_k, f_j \right\rangle = \sum_{i,j} \overline{\lambda_i} \mu_j \overline{A_{ji}}
  $$
>
> and
>
> $$
  \langle v, \alpha^\ast(w) \rangle = \left\langle \sum_i \lambda_i e_i, \alpha^\ast \left( \sum_j \mu_j f_j \right) \right\rangle
  = \sum_{i,j} \overline{\lambda_i} \mu_j \left\langle e_i, \sum_k A^\dagger_{kj} e_j \right\rangle = \sum_{i,j} \overline{\lambda_i} \mu_j \overline{A_{ji}}
  $$
>
> Hence, $\langle \alpha(v), w \rangle = \langle v, \alpha^\ast(w) \rangle$ as required.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 8.3, 8.4
