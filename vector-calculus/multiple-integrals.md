---
layout: base
title: Multiple Integrals &#124; Vector Calculus
---

# Multiple Integrals
{: .page-title}

Just as we may consider derivatives with respect to multiple variables, we can do the same for integrals.

> *Definition.*{: .def}
> Suppose that $f(x, y)$ is a function and $R$ is a closed two-dimensional region.
> Divide the region $R$ into $n$ subregions $\Delta R_p$ of area $\Delta A_p$ and let $(x_p, y_p)$ be any point in subregion $\Delta R_p$.
> If the sum
>
> $$
  S = \sum_{p=1}^n f(x_p, y_p) \Delta A_p
  $$
>
> tends to a unique limit $I$ as $n \to \infty$, then this is called the **double integral** of $f$ over the region $R$ and is denoted by
>
> $$
  I = \int_R f(x, y) dA \cong \iint_R f(x, y) \,dx \,dy
  $$

![Double Integral](../images/vector-calculus-double-integral.png)

> *Definition.*{: .def}
> Suppose that $f(x, y, z)$ is a function and $R$ is a closed three-dimensional region.
> Divide the region $R$ into $n$ subregions $\Delta R_p$ of volume $\Delta V_p$ and let $(x_p, y_p, z_p)$ be any point in subregion $\Delta R_p$.
> If the sum
>
> $$
  S = \sum_{p=1}^n f(x_p, y_p, z_p) \Delta V_p
  $$
>
> tends to a unique limit $I$ as $n \to \infty$, then this is called the **triple integral** of $f$ over the region $R$ and is denoted by
>
> $$
  I = \int_R f(x, y) dV \cong \iiint_R f(x, y, z) \,dx \,dy \,dz
  $$

![Triple Integral](../images/vector-calculus-triple-integral.png)

These ideas can be extended to define multiple integrals of higher dimensionality.

## References

* David Tong _Vector Calculus Lecture Notes_, 2024 - Chapter 2.1
* K.F. Riley _Mathematical Methods for Physicists and Engineers_, 1998 - Chapter 6
