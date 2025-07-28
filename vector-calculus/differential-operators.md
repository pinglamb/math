---
layout: base
title: Differential Operators &#124; Vector Calculus
---

# Differential Operators
{: .page-title}

Certain differential operations may be performed on scalar and vector fields and have wide range of applications.
Central to all these differential operations is the following vector operator.

> *Definition.*{: .def}
> The vector operator **del/nabla**, denoted by $\nabla$, in Cartesian coordinate systems is defined by
>
> $$
  \nabla \cong {\partial \over \partial x^i} \mathbf{e}_i
  $$

## Gradient

We start with differentiating a scalar field and assume we are working with Cartesian coordinates.

> *Definition.*{: .def}
> The **gradient** of a scalar field $\phi$ is a vector field defined by
>
> $$
  \text{grad} \,\phi = \nabla \phi \cong { \partial \phi \over \partial x^i } \mathbf{e}_i
  $$

> *Proposition.*{: .prop}
> Suppose that $\mathbf{r}(u)$ is a curve and $\phi$ is a scalar field, then
>
> $$
  {d\phi \over du} = \nabla \phi \cdot {d \mathbf{r} \over du}
  $$
>
> *Proof.*{: .prf}
>
> For an infinitesimal vector displacement $d\mathbf{r}$, we have
>
> $$
  \nabla \phi \cdot d\mathbf{r} = ({ \partial \phi \over \partial x^i } \mathbf{e}_i) \cdot (dx^j \mathbf{e}_j) = { \partial \phi \over \partial x^i } dx^i = d\phi
  $$
>
> which is the infinitesimal change of $\phi$ in going from position $\mathbf{r}$ to $\mathbf{r} + d\mathbf{r}$ along the curve.
>
> Hence,
>
> $$
  {d\phi \over du} = \nabla \phi \cdot {d\mathbf{r} \over du}
  $$
>
> and if the parameter is the arc length $s$ along the curve then
>
> $$
  {d\phi \over ds} = \nabla \phi \cdot \mathbf{t}
  $$

In the discussion of [directional derivatives](../differential-equations/directional-derivatives.md),
the rate of change of scalar field $\phi$ in a given direction $\mathbf{u}$ is given by

$$
D_{\mathbf{u}} \phi = \nabla \phi \cdot \mathbf{u}
$$

and therefore the vector $\nabla \phi(\mathbf{x})$ is pointing in the direction in which $\phi(\mathbf{x})$ changes most quickly.

## Divergence and Curl

By treating $\nabla$ as an vector and an operator that is waiting for a function to come along and be differentiated, we can see how it interacts with vector fields.

> *Definition.*{: .def}
> The **divergence** of a vector field $\mathbf{F}: \mathbb{R}^n \to \mathbb{R}^n$ is a scalar field defined by
>
> $$
  \text{div} \,\phi = \nabla \cdot \mathbf{F} = (\mathbf{e}_i {\partial \over \partial x^i}) \cdot (\mathbf{e}_j F^j) = {\partial F^i \over \partial x^i}
  $$

> *Definition.*{: .def}
> The **Jacobian** matrix of a vector field $\mathbf{F}(\mathbf{x})$ is defined by $T_{ij} = \partial_j F_i$.

> *Proposition.*{: .prop}
> The divergence is the trace of the Jacobian matrix, i.e. $\nabla \cdot \mathbf{F} = T_{ii}$.

> *Definition.*{: .def}
> The **curl** of a vector field $\mathbf{F}: \mathbf{R}^3 \to \mathbf{R}^3$ is a vector field defined by
>
> $$
  \begin{align*}
  \text{curl} \,\mathbf{F} = \nabla \times \mathbf{F}
  &= (\mathbf{i} \partial_x + \mathbf{j} \partial_y + \mathbf{j} \partial_z) \times (\mathbf{i} F_x + \mathbf{j} F_y + \mathbf{j} F_z) \\
  &= \begin{vmatrix}
     \mathbf{i} & \mathbf{j} & \mathbf{k} \\
     \partial_x & \partial_y & \partial_k \\
     F_x & F_y & F_k \\
     \end{vmatrix} \\
  &= (\partial_y F_z - \partial_z F_y, \partial_z F_x - \partial_x F_z, \partial_x F_y - \partial_y F_x)
  \end{align*}
  $$

## References

* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 1.3.1, 3
* K.F. Riley _Mathematical Methods for Physicists and Engineers_, 1998 - Chapter 10.7
