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

> *Definition.*{: .def}
> Suppose $\mathbf{f}(x)$ is a vector function from $\mathbb{R}$ to $\mathbb{R}^n$.
> The **derivative** of $\mathbf{f}(x)$ at $a$ is defined as
>
> $$
  \mathbf{f'}(a) = \lim_{x \to a} {\mathbf{f}(x) - \mathbf{f}(a) \over x - a}
  $$

> *Proposition.*{: .prop}
> Let $\mathbf{f} = f_i \mathbf{e}_i$. Then $\mathbf{f'}(a) = (f_1'(a), f_2'(a), ..., f_n'(a))$.
>
> *Proof.*{: .prf}
>
> $$
  \mathbf{f'}(a) = \lim_{x \to a} {f_i(x) \mathbf{e}_i - f_i(a) \mathbf{e}_i \over x - a}
  = {df_i \over dx}(a) \mathbf{e}_i = (f_1'(a), f_2'(a), ..., f_n'(a))
  $$

## References

* Stephen J. Cowley _Vector Calculus Lectures Notes_, 2000 - Chapter 1

