---
layout: base
title: Bilinear Forms &#124; Linear Algebra
---

# Bilinear Forms
{: .page-title}

Bilinear forms provide a different and more general way of looking at the relationship between a vector space and its dual.

> *Definition.*{: .def}
> A map $\phi: V \times W \to \mathbb{F}$ is a **bilinear form** if it is linear in both arguments, i.e.
> if $\phi(v, -): W \to \mathbb{F} \in W^\ast$ for all $v \in V$ and $\phi(-, w): V \to \mathbb{F} \in V^\ast$ for all $w \in W$.

> *Definition.*{: .def}
> Let $(e_1, ..., e_m)$ be a basis for $V$ and $(f_1, ..., f_n)$ be a basis for $W$ and $\phi: V \times W \to \mathbb{F}$ a bilinear form.
> Then the $m \times n$ matrix $A$ representing $\phi$ with respect to $(e_1, ..., e_m)$ and $(f_1, ..., f_n)$ is given by $A_{ij} = \phi(e_i, f_j)$.

Consider vectors $v = \sum \lambda_i e_i$ and $w = \sum \mu_j f_j$ then

$$
\phi(v, w) = \phi \left( \sum_i \lambda_i e_i, \sum_j \mu_j f_j \right) = \sum_i \sum_j \lambda_i \mu_j \phi(e_i, f_j)
$$

Therefore, if $A$ is the matrix representing $\phi$ then

$$
\phi(v, w) = \begin{pmatrix} \lambda_1 & \cdots & \lambda_m \end{pmatrix} A \begin{pmatrix} \mu_1 \\ \vdots \\ \mu_n \end{pmatrix}
$$

> *Definition.*{: .def}
> A bilinear form $\phi: V \times W \to \mathbb{F}$ induces linear maps $\phi_L: V \to W^\ast$ and $\phi_R: W \to V^\ast$ defined by
>
> $$
  \phi_L(v)(w) = \phi(v, w) = \phi_R(w)(v)
  $$
>
> for $v \in V$ and $w \in W$.

Base on the above, we can see that $\phi: V \times V^\ast \to \mathbb{F}, \phi(v, f) = f(v)$ is a bilinear form with $\phi_L: V \to V^{\ast\ast} = \text{ev}$ and $\phi_R: V^\ast \to V^\ast = \iota_{V^\ast}$.

> *Proposition.*{: .prop}
> $\phi_R = \phi_L^\ast \circ \text{ev}$ and $\phi_L = \phi_R^\ast \circ \text{ev}$.
>
> *Proof.*{: .prf}
>
> $\phi_L^\ast: W^{\ast\ast} \to V^\ast$ with $\phi_L^\ast(\theta)(v) = \theta(\phi_L(v)) \in \mathbb{F}$ for $\theta \in W^{\ast\ast} = \mathcal{L}(W^\ast, \mathbb{F})$ and $\text{ev}: W \to W^{\ast\ast}$
> so $\phi_L^\ast \circ \text{ev}: W \to V^\ast$ and the domain and codomain matches that of $\phi_R$.
> Hence,
>
> $$
  (\phi_L^\ast \circ \text{ev}(w))(v) = \text{ev}(w)(\phi_L(v)) = \phi_L(v)(w) = \phi_R(w)(v)
  $$

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 4
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 8.27
