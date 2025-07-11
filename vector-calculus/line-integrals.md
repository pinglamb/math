---
layout: base
title: Line Integrals &#124; Vector Calculus
---

# Line Integrals
{: .page-title}

> *Definition.*{: .def}
> Line integrals is the integration of some quantity related to a scalar/vector field
> between two given points, $A$ and $B$, in space along a prescribed curve $C$ that joins them.
> In general, they will be of the forms
>
> $$
  \int_C \phi \,d\mathbf{x} \qquad \int_C \mathbf{F} \cdot d\mathbf{x} \qquad \int_C \mathbf{F} \times d\mathbf{x}
  $$
>
> where $\phi$ is a scalar field and $\mathbf{F}$ is a vector field.

The formal definition is similar to that of ordinary integrals with the use of dissection and summing over the intervals.

> *Definition.*{: .def}
> If $C$ is closed, the line integral will be written as
>
> $$
  \oint_C \mathbf{F} \cdot d\mathbf{x}
  $$

For a close curve we have to specify the direction around the loop in which the integral is taken.
By convention, it is usually taken to be such that the region $R$ is on the left, i.e. anticlockwise if viewed from above.

> *Proposition.*{: .prop}
> In case of orthonormal basis, since $d\mathbf{x} = dx^i \mathbf{e}_i$, we have
>
> $$
  \int_C \phi \,d\mathbf{x} = \left( \int_C \phi \, dx^i \right) \mathbf{e}_i
  $$
>
> Suppose that the vector field $\mathbf{F} = F^i \mathbf{e}_i$. Then
>
> $$
  \int_C \mathbf{F} \cdot d\mathbf{x} = \int_C F_i \, dx_i
  $$
>
> and similarily procedure can be followed for the integral involving cross product.

> *Proposition.*{: .prop}
> Similar to ordinary integrals,
>
> $$
  \int_A^B \mathbf{F} \cdot d\mathbf{x} = -\int_B^A \mathbf{F} \cdot d\mathbf{x}
  $$
>
> and
>
> $$
  \int_A^B \mathbf{F} \cdot d\mathbf{x} = \int_A^C \mathbf{F} \cdot d\mathbf{x} + \int_C^B \mathbf{F} \cdot d\mathbf{x}
  $$

## References

* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 1.2, 1.3
