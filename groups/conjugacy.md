---
layout: base
title: Conjugacy &#124; Groups
---

# Conjugacy
{: .page-title}

Conjugacy is to study elements of a group that cannot be distinguished by using only group structure,
which means the elements that are conjugate to each other is essentially the "same" but are just viewed from different "perspectives".
Therefore, they share many properties.

> *Definition.*{: .def}
> Let $G$ be a group and suppose $g, g' \in G$. We say that $g, g'$ are **conjugate** in $G$, or that $g'$ is a conjugate of $g$,
> if there exists some $h \in G$ such that $g' = hgh^{-1}$.

The intuition about the definition is that if we have $G$ acts on a set $X$,
applying $g'$ has the same effect as applying $g$ to a changed perspective $hX$.

> *Proposition.*{: .prop}
> Conjugate elements have the same order.
>
> *Proof.*{: .prf}
>
> Suppose $a$ and $b$ are conjugate, say $a = hbh^{-1}$, then
>
> $$
  a^n = (hbh^{-1})^n = hb^nh^{-1}
  $$
>
> so $a^n = e$ iff $b^n = e$.

## Conjugacy Classes

> *Definition.*{: .def}
> The **conjugacy class** of $g$, denoted by $[g]$, is the set of all conjugates of $g$, i.e.
>
> $$
  [g] = \set{hgh^{-1} \in G : h \in G}
  $$

> *Proposition.*{: .prop}
> The conjugacy class of an element that commutes with everything contains only the element.
>
> *Proof.*{: .prf}
>
> Let $g \in G$ such that for all $h \in G$, $gh = hg$. So $hgh^{-1} = g$ for all $h \in G$ and $[g] = \set{g}$.

It means such element "looks the same from every perspective".

> *Proposition.*{: .prop}
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

Conjugacy classes provide a way to check if a subgroup is normal.

> *Proposition.*{: .prop}
> A subgroup $K$ of $G$ is a normal subgroup iff it is a union of conjugacy classes.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Suppose $K \trianglelefteq G$, for every $g \in G$, $gKg^{-1} = K$ and $gkg^{-1} \in K$.
> Thus, $[k] = \set{gkg^{-1} : g \in G} \subset K$ and $K$ is a union of conjugacy classes.
>
> ($\Leftarrow$) Suppose $K$ is a union of conjugacy classes, i.e. for any $k \in K$, $[k] \subset K$.
> For all $g \in G$, $gkg^{-1} \in [k]$ so if $k \in K$ then $gkg^{-1} \in K$.
> Thus, for all $g \in G$, $gKg^{-1} \subset K$. By replacing $g$ by $g^{-1}$, we have $g^{-1}Kg \subset K \implies gKg^{-1} \subset K$.
> Hence, $gKg^{-1} = K$ and $K$ is a normal subgroup of $G$.

## Conjugation Action

> *Proposition.*{: .prop}
> Any group $G$ acts on itself by conjugation, defined by $g(x) = gxg^{-1}$.
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

This action allows us to study the "similarity" of elements in the group by looking at the kernel, orbits and stabilizers, which all have special names.

> *Definition.*{: .def}
> The kernel of this action is the **centre** of $G$,
>
> $$
  Z(G) = \set{g \in G : gag^{-1} = a, \forall a \in G} = \set{g \in G : ga = ag, \forall a \in G}
  $$
>
> which are the elements that commute with everything.

These are the elements that look the same from every perspectives,
so it is made up of conjugacy classes which contain just one element,
i.e. $g \in Z(G) \iff [g] = \set{g}$.

> *Definition.*{: .def}
> The orbits of this action are the **conjugacy classes**, i.e.
>
> $$
  [g] = \set{g' \in G : \exists h \in G, hgh^{-1} = g'}
  $$

> *Definition.*{: .def}
> The stabilizers of this action are called **centralizers**,
>
> $$
  C_G(g) = \set{h \in G : hgh^{-1} = g} = \set{h \in G : hg = gh}
  $$
>
> which are the elements that commute with $g$.

> *Proposition.*{: .prop}
> $Z(G) = \bigcap_{g \in G} C_G(g)$.
>
> *Proof.*{: .prf}
>
> By the fact the [kernel is the intersection of stabilizers](group-actions.md#kernel-is-intersection-of-stabilizers).

> *Proposition.*{: .prop}
> $G$ acts by conjugation on a subgroup $K$ if $K \trianglelefteq G$.
>
> *Proof.*{: .prf}
>
> For all $g \in G$, $k \in K$, we have $gkg^{-1} \in K$. So,
>
> 0\. $g(k) = gkg^{-1} \in K$
>
> 1\. $eke^{-1} = k$ for all $k \in K$
>
> 2\. $g(h(k)) = ghkh^{-1}g^{-1} = (gh)k(gh)^{-1}$.

Hence, conjugation action restricts to only normal subgroups.

## Conjugation on Subgroups

Conjugation can also acts on the set of subgroups of $G$.
Instead of studying individual elements, we study the "similarity" of subgroups from different "perspectives" of $G$.

> *Proposition.*{: .prop}
> Let $X$ be the set of subgroups of $G$. Then $G$ acts by conjugation on $X$, defined by $g(H) = gHg^{-1}$.
>
> *Proof.*{: .prf}
>
> 0\. For $H \le G$, $e \in H$ so $geg^{-1} = e \in gHg^{-1}$ and therefore $gHg^{-1}$ is non-empty.
> Any two elements in $gHg^{-1}$ are of the form $gag^{-1}$ and $gbg^{-1}$ for some $a, b \in H$.
> Then
>
> $$
  (gag^{-1})(gbg^{-1})^{-1} = (gag^{-1})(gb^{-1}g^{-1}) = gab^{-1}g^{-1} \in gHg^{-1}
  $$
>
> as $ab^{-1} \in H$. Thus, $gHg^{-1}$ is a subgroup of $G$.
>
> 1\. $\forall H \in X$, $eHe^{-1} = H$.
>
> 2\. $g_1(g_2(H)) = g_1g_2Hg_2^{-1}g_1^{-1} = (g_1g_2)H(g_1g_2)^{-1}$
>
> So this is indeed an action.

### Normal Subgroups

The kernel of this action is exactly the normal subgroups.
It gives a very nice intuition about normal subgroups: they are subgroups that "looks the same under every perspectives".
Their conjugacy class contains only the subgroup itself, i.e. $[K] = \set{K}$ or $gKg^{-1} = K$ for every $g \in G$.
They commute with every $g \in G$, i.e. $gK = Kg$ so left cosets are same as right cosets.

We can therefore have an alternative definition of normal subgroups:

> *Definition.*{: .def}
> A subgroup $K$ of $G$ is **normal**, or **self-conjugate**,
> if every conjugate subgroup of $K$ is equal to $K$, i.e. $gKg^{-1} = K$ for every $g \in G$.

In conclusion, we have

> *Proposition.*{: .prop}
> If $K \trianglelefteq G$, the following are equivalent:
>
> 1. $gKg^{-1} = K$ for all $g \in G$.
>
> 2. $gK = Kg$ for all $g \in G$.
>
> 3. Left cosets are same as right cosets.
>
> 4. $K$ is kernel of some homomorphism.
>
> 5. $K$ is union of conjugacy classes of $G$.

### Conjugate Subgroups

> *Definition.*{: .def}
> Let $H_1, H_2 \le G$. $H_1$ and $H_2$ are **conjugate subgroups** of $G$ if for some $g \in G$, $H_1 = gH_2g^{-1}$.

> *Proposition.*{: .prop}
> Conjugate subgroups are isomorphic.
>
> *Proof.*{: .prf}
>
> Let $H_1, H_2$ be two conjugate subgroups of $G$, i.e. for some $g \in G$, $H_2 = gH_1g^{-1}$,
> which means for all $h_2 \in H_2$, there exists $h_1 \in H_1$ such that $h_2 = gh_1g^{-1}$.
>
> Let $\phi: H_1 \to H_2$ defined by $\phi(h_1) = gh_1g^{-1}$.
> It is a homomorphism because
>
> $$
  \phi(h_1h_1') = gh_1h_1'g^{-1} = gh_1g^{-1}gh_1'g^{-1} = \phi(h_1)\phi(h_1')
  $$
>
> If $gh_1g^{-1} = gh_1'g^{-1}$, then $h_1 = h_1'$ so it is injective.
> Also, it is surjective by definition.
> Hence, $\phi$ is an isomorphism and $H_1 \cong H_2$.

$\text{orb}(H)$ is the set of conjugate subgroups,
so they are the subgroups that are isomorphic to $H$ as proved above.

### Normalisers

> *Definition.*{: .def}
> The stabilizers of this action is called **normalisers**, i.e.
>
> $$
  N_G(H) = \set{g \in G : gHg^{-1} = H}
  $$
>
> which is the largest subgroup of $G$ such that $H \trianglelefteq N_G(H)$.

### Conjugate Stabilizers

> *Proposition.*{: .prop}
> The stabilizers of elements in same orbit are conjugate to each other.
>
> *Proof.*{: .prf}
>
> Let $G$ acts on $X$, and let $g \in G, x \in X$ and $y = g(x)$.
> If $h \in \text{Stab}(x)$, $ghg^{-1}(y) = gh(x) = g(x) = y$, so $ghg^{-1}$ fixes $y$ and $g\text{Stab}(x)g^{-1} \subseteq \text{Stab}(y)$.
> If $k \in \text{Stab}(y)$, $kg(x) = g(x) \implies g^{-1}kg(x) = x$, so $g^{-1}kg$ fixes $x$ and $g(g^{-1}kg)g^{-1} = k \in g\text{Stab}(x)g^{-1} \implies \text{Stab}(y) \subseteq g\text{Stab}(x)g^{-1}$.
> Hence, $\text{Stab}(g(x)) = g \text{Stab}(x) g^{-1}$.
>
> It implies that the stabilizers of elements in the same orbits are isomorphic.

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 12.10
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 7](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
