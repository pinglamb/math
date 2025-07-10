---
layout: base
title: Curves &#124; Vector Calculus
---

# Curves
{: .page-title}

> *Definition.*{: .def}
> A **parameterised curve** $C$ is a map of the form $f: \mathbb{R} \to \mathbb{R}^n$.

The choice of parameterisation is not unique, e.g. both $\mathbf{f}(t) = (\cos t, \sin t, t)$ and $\mathbf{g}(t) = (\cos \lambda t, \sin \lambda t, \lambda t)$
represents the same helix. Some of the properties depend on the parameterisation but some are not, in which will be our primary interest.

> *Definition.*{: .def}
> The vector function $\mathbf{x}(t)$ is _differentiable_ at $t$ if, as $\Delta t \to 0$, we can write
>
> $$
  \mathbf{x}(t + \Delta t) = \mathbf{x}(t) + \dot{\mathbf{x}}(t)\Delta t + o(\Delta t)
  $$
>
> The derivative $\dot{\mathbf{x}(t)}$ can also be called **tangent vector**.

It is a generation of [differentiability of scalar function](../analysis/differentiability.md#differentiability-linear-approximation) base on linear approximation.

> *Definition.*{: .def}
> A curve is said to be **smooth** if its derivative exists everywhere.

> *Definition.*{: .def}
> A parameterisation is said to be **regular** if $\dot{\mathbf{x}}(t) \not= 0$ for any $t$.

> *Proposition.*{: .prop}
> Given that the basis vectors are independent of $t$, the tangent vector can be found by differentiating the vector function component by component, i.e.
>
> $$
  {d\mathbf{x} \over dt} = \dot{\mathbf{x}}(t) = \dot{x}^i(t) \mathbf{e}_i
  $$

> *Proposition.*{: .prop}
> Suppose that $f(t)$ is a scalar function and $\mathbf{g}(t)$ and $\mathbf{h}(t)$ are vector functions.
> Then
>
> $$
  \begin{align*}
  {d \over dt} (f\mathbf{g}) &= f'\mathbf{g} + f\dot{\mathbf{g}} \\
  {d \over dt} (\mathbf{g \cdot h}) &= \dot{\mathbf{g}} \cdot \mathbf{h} + \mathbf{g} \cdot \dot{\mathbf{h}} \\
  {d \over dt} (\mathbf{g \times h}) &= \dot{\mathbf{g}} \times \mathbf{h} + \mathbf{g} \times \dot{\mathbf{h}} \\
  \end{align*}
  $$

## Arc Length

> *Definition.*{: .def}
> The **arc length** is the distance between two points along a curve, which is a scalar quantity.

> *Proposition.*{: .prop}
> The arc length $s$ between $t_1$ to $t_2$ along a curve $\mathbf{x}(t)$ is given by
>
> $$
  s = \int_{t_1}^{t_2} \sqrt{ {d\mathbf{x} \over dt} \cdot {d\mathbf{x} \over dt} } \,dt
  $$
>
> *Proof.*{: .prf}
>
> Consider an infinitesimal vector displacement
>
> $$
  d\mathbf{x} = dx^i e_i
  $$
>
> along the curve. The square of the infinitesimal distance moved is then given by
>
> $$
  (ds)^2 = dx^idx^i = d\mathbf{x} \cdot d\mathbf{x}
  $$
>
> and therefore
>
> $$
  \left( ds \over dt \right)^2 = {d\mathbf{x} \over dt} \cdot {d\mathbf{x} \over dt}
  $$
>
> Hence, the arc length between $a$ and $b$ is
>
> $$
  s = \int_{t_1}^{t_2} \sqrt{ {d\mathbf{x} \over dt} \cdot {d\mathbf{x} \over dt} } \,dt
  $$

From the above, we can see that

$$
{ds \over dt} = \pm \left| {d\mathbf{x} \over dt} \right|
$$

The $\pm$ sign depends on which direction we chose as the "positive" direction of $s$ from a reference point.
If $t$ traces the curve in the "positive" direction of $s$ then $ds/dt = \vert d\mathbf{x}/dt \vert$.

> *Proposition.*{: .prop}
> The arc length $s$ is independent of the choice of parameterisation.
>
> *Proof.*{: .prf}
>
> Let $\tau(t)$ be a different parameterisation with $d\tau/dt > 0$. By chain rule,
>
> $$
  {d\mathbf{x} \over dt} = {d\mathbf{x} \over d\tau} {d\tau \over dt}
  $$
>
> Hence,
>
> $$
  s = \int_{t_1}^{t_2} \sqrt{ {d\mathbf{x} \over dt} \cdot {d\mathbf{x} \over dt} } \,dt
  = \int_{t_1}^{t_2} \sqrt{ {d\mathbf{x} \over d\tau} \cdot {d\mathbf{x} \over d\tau} } { d\tau \over dt} \,dt
  = \int_{\tau_1}^{\tau_2} \sqrt{ {d\mathbf{x} \over d\tau} \cdot {d\mathbf{x} \over d\tau} } \,d\tau
  $$

It means that arc length itself is a natural parameterisation of the curve.
We can set a certain point on the curve as reference point, i.e. $s = 0$, choose the "positive" direction, and every point on the curve will be associated with a unique value of $s$.

> *Proposition.*{: .prop}
> A curve parameterised by its arc length always has unit tangent vector, i.e. $\vert d\mathbf{x}/ds \vert = 1$, and is denoted by $\mathbf{\hat{t}}$.
>
> *Proof.*{: .prf}
>
> Base on the fact that $(ds/dt)^2 = \dot{\mathbf{x}} \cdot \dot{\mathbf{x}}$ and chain rule.

> *Definition.*{: .def}
> The **curvature** $\kappa$ is the magnitude of the rate of change of $\mathbf{\hat{t}}$ with respect to $s$, i.e.
>
> $$
  \kappa(s) = \left| {d\mathbf{\hat{t}} \over ds } \right| = \left| {d^2\mathbf{x} \over ds^2 } \right|
  $$

> *Definition.*{: .def}
> The **principal normal** is the unit vector $\mathbf{\hat{n}}$ in the direction perpendicular to $\mathbf{\hat{t}}$.

> *Proposition.*{: .prop}
> For tangent vector $\mathbf{\hat{t}}$ with curvature $\kappa$ and principal normal $\mathbf{\hat{n}}$, we have
>
> $$
  {d\mathbf{\hat{t}} \over ds} = \kappa \mathbf{\hat{n}}
  $$
>
> *Proof.*{: .prf}
>
> Since $\mathbf{\hat{t}} \cdot \mathbf{\hat{t}} = \vert \mathbf{\hat{t}} \vert^2 = 1$ which is independent of $s$, we have
>
> $$
  {d \over ds} (\mathbf{\hat{t}} \cdot \mathbf{\hat{t}}) = 2\mathbf{\hat{t}} \cdot {d\mathbf{\hat{t}} \over ds} = 0
  $$
>
> Therefore, $d\mathbf{\hat{t}}/ds$ is perpendicular to $\mathbf{\hat{t}}$ and hence parallel to $\mathbf{\hat{n}}$ and $d\mathbf{\hat{t}}/ds = \kappa \mathbf{\hat{n}}$.

## References

* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 1
