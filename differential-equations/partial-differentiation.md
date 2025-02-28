---
layout: base
title: Partial Differentiation &#124; Differential Equations
---

# Partial Differentiation
{: .page-title}

> *Theorem.*{: .thm}
> **[Clairaut's Theorem]**
> If $f$ has continuous second partial derivatives on a disk $D$,
>
> $$
  {\partial^2 f \over \partial x \partial y} = {\partial^2 f \over \partial y \partial x}
  $$

## Chain Rule

> *Proposition.*{: .prop}
> For function $f(x, y)$ with $x = g(t)$ and $y = h(t)$,
>
> $$
  {\mathrm{d}f \over \mathrm{d}t} = {\partial f \over \partial x} {\mathrm{d}x \over \mathrm{d}t} + {\partial f \over \partial y} {\mathrm{d}y \over \mathrm{d}t}
  $$

> *Proposition.*{: .prop}
> For function $f(x, y)$ with $x = g(s, t)$ and $y = h(s, t)$,
>
> $$
  {\partial f \over \partial t} = {\partial f \over \partial x} {\partial x \over \partial t} + {\partial f \over \partial y} {\partial y \over \partial t}
  $$

> *Proposition.*{: .prop}
> For implicit function $F(x, y, z) = 0$,
>
> $$
  {\partial F \over \partial x} =
  {\partial F \over \partial x} {\partial x \over \partial x} +
  {\partial F \over \partial y} {\partial y \over \partial x} +
  {\partial F \over \partial z} {\partial z \over \partial x}
  = 0
  $$
>
> With $y$ holding as constant,
>
> $$
  {\partial z \over \partial x} \Bigg\rvert_{y} = - {\partial F / \partial x \over \partial F / \partial z}
  $$

Be noted the extra negative sign makes it different from that in single variable calculus.

> *Proposition.*{: .prop}
> For implicit function $F(x, y, z) = 0$,
>
> $$
  {\partial x \over \partial y} \Bigg\rvert_{z} {\partial y \over \partial z} \Bigg\rvert_{x} {\partial z \over \partial x} \Bigg\rvert_{y} = -1
  $$

## Reciprocals

For transformation like $(x, y) \to (r, \theta)$, we can't just write the derivatives as reciprocal of each other, i.e.

$$
{\partial r \over \partial x} \not = {1 \over \partial x / \partial r}
$$

It is because the partial derivatives on the L.H.S is holding $y$ as constant but the one on the R.H.S is holding $\theta$ as constant.

The reciprocal rule works only if we hold the same variables constant, i.e.

$$
{\partial r \over \partial x} \Bigg\rvert_{y} \not = {1 \over \partial x / \partial r \big\rvert_{y}}
$$

which in this case the partial derivatives on the R.H.S allows $\theta$ to vary so to keep $y$ constant.

## References

* James Stewart _Single Variable Calculus_, 2015 - Chapter 11.10
