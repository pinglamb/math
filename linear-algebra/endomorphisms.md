---
layout: base
title: Endomorphisms &#124; Linear Algebra
---

# Endomorphisms
{: .page-title}

> *Definition.*{: .def}
> An **endomorphism** of $V$ is a linear map $\alpha: V \to V$.
> The vector space of endomorphisms of $V$ is denoted by $\text{End}(V)$ and the identity endomorphism is denoted by $\iota$.

The key difference while considering endomorphisms as matrices is that the same basis will be used for both the domain and the range which leads to some other properties.

## Basis

The standard basis of $M_n(\mathbf{F})$ can be useful sometimes for proving properties of the corresponding endomorphism.

> *Definition.*{: .def}
> The standard basis for $M_n(\mathbf{F})$ consists of $n^2$ matrices $\Set{E\_{ij}}$ in which
>
> $$
  (E_{ij})_{kl} = \begin{cases}
  1 & i = k, j = l \\
  0 & \text{otherwise}
  \end{cases}
  $$

> *Proposition.*{: .prop}
> $E\_{ij} E\_{kl} = \delta_{jk} E_{il}$.
>
> *Proof.*{: .prf}
>
> $$
  (E_{ij} E_{kl})_{pq} = \sum_{r = 1}^n (E_{ij})_{pr} (E_{kl})_{rq}
  $$
>
> $(E\_{ij})\_{pr} = 1$ if $p = i$ and $r = j$ and $(E\_{kl})\_{rq} = 1$ if $q = l$ and $r = k$ so only $(E\_{ij} E\_{kl})_{il}$ can be non-zero provided that $j = k$.

> *Definition.*{: .def}
> The **commutator** of two elements $a$ and $b$ of a ring is the element $[a, b] = ab - ba$.
> The elements $a$ and $b$ are said to **commute** if the commutator is zero, i.e. $ab = ba$.

> *Proposition.*{: .prop}
> Every off-diagonal basis matrices are commutators, specifically $E\_{ij} = E\_{ik}E\_{kj} - E\_{kj}E\_{ik}$ for $i \not= j$.
>
> *Proof.*{: .prf}
>
> $E\_{ik}E\_{kj} = E_{ij}$ and $E\_{kj}E\_{ik} = 0$ when $i \not= j$.

Since $\text{End}(V) \cong M_n(\mathbf{F})$ for a given basis $\Set{v_1, ..., v_n}$ for $V$, the $n^2$ linear maps $\Set{\alpha_{ij}}$ in which
their matrix representations with respect to $\Set{v_i}$ are $\Set{E_{ij}}$ form a basis for $\text{End}(V)$.
In particular, $\alpha_{ij} \in \text{End}(V)$ defined by

$$
\alpha_{ij}(v_j) = v_i \quad \alpha_{ij}(v_k) = 0, k \not= j
$$

form a basis for $\text{End}(V)$.

## Invariants

We will first address properties of matrices that are invariant up to similarity.

> *Proposition.*{: .prop}
> Suppose that $(e_1, ..., e_n)$ and $(f_1, ..., f_n)$ are bases for $V$ such that $f_i = \sum P_{ki} e_k$.
> Let $\alpha \in \text{End}(V)$, $A$ be the matrix representing $\alpha$ with respect to $(e_i)$ and $B$ the matrix representing $\alpha$ with respect to $(f_i)$.
> Then $B = P^{-1}AP$.
>
> *Proof.*{: .prf}
>
> $P$ is the identity map from basis $(f_i)$ to $(e_i)$.
> The relation is just a special case of the change of basis formula with $Q = P$.

> *Definition.*{: .def}
> Matrices $A$ and $B$ are **similar** (or **conjugate**) if $B = P^{-1}AP$ for some invertible matrix $P$.

In terms of group theory, recall $\text{GL}_n(\mathbf{F})$ denotes all the invertible matrices
so $\text{GL}_n(\mathbf{F})$ acts on $M_n(\mathbf{F})$ by conjugation and two matrices are similar if they lie in the same orbit, and similarity is an equivalence relation.

> *Definition.*{: .def}
> The **trace** of a matrix $A$ is defined by $\text{tr}: M\_n(\mathbf{F}) \to \mathbf{F}$ such that $\text{tr}\,A = \sum A_{ii}$.

> *Proposition.*{: .prop}
> Suppose that $A \in M\_{n,m}(\mathbf{F})$ and $B \in M\_{m,n}(\mathbf{F})$.
> Then $\text{tr}\,AB = \text{tr}\,BA$.
>
> *Proof.*{: .prf}
>
> $$
  \text{tr}\,AB = \sum_{i=1}^n \left( \sum_{j=1}^m A_{ij} B_{ji} \right)  = \sum_{j=1}^m \left( \sum_{i=1}^n B_{ji} A_{ij} \right) = \text{tr}\,BA
  $$

> *Proposition.*{: .prop}
> Suppose that $f \in M_n(\mathbf{F})^\ast$ such that $f(AB) = f(BA)$ for all $A, B \in M_n(\mathbf{F})$.
> Then $f$ is a scalar multiple of the trace function.
>
> *Proof.*{: .prf}
>
> Since every off-diagonal basis matrices are commutators, for $i \not= j$, $f(E\_{ij}) = f(E\_{ik}E\_{kj} - E\_{kj}E\_{ik}) = 0$.
> For on-diagonal basis matrices, $f(E_{ii}) = f(E\_{ik}E\_{ki} - E\_{ki}E\_{ik}) = 0$ so $f(E_{ii}) = f(E_{kk})$ and all of them have the same scalar value $\lambda$.
> Hence, for any matrix $A$, $f(A) = \sum A_{ii} f(E_{ii}) = \lambda \text{tr}(A)$.

> *Proposition.*{: .prop}
> If matrices $A$ and $B$ are similar. Then
>
> + $\text{tr}\,A = \text{tr}\,B$;
>
> + $\det A = \det B$.
>
> *Proof.*{: .prf}
>
> + $\text{tr}\,B = \text{tr}\,P^{-1}AP = \text{tr}\,AP^{-1}P = \text{tr}\,A$.
>
> + $\det B = \det P^{-1}AP = \det A \det P^{-1} \det P = \det A$.

Since the trace and determinant are independent of the choice of basis, we can define:

> *Definition.*{: .def}
> The **trace** and **determinant** of an endomorphism $\alpha$, i.e. $\text{tr}\,\alpha$ and $\det \alpha$, are defined to be the trace and determinant of any matrix representing $\alpha$ respectively.

> *Proposition.*{: .prop}
> Let $\alpha^\ast \in \text{End}(V^\ast)$ be the dual of $\alpha \in \text{End}(V)$.
> Then $\det \alpha^\ast = \det \alpha$ and $\text{tr}\,\alpha^\ast = \text{tr}\,\alpha$.
>
> *Proof.*{: .prf}
>
> Since $\det A^\intercal = \det A$ and $\text{tr}\,A^\intercal = \text{tr}\,A$.

## Minimal Polynomials

Since $\dim \text{End}(V) = n^2$, for a fixed linear map $\alpha \in \text{End}(V)$, the $n^2 + 1$ powers of $\alpha$, i.e. $\Set{1, \alpha, \alpha^2, ..., \alpha^{n^2}}$ are linearly dependent.
That means there exists a nonzero polynomial

$$
f(x) = \lambda_0 + \lambda_1 x + ... + \lambda_{n^2} x^{n^2} \in \mathbf{F}[x]
$$

such that $f(\alpha) = 0$.

> *Proposition.*{: .prop}
> There exists a uniquely determined integer $r \le n^2$ such that $\Set{1, \alpha, ..., \alpha^{r-1}}$ are linearly independent but not $\Set{1, \alpha, ..., \alpha^{r}}$.
> Then
>
> $$
  \alpha^r = \lambda_0 \cdot 1 + \lambda_1 \alpha + ... + \lambda_{r-1} \alpha^{r-1}
  $$
>
> Let $m(x) = x^r - \lambda\_{r-1} x^{r-1} - ... - \lambda_0 \cdot 1 \in \mathbf{F}[x]$. Then
>
> + $m(x)$ is nonzero and $m(\alpha) = 0$;
>
> + If $f(x)$ is any polynomial such that $f(\alpha) = 0$, then $m(x) \mid f(x)$.
>
> *Proof.*{: .prf}
>
> Base on the above we can see that $m(x)$ exists.
>
> Let $f(x)$ be any polynomial such that $f(\alpha) = 0$. By division theorem, $f(x) = m(x) Q(x) + R(x)$ with $\deg R < r$ and $R(\alpha) = f(\alpha) - m(\alpha) Q(\alpha) = 0$.
> Since $\Set{1, \alpha, ..., \alpha^{r-1}}$ are linearly independent, there doesn't exist a nonzero polynomial $R(x)$ with $\deg R < r$ such that $R(\alpha) = 0$. Hence, $R = 0$ and $m(x) \mid f(x)$.

> *Definition.*{: .def}
> The **minimal polynomial** of linear map $\alpha \in \mathcal{L}(V, V)$ is the nonzero monic polynomial of least degree such that $m(\alpha) = 0$ and it is well-defined.

The uniqueness of minimal polynomial is the result from the fact that if both $m(x)$ and $m'(x)$ are minimal polynomials then $m \mid m'$ and $m' \mid m$ and hence $m = m'$.

## Eigenvalues and Eigenvectors

It can be hard to determine the minimal polynomials of a given linear map. Instead of studying polynomials such that $f(\alpha)$ sends the whole vector space $V$ to zero,
it is equally useful to study polynomials which send individual vectors to zero, which leads to the discussion of eigenvalues and eigenvectors.

> *Definition.*{: .def}
> Let $\alpha \in \text{End}(V)$. An element $\lambda \in \mathbf{F}$ is called a **characteristic root** (or **eigenvalue**) of $\alpha$ if there exists a vector $v \not= 0$ in $V$ such that $\alpha(v) = \lambda v$.
> That nonzero vector $v$ is called a **characteristic vector** (or **eigenvector**) belonging to $\lambda$.

We can define the same for matrices, i.e. $Av = \lambda v$ and the correspondence between linear maps and matrices show that $\lambda$ is a eigenvalue of $\alpha$ iff $\lambda$ is a eigenvalue of the matrix of $\alpha$ with respect to any basis.

> *Proposition.*{: .prop}
> Let $v_1, ..., v_r$ be eigenvectors belonging to distinct eigenvalues $\lambda_1, ..., \lambda_r$ of $\alpha \in \text{End}(V)$. Then $\Set{v_1, ..., v_r}$ are linearly independent.
>
> *Proof.*{: .prf}
>
> It is obviously true for $r = 1$. Assume it is true for any set fewer than $r$ vectors. Suppose that
>
> $$
  \mu_1 v_1 + \mu_2 v_2 + ... + \mu_r v_r = 0
  $$
>
> If any of the $\Set{\mu_i}$ are zero, all of them must be zero due to the induction hypothesis and $\Set{v_i}$ are linearly independent.
> Suppose all $\mu_i \not= 0$, we have
>
> $$
  \alpha(\mu_1 v_1 + \mu_2 v_2 + ... + \mu_r v_r) = \mu_1 \lambda_1 v_1 + \mu_2 \lambda_2 v_2 + ... + \mu_r \lambda_r v_r = 0
  $$
>
> and
>
> $$
  \lambda_1(\mu_1 v_1 + \mu_2 v_2 + ... + \mu_r v_r) = \mu_1 \lambda_1 v_1 + \mu_2 \lambda_1 v_2 + ... + \mu_r \lambda_1 v_r = 0
  $$
>
> so by subtracting one from the other, we have
>
> $$
  \mu_2 (\lambda_2 - \lambda_1) v_2 + \mu_3 (\lambda_3 - \lambda_1) v_3 + ... + \mu_r (\lambda_r - \lambda_1) v_r = 0
  $$
>
> Since the $\Set{\lambda_i}$ are distinct, by induction hypothesis, the above is only possible if $\mu_2 = ... = \mu_r = 0$ which implies $\mu_1 = 0$ and $\Set{v_i}$ are linaerly independent.

## References

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 6
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 7
