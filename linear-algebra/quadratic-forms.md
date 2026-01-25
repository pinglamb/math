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

> *Definition.*{: .def}
> A **quadratic form** on $V$ is the map $q: V \to \mathbf{F}, q(v) = \phi(v, v)$ where $\phi: V \times V \to \mathbf{F}$ is a bilinear form.

For example, if $V = \mathbf{R^2}$ and $\phi$ is represented by $A$ with respect to the standard basis then

$$
q(v) = \begin{pmatrix} x & y \end{pmatrix} A \begin{pmatrix} x \\ y \end{pmatrix} = A_{11} x^2 + (A_{12} + A_{21}) xy + A_{22} y^2
$$

Note that quadratic form is not linear.

> *Proposition.*{: .prop}
> **[Polarization Identity]**
> If $q: V \to \mathbf{F}$ is a quadratic form then there exists a unique symmetric bilinear form $\phi: V \times V \to \mathbf{F}$ such that $q(v) = \phi(v, v)$ for all $v \in V$.
>
> *Proof.*{: .prf}
>
> Let $\psi: V \times V \to \mathbf{F}$ be the bilinear form such that $\phi(v, v) = q(v)$. Then
>
> $$
  \phi(v, w) = {1 \over 2} (\psi(v, w) + \psi(w, v))
  $$
>
> is a symmetric bilinear form such that $\phi(v, v) = q(v)$.
>
> Suppose that $\phi$ is symmetric bilinear form such that $\phi(v, v) = q(v)$, then
>
> $$
  q(v + w) = \phi(v + w, v + w) = \phi(v, v + w) + \phi(w, v + w) = \phi(v, v) + 2 \phi(v, w) + \phi(w, w)
  $$
>
> and hence
>
> $$
  \phi(v, w) = {1 \over 2} (q(v + w) - q(v) - q(w))
  $$
>
> is unique.

To conclude, there is a one-to-one mapping between symmetric bilinear form and quadratic form in which the above formula can be used to determine the matrix of the corresponding bilinear form given a quadratic form.

## Matrix Representation

> *Proposition.*{: .prop}
> **[Diagonalization of symmetric bilinear forms]**
> If $\phi: V \times V \to \mathbf{F}$ is a symmetric bilinear form of a finite dimensional vector space $V$
> then there is a basis $(e_1, ..., e_n)$ for $V$ such that $\phi$ is represented by a diagonal matrix.
>
> *Proof.*{: .prf}
>
> By induction on $n = \dim V$. When $n = 0, 1$, every matrix is diagonal matrix. Assume it is true for all spaces of dimension strictly smaller than $n$.
> If $\phi(v, v) = 0$ for all $v \in V$ then by polarization identity $\phi(v, w) = 0$ so $\phi$ is represented by the zero matrix when is diagonal.
> Otherwise, we can choose $e_1$ such that $\phi(e_1, e_1) \not= 0$. Consider the subspace
>
> $$
  U = \Set{ u \in V : \phi(e_1, u) = 0 } = \ker \phi(e_1, -): V \to \mathbf{F}
  $$
>
> Since the codomain $\mathbf{F}$ is one-dimensional, by rank-nullity theorem, $\dim U = n - 1$. Also, $e_1 \not= U$ so $V = \langle e_1 \rangle \oplus U$.
>
> The bilinear map $\phi_{U \times U} : U \times U \to \mathbf{F}$ is also symmetric so by the induction hypothesis, there exists basis $\Set{e_2, ..., e_n}$ such that the matrix representing $\phi_{U \times U}$ is diagonal.
> Hence, the basis $\Set{e_1, ..., e_n}$ satisfies $\phi(e_i, e_j) = 0$ for $i \not= j$ as required.

> *Corollary.*{: .cor}
> Let $\phi$ be a symmetric bilinear form on a finite dimensional $\mathbf{C}$-vector space $V$.
> Then there is basis $(v_1, ..., v_n)$ for $V$ such that $\phi$ is represented by a matrix of the form
>
> $$
  \begin{pmatrix}
  I_r & 0 \\
  0 & 0 \\
  \end{pmatrix}
  $$
>
> with $r = r(\phi)$ or equivalently such that the corresponding quadratic form $q$ is given by
>
> $$
  q(v) = q(\sum_{i=1}^n a_i v_i) = \sum_{i=1}^r a_i^2
  $$
>
> *Proof.*{: .prf}
>
> From the above, there is basis $(e_1, ..., e_n)$ such that $\phi(e_i, e_j) = \delta_{ij} \lambda_i$ for $1 \le i \le n$.
> By reordering the $e_i$'s we can assume $\lambda_i \not= 0$ for $1 \le i \le r$ and $\lambda_i = 0$ for $r+1 \le i \le n$.
> Since we are working with $\mathbf{C}$, each $\lambda_i \not= 0 $ has a non-zero square root $\mu_i$ and by having $v_i = e_i / \mu_i$ for $1 \le i \le r$
> and $v_i = e_i$ for $r+1 \le i \le n$ we have $\phi(v_i, v_j) = 0$ for $i \not= j$ or $i = j > r$ and $\phi(v_i, v_i) = 1$ for $1 \le i \le r$ as required.

> *Corollary.*{: .cor}
> Every symmetric matrix $S \in \text{Mat}_n(\mathbf{C}$ is congruent to a unique matrix of the form
>
> $$
  \begin{pmatrix}
  I_r & 0 \\
  0 & 0 \\
  \end{pmatrix}
  $$

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 7
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Section 31
