---
layout: base
title: Surfaces &#124; Vector Calculus
---

# Surfaces
{: .page-title}

> *Definition.*{: .def}
> A **parameterised surface** $S$ is a map of the form $\mathbf{r}: \mathbb{R}^2 \to \mathbb{R}^3$.

We can also represent a surface by $z = f(x, y)$ or $F(x, y, z) = 0$ and convert them to parametric form by for example, having

$$
\mathbf{r}(u, v) = u \mathbf{i} + v \mathbf{j} + f(u, v) \mathbf{k}
$$

> *Definition.*{: .def}
> The two curves $u = $ constant and $v = $ constant passing through $P$ on $S$ are called **coordinate curves**.

> *Definition.*{: .def}
> A **normal vector** $\mathbf{n}$ of $P$ on $S$ is the vector which points perpendicularly away from the surface.
> For the parameterised surface $\mathbf{r}(u, v) \in \mathbb{R}^3$, the normal direction is
>
> $$
  \mathbf{n} = {\partial \mathbf{r} \over \partial u} \times {\partial \mathbf{r} \over \partial v}
  $$
>
> It is the normal vector of the **tangent plane**.

> *Proposition.*{: .prop}
> An infinitesimal vector displacement $d\mathbf{r}$ in the position of $P$ is given by
>
> $$
  d\mathbf{r} = {\partial \mathbf{r} \over \partial u} du + {\partial \mathbf{r} \over \partial v} dv
  $$

> *Proposition.*{: .prop}
> The area of the infinitesimal parallelogram whose sides are the coordinate curves is
>
> $$
  dS = \left| {\partial \mathbf{r} \over \partial u} du \times {\partial \mathbf{r} \over \partial v} dv \right|
  = \left| {\partial \mathbf{r} \over \partial u} \times {\partial \mathbf{r} \over \partial v} \right| \,du \,dv
  = |\mathbf{n}| \,du \,dv
  $$

## References

* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 2.2
* K.F. Riley _Mathematical Methods for Physicists and Engineers_, 1998 - Chapter 10.5
