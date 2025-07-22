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

> *Definition.*{: .def}
> The **gradient** of a scalar field $\phi$ is a vector field defined by
>
> $$
  \text{grad}\, \phi \cong \nabla \phi \cong { \partial \phi \over \partial x^i } \mathbf{e}_i
  $$

> *Definition.*{: .def}
> The **directional derivative** is the rate of change of $\phi$ in a given direction $\mathbf{n}$, denoted by $D_{\mathbf{n}} \phi$.

> *Proposition.*{: .prop}
> $D_{\mathbf{n}} \phi = \nabla \phi \cdot \mathbf{n}$.

> *Corollary.*{: .cor}
> At each point in space, the vector $\nabla \phi(\mathbf{x})$ is pointing in the direction in which $\phi(\mathbf{x})$ changes most quickly.

## References

* K.F. Riley _Mathematical Methods for Physicists and Engineers_, 1998 - Chapter 10.7
