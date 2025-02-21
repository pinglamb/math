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
  f^{-1}(f(z)) = { (ad - bc)z + (bd - bd) \over (-ac + ac)z + (-bc + ad) } = z
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

In fact, the Möbius maps form a group under composition and is called [Möbius Group](../groups/mobius-groups.md).

## Existence and Uniqueness

Clearly we have

$$
f(z) = {az + b \over cz + d} = {\lambda az + \lambda b \over \lambda cz + \lambda d}
$$

so the representation is not unique (similar to fractions). However,

> *Proposition.*{: .prop}
> Suppose $a, b, c, d, a', b', c', d' \in \mathbb{C}$ with $(ad - bc)(a'd' - b'c') \not= 0$.
> If there exists at least three values of $z \in \mathbb{C}$ such that $cz + d \not= 0$, $c'z + d' \not= 0$ and
>
> $$
  {az + b \over cz + d} = {a'z + b' \over c'z + d'}
  $$
>
> then
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
> for some non-zero complex number $\lambda$, i.e. the representation is determined up to a complex scalar multiple.
>
> *Proof.*{: .prf}
>
> The existence of three values of $z \in \mathbb{C}$ satisfying the above conditions implies that the quadratic equation
>
> $$
  (az + b)(c'z + d') = (a'z + b')(cz + d)
  $$
>
> has three distinct solutions, which means we can equate the coefficients and have $ac' = a'c$, $bc' + ad' = a'd + b'c$ and $bd' = b'd$.
> It is equivalent to the existence of a complex number $\mu$ such that
>
> $$
  \begin{pmatrix}
  d & -b \\
  -c & a \\
  \end{pmatrix}
  \begin{pmatrix}
  a' & b' \\
  c' & d' \\
  \end{pmatrix}
  =
  \begin{pmatrix}
  \mu & 0 \\
  0 & \mu \\
  \end{pmatrix}
  $$
>
> and hence
>
> $$
  \begin{pmatrix}
  a' & b' \\
  c' & d' \\
  \end{pmatrix}
  =
  {\mu \over ad - bc}
  \begin{pmatrix}
  a & b \\
  c & d \\
  \end{pmatrix}
  $$

It suggests that the general Möbius map should have three degrees of freedom.

> *Lemma.*{: .lem}
> A Möbius map is anidentity map if it has three fixed points.
>
> *Proof.*{: .prf}
>
> Consider the quadratic equation $az + b = z(cz + d)$ having three distinct solutions,
> it implies $c = b = 0$ and $a = d$, i.e. the identity map.

> *Theorem.*{: .thm}
> Let $\Set{z\_1, z\_2, z\_3}$ and $\Set{w\_1, w\_2, w\_3}$ be triples of distinct points in $\mathbb{C}\_\infty$.
> Then there is a _unique_ Möbius map $f$ such that $f(z\_i) = w\_i$.
>
> *Proof.*{: .prf}
>
> Suppose $z\_i \not= \infty$, consider
>
> $$
  g(z) = \left( {z_3 - z_2 \over z_3 - z_1} \right) {z - z_1 \over z - z_2}
  $$
>
> we have $g(z\_1) = 0$, $g(z\_2) = \infty$ and $g(z\_3) = 1$.
> If any of the $z\_i = \infty$, by choosing $z\_4$ distinct from $z\_i$, we can construct $g$ base on $z'\_i = 1 / (z\_i - z\_4)$.
>
> Similarily, we can construct $h(z)$ such that $h(w\_1) = 0$, $h(w\_2) = \infty$ and $h(w\_3) = 1$ and $f = h^{-1}g$ is the map satisfying $f(z\_i) = w\_i$.
>
> Suppose $f$ and $f'$ are Möbius map such that $f(z\_i) = w\_i = f'(z\_i)$.
> As the map $f'^{-1}f$ fixes each $z\_i$, it is the identity map and hence $f = f'$.

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

