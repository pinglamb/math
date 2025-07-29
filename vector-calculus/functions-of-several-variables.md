---
layout: base
title: Functions of Several Variables &#124; Vector Calculus
---

# Functions of Several Variables
{: .page-title}

We have in depth analysis of [differentiability](../analysis/differentiability.md) of scalar functions of a scalar, i.e. $f(x): \mathbb{R} \to \mathbb{R}$.
However, we may equally well consider scalar or vector functions of multiple variables, i.e.
$f(\mathbf{x}): \mathbb{R}^m \to \mathbb{R}$, $\mathbf{f}(x): \mathbb{R} \to \mathbb{R}^n$ and $\mathbf{f}(\mathbf{x}): \mathbb{R}^m \to \mathbb{R}^n$.

> *Definition.*{: .def}
> A function $\mathbf{f}: \mathbb{R}^m \to \mathbb{R}^n$ has **limit** $\boldsymbol{\ell}$ as $\mathbf{x} \to \mathbf{a}$ if
>
> $$
  \lim_{\mathbf{x} \to \mathbf{a}} \mathbf{f}(\mathbf{x}) = \boldsymbol{\ell}
  $$
>
> _independently_ of the way that $\mathbf{x}$ approaches $\mathbf{a}$.

Different from the ordinary limit that we only need to have the left and right limits being equal,
there are infinitely many routes for $\mathbf{x}$ to approach $\mathbf{a}$ and the limit exists only if they all agree.

> *Definition.*{: .def}
> A function $\mathbf{f}: \mathbb{R}^m \to \mathbb{R}^n$ is **continuous** at $\mathbf{a}$ iff
>
> $$
  \lim_{\mathbf{x} \to \mathbf{a}} \mathbf{f}(\mathbf{x}) = \mathbf{f}(\mathbf{a})
  $$

Similarily, all routes have to agree so for $\mathbf{f}$ to be continuous.

## Vector Functions of One Variable

> *Definition.*{: .def}
> Suppose $\mathbf{f}(x)$ is a vector function from $\mathbb{R}$ to $\mathbb{R}^n$.
> The **derivative**/**tangent vector** of $\mathbf{f}(x)$ at $a$ is defined as
>
> $$
  \mathbf{f'}(a) = \lim_{x \to a} {\mathbf{f}(x) - \mathbf{f}(a) \over x - a}
  $$

Alternatively, we can generalize the concept of linear approximation in [differentiability of scalar function](../analysis/differentiability.md#differentiability-linear-approximation).

> *Definition.*{: .def}
> A vector function $\mathbf{f}(x)$ is **differentiable** at $a$ iff we can write
>
> $$
  \mathbf{f}(x + h) = \mathbf{f}(x) + \mathbf{f'}(x)h + o(h)
  $$

> *Proposition.*{: .prop}
> Let $\mathbf{f} = f_i \mathbf{e}_i$, with $\Set{\mathbf{e}_i}$ being the basis vectors independent of $x$. Then
>
> $$
  \mathbf{f'}(a) = (f_1'(a), f_2'(a), ..., f_n'(a))
  $$
>
> *Proof.*{: .prf}
>
> $$
  \mathbf{f'}(a) = \lim_{x \to a} {f_i(x) \mathbf{e}_i - f_i(a) \mathbf{e}_i \over x - a}
  = {df_i \over dx}(a) \mathbf{e}_i = (f_1'(a), f_2'(a), ..., f_n'(a))
  $$

> *Definition.*{: .def}
> The **differential** of a vector function, denoted by $d\mathbf{f}$, is defined as
>
> $$
  d\mathbf{f} = {d\mathbf{f} \over dx} dx
  $$

> *Definition.*{: .def}
> The integration of a vector function with respect to a scalar can be regarded as the inverse of differentiation,
> i.e. if $\mathbf{f}(x) = d\mathbf{F}/dx$, then
>
> $$
  \int_a^b \mathbf{f}(x) \,dx = \mathbf{F}(b) - \mathbf{F}(a)
  $$
>
> in which the integral is also a vector.

## References

* Stephen J. Cowley _Vector Calculus Lectures Notes_, 2000 - Chapter 1

