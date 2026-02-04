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

> *Proposition.*{: .prop}
> Suppose that $\alpha \in \text{End}(V)$ is self-adjoint then all eigenvalues of $\alpha$ are real.
>
> *Proof.*{: .prf}
>
> Suppose that $\alpha v = \lambda v$, then
>
> $$
  \lambda \langle v, v \rangle = \langle v, \lambda v \rangle = \langle v, \alpha(v) \rangle = \langle \alpha(v), v \rangle = \langle \lambda v, v \rangle = \bar{\lambda} \langle v, v \rangle
  $$
>
> so $\lambda \in \mathbf{R}$.

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

> *Lemma.*{: .lem}
> Let $\Set{\beta_1, ..., \beta_s}$ a set of linear maps of $V$ such that $\iota = \sum \beta_i$ and $\beta_i \beta_j = 0$ if $i \not= j$.
> Then $\Set{\beta_i}$ are self-adjoint iff the subspaces $\Set{\beta_i V}$ are mutually orthogonal.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) For any $w_i = \beta_i(v)$ and $w_j \in \beta_j(v')$ with $i \not= j$,
>
> $$
  \langle w_i, w_j \rangle = \langle \beta_i(v), \beta_j(v') \rangle = \langle v, \beta_i \beta_j(v') \rangle = 0
  $$
>
> since $\beta_i = \beta_i^\ast$ and $\beta_i \beta_j = 0$.
>
> ($\Leftarrow$) Suppose that $\beta_i V$ and $\beta_j V$ are orthogonal for $i \not= j$, then $V$ and $\beta_i^\ast \beta_j V$ are orthogonal which implies $\beta_i^\ast \beta_j = 0$.
> Since $\iota = \sum \beta_i$ and $\beta_i \beta_j = 0$, we also have $\iota = \sum \beta_i^\ast$ and $\beta_i^\ast \beta_j^\ast = 0$ for $i \not= j$. Then
>
> $$
  \beta_i = \iota \beta_i = \left( \sum_k \beta^\ast_k \right) \beta_i = \beta_i^\ast \beta_i
  $$
>
> and
>
> $$
  \beta^\ast_i = \beta^\ast_i \iota = \beta^\ast_i \left( \sum_k \beta_k \right)= \beta_i^\ast \beta_i
  $$
>
> so $\beta_i^\ast = \beta_i$ and $\beta_i$ is self-adjoint.

> *Theorem.*{: .thm}
> **[Spectral Theorem]**
> Suppose that $V$ is an inner product space and $\alpha \in \text{End}(V)$ is normal.
> Let $\Set{\lambda_1, ..., \lambda_s}$ be distinct eigenvalues of $\alpha$.
> Then there exists polynomials $\Set{f_i(x)}$ such that the linear maps $\Set{\beta_i = f_i(\alpha)}$ are self-adjoint
> and satisfy the conditions $1 = \sum \beta_i$ and $\beta_i \beta_j = 0$ if $i \not= j$. Moreoever, $\alpha$ has a **spectral decomposition** of the form
>
> $$
  \alpha = \lambda_1 \beta_1 + \cdots + \lambda_s \beta_s
  $$
>
> *Proof.*{: .prf}
>
> If $\dim V = 1$, $\alpha$ is diagonalizable. Assume it is true for inner product space with $\dim V < n$.
> For $\dim V = n$, there exists a common eigenvector $u$ for $\alpha$ and $\alpha'$ such that $\alpha u = \lambda u$ and $\alpha^\ast u = \bar{\lambda} u$.
> Let $U = \langle u \rangle$ and $u^\perp \in U^\perp$. Then
>
> $$
  \langle u, \alpha(u^\perp) \rangle = \langle \alpha^\ast(u), u^\perp \rangle = \lambda \langle u, u^\perp \rangle = 0
  $$
>
> Similarily, $\langle u, \alpha^\ast(u^\perp) \rangle = 0$ so $\alpha(u^\perp), \alpha^\ast(u^\perp) \in U^\perp$ and $U^\perp$ is $\alpha$ and $\alpha^\ast$ invariant.
> Thus, since $\alpha$ is normal in $V$, the restriction of $\alpha$ to $U^\perp$ is also normal. By induction hypothesis, $U^\perp$ is diagonalizable and so as $V = U \oplus U^\perp$.
>
> Since $V$ is diagonalizable, there exists polynomials $\Set{f_i(x)}$ such that the linear maps $\Set{\beta_i = f_i(\alpha)}$ satisfy the conditions stated except for being self-adjoint,
> which is true if the subspaces $\beta_i V$ are mutually orthogonal. Since $\alpha$ and $\alpha'$ commutes and $\beta_i = f_i(\alpha)$, for any $v_i \in \beta_i V$, we have
>
> $$
  \alpha^\ast(v_i) = \alpha^\ast(\beta_i(v)) = \beta_i(\alpha^\ast(v)) \in \beta_i V
  $$
>
> so $\beta_i V$ is $\alpha^\ast$ invariant as well. Therefore, the restriction of $\alpha^\ast$ to $\beta_i V$ is normal and is diagonalizable.
> All the eigenvalues of $\alpha^\ast$ on $\beta_i V$ are therefore $\overline{\lambda_i}$ and every vector in $\beta_i V$ is a eigenvector for both $\alpha$ and $\alpha^\ast$.
> Hence, for $i \not= j$, $v_i \in \beta_i V$ and $v_j \in \beta_j V$ are both eigenvectors for $\alpha$ and $\alpha^\ast$ belonging to distinct eigenvalues $\lambda_i$ and $\lambda_j$
> so $\langle v_i, v_j \rangle = 0$ and $\beta_i V$ and $\beta_j V$ are orthogonal so $\Set{\beta_i}$ are self-adjoint.

It means that $\alpha$ can be decomposed to a sum of projection maps $\beta_i$ onto the each eigenspace $E_i$ and each projection is scaled by the corresponding eigenvalue $\lambda_i$.

> *Corollary.*{: .cor}
> Let $\alpha \in \text{End}(V)$ be normal. Then there exists an orthonormal basis of consisting of eigenvectors of $\alpha$.

> *Corollary.*{: .cor}
> Let $\alpha \in \text{End}(V)$ be self-adjoint. Then $V$ is the orthogonal direct sum of the $\alpha$-eigenspaces (and all eigenvalues are real).

Being able to derive orthonormal basis from eigenvectors whenever $\alpha$ is normal has many useful implications.

> *Corollary.*{: .cor}
> Let $A \in \text{Mat}_n(\mathbf{R})$ (resp. $\text{Mat}_n(\mathbf{C})$) be a symmetric bilinear matrix (resp. Hermitian).
> Then there is orthogonal (resp. unitary) matrix $P$ such that $P^\intercal A P$ (resp. $P^\dagger A P$) is diagonal with real entries.
>
> *Proof.*{: .prf}
>
> $\mathbf{F}^n$ has standard inner product so $A \in \text{End}(\mathbf{F}^n)$ is self-adjoint since $A$ is symmetric/Hermitian.
> Thus, there is an orthonormal basis $(e_1, ..., e_n)$ consisting of eigenvectors of $A$ and let $P$ be the matrix whose columns are given by $e_1, ..., e_n$.
> Then $P$ is orthogonal (resp. unitary), i.e. $P^{-1} = P^\intercal$ (resp. $P^{-1} = P^\dagger$),
> and $D = P^{-1} A P = P^\intercal A P$ (resp. $D = P^{-1} A P = P^\dagger A P$) is diagonal with real entries (the eigenvalues).

> *Corollary.*{: .cor}
> Suppose that $V$ is a finite dimensional real (resp. complex) inner product space and $\psi: V \times V \to \mathbf{F}$ a symmetric bilinear (resp. Hermitian) form.
> Then there is an orthonormal basis of $V$ such that $\psi$ is represented by a diagonal matrix.
>
> *Proof.*{: .prf}
>
> This is similar to the previous corollary but for symmetric bilinear (resp. Hermitian) form.
> Let $(e_1, ..., e_n)$ be any basis for $V$ and $A$ be the matrix representing $\psi$ with respect to this basis.
> Then there exists $P$ such that $D = P^\intercal A P$ (resp. $D = P^\dagger A P$) where $D$ is diagonal representing $\psi$ with respect to the basis $(f_i = \sum_k P_{ki} e_k)$.

Since the diagonal entries of $P^\intercal A P$ are the eigenvalues of $A$, we can find the signature of $A$ by counting the number of positive and negative eigenvalues of $A$.

> *Corollary.*{: .cor}
> Let $V$ be a finite dimensional real (resp. complex) vector space and let $\phi$ and $\psi$ be symmetric bilinear (resp. Hermitian) forms on $V$.
> If $\phi$ is positive definite then there is a basis $(e_1, ..., e_n)$ for $V$ with respect to which both forms are represented by a diagonal matrix.
>
> *Proof.*{: .prf}
>
> Use $\phi$ to make $V$ an inner product space and there is an orthonormal basis with respect to which $\psi$ is represented by a diagonal matrix.
> Then $\phi$ is represented by $I_n$ with respect to this basis.

Therefore, for $A, B \in \text{Mat}_n(\mathbf{R})$ be symmetric matrices such that $A$ is positive definite. Then there is invertible matrix $P$ such that $P^\intercal A P$ and $P^\intercal B P$ are both diagonal.

## Polar Decomposition

Each complex number can be expressed in polar form, i.e. $z = r(\cos \theta + i \sin \theta)$, where $r$ is positive real number and $\cos \theta + i \sin \theta$ is unitary.
The following demonstrates the use of the Spectral Theorem to prove the analogy of that to endomorphisms, i.e. $\alpha = \beta \gamma$ where $\beta$ is _unitary_ and $\gamma$ is _positive_.

> *Definition.*{: .def}
> $\alpha \in \text{End}(V)$ is _positive_ if $\alpha$ is self-adjoint and $\langle \alpha(v), v \rangle$ is real and positive for all vectors $v \not= 0$.

> *Lemma.*{: .lem}
> A self-adjoint endomorphism $\alpha \in \text{End}(V)$ is positive iff all the eigenvalues are positive.
>
> *Proof.*{: .prf}
>
> Note that $\alpha$ is self-adjoint so all the eigenvalues are real.
>
> ($\Rightarrow$) Since $\langle \alpha(v), v \rangle = \lambda \langle v, v \rangle$ so if $\langle \alpha(v), v \rangle > 0$
>
> $$
  \lambda = {\langle \alpha(v), v \rangle \over \langle v, v \rangle} > 0
  $$
>
> ($\Leftarrow$) Consider the spertral decomposition of $\alpha = \sum \lambda_i \beta_i$, all $\lambda_i$ are real and positive.
> Also, any $v \in V$ can be expressed in the form $v = \sum \beta_i v_i$ for some $v_i \in V$ since $V$ is the direct sum of the eigenspaces.
> Then
>
> $$
  \langle \alpha(v), v \rangle = \langle \sum_i \lambda_i \beta_i^2(v_i), \sum_j \beta_j v_j \rangle = \sum_{i,j} \lambda_i \langle \beta_i(v_i), \beta_j(v_j) \rangle = \sum_i \lambda_i \langle \beta_i(v_i), \beta_i(v_i) \rangle > 0
  $$
>
> except for $v = 0$, so $\alpha$ is positive.

> *Theorem.*{: .thm}
> **[Polar Decomposition]**
> Suppose that $V$ is an inner product space and $\alpha \in \text{End}(V)$ is invertible.
> Then $\alpha$ can be expressed in the form $\alpha = \beta \gamma$, where $\beta$ is unitary and $\gamma$ is positive.
>
> *Proof.*{: .prf}
>
> Since $\alpha$ is invertible, $\ker \alpha = 0$ so $\langle \alpha(v), \alpha(v) \rangle$ is real and positive for all $v \not= 0$.
> Then $\langle \alpha^\ast \alpha v, v \rangle = \langle \alpha(v), \alpha(v) \rangle$ is also real and positive for $v \not= 0$.
> Also, $(\alpha^\ast \alpha)^\ast = \alpha^\ast \alpha$ so $\alpha^\ast \alpha$ is self-adjoint.
> Therefore, $\alpha^\ast \alpha$ is positive and it can be decomposed to
>
> $$
  \alpha^\ast \alpha = \sum_i \lambda_i \beta_i
  $$
>
> where $\Set{\lambda_i}$ are positive and real. Let
>
> $$
  \gamma = \sum_i \sqrt{\lambda_i} \beta_i
  $$
>
> since $\beta_i^2 = \beta_i$ and $\beta_i \beta_j = 0$ for $i \not= j$, we have $\gamma^2 = \alpha$.
> Morever, $\gamma$ is self-adjoint, invertible and positive since $\Set{\sqrt{\lambda_i}}$ are positive and $\beta_i$ are self-adjoint, in which $\gamma^{-1}$ is also self-adjoint.
> Let $\beta = \alpha \gamma^{-1}$, then
>
> $$
  \beta^\ast \beta = (\gamma^{-1})^\ast \alpha^\ast \alpha \gamma^{-1} = \gamma^{-1} \gamma^2 \gamma^{-1} = \iota
  $$
>
> so $\beta$ is unitary and $\alpha = \beta \gamma$ is the required decomposition.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 8.3, 8.4
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 32
