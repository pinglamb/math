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
  \nabla \cong \mathbf{e}_j{\partial \over \partial x_j}
  $$

## Gradient

We start with differentiating a scalar field and assume we are working with Cartesian coordinates.

> *Definition.*{: .def}
> The **gradient** of a scalar field $\phi: \mathbb{R}^m \to \mathbb{R}$ is a vector field defined by
>
> $$
  \text{grad} \,\phi = \nabla \phi \cong \mathbf{e}_j { \partial \phi \over \partial x_j }
  = \left({\partial \phi \over \partial x_1}, {\partial \phi \over \partial x_2}, ..., {\partial \phi \over \partial x_m} \right)
  $$

> *Proposition.*{: .prop}
> The directional derivative of $\phi$ in the direction of $\mathbf{u}$ is given by
>
> $$
  D_\mathbf{u} \,\phi = \nabla \phi \cdot \mathbf{u}
  $$
>
> *Proof.*{: .prf}
>
> The [directional derivative](functions-of-several-variables.md#directional-derivative-as-partial) is given by
>
> $$
  D_\mathbf{u} \,\phi = {\partial \phi \over \partial x_j} u_j = \mathbf{e_j} {\partial \phi \over \partial x_j} \mathbf{e_i} \,u_i = \nabla \phi \cdot \mathbf{u}
  $$

> *Corollary.*{: .cor}
> $\nabla \phi$ lies in the direction of the fastest rate of increase in $\phi$.
> The largest rate of decrease of $\phi$ is in the direction of $-\nabla \phi$.

> *Proposition.*{: .prop}
> Suppose that $\mathbf{r}(u)$ is a curve and $\phi: \mathbb{R}^m \to \mathbb{R}$ is a scalar field,
> then the derivative of $\phi(\mathbf{r}(u))$ along the curve is given by
>
> $$
  {d \over du} \phi(\mathbf{r}(u)) = \nabla \phi \cdot {d \mathbf{r} \over du}
  $$
>
> If the parameter is the arc length $s$ then $d\phi/ds = \nabla \phi \cdot \mathbf{t}$.
>
> *Proof.*{: .prf}
>
> By chain rule,
>
> $$
  {d \over du} \phi(\mathbf{r}(u)) = {\partial \phi \over \partial x_j} {dx_j \over du}
  $$
>
> By definition,
>
> $$
  {d\mathbf{r} \over du} = \mathbf{e}_j {dx_j \over du}
  $$
>
> Hence,
>
> $$
  \nabla \phi \cdot {d\mathbf{r} \over du} = \mathbf{e}_j {\partial f \over \partial x_j} \mathbf{e}_i {dx_i \over du}
  = \delta_{ij} {\partial f \over \partial x_j} {dx_i \over du} = {\partial f \over \partial x_j} {dx_j \over du} = {d \over du} \phi(\mathbf{r}(u))
  $$

> *Proposition.*{: .prop}
> The differential $d\phi$ along the curve $\mathbf{r}(u)$ is given by
>
> $$
  d\phi = \nabla \phi \cdot d\mathbf{r}
  $$
>
> *Proof.*{: .prf}
>
> $$
  \nabla \phi \cdot d\mathbf{r} = \mathbf{e}_j {\partial f \over \partial x_j} \mathbf{e}_i \,dx_i = d\phi
  $$

## Divergence and Curl

By treating $\nabla$ as an vector and an operator that is waiting for a function to come along and be differentiated, we can see how it interacts with vector fields.

> *Definition.*{: .def}
> The **divergence** of a vector field $\mathbf{F}: \mathbb{R}^n \to \mathbb{R}^n$ is a scalar field defined by
>
> $$
  \text{div} \,\phi = \nabla \cdot \mathbf{F} = (\mathbf{e}_i {\partial \over \partial x^i}) \cdot (\mathbf{e}_j F^j) = {\partial F^i \over \partial x^i}
  $$

> *Definition.*{: .def}
> A vector field $\mathbf{F}$ is **solenoidal** if $\nabla \cdot \mathbf{F} = 0$.

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

## Basic Properties

> *Property.*{: .prop}
> **[Linearity]**
> Suppose that $\phi$ and $\psi$ are scalar fields and $\mathbf{F}$ and $\mathbf{G}$ are vector fields and $\lambda, \mu \in \mathbf{R}$. Then
>
> $$
  \begin{align*}
  \nabla (\lambda \phi + \mu \psi) &= \lambda(\nabla \phi) + \mu(\nabla \psi) \\
  \nabla \cdot (\lambda \mathbf{F} + \mu \mathbf{G}) &= \lambda(\nabla \cdot \mathbf{F}) + \mu(\nabla \cdot \mathbf{G}) \\
  \nabla \times (\lambda \mathbf{F} + \mu \mathbf{G}) &= \lambda(\nabla \times \mathbf{F}) + \mu(\nabla \times \mathbf{G}) \\
  \end{align*}
  $$

> *Property.*{: .prop}
> **[Leibniz Property]**
> Suppose that $\phi$ and $\psi$ are scalar fields and $\mathbf{F}$ is a vector field. Then
>
> $$
  \begin{align*}
  \nabla (\phi \psi) &= (\nabla \phi)\psi + \phi (\nabla \psi) \\
  \nabla \cdot (\phi \mathbf{F}) &= (\nabla \phi) \cdot \mathbf{F} + \phi(\nabla \cdot \mathbf{F}) \\
  \nabla \times (\phi \mathbf{F}) &= (\nabla \phi) \times \mathbf{F} + \phi(\nabla \times \mathbf{F}) \\
  \end{align*}
  $$

> *Property.*{: .prop}
> Suppose that $\mathbf{F}$ and $\mathbf{G}$ are vector fields. Then
>
> $$
  \begin{align*}
  \nabla \cdot (\mathbf{F} \times \mathbf{G}) &= (\nabla \times \mathbf{F}) \cdot \mathbf{G} - \mathbf{F} \cdot (\nabla \times \mathbf{G}) \\
  \nabla \times (\mathbf{F} \times \mathbf{G}) &= (\nabla \cdot \mathbf{G}) \mathbf{F} - (\nabla \cdot \mathbf{F}) \mathbf{G} + (\mathbf{G} \cdot \nabla) \mathbf{F} - (\mathbf{F} \cdot \nabla) \mathbf{G} \\
  \nabla (\mathbf{F} \cdot \mathbf{G}) &= \mathbf{F} \times (\nabla \times \mathbf{G}) + \mathbf{G} \times (\nabla \times \mathbf{F}) + (\mathbf{F} \cdot \nabla) \mathbf{G} + (\mathbf{G} \cdot \nabla) \mathbf{F} \\
  \end{align*}
  $$

## References

* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 1.3.1, 3
* K.F. Riley _Mathematical Methods for Physicists and Engineers_, 1998 - Chapter 10.7
