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
> The **differential** of a vector function $f: \mathbf{R} \to \mathbf{R}^n$, denoted by $d\mathbf{f}$, is defined as
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

## Partial and Directional Derivatives

Before discussing differentiability of functions of several variables, we need to introduce more tools.

> *Definition.*{: .def}
> For $\mathbf{f}: \mathbb{R}^m \to \mathbb{R}^n$, the $j$th **partial derivative** of $\mathbf{f}$ at $\mathbf{a}$ is
>
> $$
  {\partial \mathbf{f} \over \partial x_j} = \partial_j \mathbf{f}(\mathbf{a})
  = \lim_{h_j \to 0} {\mathbf{f}(a_1, ..., a_j + h_j, ..., a_m) - \mathbf{f}(a_1, ..., a_j, ..., a_m) \over h_j}
  $$
>
> whenever the limit exists.

The idea can be generalized to directions other than parallel to the basis vectors.

> *Definition.*{: .def}
> For $\mathbf{f}: \mathbb{R}^m \to \mathbb{R}^n$, the **directional derivative** of $\mathbf{f}$ at $\mathbf{a}$ in the direction $\mathbf{u}$, where $\mathbf{u}$ is a unit vector, is
>
> $$
  D_{\mathbf{u}}(\mathbf{a}) = \lim_{h \to 0} {\mathbf{f}(\mathbf{a} + h\mathbf{u}) - \mathbf{f}(\mathbf{a}) \over h}
  $$
>
> whenever the limit exists

> *Proposition.*{: .prop}
> The existence of partial/directional derivatives does not imply differentiability and continuity.

## Scalar Functions of Two Variables

> *Definition.*{: .def}
> A function $f(x, y): \mathbf{R}^2 \to \mathbf{R}$ is **differentiable** at $(a, b)$ if
>
> $$
  f(a + h, b + k) = f(a, b) + T_xh + T_yk + o(|h| + |k|)
  $$
>
> where $T_x$ and $T_y$ are independent of $h$ or $k$.

Alternatively, we can put the "error term" in different forms such as $o(\sqrt{h^2 + k^2})$.

> *Proposition.*{: .prop}
> $T_x = \partial_x f$ and $T_y = \partial_y f$.
>
> *Proof.*{: .prf}
>
> Let $h \to 0$ with $k = 0$ and from the definition of partial derivative, we have
>
> $$
  T_x = \lim_{h \to 0} {f(a + h, b) - f(a, b) \over h} = \partial_x f
  $$

> *Proposition.*{: .prop}
> Let $z = f(x, y)$ which defines a surface. Then
>
> $$
  z = f(a, b) + [\partial_x f(a, b)](x - a) + [\partial_y f(a, b)](y - b)
  $$
>
> is a tangent plane touching the surface at the point $(a, b, f(a, b))$.

> *Proposition.*{: .prop}
> The **total differential** of a function $f: \mathbf{R}^2 \to \mathbf{R}$ is given by
>
> $$
  d\mathbf{f} = {\partial f \over \partial x} dx + {\partial f \over \partial y} dy
  $$
>
> *Proof.*{: .prf}
>
> Consider the rate of change of $f$ in an arbitrary direction, we can express the change of $f$ as
>
> $$
  \begin{align*}
  \Delta f &= f(x + \Delta x, y + \Delta y) - f(x, y) \\
  &= f(x + \Delta x, y + \Delta y) - f(x, y + \Delta y) + f(x, y + \Delta y) - f(x, y) \\
  &= \left[ {f(x + \Delta x, y + \Delta y) - f(x, y + \Delta y) \over \Delta x} \right] \Delta x + \left[ {f(x, y + \Delta y) - f(x, y) \over \Delta y} \right] \Delta y \\
  &\approx {\partial f \over \partial x} \Delta x + {\partial f \over \partial y} \Delta y
  \end{align*}
  $$
>
> with the first term replaced from $\partial f(x, y + \Delta y) / \partial x$ to $\partial f(x, y) / \partial x$.

> *Proposition.*{: .prop}
> The directional derivative in the direction $\mathbf{u} = (u_x, u_y)$ is given by
>
> $$
  D_\mathbf{u} f(a, b) = [\partial_x f(a, b)] u_x + [\partial_y f(a, b)] u_y
  $$
>
> *Proof.*{: .prf}
>
> By definition, the directional derivative of $f$ at $\mathbf{x} = (a, b)$ in the direction $\mathbf{u}$ is
>
> $$
  D_\mathbf{u}(\mathbf{x}) = \lim_{t \to 0} {f(\mathbf{x} + t\mathbf{u}) - f(\mathbf{x}) \over t} = \lim_{t \to 0} {f(a + tu_x, b + tu_y) - f(a, b) \over t}
  $$
>
> As $f$ is differentiable at $(a, b)$ and let $h = tu_x$ and $k = tu_y$, we have
>
> $$
  f(a + tu_x, b + tu_y) = f(a, b) + T_x tu_x + T_y tu_y + o(\sqrt{(tu_x)^2 + (tu_y)^2})
  $$
>
> Since $\mathbf{u}$ is a unit vector, $o(\sqrt{(tu_x)^2 + (tu_y)^2}) = o(\vert t \vert \sqrt{(u_x)^2 + (u_y)^2}) = o(\vert t \vert)$ and so
>
> $$
  f(a + tu_x, b + tu_y) = f(a, b) + (T_x u_x + T_y u_y)t + o(|t|)
  $$
>
> and hence
>
> $$
  D_\mathbf{u}(a, b) = T_x u_x + T_y u_y = [\partial_x f(a, b)]u_x + [\partial_y f(a, b)]u_y
  $$

## Vector Functions of Several Variables

> *Definition.*{: .def}
> A function $\mathbf{f}: \mathbf{R}^m \to \mathbf{R}^n$ is **differentiable** at $\mathbf{a} \in \mathbf{R}^m$ if for all $\mathbf{h} \in \mathbf{R}^m$
>
> $$
  \mathbf{f}(\mathbf{a} + \mathbf{h}) = \mathbf{f}(\mathbf{a}) + \mathsf{T}\mathbf{h} + o(\mathbf{h})
  $$
>
> where $\mathsf{T}$ is a $n \times m$ matrix that is independent of $\mathbf{h}$.

> *Proposition.*{: .prop}
> $T_{ij} = \partial_j f_i$.
>
> *Proof.*{: .prf}
>
> Similarily, by considering the special case $\mathbf{h} = (0, 0, ..., h_j, 0, ..., 0)$,
>
> $$
  T_{ij} = \lim_{h_j \to 0} {f_i(a_1, ..., a_j + h_j, ..., a_m) - f_i(a_1, ..., a_j, ..., a_m) \over h_j} = \partial_j f_i
  $$

> *Definition.*{: .def}
> The $n \times m$ **Jacobian matrix** $\mathsf{T}$ is defined by
>
> $$
  \mathsf{T} = \begin{pmatrix}
  \dfrac{\partial f_1}{\partial x_1} & \dfrac{\partial f_1}{\partial x_2} & \cdots & \dfrac{\partial f_1}{\partial x_m} \\
  \dfrac{\partial f_2}{\partial x_1} & \dfrac{\partial f_2}{\partial x_2} & \cdots & \dfrac{\partial f_2}{\partial x_m} \\
  \vdots & \vdots & \ddots & \vdots \\
  \dfrac{\partial f_n}{\partial x_1} & \dfrac{\partial f_n}{\partial x_2} & \cdots & \dfrac{\partial f_n}{\partial x_m} \\
  \end{pmatrix}
  $$

## Chain Rule

> *Proposition.*{: .prop}
> For functions $\mathbf{x}(u): \mathbb{R} \to \mathbb{R}^m$ and $f: \mathbf{R}^m \to \mathbf{R}$,
>
> $$
  {d \over du} f(\mathbf{x}(u)) = {\partial f \over \partial x_j} {d x_j \over du}
  $$
>
> *Proof.*{: .prf}
>
> When $m = 2$ and let $\mathbf{x} = (x, y)$, we have
>
> $$
  \begin{align*}
  {d \over du} f(x, y) &= \lim_{\Delta u \to 0} {f(x + \Delta x, y + \Delta y) - f(x, y) \over \Delta u} \\
  &= \lim_{\Delta u \to 0} {f(x + \Delta x, y + \Delta y) - f(x, y + \Delta y) \over \Delta x} {\Delta x \over \Delta u} + {f(x, y + \Delta y) - f(x, y) \over \Delta y} {\Delta y \over \Delta u} \\
  &= {\partial f \over \partial x} {dx \over du} + {\partial f \over \partial y} {dy \over du}
  \end{align*}
  $$
>
> where we have written $x(t + \Delta t) = x(t) + \Delta x(t)$.

> *Proposition.*{: .prop}
> For functions $\mathbf{x}(\mathbf{u}): \mathbb{R}^\ell \to \mathbb{R}^m$ and $f: \mathbf{R}^m \to \mathbf{R}$, where $\mathbf{u} = (u_1, ..., u_\ell)$,
>
> $$
  {\partial \over \partial u_k} f(\mathbf{x}(\mathbf{u})) = {\partial f \over \partial x_j} {\partial x_j \over \partial u_k}
  $$

> *Proposition.*{: .prop}
> For functions $\mathbf{x}(\mathbf{u}): \mathbb{R}^\ell \to \mathbb{R}^m$ and $\mathbf{f}: \mathbf{R}^m \to \mathbf{R}^n$, where $\mathbf{u} = (u_1, ..., u_\ell)$,
>
> $$
  \left({\partial \mathbf{f} \over \partial u_k}\right)_i = {\partial \over \partial u_k} f_i(\mathbf{x}(\mathbf{u})) = {\partial f_i \over \partial x_j} {\partial x_j \over \partial u_k}
  $$

## References

* Stephen J. Cowley _Vector Calculus Lectures Notes_, 2000 - Chapter 1

