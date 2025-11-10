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
> A bilinear form $\phi: V \times W \to \mathbb{F}$ induces linear maps $\phi_L: V \to W^\ast$ and $\phi_R: W \to V^\ast$ defined by
>
> $$
  \phi_L(v)(w) = \phi(v, w) = \phi_R(w)(v)
  $$
>
> for $v \in V$ and $w \in W$.

Base on the above, we can see that $\phi: V \times V^\ast \to \mathbb{F}, \phi(v, \theta) = \theta(v)$ is a bilinear form with $\phi_L: V \to V^{\ast\ast} = \text{ev}$ and $\phi_R: V^\ast \to V^\ast = \iota_{V^\ast}$.

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

> *Definition.*{: .def}
> $\ker \phi_L$ is the **left kernel** of $\phi$ and $\ker \phi_R$ is the **right kernel** of $\phi$, i.e.
>
> $$
  \begin{align*}
  \ker \phi_L &= \Set{v \in V : \forall w \in W, \phi(v, w) = 0} \\
  \ker \phi_R &= \Set{w \in W : \forall v \in V, \phi(v, w) = 0}
  \end{align*}
  $$

By considering the subsets $S \subset V$ and $T \subset W$, it is a more general idea of _annihilator_.

> *Definition.*{: .def}
> Suppose that $V$ and $W$ are vector spaces with subspaces $S$ and $T$ respectively and $\phi: V \times W \to \mathbb{F}$ is a bilinear form.
> Then we define
>
> $$
  \begin{align*}
  S^\perp &= \Set{w \in W : \forall s \in S, \phi(s, w) = 0} \\
  {}^\perp T  &= \Set{v \in V : \forall t \in T, \phi(v, t) = 0}
  \end{align*}
  $$

## Non-degeneracy

We can now explore how bilinear form relates to dual spaces.

> *Definition.*{: .def}
> A bilinear form $\phi: V \times W \to \mathbb{F}$ is **non-degenerate** if $\ker \phi_L = 0$ and $\ker \phi_R = 0$. Otherwise $\phi$ is **degenerate**.

> *Proposition.*{: .prop}
> Suppose that $V$ and $W$ are finite dimensional vector spaces and $\phi: V \times W \to \mathbb{F}$ is a non-degenerate bilinear form.
> Then both $\phi_L: V \to W^\ast$ and $\phi_R: W \to V^\ast$ are isomorphisms and $\dim V = \dim W$.
>
> *Proof.*{: .prf}
>
> $\ker \phi_L = 0$ implies $\phi_L$ is injective and $\ker \phi_R = 0$ implies $\phi_R$ is injective.
> Therefore, $\dim W^\ast \ge \dim V$ and $\dim V^\ast \ge \dim W$ but $\dim V = \dim V^\ast$ so we have $\dim V = \dim W$.
> Hence, $\phi_L$ and $\phi_R$ are isomorphisms.

Base on that, the following definition of dual spaces is rather natural.

> *Definition.*{: .def}
> A pair of finite dimensional vector spaces $V$ and $W$ are **dual** with respect to a bilinear form $\phi: V \times W \to \mathbb{F}$ if $\phi$ is non-degenerate,
> i.e. each vector space is isomorphic to the dual space of the other.

## Matrix Representation

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

> *Proposition.*{: .prop}
> Let $(e_1, ..., e_m)$ be a basis for $V$ with dual basis $(\epsilon_1, ..., \epsilon_m)$ and $(f_1, ..., f_n)$ be a basis for $W$ with dual basis $(\eta_1, ..., \eta_n)$.
> If $A$ represents the bilinear form $\phi: V \times W \to \mathbb{F}$ with respect to $(e_i)$ and $(f_i)$
> then $A$ represents $\phi_R$ with respect to $(f_i)$ and $(\epsilon_i)$ and $A^\intercal$ represents $\phi_L$ with respect to $(e_i)$ and $(\eta_i)$.
>
> *Proof.*{: .prf}
>
> Suppose that $B$ is matrix representing $\phi_R$ and $C$ be that representing $\phi_L$. Then
>
> $$
  A_{ij} = \phi(e_i, f_j) = \phi_R(f_j)(e_i) = \left( \sum_k B_{kj} \epsilon_k \right) (e_i) = \sum_k B_{kj} \delta_{ik} = B_{ij}
  $$
>
> and
>
> $$
  A_{ij} = \phi(e_i, f_j) = \phi_L(e_i)(f_j) = \left( \sum_k C_{ki} \eta_k \right) (f_j) = \sum_k C_{ki} \delta_{kj} = C_{ji} = C_{ij}^\intercal
  $$

> *Proposition.*{: .prop}
> A bilinear form $\phi$ represented by matrix $A$ is non-degenerate iff $A$ is invertible.
>
> *Proof.*{: .prf}
>

> *Proposition.*{: .prop}
>

> *Definition.*{: .def}
> The **rank** of $\phi$, denoted by $r(\phi)$, is defined to be the rank of any matrix representing $\phi$.

We can see that the rank is independent of any choices and $r(\phi) = r(\phi_R) = r(\phi_L)$.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 4
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 8.27
