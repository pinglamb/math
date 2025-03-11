---
layout: base
title: Difference Equations &#124; Differential Equations
---

# Difference Equations
{: .page-title}

Difference equations can appear in numerical approximations and other problems that the independent variable only takes discrete values.

> *Definition.*{: .def}
> The **order** of a difference equation is the largest difference between any two of the indices of $x$.

## First Order + Homogeneous + Linear

> *Proposition.*{: .prop}
> For a first order linear difference equation
>
> $$
  x_{n+1} = kx_n
  $$
>
> the solution is
>
> $$
  x_n = k^n x_0
  $$

## Second Order + Homogeneous + Linear

The way of solving linear difference equations is analogous to that of differential equations.

> *Proposition.*{: .prop}
> Consider a difference equation of the form
>
> $$
  ax_{n+2} + bx_{n+1} + cx_n = 0
  $$
>
> Let $x_n = k^n$ be the solution. Then
>
> $$
  ak^{n+2} + bk^{n+1} + ck^n = 0
  $$
>
> and cancelling $k^n$ gives us the **auxiliary equation**
>
> $$
  ak^2 + bk + c = 0
  $$

> *Proposition.*{: .prop}
> If the auxiliary equation has two distinct real roots $k_1$ and $k_2$,
> then the general solution is
>
> $$
  x_n = Ak_1^n + Bk_2^n
  $$

> *Proposition.*{: .prop}
> If the auxiliary equation has one repeated root $k$,
> then the general solution is
>
> $$
  x_n = Ak^n + Bnk^n
  $$

> *Proposition.*{: .prop}
> If the auxiliary equation has two complex roots $k = a \pm bi = r e^{i\theta}$,
> then the general solution is
>
> $$
  x_n = r^n(A\cos n\theta + B\sin n\theta)
  $$
>
> *Proof.*{: .prf}
>
> The complex roots can be handled just like they are real, i.e.
>
> $$
  \begin{align*}
  x_n &= C(re^{i\theta})^n + C^\ast(re^{-i\theta})^n \\
  &= r^n[2\text{Re}(Ce^{in\theta})] \\
  &= r^n[2\text{Re}((\alpha + \beta i)(\cos n\theta + i \sin n\theta))] \\
  &= r^n[2(\alpha \cos n \theta - \beta \sin n \theta)] \\
  &= r^n(A \cos n \theta + B \sin n \theta)
  \end{align*}
  $$

## Inhomogeneous second order linear difference equation

For difference equation like

$$
ax_{n+2} + bx_{n+1} + cx_n = f_n
$$

Same as differential equation, we need to find a particular solution $x_p$ so

$$
x_n = x_h + x_p
$$

is the general solution.

Similarily, if the particular solution already appears in the complimentary solution, we need to add $n$ or $n^2$ to form a new particular solution.

## Reference

* James C. Robinson _An Introduction to Ordinary Differential Equations_, 2004 - Chapter 22
