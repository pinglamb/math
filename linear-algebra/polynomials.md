---
layout: base
title: Polynomials &#124; Linear Algebra
---

# Polynomials
{: .page-title}

A prerequisite for understanding the deeper theorems about linear maps is a knowledge of factorization of polynomials as products of prime polynomials.
Most of the theorems will be stated without detailed proofs as they are most of the time intuitive.

> *Definition.*{: .def}
> A **polynomial** with coefficients in $\mathbf{F}$ is by definition a sequence
>
> $$
  f = \Set{a_0, a_1, a_2, ... }, \qquad a_i \in \mathbf{F}
  $$
>
> such that for some positive integer $M$ depending on $f$, $a_M = a\_{M+1} = ... = 0$.
> Two polynomials $f = \Set{a_i}$ and $g = \Set{b_i}$ are equal, i.e. $f = g$, iff $a_0 = b_0$, $a_1 = b_1$, etc.
> Addition is the same as for vectors, i.e.
>
> $$
  f + g = \Set{a_0 + b_0, a_1 + b_1, ...}
  $$
>
> and multiplication is defined by the rule
>
> $$
  fg = \Set{c_0, c_1, ...} \quad \text{where} \quad c_k = \sum_{i + j = k} a_i b_j = a_0 b_k + a_1 b_{k-1} + ... + a_k b_0
  $$

Let $\mathbf{F}'$ be the set of all polynomials of the form

$$
a = \Set{a, 0, 0, ...}
$$

and $x^i$ be the polynomial with $1$ at the $i$-th position, i.e.

$$
x^i = \Set{0, ..., 1, ...}
$$

then we have

$$
ax^i = \Set{a, 0, 0, ...}\Set{0, ..., 1, ...} = \Set{0, ..., a, ...}
$$

and therefore an arbitrary polynomial $f$ can be expressed uniquely in the form

$$
f = a_0 + a_1 x + a_2 x^2 + ...
$$

> *Definition.*{: .def}
> The set of polynomials with coefficients in $\mathbf{F}$ is denoted by $\mathbf{F}[x]$.

> *Theorem.*{: .thm}
> $\mathbf{F}[x]$ is a commutative ring.

## Degree

> *Definition.*{: .def}
> The **degree** of $f$ is $r$, i.e. $\deg f = r$, if $a_r \not= 0$ and $a\_{r+1} = a\_{r+2} = ... = 0$.

Note that the polynomial $0$ does not have a degree or $\deg 0 = -\infty$.

> *Proposition.*{: .prop}
> Let $f, g$ be nonzero polynomials in $\mathbf{F}[x]$ then
>
> $$
  \begin{align*}
  \deg f + g &\le \max \Set{\deg f, \deg g} \\
  \deg fg &= \deg f+ \deg g \\
  \end{align*}
  $$

> *Corollary.*{: .cor}
> If $f, g \in \mathbf{F}[x]$, then $fg = 0$ implies that $f = 0$ or $g = 0$. If $fh = gh$ and $h \not= 0$, then $f = g$.
>
> *Proof.*{: .prf}
>
> If $f \not= 0$ and $g \not= 0$, then $\deg fg \ge 0$ and $fg \not= 0$.
>
> If $fh = gh$, then $(f - g)h = 0$. Since $h \not= 0$, $f - g = 0$ so $f = g$.

## Factorization

> *Proposition.*{: .prop}
> Let $f, g \in \mathbf{F}$ such that $g \not= 0$, then there exists unique polynomials $Q, R$ such that
>
> $$
  f = Qg + R
  $$
>
> where either $R = 0$ or $\deg R < \deg g$.

> *Definition.*{: .def}
> For $f \in \mathbf{F}[x]$, the **polynomial function** $f(x)$ assigns each $\xi \in \mathbf{F}$ to the element $f(\xi) \in \mathbf{F}$ by the rule $f(\xi) = \sum a_i \xi^i$.
> An element $\lambda \in \mathbf{F}$ such that $f(\lambda) = 0$ is called a **root** of the polynomial.

The distinction between polynomials $f$ and polynomial functions $f(x)$ arises from the fact that for finite fields, two polynomials may correspond to the same polynomial function.

> *Proposition.*{: .prop}
> If $\lambda \in \mathbf{F}$ is a root of a polynomial $f$, i.e. $f(\lambda) = 0$, then $f(x) = (x - \lambda) g(x)$ for some $g \in \mathbf{F}[x]$.
>
> *Proof.*{: .prf}
>
> By division we have $f(x) = (x - \lambda)g(x) + R(x)$ with $\deg R < 1$, i.e. $R(x) = r_0$ for some $r_0 \in \mathbf{F}$.
> But $f(\lambda) = R(\lambda) = r_0 = 0$ so $f(x) = (x - \lambda)g(x)$.

> *Definition.*{: .def}
> Suppose that $f \in \mathbf{F}[x]$ and $\lambda \in \mathbf{F}$ is a root of $f$.
> Then $\lambda$ is a root of **multiplicity** $k$ if $(x - \lambda)^k$ is a factor of $f(x)$ but not $(x - \lambda)^{k+1}$, i.e.
> if $f(x) = (x - \lambda)^k g(x)$ where $g(\lambda) \not= 0$.

> *Proposition.*{: .prop}
> Every polynomial $f$ can be written as
>
> $$
  f(x) = \prod_{i=1}^r (x - \lambda_i)^{a_i} g(x)
  $$
>
> with $r \ge 0$, $a_i \ge 1$, $\lambda_i \in \mathbf{F}$ and $g \in \mathbf{F}[x]$ with no roots in $\mathbf{F}$.

> *Proposition.*{: .prop}
> A polynomial $f \in \mathbf{F}[x]$ of degree $n \ge 0$ has at most $n$ roots counted with multiplicity.

> *Theorem.*{: .thm}
> **[Fundamental Theorem of Algebra]**
> Every polynomial $f \in \mathbf{C}[x]$ with $\deg f \ge 1$ has a root in $\mathbf{C}$.

It follows that $f \in mathbf{C}[x]$ has precisely $n$ roots in $\mathbf{C}$ counted with multiplicity and every $f \in \mathbf{R}[x]$ can be written as a product of linear and quadratic factors.

## References

* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Section 20
