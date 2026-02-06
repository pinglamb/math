---
layout: base
title: Metric Spaces &#124; Analysis II
---

# Metric Spaces
{: .page-title}

So far the theory of analysis are developed with points and functions base on Euclidean space or complex plane.
Metric spaces provide a more general setup for analysis, in which the fundamental property is that there is a distance between any two points.

> *Definition.*{: .def}
> Suppose that $X$ is a (non-empty) set and that $\rho: X \times X \to \mathbf{R}$ is a real valued function with the following properties:
>
> + $\rho(x, y) \ge 0$ for all $x, y \in X$ with equality iff $x = y$;
>
> + $\rho(x, y) = \rho(y, x)$ for all $x, y \in X$;
>
> + $\rho(x, z) \le \rho(x, y) + \rho(y, z)$ for all $x, y, z \in X$ (triangle inequality).
>
> Then the function $\rho$ is called a **metric/distance** on $X$ and $(X, \rho)$ is called a **metric space**.

+ For $\mathbf{R}$, the usual metric is given by $\rho(x, y) = \vert x - y \vert$.

+ For $\mathbf{R}^n$, the usual metric is the _norm_, i.e. $\rho(x, y) = \sqrt{\sum (x_i - y_i)^2}$.

+ For $\mathbf{C}$, the usual metric is the same as $\mathbf{R}^2$, i.e. $\rho(z, z') = \vert z - z' \vert = \sqrt{(x - x')^2 + (y - y')^2}$.

+ For $B[a, b]$ being the set of bounded real functions on the interval $[a, b]$, we can have $\rho(f, g) = \sup \vert f(x) - g(x) \vert$, i.e. the maximum vertical distance between the two functions.

> *Definition.*{: .def}
> Let $(X, \rho)$ be a metric space and $Y \subset X$ and $\sigma: Y \times Y \to \mathbf{R}$ be the restriction of $\rho$ to $Y \times Y$, i.e. $\sigma(y, y') = \rho(y, y')$ for $y, y' \in Y$.
> Then $\sigma$ is a metric _induced_ by $(X, \rho)$ on $Y$ and $(Y, \sigma)$ is a **metric subspace** of $(X, \rho)$.
