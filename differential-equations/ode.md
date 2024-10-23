---
layout: base
title: Ordinary Differential Equations &#124; Differential Equations
---

# Ordinary Differential Equations

## Existence and Uniqueness

Given an initial value problem with

$$
{\mathrm{d}y \over \mathrm{d}x} = f(x, y) \quad \text{and} \quad y(x_0) = y_0
$$

If $f(x, y)$ and $\partial f / \partial y (x, y)$ are continuous for $a < x < b$ and $c < y < d$
then for any $x_0 \in (a, b)$ and $y_0 \in (c, d)$ the initial value problem has a unique solution on some open interval $I$ containing $x_0$.

## Separable Equations

Given a first order differential equation of the form

$$
{\mathrm{d}y \over \mathrm{d}x} = f(x)g(y)
$$

and assume $g(y)$ is sufficiently smooth so that it has a unique solution for any specified initial condition.

Suppose $y(x)$ is a solution such that $g(y(x')) = 0$ for some $x'$.
Assume $y(x) = y(x')$ for all $x \in \mathbb{R}$, we have $g(y(x)) = g(y(x')) = 0$ for all $x \in \mathbb{R}$,
and substituding it back to the equation we have $y'(x) = 0$.
We can see that the constant function $y(x) = y(x')$ is the unique solution to the equation.

It implies that either $g(y(x)) = 0$ for every value of $x$ or $g(y(x)) \not = 0$ for every value of $x$.

In the case of $g(y(x)) \not = 0$ for all $x$, we can divide both sides of the equation by $g(y)$, i.e.

$$
{1 \over g(y)} {\mathrm{d}y \over \mathrm{d}x} = f(x)
$$

Let $H(y)$ be the anti-derivative of $1/g(y)$, i.e.

$$
H'(y) = {1 \over g(y)}
$$

By chain rule, we have

$$
{\mathrm{d} \over \mathrm{d}x} H(y) = H'(y) {\mathrm{d}y \over \mathrm{d}x} = {1 \over g(y)} {\mathrm{d}y \over \mathrm{d}x} = f(x)
$$

By integrating both sides we have

$$
H(y) = \int {1 \over g(y)} \, \mathrm{d}y = \int f(x) \, \mathrm{d}x
$$

which is like "multiplying" $\mathrm{d}x$ and then integrate both sides in the original equation.

Let $F(x)$ be the anti-derivative of $f(x)$, we have

$$
H(y(x)) = F(x) + c
$$

Subsituding the initial condition $(x_0, y_0)$ into the equation we have

$$
H(y_0) = F(x_0) + c \implies c = H(y_0) - F(x_0)
$$

and the solution is

$$
H(y) - H(y_0) = F(x) - F(x_0)
$$

By the fundamental theorem of calculus, we have

$$
\int_{y_0}^{y} {1 \over g(y)} \, \mathrm{d}y = \int_{x_0}^{x} f(x) \, \mathrm{d}x
$$

### Eliminating the absolute sign

This method frequently gives solution with absolute sign as we are integrating $1/g(y)$ on one side.
The absolute sign can most of the time eliminated by renaming the variables with a different condition.

For example, for equation

$$
y' = xy
$$

We will have

$$
\begin{align*}
ln|y| &= {x^2 \over 2} + c \\
|y| &= Ae^{x^2/2} \quad \text{where } A = e^c > 0 \\
y &= Be^{x^2/2} \quad \text{where } B \in \mathbb{R}
\end{align*}
$$

which is a general solution for the equation.

## Integrating Factors

Consider the linear differential equation

$$
y' + p(x)y = q(x)
$$

Multiplying both sides by a factor of $I(x)$ and we have

$$
I(x)y' + I(x)p(x)y = I(x)q(x)
$$

Consider the derivative of $I(x)y$, by product rule,

$$
{\mathrm{d} \over \mathrm{d}x}I(x)y = I(x)y' + I'(x)y
$$

Thus, in order for the L.H.S. to be grouped together, we need to have

$$
I(x)p(x) = I'(x)
$$

which is a separable equation, i.e.

$$
\int {1 \over I} \mathrm{d}I = \int p(x) \mathrm{d}x
$$

and we have the integrating factor

$$
I(x) = e^{\int p(x) \mathrm{d}x}
$$

Back to the linear differential equation, the general solution is

$$
\begin{align*}
{\mathrm{d} \over \mathrm{d}x} I(x)y &= I(x)q(x) \\
I(x)y &= \int I(x)q(x) \mathrm{d}x \\
y &= {1 \over I(x)} \int I(x)q(x) \mathrm{d}x
\end{align*}
$$

## References

* James C. Robinson _An Introduction to Ordinary Differential Equations_, 2004 - Chapter 8, 9
* [https://youtu.be/u0vbm1T420g](https://youtu.be/u0vbm1T420g)
