---
layout: base
title: Conjugacy &#124; Groups
---

# Conjugacy

> *Definition.*{: .def}
> Let $G$ be a group and suppose $g, g' \in G$. We say that $g, g'$ are **conjugate** in $G$, or that $g'$ is a conjugate of $g$,
> if there exists some $h \in G$ such that $g' = hgh^{-1}$.

> *Definition.*{: .def}
> Let $H_1, H_2 \le G$. $H_1$ and $H_2$ are **conjugate subgroups** of $G$ if for some $h \in G$, $H_1 = hH_2h^{-1}$.

> *Lemma.*{: .lem}
> Conjugate elements has the same order.
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

## Conjugacy Classes

> *Definition.*{: .def}
> The **conjugacy class** of $g$, denoted by $[g]$, is the set of all conjugates of $g$, i.e.
>
> $$
  [g] = \set{hgh^{-1} \in G : h \in G}
  $$

As $heh^{-1} = e$ for all $h \in G$, $[e] = \set{e}$.
As $ege^{-1} = g$, $g \in [g]$.

> *Theorem.*{: .thm}
> The relation of conjugacy in a group $G$ is an equivalence relation,
> meaning $G$ is the disjoint union of mutually disjoint conjugacy classes.
>
> *Proof.*{: .prf}
>
> Let $g \sim g'$ to mean that $g$ is conjugate to $g'$.
>
> 0\. [Reflexive] $g = ege^{-1}$ so $g \sim g$.
>
> 1\. [Symmetric] If $g' = hgh^{-1}$, $g = (h^{-1})g'(h^{-1})^{-1}$, so $g \sim g' \implies g' \sim g$.
>
> 2\. [Transitive] If $g' = hgh^{-1}$ and $g'' = h'g'h'^{-1}$, $g'' = (h'h)g(h'h)^{-1}$, so $g \sim g'$ and $g' \sim g'' \implies g \sim g''$
>
> So $\sim$ is a equivalence relation and hence the conjugacy classes partition $G$.

## Normal Subgroups

Conjugacy and normal subgroups are very closely related.

Consider the conjugacy class $[g]$, in general $[g] = \set{g}$ iff $g$ commutes with every element of $G$.
The conjugates of $g$ are giving us important information about the element $g$, for example, the more elements $g$ commutes with, the smaller $[g]$ is.
This idea can be extended to subgroups, which leads to an alternative definition of normal subgroups.

> *Definition.*{: .def}
> A subgroup $K$ of $G$ is a **normal**, or **self-conjugate**,
> if every conjugate subgroup of $H$ is equal to $H$, i.e. $gHg^{-1} = H$ for every $g \in G$.

## Conjugation Action

> *Lemma.*{: .lem}
> Any group $G$ acts on itself by conjugation, i.e. $\varphi: G \times G \to G$ defined by $\varphi(g)(x) = g(x) = gxg^{-1}$.
>
> *Proof.*{: .prf}
>
> 0\. $g(x) = gxg^{-1} \in G$ for all $g, x \in G$.
>
> 1\. $e(x) = exe^{-1} = x$ for all $x \in G$.
>
> 2\. $g(h(x)) = g(hxh^{-1}) = ghxh^{-1}g^{-1} = (gh)x(gh)^{-1} = gh(x)$
>
> So it is indeed an action.

The kernel, orbits and stabilizers of it has special names.

> *Definition.*{: .def}
> The kernel of this action is the **centre** of $G$,
>
> $$
  Z(G) = \set{g \in G : gag^{-1} = a, \forall a \in G} = \set{g \in G : ga = ag, \forall a \in G}
  $$
>
> which are the elements that commute with everything.

> *Definition.*{: .def}
> The orbits of this action are the **conjugacy classes** like that defined above, i.e.
>
> $$
  [g] = \set{g' \in G : \exists h \in G, hgh^{-1} = g'}
  $$

> *Definition.*{: .def}
> The stabilizers of this action are called **centralisers**,
>
> $$
  C_G(g) = \set{h \in G : hgh^{-1} = g} = \set{h \in G : hg = gh}
  $$
>
> which are the elements that commute with $g$.

> *Lemma.*{: .lem}
> $Z(G) = \bigcap_{g \in G} C_G(g)$.
>
> *Proof.*{: .prf}
>

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 12.10
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 7](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
