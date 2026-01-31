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

> *Definition.*{: .def}
> Suppose that $V$ is an inner product space. Then $\alpha \in \text{End}(V)$ is **self-adjoint** if $\alpha = \alpha^\ast$,
> i.e. if $\langle \alpha(v_1), v_2 \rangle = \langle v_1, \alpha(v_2) \rangle$ for all $v_1, v_2 \in V$.

Therefore, a complex matrix $A$ is self-adjoint iff $A = A^\dagger$, i.e. Hermitian.

> *Definition.*{: .def}
> Suppose that $V$ is an inner product space. Then $\alpha \in \text{End}(V)$ is **normal** if $\alpha \alpha^\ast = \alpha^\ast \alpha$.

Self-adjoint maps are always normal but normal maps might not be self-adjoint, like the _unitary_ map.

> *Definition.*{: .def}
> Suppose that $V$ is real (resp. complex) inner product space and $\alpha \in \text{End}(V)$.
> Then $\alpha$ is **orthogonal** (resp. **unitary**) if $\langle \alpha(v_1), \alpha(v_2) \rangle = \langle v_1, v_2 \rangle$ for all $v_1, v_2 \in V$.

By polarization identity, $\alpha$ is orthogonal/unitary iff $\Vert \alpha(v) \Vert = \Vert v \Vert$ for all $v \in V$.

> *Proposition.*{: .prop}
> $\alpha \in \text{End}(V)$ is orthogonal/unitary iff $\alpha$ is invertible and $\alpha^\ast = \alpha^{-1}$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Let $(e_1, ..., e_n)$ be an orthonormal basis for $V$. Then
>
> $$
  \delta_{ij} = \langle e_i, e_j \rangle = \langle \alpha(e_i), \alpha(e_j) \rangle = \langle e_i, \alpha^\ast \alpha(e_j) \rangle
  $$
>
> so $\alpha^\ast \alpha = \iota$ as required.
>
> ($\Leftarrow$) If $\alpha^\ast = \alpha^{-1}$, then $\langle v_1, v_2 \rangle = \langle v_1, \alpha^\ast \alpha(v_2) \rangle = \langle \alpha(v_1), \alpha(v_2) \rangle$.

A square real (resp. complex) matrix is therefore orthogonal (resp. unitary) iff $A^\intercal A = I$ (resp. $A^\dagger A = I$) or equivalently iff the columns of $A$ form an orthonormal basis.

> *Corollary.*{: .cor}
> $\alpha \in \text{End}(V)$ is orthogonal/unitary iff $\alpha$ is represented by an orthogonal/unitary matrix with respect to any orthonormal basis.

## Spectral Theorem

The result of the theorem is that normal linear maps are always diagonalizable and the corresponding eigenvectors belonging to distinct eigenvalues are orthogonal.

> *Lemma.*{: .lem}
> Let $\alpha \in \text{End}(V)$ be normal. Then there exist common eigenvectors $v$ for $\alpha$ and $\alpha^\ast$ such that $\alpha v = \lambda v$ and $\alpha^\ast v = \bar{\lambda} v$.
>
> *Proof.*{: .prf}
>
> Let $\lambda$ be an eigenvalue of $\alpha$ which always exist since $\mathbf{C}$ is algebraically closed and $v \in E_\alpha(\lambda)$. Then
>
> $$
  \alpha (\alpha^\ast v) = \alpha^\ast \alpha v = \alpha^\ast \lambda v = \lambda(\alpha^\ast v)
  $$
>
> so $\alpha^\ast v \in E_\alpha(\lambda)$ and $\lambda$-eigenspace is $\alpha^\ast$-invariant.
> Therefore, $\alpha^\ast_{E_\alpha(\lambda)} \in \text{End}(E_\alpha(\lambda))$ has an eigenvector in $E_\alpha(\lambda)$ and so as $\alpha^\ast$ and such a vector is a common eigenvector of $\alpha$ and $\alpha^\ast$.
>
> Let $\alpha(v) = \lambda v$ and $\alpha^\ast(v) = \mu v$. Then
>
> $$
  \bar{\lambda} \langle v, v \rangle = \langle \alpha(v), v \rangle = \langle v, \alpha^\ast(v) \rangle = \mu \langle v, v \rangle
  $$
>
> so $\mu = \bar{\lambda}$ as required.

> *Lemma.*{: .lem}
> Let $\alpha \in \text{End}(V)$ be normal and $v$ and $v'$ be eigenvectors for $\alpha$ and $\alpha^\ast$ simultaneously such that $v$ and $v'$ belong to distinct eigenvalues for $\alpha$.
> Then $\langle v, v' \rangle = 0$.
>
> *Proof.*{: .prf}
>
> Let $\alpha v = \lambda v$ and $\alpha v' = \mu v'$ with $\lambda \not= \mu$. Then $\alpha^\ast v = \bar{\lambda v}$ and $\alpha^\ast v' = \bar{\mu} v'$.
> Therefore, we have
>
> $$
  \bar{\lambda} \langle v, v' \rangle = \langle \alpha(v), v' \rangle = \langle v, \alpha^\ast(v') \rangle = \langle v, \bar{\mu} v' \rangle = \bar{\mu} \langle v, v' \rangle
  $$
>
> and $\langle v, v' \rangle = 0$ since $\lambda \not= \mu$.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 8.3, 8.4
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 32
