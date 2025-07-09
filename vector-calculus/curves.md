---
layout: base
title: Curves &#124; Vector Calculus
---

# Curves
{: .page-title}

> *Definition.*{: .def}
> A **parameterised curve** $C$ is a map of the form $f: \mathbb{R} \to \mathbb{R}^n$.

The choice of parameterisation is not unique, e.g. both $\mathbf{f}(t) = (\cos t, \sin t, t)$ and $\mathbf{g}(t) = (\cos \lambda t, \sin \lambda t, \lambda t)$
represents the same helix. Some of the properties depend on the parameterisation but some are not, in which will be our primary interest.

> *Definition.*{: .def}
> The vector function $\mathbf{x}(t)$ is _differentiable_ at $t$ if, as $\Delta t \to 0$, we can write
>
> $$
  \mathbf{x}(t + \Delta t) = \mathbf{x}(t) + \dot{\mathbf{x}}(t)\Delta t + o(\Delta t)
  $$
>
> The derivative $\dot{\mathbf{x}(t)}$ can also be called **tangent vector**.

It is a generation of [differentiability of scalar function](../analysis/differentiability.md#differentiability-linear-approximation) base on linear approximation.

> *Definition.*{: .def}
> A curve is said to be **smooth** if its derivative exists everywhere.

> *Definition.*{: .def}
> A parameterisation is said to be **regular** if $\dot{\mathbf{x}}(t) \not= 0$ for any $t$.

> *Proposition.*{: .prop}
> Given that the basis vectors are independent of $t$, the tangent vector can be found by differentiating the vector function component by component, i.e.
>
> $$
  {d\mathbf{x} \over dt} = \dot{\mathbf{x}}(t) = \dot{x}^i(t) \mathbf{e}_i
  $$

> *Proposition.*{: .prop}
> Suppose that $f(t)$ is a scalar function and $\mathbf{g}(t)$ and $\mathbf{h}(t)$ are vector functions.
> Then
>
> $$
  \begin{align*}
  {d \over dt} (f\mathbf{g}) &= f'\mathbf{g} + f\dot{\mathbf{g}} \\
  {d \over dt} (\mathbf{g \cdot h}) &= \dot{\mathbf{g}} \cdot \mathbf{h} + \mathbf{g} \cdot \dot{\mathbf{h}} \\
  {d \over dt} (\mathbf{g \times h}) &= \dot{\mathbf{g}} \times \mathbf{h} + \mathbf{g} \times \dot{\mathbf{h}} \\
  \end{align*}
  $$

## References

* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 1
