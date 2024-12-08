---
layout: base
title: Lagrange's Theorem &#124; Groups
---

# Subgroups, Cosets and Lagrange's Theorem
{: .page-title}

## Subgroups

> *Definition.*{: .def}
> A **subgroup** $(H, \ast) \le (G, \ast)$ is a subset $H \subseteq G$ such that $H$ is still a group under the operation $\ast$.
If $H \le G$ and $H \not = G$, then $H$ is a proper subgroup.

To determine if a subset $H$ of $G$ is a subgroup, we check the following usual subgroup criterion:

> *Theorem.*{: .thm}
> Let $(G, \ast)$ be a group and let $H \subseteq G$ be a subset. Then $H \le G$ if and only if
>
> 1. [Identity] $e \in H$
>
> 2. [Closed] for $a, b \in H$, also $a \ast b \in H$
>
> 3. [Inverse] for $a \in H$, also $a^{-1} \in H$
>
> *Proof.*{: .prf}
>
> $(\Leftarrow)$ Note that associativity in $H$ is inherited from $G$ and these criterion ensures other group axioms for $H$.
>
> $(\Rightarrow)$ Conversely, suppose $(H, \ast)$ is a group.
> Firstly, let $e_H$ be the identity element in $H$, we have $e_H \ast e_H = e_H$ in $H$, so as in $G$.
> Thus $e_H = e_H \ast e = e_H \ast (e_H \ast e_H^{-1}) = (e_H \ast e_H) \ast e_H^{-1} = e_H \ast e_H^{-1} = e$.
> Hence, the identity of $H$ has to be the same as $G$, (1) is true.
> Secondary, (2) is true as $H$ has to be closed.
> Finally, as inverse is unique, the inverse of $a$ in $H$ has to be the same as that in $G$ so (3) is true.

The first criteria can be omitted if we know $H$ is non-empty subset.
As if $H$ is non-empty, there is some element $a \in H$ and by (3) then (2), $a \ast a^{-1} = e \in H$.

There is also a super-efficient subgroup criterion which is useful sometimes:

> *Theorem.*{: .thm}
> Let $(G, \ast)$ be a group and let $H \subseteq G$ be a subset. Then $H \le G$ if and only if
>
> 1. H is non-empty
>
> 2. Given $a, b \in H$, also $a \ast b^{-1} \in H$
>
> *Proof.*{: .prf}
>
> Similar to the above, $H$ is non-empty implies $e \in H$ (identity).
>
> For all $b \in H$, by (2) and setting $a = e$, we have $e \ast b^{-1} = b^{-1} \in H$ (inverse).
>
> For all $a, b \in H$, we have $b^{-1} \in H$, therefore by (2), $a \ast (b^{-1})^{-1} = a \ast b \in H$ (closed).

The following are some examples of subgroups:

* $(\mathbb{Z}, +) \le (\mathbb{Q}, +) \le (\mathbb{R}, +) \le (\mathbb{C}, +)$

* $(\set{e}, \ast) \le (G, \ast)$ (trivial subgroup)

* For $n \in \mathbb{Z}$, ($n\mathbb{Z}, +) \le (\mathbb{Z}, +)$

## Cosets

> *Definition.*{: .def}
> Let $H$ be a subgroup of $G$, i.e. $H \le G$. Given an element $a \in G$, the set
>
> $$
  aH = \set{ah : h \in H}
  $$
>
> is a _left coset_ of $H$. Similarily,
>
> $$
  Ha = \set{ha : h \in H}
  $$
>
> is a _right coset_ of $H$. (Note: coset is not necessary a group)

### Properties

> *Lemma.*{: .lem}
> Given $H \le G$ and $a \in G$. $a \in H$ if and only if $aH = H$.
>
> *Proof.*{: .prf}
>
> $(\Leftarrow)$ If $aH = H$, as $e \in H$, $ae = a \in H$.
>
> $(\Rightarrow)$ If $a \in H$, for any $h \in H$, $ah \in H$ (closure), so $aH \subseteq H$.
> We also have $a^{-1} \in H$, for any $h \in H$, $a^{-1}h \in H$ (closure), $a(a^{-1}h) = h \in aH$, so $H \subseteq aH$.
>
> Hence, $a \in H \iff aH = H$.

> *Lemma.*{: .lem}
> Given $H \le G$ and $a, b \in G$, $aH$ and $bH$ is either the same or disjoint.
>
> *Proof.*{: .prf}
>
> Assume they are not disjoint, that means for some $h_1 \in H$, $ah_1 \in bH$.
> Suppose $ah_1 = bh_2 \in bH$, we have $a = bh_2h_1^{-1}$.
> Thus, for any $h \in H$, $ah = bh_2h_1^{-1}h \in bH$, so $aH \subseteq bH$.
> Similarily, $b = ah_1h_2^{-1}$, $bH \subseteq aH$.
> Hence, $aH$ and $bH$ are either the same or disjoint.

> *Lemma.*{: .lem}
> $aH = bH$ if and only if $b^{-1}a \in H$.
>
> *Proof.*{: .prf}
>
> $(\Leftarrow)$ If $b^{-1}a \in H$, $(ba^{-1})^{-1} = a^{-1}b \in H$ as well.
> For any $h \in H$,
>
> $$
  ah = (bb^{-1})ah = b(b^{-1}ah) \in bH
  $$
>
> similarily $bh = (a(a^{-1})bh = a(a^{-1}bh) \in aH$. Hence, $aH = bH$.
>
> $(\Rightarrow)$ If $aH = bH$, say $ah_1 = bh_2$ for some $h_1, h_2 \in H$, $b^{-1}a = h_2h_1^{-1} \in H$ (closure).

> *Lemma.*{: .lem}
> All the left cosets of $H$ are of the same size as $H$.
>
> *Proof.*{: .prf}
>
> Let $aH$ be a left coset of $H$, if $ah_1 = ah_2$, $h_1 = h_2$, hence each $ah$ maps to a different element and $\|aH\| = \|H\|$.

> *Lemma.*{: .lem}
> Given $H \le G$, $G$ is the union of all the left cosets of $H$.
>
> *Proof.*{: .prf}
>
> For any $a \in G$, as $e \in H$, $a \in aH$. Hence, the union of all of the left cosets is $G$.

All the above properties is applicable to the right cosets. However

> *Theorem.*{: .thm}
> Left cosets and right cosets are of same size, i.e.
>
> $$
  \left|\set{aH : a \in G}\right| = \left|\set{Ha : a \in G}|\right|
  $$
>
> but in general they partition $G$ differently.
>
> *Proof.*{: .prf}
>
> Let $H \le G$ and $\phi$ be a mapping from the left cosets to right cosets defined as
>
> $$
  \forall a \in G, \phi(aH) = Ha^{-1}
  $$
>
> Assume $aH = bH$, we have
>
> $$
  aH = bH \implies b^{-1}a = b^{-1}(a^{-1})^{-1} \in H \implies Ha^{-1} = Hb^{-1}
  $$
>
> by the lemma above. Hence, $\phi$ is well-defined.
>
> Suppose $\phi(aH) = \phi(bH)$, we have
>
> $$
  Ha^{-1} = Hb^{-1} \implies b^{-1}(a^{-1})^{-1} = b^{-1}a \in H \implies aH = bH
  $$
>
> Hence, $\phi$ is injective.
>
> For all $a \in G$,
>
> $$
  Ha = H(a^{-1})^{-1} = \phi(a^{-1}H)
  $$
>
> Hence, $\phi$ is surjective.
>
> In conclusion, $\phi$ is a bijection and therefore the sizes of left cosets and right cosets are the same.
>
> Left cosets and right cosets in general partition $G$ differently. For example, let $H = \set{e, s} \le D_6$, we have
>
> $$
  \begin{align*}
  \set{aH: a \in D_6} &= \set{\set{e, s}, \set{r, rs}, \set{r^2, r^2s}} \\
  \set{Ha: a \in D_6} &= \set{\set{e, s}, \set{r, sr = r^2s}, \set{r^2, sr^2 = rs}}
  \end{align*}
  $$

### Coset as equivalence classes

> *Theorem.*{: .thm}
> Let $H \le G$, defining $a \sim b$ if $b^{-1}a \in H$ gives an equivalence relation on $G$, whose equivalence classes are the left cosets of $H$.
>
> *Proof.*{: .prf}
>
> The conditions for equivalence relation
>
> + [Reflexive] $a \sim a$ as $a^{-1}a = e \in H$
>
> + [Symmetric] $a \sim b \implies b \sim a$ as $(b^{-1}a)^{-1} = a^{-1}b \in H$
>
> + [Transitive] $a \sim b$ and $b \sim c \implies a \sim c$ as $(c^{-1}b)(b^{-1}a) = c^{-1}a \in H$.

## Lagrange's Theorem

> *Theorem.*{: .thm}
> If $G$ is a finite group and $H \le G$, then $\|H\|$ divides $\|G\|$.
>
> *Proof.*{: .prf}
>
> Base on the above properties of left cosets, the group $G$ is partitioned by the distinct cosets into disjoint sets with respect to $H$, which is called _coset decomposition_.
>
> Hence, $\|G\| = \text{number of distinct cosets} \times \|H\|$ and $\|H\| \mid \|G\|$.

Lagrange's Theorem shows that the order of $G$ influences the number of subgroups $G$ can have, regardless of the group structure.

> *Definition.*{: .def}
> The **index** of $H$ in $G$, denoted by $\|G:H\|$, is the number of distinct cosets of $H$ in $G$.
> Hence,
>
> $$
  |G| = |G:H||H|
  $$

> *Corollary.*{: .cor}
> Suppose $G$ is a finite group, for $a \in G$, $\text{ord}(a)$ divides $\|G\|$.
>
> *Proof.*{: .prf}
>
> Consider the subgroup $H = \langle a \rangle$ generated by $a$, by Lagrange's Theorem, $\text{ord}(a) = \|H\|$ divides $\|G\|$.

> *Corollary.*{: .cor}
> Suppose $G$ is a finite group, for $a \in G$, $a^{\|G\|} = e$.
>
> *Proof.*{: .prf}
>
> We have $\|G\| = k \cdot \text{ord}(a)$, hence $a^{\|G\|} = (a^{\text{ord}(a)})^k = e$.

> *Definition.*{: .def}
> The **exponent** of $G$ is the smallest number $m$ such that $a^m = e$ for all $a \in G$.
> Thus, $m$ is the least common multiple of all the orders of elements, which are divisors of $\|G\|$, so $m$ divides $\|G\|$.

> *Corollary.*{: .cor}
> Suppose $G$ is a finite group of order $p$, where $p$ is prime. Then $G$ is cyclic and the only subgroups are $\set{e}$ and $G$.
>
> *Proof.*{: .prf}
>
> For $H \le G$, by Lagrange's Theorem, $\|H\|$ divides $\|G\| = p$, hence $\|H\| = 1$ or $p$.
> When $\|H\| = 1$, $H = \set{e}$. When $\|H\| = p$, $H = G$. For any $a \in G$, $\text{ord}(a) = p$ and generates $G$.

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 12
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 3](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
