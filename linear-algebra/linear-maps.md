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
> A linear map $\alpha: U \to V$ is an **isomorphism** if there is a $\beta: V \to U$ such that $\beta \alpha = \mathrm{id}_U$ and $\alpha \beta = \mathrm{id}_V$.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 2
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 3
