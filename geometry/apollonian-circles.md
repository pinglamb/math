---
layout: base
title: Apollonian Circles &#124; Geometry
---

# Apollonian Circles
{: .page-title}

Apollonian Circles are two families of circles such that every circles in the first family intersects orthogonally with every circles in the second family, and vice verse.

## By Complex Number

> *Problem.*{: .pro}
> Let $z, a, b \in \mathbb{C}$ correspond to points $P, A, B$ in the complex plane.
> Let $C_\lambda$ be the locus of $P$ defined by $\|PA\|/\|PB\| = \lambda$, where $\lambda$ is a fixed real positive constant.
> Show that $C_\lambda$ is a circle if $\lambda \not = 1$ and find its centre and radius.
>
> *Solution.*{: .sol}
>
> As $\|z - a\|^2 = (z - a)(\bar{z} - \bar{a})$ and $\|z - b\|^2 = (z - b)(\bar{z} - \bar{b})$, we have
>
> $$
  (1 - \lambda^2)z\bar{z} - (a - \lambda^2b)\bar{z} - (\bar{a} - \lambda^2\bar{b})z + |a|^2 - \lambda^2|b|^2 = 0
  $$
>
> From that, we can see the centre $w_\lambda$ should be
>
> $$
  w_\lambda = {a - \lambda^2b \over 1 - \lambda^2}
  $$
>
> By rearranging the terms, we have
>
> $$
  \begin{align*}
  (z - w_\lambda)(\bar{z} - \bar{w_\lambda}) &= {1 \over (1 - \lambda^2)^2}\left( (1 - \lambda^2)\lambda^2|b|^2 - (1 - \lambda^2)|a|^2 + |a - \lambda^2b|^2\right) \\
  &= {1 \over (1 - \lambda^2)^2} \left( \lambda^2|b|^2 + \lambda^2|a|^2 - \lambda^2(\bar{a}b + a\bar{b})\right) \\
  &= \left( {\lambda \over 1 - \lambda^2} |a - b| \right)^2
  \end{align*}
  $$
>
> Therefore,
>
> $$
  r_\lambda = {\lambda \over 1 - \lambda^2} |a - b|
  $$
>
> When $\lambda = 1$, $\|z - a\| = \|z - b\|$, hence it becomes the perpendicular bisector of $a$ and $b$.

> *Problem.*{: .pro}
> For the case $a = -b = p$, $p \in \mathbb{R}$, and for each fixed $\mu \in \mathbb{R}$, show that
>
> $$
  S_\mu = \Set{ z \in \mathbb{C} : \left|z - i\mu\right| = \sqrt{p^2 + \mu^2}}
  $$
>
> is a circle passing through $A$ and $B$ with its centre on the perpendicular bisector of $AB$.
>
> *Solution.*{: .sol}
>
> By definition, $S_\mu$ is a circle with centre $w_\mu = i\mu$ and radius $r_\mu = \sqrt{p^2 + \mu^2}$.
> As $a = p$, $\|a - i\mu\| = \|p - i\mu\| = \sqrt{p^2 + \mu^2}$, the circle passes through $A$.
> Similarily, it passes through $B$.
>
> As $\|a - i\mu\| = \|b - i\mu\|$, the centre of the circle $i\mu$ is always equidistant from $A$ and $B$,
> therefore it is the perpendicular bisector of $AB$.

> *Problem.*{: .pro}
> Show that the circles $C_\lambda$ and $S_\mu$ intersect orthogonally for all $\lambda$ and $\mu$.
>
> *Solution.*{: .sol}
>
> As $a = -b = p$, we have
>
> $$
  w_\lambda = {p - \lambda^2(-p) \over 1 - \lambda^2} = {1 + \lambda^2 \over 1 - \lambda^2}\,p
  $$
>
> and $\|a - b\| = 2p$, hence
>
> $$
  r_\lambda = {2\lambda p \over 1 - \lambda^2}
  $$
>
> Suppose $C_\lambda$ and $S_\mu$ intersects at $z$, we have
>
> $$
  |z - w_\lambda|^2 = r_\lambda^2 = \left({2\lambda p \over 1 - \lambda^2} \right)^2
  \quad\text{and}\quad
  |z - w_\mu|^2 = r_\mu^2 = p^2 + \mu^2
  $$
>
> The square of the distance between the two centres is
>
> $$
  \begin{align*}
  |w_\lambda - w_\mu|^2 &= \left| {1 + \lambda^2 \over 1 - \lambda^2}p - i\mu \right|^2 \\
  &= \left({1 + \lambda^2 \over 1 - \lambda^2} \right)^2p^2 + \mu^2 \\
  &= {4\lambda^2 + (1 - \lambda^2)^2 \over (1 -\lambda^2)^2}\,p^2 + \mu^2 \\
  &= \left({2\lambda p \over 1 - \lambda^2} \right)^2 + p^2 + \mu^2 \\
  &= r_\lambda^2 + r_\mu^2
  \end{align*}
  $$
>
> Hence, for any $\lambda$ and $\mu$, by the converse of Pythagorean Theorem,
> the radii drawn to the points of intersection meet at right angle and the two circles $C_\lambda$ and $S_\mu$ intersects orthogonally.

## References

* [https://en.wikipedia.org/wiki/Apollonian\_circles](https://en.wikipedia.org/wiki/Apollonian\_circles)
* [https://www.cut-the-knot.org/Curriculum/Geometry/LocusCircle.shtml](https://www.cut-the-knot.org/Curriculum/Geometry/LocusCircle.shtml)
