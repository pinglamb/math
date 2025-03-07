---
layout: base
title: Laplace Transform &#124; Differential Equations
---

# Laplace Transform
{: .page-title}

> *Definition.*{: .def}
> An **integral transform** is a relation of the form
>
> $$
  F(s) = \int_\alpha^\beta K(s, t)f(t) \mathrm{d}t
  $$
>
> where $K(s, t)$ is a given function, called the **kernel** of the transformation,
> and the limits of integration $\alpha$ and $\beta$ are also given.

> *Definition.*{: .def}
> **[Laplace Transform]**
> Let $f(t)$ be given fo $t \ge 0$. Then the Laplace transform of $f$ is defined by
>
> $$
  \mathcal{L}\{f(t)\} = F(s) = \int_0^\infty e^{-st}f(t)\mathrm{d}t
  $$
>
> whenever this improper integral converges.

> *Theorem.*{: .thm}
> Suppose $f$ is piecewise continuous and $\vert f(t) \vert \le Ke^{at}$ when $t \ge M$.
> Then the Laplace transform $\mathcal{L}\\{f(t)\\}$ exists for $s > a$.

The Laplace transform of some important elementary functions are given in the following examples

> *Example.*{: .eg}
> Let $f(t) = 1$, $t \ge 0$. Then
>
> $$
  \mathcal{L}\{1\} = \int_0^\infty e^{-st} \mathrm{d}t = - \lim_{A \to \infty} \left[{e^{-st} \over s}\right]_0^A = {1 \over s}, \quad s > 0
  $$

> *Example.*{: .eg}
> Let $f(t) = e^{at}$, $t \ge 0$. Then
>
> $$
  \mathcal{L}\{e^{at}\} = \int_0^\infty e^{-(s - a)t} \mathrm{d}t = - \lim_{A \to \infty} \left[{e^{-(s - a)t} \over s - a}\right]_0^A = {1 \over s - a}, \quad s > a
  $$

> *Example.*{: .eg}
> Let $f(t) = \sin at$, $t \ge 0$. Then
>
> $$
  \mathcal{L}\{\sin at\} = {a \over a^2 + s^2}, \quad s > 0
  $$

> *Proposition.*{: .prop}
> The Laplace transform is a _linear operator_, i.e.
>
> $$
  \mathcal{L}\{\alpha f_1(t) + \beta f_2(t) \} = \alpha \mathcal{L}\{f_1(t)\} + \beta \mathcal{L}\{f_2(t)\}
  $$

> *Theorem.*{: .thm}
> Suppose that $f$ is continuous and $f'$ is piecewise continuous. Then
>
> $$
  \mathcal{L}\{f'(t)\} = s \mathcal{L}\{f(t)\} - f(0)
  $$
>
> *Proof.*{: .prf}
>
> Let $f'$ has $n$ points of discontinuity at $t_i$ and $t_0 = 0$ and $t_{n+1} = \infty$. By definition,
>
> $$
  \mathcal{L}\{f'(t)\} = \int_0^\infty e^{-st}f'(t)\mathrm{d}t = \sum_{i=0}^{n} \left[ e^{-st}f(t) \right]_{t_i}^{t_{i+1}} + s\int_0^\infty e^{-st}f(t)\mathrm{d}t
  $$
>
> As $f$ is continuous,
>
> $$
  \sum_{i=0}^{n} \left[ e^{-st}f(t) \right]_{t_i}^{t_{i+1}} = \left[ e^{-st}f(t) \right]_0^\infty = -f(0)
  $$
>
> Hence,
>
> $$
  \mathcal{L}\{f'(t)\} = s \mathcal{L}\{f(t)\} - f(0)
  $$

> *Corollary.*{: .cor}
> Suppose that $f'$ is continuous and $f''$ is piecewise continuous. Then
>
> $$
  \mathcal{L}\{f''(t)\} = s^2 \mathcal{L}\{f(t)\} - sf(0) - f'(0)
  $$
>
> In general,
>
> $$
  \mathcal{L}\{f^{(n)}(t)\} = s^n \mathcal{L}\{f(t)\} - s^{n-1}f(0) - \cdots - sf^{(n-2)}(0) - f^{(n-1)}(0)
  $$

The Laplace transform is useful for solving differential equations as it reduces the problem to an algebraic equation.

## References

* William E. Boyce _Elementary Differential Equations and Boundary Value Problems_, 2009 - Chapter 6
