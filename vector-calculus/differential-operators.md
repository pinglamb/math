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

> *Property.*{: .prop}
> **[Linearity]**
> Suppose that $\phi$ and $\psi$ are scalar fields and $\lambda, \mu \in \mathbb{R}$. Then
>
> $$
  \nabla (\lambda \phi + \mu \psi) = \lambda(\nabla \phi) + \mu(\nabla \psi)
  $$
>
> *Proof.*{: .prf}
>
> $$
  \nabla (\lambda \phi + \mu \psi)
  = \mathbf{e}_j \left[{\partial \over \partial x_j} (\lambda \phi + \mu \psi)\right]
  = \lambda \left(\mathbf{e}_j {\partial \phi \over \partial x_j}\right) + \mu \left(\mathbf{e}_j {\partial \psi \over \partial x_j}\right)
  = \lambda(\nabla \phi) + \mu(\nabla \psi)
  $$

## Divergence

By treating $\nabla$ as an vector and an operator that is waiting for a function to come along and be differentiated, we can develop how it interacts with vector fields.

> *Definition.*{: .def}
> The **divergence** of a vector field $\mathbf{F}: \mathbb{R}^n \to \mathbb{R}^n$ is a scalar field defined by
>
> $$
  \text{div} \,\phi = \nabla \cdot \mathbf{F} = (\mathbf{e}_i {\partial \over \partial x_i}) \cdot (\mathbf{e}_j \,F_j) = {\partial F_j \over \partial x_j}
  $$

For a vector function $\mathbf{F}: \mathbb{R}^3 \to \mathbb{R}^3 = (F_1, F_2, F_3)$,

$$
\nabla \cdot \mathbf{F} = {\partial F_1 \over \partial x} + {\partial F_2 \over \partial y} + {\partial F_3 \over \partial z}
$$

> *Definition.*{: .def}
> A vector field $\mathbf{F}$ is **solenoidal** if $\nabla \cdot \mathbf{F} = 0$.

> *Proposition.*{: .prop}
> The divergence of a vector field is the trace of its Jacobian matrix.

> *Property.*{: .prop}
> **[Linearity]**
> Suppose that $\mathbf{F}$ and $\mathbf{G}$ are vector fields and $\lambda, \mu \in \mathbb{R}$. Then
>
> $$
  \nabla \cdot (\lambda \mathbf{F} + \mu \mathbf{G}) = \lambda(\nabla \cdot \mathbf{F}) + \mu(\nabla \cdot \mathbf{G})
  $$
>
> *Proof.*{: .prf}
>
> $$
  \nabla \cdot (\lambda \mathbf{F} + \mu \mathbf{G})
  = {\partial \over \partial x_j} (\lambda F_j + \mu G_j)
  = \lambda {\partial F_j \over \partial x_j} + \mu {\partial G_j \over \partial x_j}
  = \lambda(\nabla \cdot \mathbf{F}) + \mu(\nabla \cdot \mathbf{G})
  $$

## Curl

> *Definition.*{: .def}
> The **curl** of a vector field $\mathbf{F}: \mathbb{R}^3 \to \mathbb{R}^3$ is a vector field defined by
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
  &= (\partial_y F_z - \partial_z F_y, \partial_z F_x - \partial_x F_z, \partial_x F_y - \partial_y F_x) \\
  &= \varepsilon_{ijk} \,\mathbf{e}_i \,{\partial F_k \over \partial x_j}
  \end{align*}
  $$

> *Proposition.*{: .prop}
> Let $\mathsf{T}$ be the Jacobian matrix of $\mathbf{F}$. Then
>
> $$
  \nabla \times \mathbf{F} = \varepsilon_{ijk} \,\mathbf{e}_i T_{kj}
  $$

> *Definition.*{: .def}
> A vector field $\mathbf{F}$ is **irrotational** if $\nabla \times \mathbf{F} = 0$.

> *Property.*{: .prop}
> **[Linearity]**
> Suppose that $\mathbf{F}$ and $\mathbf{G}$ are vector fields and $\lambda, \mu \in \mathbb{R}$. Then
>
> $$
  \nabla \times (\lambda \mathbf{F} + \mu \mathbf{G}) = \lambda(\nabla \times \mathbf{F}) + \mu(\nabla \times \mathbf{G})
  $$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \nabla \times (\lambda \mathbf{F} + \mu \mathbf{G})
  &= \varepsilon_{ijk} \,\mathbf{e}_i \,{\partial \over \partial x_j}(\lambda F_k + \mu G_k) \\
  &= \lambda \left(\varepsilon_{ijk} \,\mathbf{e}_i \,{\partial F_k \over \partial x_j}\right)
    + \mu \left(\varepsilon_{ijk} \,\mathbf{e}_i \,{\partial G_k \over \partial x_j}\right) \\
  &= \lambda(\nabla \times \mathbf{F}) + \mu(\nabla \times \mathbf{G})
  \end{align*}
  $$

## Vector Differential Identities

> *Definition.*{: .def}
> Suppose $\mathbf{F}$ is a vector field, $\mathbf{F} \cdot \nabla$ is the differential _operator_
>
> $$
  \mathbf{F} \cdot \nabla \cong F_j {\partial \over \partial x_j}
  $$

For a scalar field $\phi: \mathbb{R}^3 \to \mathbb{R}$,

$$
(\mathbf{F} \cdot \nabla)\phi = F_j {\partial \phi \over \partial x_j} = F_1 {\partial \phi \over \partial x} + F_2 {\partial \phi \over \partial y} + F_3 {\partial \phi \over \partial z} = \mathbf{F} \cdot (\nabla \phi)
$$

For a vector field $\mathbf{G}: \mathbb{R}^3 \to \mathbb{R}^3$,

$$
\begin{align*}
(\mathbf{F} \cdot \nabla)\mathbf{G} = \mathbf{e}_i \,F_j {\partial G_i \over \partial x_j}
&= \left(F_1 {\partial G_1 \over \partial x} + F_2 {\partial G_1 \over \partial y}+ F_3 {\partial G_1 \over \partial z} \right) \,\mathbf{i} \\
&\qquad + \left(F_1 {\partial G_2 \over \partial x} + F_2 {\partial G_2 \over \partial y}+ F_3 {\partial G_2 \over \partial z} \right) \,\mathbf{j} \\
&\qquad + \left(F_1 {\partial G_3 \over \partial x} + F_2 {\partial G_3 \over \partial y}+ F_3 {\partial G_3 \over \partial z} \right) \,\mathbf{k}
\end{align*}
$$

> *Proposition.*{: .prop}
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

> *Proposition.*{: .prop}
> Suppose that $\mathbf{F}$ and $\mathbf{G}$ are vector fields. Then
>
> $$
  \begin{align*}
  \nabla \cdot (\mathbf{F} \times \mathbf{G}) &= (\nabla \times \mathbf{F}) \cdot \mathbf{G} - \mathbf{F} \cdot (\nabla \times \mathbf{G}) \\
  \nabla \times (\mathbf{F} \times \mathbf{G}) &= (\nabla \cdot \mathbf{G}) \mathbf{F} - (\nabla \cdot \mathbf{F}) \mathbf{G} + (\mathbf{G} \cdot \nabla) \mathbf{F} - (\mathbf{F} \cdot \nabla) \mathbf{G} \\
  \nabla (\mathbf{F} \cdot \mathbf{G}) &= \mathbf{F} \times (\nabla \times \mathbf{G}) + \mathbf{G} \times (\nabla \times \mathbf{F}) + (\mathbf{F} \cdot \nabla) \mathbf{G} + (\mathbf{G} \cdot \nabla) \mathbf{F} \\
  \end{align*}
  $$

## Second Order Differential Operators

There are a number of possible ways to combining the differential operators.

### Divergence of Gradient

Consider the divergence of the gradient of a scalar field $\phi: \mathbb{R}^3 \to \mathbb{R}$, by definition

$$
\nabla \cdot (\nabla \phi) = {\partial \over \partial x_j} \left({\partial \phi \over \partial x_j }\right)
= {\partial^2 \phi \over \partial x^2} + {\partial^2 \phi \over \partial y^2} + {\partial^2 \phi \over \partial z^2}
$$

> *Definition.*{: .def}
> The **Laplacian operator** $\nabla^2$ is defined by
>
> $$
  \nabla^2 = \nabla \cdot \nabla = { \partial^2 \over \partial x_j \partial x_j }
  $$

### Divergence of Curl

> *Proposition.*{: .prop}
> The divergence of the curl of vector field $\mathbf{F}$ with equal mixed partial derivatives is always zero, i.e.
>
> $$
  \nabla \cdot (\nabla \times \mathbf{F}) = 0
  $$
>
> *Proof.*{: .prf}
>
> $$
  \nabla \cdot (\nabla \times \mathbf{F})
  = { \partial \over \partial x_i } \left( \varepsilon_{ijk} {\partial F_k \over \partial x_j} \right)
  = \varepsilon_{ijk} {\partial f_k \over \partial x_i \partial x_j} = 0
  $$
>
> since $\partial_i \partial_j F_k = \partial_j \partial_j F_k$.

> *Proposition.*{: .prop}
> Conversely, suppose that a vector field $\mathbf{v}$ is solenoidal, i.e. $\nabla \cdot \mathbf{v} = 0$,
> then there exists a non-unique **vector potential** $\mathbf{A}$ such that $\nabla \times \mathbf{A} = \mathbf{v}$.

It is relatively straightforward to construct a vector potential.
Let $\mathbf{v} = (v_1, v_2, v_3)$ to be defined throughout $\mathbb{R}^3$, then a possible vector potential is

$$
\mathbf{A}(\mathbf{x}) = \left( \int_{z_0}^z v_2(x, y, z') \,dz', \int_{x_0}^x v_3(x', y, z_0) \,dx' - \int_{z_0}^z v_1(x, y, z') \,dz', 0 \right)
$$

where $\mathbf{x}_0 = (x_0, y_0, z_0)$ is a constant.

### Curl of Gradient

> *Proposition.*{: .prop}
> The curl of the gradient of a scalar field $\phi$ with equal mixed partial derivatives is always zero, i.e.
>
> $$
  \nabla \times (\nabla \phi) = \mathbf{0}
  $$
>
> *Proof.*{: .prf}
>
> $$
  [\nabla \times (\nabla \phi)]_i
  = \varepsilon_{ijk} {\partial \over \partial x_j} \left( { \partial \phi \over \partial x_k } \right)
  = \varepsilon_{ijk} {\partial^2 \phi \over \partial x_j \partial x_k} = 0
  $$
>
> since $\partial_j \partial_k \phi = \partial_k \partial_j \phi$.

The vector potential defined above is not unique since if $\nabla \times \mathbf{A} = \mathbf{v}$, then

$$
\nabla \times (\mathbf{A} + \nabla \phi) = \nabla \times \mathbf{A} = \mathbf{v}
$$

for all scalar functions $\phi$.

### Curl of Curl

Consider the curl of the curl of a vector field $\mathbf{F}$ with equal mixed derivatives, then

$$
\begin{align*}
[\nabla \times (\nabla \times \mathbf{F})]_i
&= \varepsilon_{ijk} {\partial \over \partial x_j} \left( \varepsilon_{kpq} { \partial F_q \over \partial x_p } \right) \\
&= (\delta_{ip}\delta_{jq} - \delta_{iq}\delta_{jp}) {\partial^2 F_q \over \partial x_j \partial x_p} \\
&= {\partial^2 F_j \over \partial x_j \partial x_i } - {\partial^2 F_i \over \partial x_j \partial x_j } \\
&= [\nabla(\nabla \cdot \mathbf{F}) - \nabla^2 \mathbf{F}]_i
\end{align*}
$$

> *Definition.*{: .def}
> The **Laplacian operator** $\nabla^2$ acting on a vector function $\mathbf{F}$ is defined by
>
> $$
  \nabla^2 \mathbf{F} = \nabla(\nabla \cdot \mathbf{F}) - \nabla \times (\nabla \times \mathbf{F})
  $$

## References

* Stephen J. Cowley _Vector Calculus Lectures Notes_, 2000 - Chapter 5
* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 1.3.1, 3.1, 3.2
* K.F. Riley _Mathematical Methods for Physicists and Engineers_, 1998 - Chapter 10.7, 10.8
