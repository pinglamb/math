---
layout: base
title: Vector Functions &#124; Vector Calculus
---

# Vector Functions
{: .page-title}

> *Definition.*{: .def}
> A vector function $\mathbf{r}(u)$ is _differentiable_ at $u$ if, as $\Delta u \to 0$, we can write
>
> $$
  \mathbf{r}(u + \Delta u) = \mathbf{r}(u) + \mathbf{\dot{r}}(u)\Delta u + o(\Delta u)
  $$
>
> The derivative $\mathbf{\dot{r}}(u)$ can also be called **tangent vector**.

It is a generation of [differentiability of scalar function](../analysis/differentiability.md#differentiability-linear-approximation) base on linear approximation.

> *Proposition.*{: .prop}
> Given that the basis vectors are independent of $u$, the tangent vector can be found by differentiating the vector function component by component, i.e.
>
> $$
  {d\mathbf{r} \over du} = \mathbf{\dot{r}}(u) = \dot{x}^i(u) \,\mathbf{e}_i
  $$

> *Proposition.*{: .prop}
> Suppose that $f(u)$ is a scalar function and $\mathbf{g}(u)$ and $\mathbf{h}(u)$ are vector functions.
> Then
>
> $$
  \begin{align*}
  {d \over dt} (f\mathbf{g}) &= f'\mathbf{g} + f\dot{\mathbf{g}} \\
  {d \over dt} (\mathbf{g \cdot h}) &= \dot{\mathbf{g}} \cdot \mathbf{h} + \mathbf{g} \cdot \dot{\mathbf{h}} \\
  {d \over dt} (\mathbf{g \times h}) &= \dot{\mathbf{g}} \times \mathbf{h} + \mathbf{g} \times \dot{\mathbf{h}} \\
  \end{align*}
  $$

> *Definition.*{: .def}
> The **differential** of a vector, denoted by $d\mathbf{r}$, is the vector
>
> $$
  d\mathbf{r} = {d\mathbf{r} \over du} du
  $$

> *Definition.*{: .def}
> The integration of a vector with respect to a scalar can be regarded as the inverse of differentiation,
> i.e. if $\mathbf{r}(u) = d\mathbf{R}/du$, then
>
> $$
  \int_{u_1}^{u_2} \mathbf{r}(u) \,du = \mathbf{R}(u_2) - \mathbf{R}(u_1)
  $$
>
> in which the integral is also a vector.

## Several Variables

The concept of derivatives can be extend to cases where the vectors are functions of more than one independent variables.

> *Definition.*{: .def}
> The partial derivative of vector function of several variables, i.e. $\mathbf{r}(u_1, u_2, ..., u_n)$, is defined to be
>
> $$
  {\partial \mathbf{r} \over du_k} = {\partial x^i \over \partial u_k} \,\mathbf{e}_i
  $$

> *Proposition.*{: .prop}
> **[Chain Rule]** If each of the variable $u_i$ is a function $u_i(v_1, v_2, ..., v_n)$ of the variables $v_i$, then
>
> $$
  {\partial \mathbf{r} \over dv_k} = {\partial \mathbf{r} \over \partial u^i} {\partial u^i \over \partial v_k}
  $$

> *Definition.*{: .def}
> The differential is defined to be
>
> $$
  d\mathbf{r} = {\partial \mathbf{r} \over \partial u^i} du^i
  $$

## References

* K.F. Riley _Mathematical Methods for Physicists and Engineers_, 1998 - Chapter 10.1, 10.2, 10.4
