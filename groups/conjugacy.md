---
layout: base
title: Conjugacy &#124; Groups
---

# Conjugacy

> *Definition.*{: .def}
> Let $G$ be a group and suppose $g, g' \in G$. We say that $g, g'$ are **conjugate** in $G$, or that $g'$ is a conjugate of $g$,
> if there exists some $h \in G$ such that $g' = hgh^{-1}$.

> *Definition.*{: .def}
> The **conjugacy class** of $g$, denoted by $[g]$, is the set of all conjugates of $g$, i.e.
>
> $$
  [g] = \set{hgh^{-1} : h \in G}
  $$

As $heh^{-1} = e$ for all $h \in G$, $[e] = \set{e}$.
As $ege^{-1} = g$, $g \in [g]$.

> *Definition.*{: .def}
> Let $H_1, H_2 \le G$. $H_1$ and $H_2$ are **conjugate subgroups** of $G$ if for some $h \in G$, $H_1 = hH_2h^{-1}$.

> *Lemma.*{: .lem}
> Conjugate elements has the same order..
>
> *Proof.*{: .prf}
>
> Suppose $a$ and $b$ are conjugate, say $a = hbh^{-1}$, then
>
> $$
  a^n = (hbh^{-1})^n = hb^nh^{-1}
  $$
>
> so $a^n = e$ if and only if $b^n = e$.

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 12.10
