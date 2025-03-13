---
layout: base
title: Directional Derivatives &#124; Differential Equations
---

# Directional Derivatives
{: .page-title}

Directional derivatives are the generalization of partial derivatives for obtaining rate of change on an arbitrary direction.

> *Definition.*{: .def}
> The **directional derivative** of $f$ at $(x_0, y_0)$ in the direction of a unit vector $\mathbf{u} = (a, b)$ is
>
> $$
  D_\mathbf{u} f(x_0, y_0) = \lim_{h \to 0} {f(x_0 + ha, y_0 + hb) - f(x_0, y_0) \over h}
  $$
>
> if this limit exists.

If $\mathbf{u} = \mathbf{i} = (1, 0)$, then $D_\mathbf{i} f = f_x$.
If $\mathbf{u} = \mathbf{j} = (0, 1)$, then $D_\mathbf{j} f = f_y$.

![Directional Derivative](../images/ode-directional-derivative-geometry.png)

> *Theorem.*{: .thm}
> If $f$ is a differentiable function of $x$ and $y$,
> then $f$ has a directional derivative in the direction of any unit vector $\mathbf{u} = (a, b)$ and
>
> $$
  D_\mathbf{u} f(x, y) = f_x(x, y)a + f_y(x, y)b
  $$
>
> Alternatively, if $\mathbf{u} = (\cos \theta, \sin \theta)$, then $D_\mathbf{u} f(x, y) = f_x(x, y)\cos\theta + f_y(x, y)\sin\theta$.
>
> *Proof.*{: .prf}
>
> If we define a function $g$ of the single variable $h$ by
>
> $$
  g(h) = f(x_0 + ha, y_0 + hb)
  $$
>
> then, by the definition of a derivative, we have
>
> $$
  \begin{align*}
  g'(0) &= \lim_{h \to 0} {g(h) - g(0) \over h} = \lim_{h \to 0} { f(x_0 + ha, y_0 + hb) - f(x_0, y_0) \over h} \\
  &= D_\mathbf{u} f(x_0, y_0)
  \end{align*}
  $$
>
> On the other hand, we can write $g(h) = f(x, y)$, where $x = x_0 + ha$, $y = y_0 + hb$, so
>
> $$
  g'(h) = {\partial f \over \partial x} {\mathrm{d} x \over \mathrm{d} h} + {\partial f \over \partial y} {\mathrm{d} y \over \mathrm{d} h} = f_x(x, y)a + f_y(x, y)b
  $$
>
> If we put $h = 0$, then $x = x_0$ and $y = y_0$ and
>
> $$
  g'(0) = f_x(x_0, y_0)a + f_y(x_0, y_0)b
  $$
>
> Hence,
>
> $$
  D_\mathbf{u} f(x_0, y_0) = f_x(x_0, y_0)a + f_y(x_0, y_0)b
  $$

## References

* James Stewart _Single Variable Calculus_, 2015 - Chapter 14
