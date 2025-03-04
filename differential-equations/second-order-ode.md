---
layout: base
title: Second Order Ordinary Differential Equations &#124; Differential Equations
---

# Second Order Ordinary Differential Equations
{: .page-title}

## Existence and Uniqueness

> *Theorem.*{: .thm}
> Given a function $f(x_2, x_1, t)$.
> Suppose that $f$, $\partial f / \partial x_1$ and $\partial f / \partial x_2$ are continuous functions
> for $a_1 < x_1 < a_2$, $b_1 < x_2 < b_2$ and $t_1 < t < t_2$.
> Then for all initial conditions
>
> $$
  x(t_0) = x_0 \quad \text{and} \quad x'(t_0) = y_0
  $$
>
> with $a_1 < x_0 < x_2$, $b_1 < y_0 < b_2$ and $t_1 < t_0 < t_2$ there exists a unique solution of
>
> $$
  x'' = f(x', x, t)
  $$
>
> on some interval $I$ containing $t_0$, i.e. a continuous function with two continuous derivatives satisfying
> the the initial conditions and the differential equation on $I$.

## Linearity

> *Proposition.*{: .prop}
> The differential operator $L$ defined by
>
> $$
  L[x](t) = {\mathrm{d}^2x \over \mathrm{d}t^2}(t) + p(t) {\mathrm{d}x \over \mathrm{d}t}(t) + q(t)x(t)
  $$
>
> is linear.
>
> *Proof.*{: .prf}
>
> Consider a homogeneous second order linear differential equation
>
> $$
  {\mathrm{d}^2x \over \mathrm{d}t^2} + p(t) {\mathrm{d}x \over \mathrm{d}t} + q(t) x = 0
  $$
>
> which is equivalent to
>
> $$
  L[x] = 0
  $$
>
> Suppose $x_1$ and $x_2$ are two solutions to the equation, for all $\alpha, \beta \in \mathbb{R}$, we have
>
> $$
  \begin{align*}
  L[\alpha x_1 + \beta x_2]
  &= {\mathrm{d}^2 \over \mathrm{d}t^2}(\alpha x_1 + \beta x_2) + p(t) {\mathrm{d} \over \mathrm{d}t}(\alpha x_1 + \beta x_2) + q(t) (\alpha x_1 + \beta x_2) \\
  &= \alpha \left[ {\mathrm{d}^2 x_1 \over \mathrm{d}t^2} + p(t) {\mathrm{d} x_1 \over \mathrm{d}t} + q(t) x_1) \right]
     + \beta \left[ {\mathrm{d}^2 x_2 \over \mathrm{d}t^2} + p(t) {\mathrm{d} x_2 \over \mathrm{d}t} + q(t) x_2) \right] \\
  &= \alpha L[x_1] + \beta L[x_2] = 0
  \end{align*}
  $$
>
> so $\alpha x_1 + \beta x_2$ is also a solution.
> Hence, $L$ is linear.

## Linear Independence of Functions

> *Definition.*{: .def}
> The functions $x_1(t), ..., x_n(t)$ are **linearly independent** on an interval $I$ if
>
> $$
  a_1x_1(t) + \cdots + a_nx_n(t) = 0 \quad \implies \quad a_1 = \cdots = a_n = 0
  $$

> *Proposition.*{: .prop}
> Two linearly independent solutions are necessary and sufficient to obtain all possible solutions of homogeneous second order ODE.
>
> *Proof.*{: .prf}
>
> Given a homogeneous second order ODE.
> Suppose $x_1(t)$ is the solution satisfying
>
> $$
  x_1(t_0) = 1 \quad \text{and} \quad x_1'(t_0) = 0
  $$
>
> and $x_2(t)$ is the solution satisfying
>
> $$
  x_2(t_0) = 0 \quad \text{and} \quad x_1'(t_0) = 1
  $$
>
> By the existence and uniqueness theorem, both should exist but one cannot be a multiple of the other.
> Hence, at least two linearly independent solutions are necessary.
>
> Given two solutions that are linearly independent like above and for any given initial condition
>
> $$
  x(t_0) = x_0 \quad \text{and} \quad x'(t_0) = x_0'
  $$
>
> We have the following system of linear equations
>
> $$
  \begin{pmatrix}
  x_1(t_0) & x_2(t_0) \\
  x_1'(t_0) & x_2'(t_0) \\
  \end{pmatrix}
  \begin{pmatrix}
  \alpha \\
  \beta
  \end{pmatrix}
  =
  \begin{pmatrix}
  x_0 \\
  x_0'
  \end{pmatrix}
  $$
>
> As the two solutions are linearly independent, the system has a unique solution.
> Hence, two linearly independent solutions are sufficient to form any solution.

## The Wronskian

> *Definition.*{: .def}
> The **Wronskian** of two functions $x_1(t)$ and $x_2(t)$ is defined by
>
> $$
  W[x_1, x_2](t) = \begin{vmatrix} x_1(t) & x_2(t) \\ x_1'(t) & x_2'(t) \end{vmatrix} = x_1(t)x_2'(t) - x_2(t)x_1'(t)
  $$

> *Proposition.*{: .prop}
> The function $x_1$ and $x_2$ are linearly independent on an interval $I$ iff their Wronskian $W\[x_1, x_2\](t) \not \equiv 0$ on $I$.
> Hence, if $W\[x_1, x_2\](t) = 0$ for any $t \in I$, then $x_1$ and $x_2$ are linearly dependent.
>
> *Proof.*{: .prf}
>
> Given a homogeneous second order differential equation
>
> $$
  {\mathrm{d}x \over \mathrm{d}t^2} + p(t) {\mathrm{d}x \over \mathrm{d}t} + q(t)x = 0
  $$
>
> with two solutions $x_1$ and $x_2$. Then
>
> $$
  W(t) = x_1(t)x_2'(t) - x_2(t)x_1'(t) \quad \text{and} \quad W'(t) = x_1(t)x_2''(t) - x_1''(t)x_2(t)
  $$
>
> and we have
>
> $$
  \begin{align*}
  W'(t) + p(t)W(t) &= x_1(t) [x_2''(t) + p(t)x_2'(t)] - x_2(t) [x_1''(t) + p(t)x_1'(t)] \\
  &= x_1(t)[-q(t)x_2(t)] - x_2(t)[-q(t)x_1(t)] \\
  &= 0
  \end{align*}
  $$
>
> Therefore, we have the Wronskian satisfying the differential equation
>
> $$
  W'(t) = -p(t)W(t)
  $$
>
> If $W(t) = 0$, $W'(t) = 0$, then $W(t) \equiv 0$ for all $t \in I$.
>
> If $W(t) \not = 0$, $\vert W(t) \vert = e^{\int -p(t) \mathrm{d}t}$, then $W(t) \not = 0$ for all $t \in I$.

## Homogeneous linear equations with constant coefficient

For differential equation like

$$
ay'' + by' + cy = 0
$$

we guess the solution is of the form $y = e^{kt}$, substituding it into the equation we have

$$
(ak^2 + bk + c) e^{kt} = 0
$$

Since $e^{kt}$ is non-zero, we can divide both side with that and end up with a quadratic equation

$$
ak^2 + bk + c = 0
$$

which is called the _auxiliary equation_ or _characteristic equation_.

The quadratic equation can either have 2 real roots, 1 repeated real root and 2 complex roots,
which correspond to 3 different cases.

For 2 real roots $k_1, k_2$, the general solution is

$$
y = Ae^{k_1 t} + Be^{k_2 t}
$$

For 1 repeated root $k$, the general solution is

$$
y = Ae^{kt} + Bte^{kt}
$$

For 2 complex root $k = \rho \pm \omega i$, the general solution is

$$
y = e^{\rho t}(A \cos \omega t + B \sin \omega t)
$$

To derive the general solution for the case of complex roots, we start by treating them like they are real roots, i.e.

$$
y = Ce^{(\rho + \omega i)t} + De^{(\rho - \omega i)t}
$$

We want to restrict the solutions to be real. As $e^{(\rho - \omega i)t}$ is the complex conjugate of $e^{(\rho + \omega i)t}$,
by having $D$ being complex comjungate of $C$, we will restrict the right hand side to be real.

Therefore, let $C = \alpha + \beta i$,

$$
\begin{align*}
y &= 2 \text{Re}[Ce^{(\rho + \omega i)t}] \\
&= 2e^{\rho t} \text{Re}[(\alpha + \beta i)(\cos \omega t + i \sin \omega t)] \\
&= 2e^{\rho t} (\alpha \cos \omega t - \beta \sin \omega t) \\
&= e^{\rho t} (A \cos \omega t + B \sin \omega t)
\end{align*}
$$

We can combine $A \cos \omega t + B \sin \omega t$ to one oscillating term $M \cos (\omega t - \theta)$,
the amplitude is controlled by the sign of $\rho$.
If $\rho < 0$, the solution decays to $0$.
If $\rho = 0$, we have pure oscillations.
If $\rho > 0$, the solution grows exponentially fast.

## Inhomogeneous linear equation with constant coefficients

For differential equation like

$$
L[t] = ay'' + by' + c = f(t)
$$

Let $y_h$ be the solution of $L[t] = 0$, the homogeneous version of the equation,
and $y_p$ be a particular solution of $L[t] = f(t)$. We have

$$
L[y_h + y_p] = L[y_h] + L[y_p] = f(t)
$$

which is the general solution of the differential equation.

$y_h$ is called the _complimentary function_ which provides the two free variables for the initial conditions and
$y_p$ is called the _particular integral_.

Finding $y_p$ involves some educated guess, and in case $y_p$ is one of the function is $y_h$,
we can multiply it by $t$ or $t^2$ to form a new particular integral.

## Reduction of order

For a more general case of having coefficients as functions of $t$ for homogeneous linear differential equations

$$
a(t)y'' + b(t)y' + c(t)y = 0
$$

In case we know a particular solution $u(t)$ to the equation, let $y(t) = u(t)v(t)$, we have

$$
y' = u'v + v'u \quad \text{and} \quad y'' = u''v + 2u'v' + v''u
$$

Substituding it back and grouping the terms containing $v$, we have

$$
a(t)[v''u + 2u'v'] + b(t)[v'u] = v[a(t)u'' + b(t)u' + c(t)u] = 0
$$

as $u(t)$ is a solution of the equation.

Thus, by letting $z = v'$

$$
[a(t)u(t)]z' + [2a(t)u'(t) + b(t)u(t)]z = 0
$$

which is a first order differential equation that can be solved by the method of integrating factors.

## References

* James C. Robinson _An Introduction to Ordinary Differential Equations_, 2004 - Chapter 11, 12, 14, 17
