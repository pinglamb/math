---
layout: base
title: Difference Equations &#124; Differential Equations
---

# Difference Equations
{: .page-title}

A difference equation is equation associates values of $x_n$ with different values of $n$.
The order of adifference equation is the largest difference between any two of the indices of $x$.

## First order difference equation

A simple linear difference equation

$$
x_{n+1} = kx_n
$$

has a solution

$$
x_n = k^n x_0
$$

## Homogeneous second order linear difference equation

The way of solving linear difference equation is similar to that of differential equation.
Consider a general difference equation

$$
ax_{n+2} + bx_{n+1} + cx_n = 0
$$

Let $x_n = k^n$, substituding it back we have

$$
ak^{n+2} + bk^{n+1} + ck^n = 0
$$

Cancelling $k^n$ on both side of the equation gives us the auxiliary equation

$$
ak^2 + bk + c = 0
$$

Similar to that of differential equation, there are 3 different cases.

For 2 real roots, the general solution is

$$
x_n = Ak_1^n + Bk_2^n
$$

For repeated root, the general solution is

$$
x_n = Ak^n + Bnk^n
$$

For 2 complex roots $k = a \pm bi = r e^{i\theta}$ where $r = \sqrt{a^2 + b^2}$ and $\theta = \tan^{-1} b/a$, the general solution is

$$
x_n = r^n(A\cos n\theta + B\sin n\theta)
$$

To justify the general solution in case of complex roots, similarily, we can substitude the complex roots like they are real, i.e.

$$
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
