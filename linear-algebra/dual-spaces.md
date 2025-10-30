---
layout: base
title: Dual Spaces &#124; Linear Algebra
---

# Dual Spaces
{: .page-title}

The other way to construct is base on the idea that every vector space $V$ and linear map $\alpha$,
there is a vector space $V^\ast$ which mirrors $V$, and a linear map $\alpha^\ast$ of $V^\ast$ which mirrors $\alpha$.

> *Definition.*{: .def}
> Let $V$ be a finite dimensional vector space over $\mathbb{F}$.
> The **dual space** $V^\ast$ of $V$ is defined to be the vector space $\mathcal{L}(V, \mathbb{F})$.
> The elements of $V^\ast$ are **linear forms/functions** from $V$ into $\mathbb{F}$,
> i.e. $f: V \to \mathbb{F} \in V^\ast$ such that $f(v_1 + v_2) = f(v_1) + f(v_2)$ and $f(\lambda v) = \lambda f(v)$.
> The addition and scalar multiplication of $V^\ast$ are $(f_1 + f_2)(v) = f_1(v) + f_2(v)$ and $(\lambda f)(v) = f(\lambda v)$.

> *Proposition.*{: .prop}
> Suppose that $V$ is finite dimensional vector space over $\mathbb{F}$ with basis $(e_1, ..., e_n)$.
> Then $V^\ast$ has a basis $(f_1, ..., f_n)$ such that $f_i(e_j) = \delta_{ij}$.
>
> *Proof.*{: .prf}
>
> The linear functions ${f_i}$ exist because we can always map the basis vectors to arbitrary vectors in the codomain.
> For $(f_1, ..., f_n)$ to be a basis, we need to show that it is linearly independent and spans $V^\ast$.
> Since they are linear functions, we just need to care about how they transform the basis vectors $(e_1, ..., e_n)$ as
> $f = f'$ iff $f(e_j) = f'(e_j)$ for $j = 1, ..., n$.
>
> Suppose that $\sum \lambda_i f_i = 0$, in which $0$ is the zero function $0(v) = 0$ for all $v \in V$.
> Since
>
> $$
  \sum_i \lambda_i f_i(e_j) = \sum_i \lambda_i \delta_{ij} = \lambda_j = 0(e_j) = 0
  $$
>
> for all $j$, $\Set{f_i}$ is linearly independent.
>
> For any linear function $f \in V^\ast$, let $f(e_i) = \lambda_i$ for $i = 1, ..., n$. Then
>
> $$
  \sum_i \lambda_i f_i(e_j) = \lambda_j = f(e_j)
  $$
>
> and $\langle f_i \rangle = V^\ast$.

> *Definition.*{: .def}
> The basis $(f_1, ..., f_n)$ is called the **dual basis** of $V^\ast$ with respect to $(e_1, ..., e_n)$.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 3
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 8.26
