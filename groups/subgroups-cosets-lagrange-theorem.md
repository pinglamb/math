---
layout: base
title: Lagrange's Theorem &#124; Groups
---

# Lagrange's Theorem

## Subgroups

A _subgroup_ $(H, \ast) \le (G, \ast)$ is a subset $H \subseteq G$ such that $H$ is still a group under the operation $\ast$.
If $H \le G$ and $H \not = G$, then $H$ is a proper subgroup.

### Usual subgroup criterion

Let $(G, \ast)$ be a group and let $H \subseteq G$ be a subset. Then $H \le G$ if and only if

(i) [Identity] $e \in H$

(ii) [Closed] for $a, b \in H$, also $a \ast b \in H$

(iii) [Inverse] for $a \in H$, also $a^{-1} \in H$

_[Proof]_ Note that associativity in $H$ is inherited from $G$ and these criterion ensures other group axioms for $H$.

Conversely, suppose $(H, \ast)$ is a group.
Firstly, let $e_H$ be the identity element in $H$, we have $e_H \ast e_H = e_H$ in $H$, so as in $G$.
Thus $e_H = e_H \ast e = e_H \ast (e_H \ast e_H^{-1}) = (e_H \ast e_H) \ast e_H^{-1} = e_H \ast e_H^{-1} = e$.
Hence, the identity of $H$ has to be the same as $G$, (i) is true.
Secondary, (ii) is true as $H$ has to be closed.
Finally, as inverse is unique, the inverse of $a$ in $H$ has to be the same as that in $G$.

The first criteria can be omitted if we know $H$ is non-empty subset.
As if $H$ is non-empty, there is some element $a \in H$ and by (iii) then (ii), $a \ast a^{-1} = e \in H$.

### Super-efficient subgroup criterion

Let $(G, \ast)$ be a group and let $H \subseteq G$ be a subset. Then $H \le G$ if and only if

(i) H is non-empty
(ii) Given $a, b \in H$, also $a \ast b^{-1} \in H$

_[Proof]_ Similar to the above, $H$ is non-empty implies $e \in H$ (identity).
For all $b \in H$, by (ii) and setting $a = e$, we have $e \ast b^{-1} = b^{-1} \in H$ (inverse).
For all $a, b \in H$, we have $b^{-1} \in H$, therefore by (ii), $a \ast (b^{-1})^{-1} = a \ast b \in H$ (closed).

### Examples

* $(\mathbb{Z}, +) \le (\mathbb{Q}, +) \le (\mathbb{R}, +) \le (\mathbb{C}, +)$
* $(\set{e}, \ast) \le (G, \ast)$ (trivial subgroup)
* For $n \in \mathbb{Z}$, ($n\mathbb{Z}, +) \le (\mathbb{Z}, +)$

## Cosets

Let $H$ be a subgroup of $G$, i.e. $H \le G$. Given an element $a \in G$, the set

$$
aH = \set{ah : h \in H}
$$

is a _left coset_ of $H$. Similarily,

$$
Ha = \set{ha : h \in H}
$$

is a _right coset_ of $H$. (Note: coset is not necessary a group)

### Properties

Given $H \le G$ and $a \in G$. $a \in H$ if and only if $aH = H$.

_[Proof]_ If $aH = H$, as $e \in H$, $ae = a \in H$.

If $a \in H$, for any $h \in H$, $ah \in H$ (closure), so $aH \subseteq H$.

We also have $a^{-1} \in H$, for any $h \in H$, $a^{-1}h \in H$ (closure), $a(a^{-1}h) = h \in aH$, so $H \subseteq aH$.

Hence, $a \in H \iff aH = H$.

Given $H \le G$ and $a, b \in G$, $aH$ and $bH$ is either the same or disjoint.

_[Proof]_ Assume they are not disjoint, that means for some $h_1 \in H$, $ah_1 \in bH$.
Suppose $ah_1 = bh_2 \in bH$, we have $a = bh_2h_1^{-1}$.
Thus, for any $h \in H$, $ah = bh_2h_1^{-1}h \in bH$, so $aH \subseteq bH$.
Similarily, $b = ah_1h_2^{-1}$, $bH \subseteq aH$.
Hence, $aH$ and $bH$ are either the same or disjoint.

$aG = bG$ if and only if $b^{-1}a \in H$.

_[Proof]_

If $b^{-1}a \in H$, $(ba^{-1})^{-1} = a^{-1}b \in H$ as well.
For any $h \in H$, $ah = (bb^{-1})ah = b(b^{-1}ah) \in bH$, similarily $bh = (a(a^{-1})bh = a(a^{-1}bh) \in aH$. Hence, $aH = bH$.

If $aH = bH$, say $ah_1 = bh_2$ for some $h_1, h_2 \in H$, $b^{-1}a = h_2h_1^{-1} \in H$ (closure).

All the left cosets of $H$ are of same size as $H$.

_[Proof]_ Let $aH$ be a left coset of $H$, if $ah_1 = ah_2$, $h_1 = h_2$, hence each $ah$ maps to a different element and $\|aH\| = \|H\|$.

Given $H \le G$, $G$ is the union of all the left cosets of $H$.

_[Proof]_ For any $a \in G$, as $e \in H$, $a \in aH$. Hence, the union of all of the left cosets is $G$.

All the above properties is applicable to the right cosets.

### Coset as equivalence classes

Let $H \le G$, defining $a \sim b$ if $b^{-1}a \in H$ gives an equivalence relation on $G$, whose equivalence classes are the left cosets of $H$.

_[Proof]_ The conditions for equivalence relation

* [Reflexive] $a \sim a$ as $a^{-1}a = e \in H$

* [Symmetric] $a \sim b \implies b \sim a$ as $(b^{-1}a)^{-1} = a^{-1}b \in H$

* [Transitive] $a \sim b$ and $b \sim c \implies a \sim c$ as $(c^{-1}b)(b^{-1}a) = c^{-1}a \in H$.

## Lagrange's Theorem

If $G$ is a finite group and $H \le G$, then $\|H\|$ divides $\|G\|$.

_[Proof]_ Base on the above facts about left cosets, the group $G$ is partitioned by the distinct cosets into disjoint sets with respect to $H$, which is called _coset decomposition_.
Hence, $\|G\| = \text{number of distinct cosets} \times \|H\|$

Lagrange's Theorem shows that the order of $G$ influences the number of subgroups $G$ can have, regardless of the group structure.

### Index

The _index_ of $H$ in $G$, denoted by $\|G:H\|$, is the number of distinct cosets of $H$ in $G$.

Hence,

$$
|G| = |G:H||H|
$$

## Lagrange Corollaries

### Order of element

Suppose $G$ is a finite group, for $a \in G$, $\text{ord}(a)$ divides $\|G\|$.

_[Proof]_ Consider the subgroup $\|H\|$ generated by $a$, by Lagrange's Theorem, $\text{ord}(a) = \|H\|$ divides $\|G\|$.

### Exponent of group

Suppose $G$ is a finite group, for $a \in G$, $a^{\|G\|} = e$.

_[Proof]_ We have $\|G\| = k \cdot \text{ord}(a)$, hence $a^{\|G\|} = (a^{\text{ord}(a)})^k = e$.

The _exponent_ of $G$ is the smallest number $m$ such that $a^m = e$ for all $a \in G$.
Thus, $m$ is the least common multiple of all the orders of elements, which are divisors of $\|G\|$, so $m$ divides $\|G\|$.

### Group of prime order

Suppose $G$ is a finite group of order $p$, where $p$ is prime. Then $G$ is cyclic and the only subgroups are $\set{e}$ and $G$.

_[Proof]_ For $H \le G$, by Lagrange's Theorem, $\|H\|$ divides $\|G\| = p$, hence $\|H\| = 1$ or $p$.
When $\|H\| = 1$, $H = \set{e}$. When $\|H\| = p$, $H = G$ and for any $a \in G$, $\text{ord}(a) = p$ and generates $G$.

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 12
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 3](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
