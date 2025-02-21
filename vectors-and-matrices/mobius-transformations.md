---
layout: base
title: Möbius Transformations &#124; Vectors and Matrices
---

# Möbius Transformations
{: .page-title}

Consider a transformation $f: \mathbb{C} \to \mathbb{C}$ with

$$
f(z) = {az + b \over cz + d}
$$

for some complex numbers $a, b, c$ and $d$ with $ad - bc \not= 0$.

As

$$
f(z) - f(w) = {(ad - bc)(z - w) \over (cz + d)(cw + d)}
$$

By having $ad - bc \not= 0$, we ensure $f$ is not constant and is injective, i.e. $f(z) = f(w)$ implies $z = w$.

However, if $c \not= 0$, $f(-d/c)$ is not defined.
It makes composition hard because each transformation will have its own undefined point.
In order to make $f$ complete, we need to add the "point at infinity" to $\mathbb{C}$ to form the extended complex plane.

> *Definition.*{: .def}
> The set $\mathbb{C}_{\infty} = \mathbb{C} \cup \Set{\infty}$ is called the **extended complex plane**.

> *Definition.*{: .def}
> A **Möbius transformation** is a map of $\mathbb{C}\_\infty \to \mathbb{C}\_\infty$ defined by
>
> $$
  f(z) = {az + b \over cz + d}
  $$
>
> for $a, b, c, \in \mathbb{C}$ and $ad - bc \not= 0$.
>
> If $c \not= 0$,
>
> $$
  f(-{d \over c}) = \infty \quad \text{and} \quad f(\infty) = {a \over c}
  $$
>
> If $c = 0$,
>
> $$
  f(\infty) = \infty
  $$

## Existence and Uniqueness

Clearly we have $f(z) = {az + b \over cz + d} = {\lambda az + \lambda b \over \lambda cz + \lambda d}$ so the representation is not unique (similar to fractions).
However,

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
>
> *Proof.*{: .prf}
>
> From the result of composition, we have
>
> $$
  f^{-1}(f(z)) = { (ad - bc)z + (bd - bd) \over (-ac + ac)z + (-bc + ad) } = 1
  $$
>
> Similarly, $f^{-1}(f(z)) = 1$.
>
> Also, $f^{-1}(f(-d/c)) = f^{-1}(\infty) = -d/c$ and $f^{-1}(f(\infty)) = f^{-1}(a/c) = \infty$.
> Hence, $f^{-1}(z)$ is the inverse of $f(z)$.

> *Proposition.*{: .prop}
> Möbius maps are bijections.
>
> $f(z)$ is injective as shown above under the condition $ad - bc \not= 0$.
>
> Consider
>
> $$
  g(z) = {dz - b \over -cz + a}
  $$
>
> we have $f(g(z)) = g(f(z)) = z$.

## Decomposition

> *Theorem.*{: .thm}
> Every Möbius transformation can be expressed as the composition of at most four maps, each of which is of one of the forms
>
> $$
  z \mapsto az, \quad z \mapsto z + b, \quad z \mapsto 1/z
  $$
>
> *Proof.*{: .prf}
>
> If $c = 0$ and $d \not= 0$, then $f = f\_2f\_1$ where
>
> $$
  \begin{align*}
  f_1(z) &= (a/d)z \\
  f_2(z) &= z + b/d
  \end{align*}
  $$
>
> If $c \not= 0$, then $f = f\_4f\_3f\_2f\_1$ where
>
> $$
  \begin{align*}
  f_1(z) &= z + (d/c) \\
  f_2(z) &= 1/z \\
  f_3(z) &= -((ad - bc)/c^2)z \\
  f_4(z) &= z + a/c
  \end{align*}
  $$

These simple maps are rotations, dilations, translations and complex inversion.

## Reference

* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Chapter A](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 13

