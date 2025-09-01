---
layout: base
title: Poisson's Equation and Lapalce's Equation &#124; Vector Calculus
---

# Poisson's Equation and Laplace's Equation
{: .page-title}

With the understanding about how to differentiate and integrate scalar/vector fields in various types,
we can now explore differential equations that can be written in the language of vector calculus.

> *Definition.*{: .def}
> The **Poisson's equation** is of the form
>
> $$
  \nabla^2 \psi(\mathbf{x}) = \rho(\mathbf{x})
  $$
>
> and **Laplace's equation** is a special case of Poisson's equation of the form
>
> $$
  \nabla^2 \psi(\mathbf{x}) = 0
  $$

> *Proposition.*{: .prop}
> Laplace's equation is _linear_, i.e. if $\psi_1$ and $\psi_2$ are solutions,
> then $\lambda \phi_1 + \mu \psi_2$, where $\lambda$ and $\mu$ are real constants, is another solution.

## Separable Equations

> *Proposition.*{: .prop}
> Laplace's equation is _separable_ if it can be written in the form
>
> $$
  \psi(u, v, w) = U(u)V(v)W(w)
  $$
>
> where $(u, v, w)$ are orthogonal curvilinear.

It means that equation that is not separable in Cartesian coordinates can be separable in others and solvable.
For example,

$$
f(x, y, z) = {1 \over (x^2 + y^2 + z^2)^{1 \over 2}} \quad \implies \quad f(r, \theta, \phi) = {1 \over r}
$$

becomes separable in spherical polars.

Using 2D Cartesian coodinates as example, given $\psi = X(x)Y(y)$, substituting it to the Laplace's equation we have

$$
\nabla^2 \psi = X''(x) Y(y) + X(x) Y''(y) = 0
$$

and therefore

$$
{X''(x) \over X(x)} = {Y''(y) \over Y(y)} = C
$$

When $C = 0$, then $X'\'(x) = Y'\'(y) = 0$ so

$$
X = Ax + B \qquad Y = Cy + D
$$

When $C = k^2$, then $X'\' - k^2X = 0$ and $Y'\' + k^2Y = 0$ so

$$
X = Ae^{kx} + Be^{-kx} \qquad Y = C\sin ky + D\cos ky
$$

When $C = -k^2$, then $X'\' + k^2X = 0$ and $Y'\' - k^2Y = 0$ so

$$
X = C\sin kx + D\cos kx \qquad Y = Ae^{ky} + Be^{-ky}
$$

We can see that the solutions to separable Laplace's equations tend to grow or decay smoothly in one direction while oscillating in the other.

## References

* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 5
* K.F. Riley _Mathematical Methods for Physicists and Engineers_, 1998 - Chapter 8
