---
layout: base
title: Second Order Ordinary Differential Equations &#124; Differential Equations
---

# Second Order Ordinary Differential Equations

## Existence and Uniqueness

Given a function $f(x, y, z)$, suppose $f$, $\partial f / \partial y$ and $\partial f / \partial z$ are
continuous functions for $x_1 < x < x_2$, $y_1 < y < y_2$ and $z_1 < z < z_2$.
Then for all initial conditions

$$
y(x_0) = y_0 \quad \text{and} \quad y'(x_0) = z_0
$$

with $x_1 < x_0 < x_2$, $y_1 < y_0 < y_2$ and $z_1 < z_0 < z_2$ there exists a unique solution of

$$
y'' = f(x, y, y')
$$

on some interval $I$ containing $x_0$, i.e. a continuous function with two continuous derivatives satisfying
the the initial conditions and the differential equation.

## Linearity

Define

$$
L[y] = {\mathrm{d}^2y \over \mathrm{d}x^2} + p(x) {\mathrm{d}y \over \mathrm{d}x} + q(x) y
$$

which is a function of $x$.

Consider a homogeneous second order linear differential equation

$$
{\mathrm{d}^2y \over \mathrm{d}x^2} + p(x) {\mathrm{d}y \over \mathrm{d}x} + q(x) y = 0
$$

which we can simplify it as

$$
L[y] = 0
$$

Suppose $y_1$ and $y_2$ are solutions to the equation, we have

$$
\begin{align*}
L[\alpha y_1 + \beta y_2]
&= {\mathrm{d}^2 \over \mathrm{d}x^2}(\alpha y_1 + \beta y_2) + p(x) {\mathrm{d} \over \mathrm{d}x}(\alpha y_1 + \beta y_2) + q(x) (\alpha y_1 + \beta y_2) \\
&= \alpha \left[ {\mathrm{d}^2 y_1 \over \mathrm{d}x^2} + p(x) {\mathrm{d} y_1 \over \mathrm{d}x} + q(x) y_1) \right] + \beta \left[ {\mathrm{d}^2 y_2 \over \mathrm{d}x^2} + p(x) {\mathrm{d} y_2 \over \mathrm{d}x} + q(x) y_2) \right] \\
&= \alpha L[y_1] + \beta L[y_2] = 0
\end{align*}
$$

We can see that the differential operator $L$ is linear and we can express the general solution of the equation as

$$
y(x) = \alpha y_1(x) + \beta y_2(x)
$$

for linear independent solutions $y_1$ and $y_2$.

## Linear Independence

### The Wronskian

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
L[x] = ay'' + by' + c = f(x)
$$

Let $y_h$ be the solution of $L[x] = 0$, the homogeneous version of the equation,
and $y_p$ be a particular solution of $L[x] = f(x)$. We have

$$
L[y_h + y_p] = L[y_h] + L[y_p] = f(x)
$$

which is the general solution of the differential equation.

$y_h$ is called the _complimentary function_ which provides the two free variables for the initial conditions and
$y_p$ is called the _particular integral_.

Finding $y_p$ involves some educated guess, and in case $y_p$ is one of the function is $y_h$,
we can multiply it by $t$ or $t^2$ to form a new particular integral.

## Reduction of order

## References

* James C. Robinson _An Introduction to Ordinary Differential Equations_, 2004 - Chapter 11, 12, 14, 17
