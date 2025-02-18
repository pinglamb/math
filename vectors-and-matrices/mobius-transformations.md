---
layout: base
title: Möbius Transformations &#124; Vectors and Matrices
---

# Möbius Transformations
{: .page-title}

> *Definition.*{: .def}
> A **Möbius transformation** is a map of $\mathbb{C} \to \mathbb{C}$ defined by
>
> $$
  f(z) = {az + b} \over {cz + d}
  $$
>
> for some complex numbers $a, b, c$ and $d$ with $ad - bc \not= 0$.

The $ad - bc \not= 0$ because we would like to make $f$ injective, i.e.

$$
f(z) - f(w) = {(ad - bc)(z - w) \over (cz + d)(cw + d)}
$$

and $ad - bc \not= 0$ so that $f(z) = f(w)$ implies $z = w$.

> *Proposition.*{: .prop}
> The representation is determined up to a complex scalar multiple, i.e. if
>
> $$
  {az + b \over cz + d} = {a'z + b' \over c'z + d'}
  $$
>
> with $(ad - bc)(a'd' - b'c') \not= 0$, then
>
> $$
  \begin{pmatrix}
  a' & b' \\
  c' & d' \\
  \end{pmatrix} = \lambda \begin{pmatrix}
  a & b \\
  c & d \\
  \end{pmatrix}
  $$
>
> for some non-zero complex number $lambda$.

From the definition, we can see that $f(-d/c)$ is not defined, given $c \not= 0$.
It makes composition hard because each transformation will have its own undefined point.
In order to make $f$ complete, we need to add the "point at infinity".

> *Definition.*{: .def}
> Let $f$ be a Möbius transformation.
> If $c \not= 0$, then
>
> $$
  f(\infty) = a/c \quad \text{and} \quad f(-d/c) = \infty
  $$
>
> If $c = 0$, then
>
> $$
  f(\infty) = \infty
  $$

> *Definition.*{: .def}
> The set $\mathbb{C} \cup \Set{\infty}$ is called the **extended complex plane** and is denoted by $\mathbb{C}_{\infty}$.

## Composition

> *Proposition.*{: .prop}
> The composition of two Möbius maps is again a Möbius map.
>
> *Proof.*{: .prf}
>
> Let
>
> $$
  f(z) = {az + b \over cz + d} \quad \text{and} \quad g(z) = {\alpha z + \beta \over \gamma z + \delta}
  $$
>
> Then
>
> $$
  \begin{align*}
  g(f(z)) &= {\alpha (az + b) + \beta (cz + d) \over \gamma (az + b) + \delta (cz + d)} \\
  &= { (\alpha a + \beta c)z + (\alpha b + \beta d) \over (\gamma a + \delta c)z + (\gamma b + \delta d)}
  \end{align*}
  $$
>
> where we note that $(\alpha a + \beta c)(\gamma a + \delta c) - (\alpha b + \beta d)(\gamma b + \delta d) = (ad - bc)(\alpha \gamma - \beta \delta) \not= 0$.
>
> We also need to check a few special cases regarding $\infty$ which are omitted.

In other words, all Möbius maps are _closed_ under composition.

## Inverse

> *Proposition.*{: .prop}
> The Möbius map
>
> $$
  f^{-1}(z) = {dz - b \over -cz + a}
  $$
>
> is the inverse of $f(z)$.


## Decomposition

## Reference

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter A](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 13

