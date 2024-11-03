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

## Homogeneous with constant coefficient

## References

* James C. Robinson _An Introduction to Ordinary Differential Equations_, 2004 - Chapter 11, 12
