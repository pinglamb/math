---
layout: base
title: Cyclic Groups &#124; Groups
---

# Cyclic Groups

## Definition

A group $G$ is _cyclic_ if there is an element $g \in G$ such that all elements of $G$ are powers of $g$.
Such an element is called a _generator_.

$$
G = \set{g^n : n \in \mathbb{Z}}
$$

## Cyclic subgroup

For a group $G$ and $a \in G$, the cyclic subgroup generated by $a$, denoted by $\left<a\right>$,
is defined to be the smallest subgroup containing $a$.
It is in fact the set of all powers of $a$.

_[Proof]_ For the set of all powers of $a$, $a^0 = e$ is a power of $a$, so it is non-empty.
Given $a^m$ and $a^n$, $(a^m)(a^n)^{-1} = a^{m-n}$ is a power of $a$. So, the powers of $a$ is a subgroup of $G$.

If $a$ is in any subgroup, the inverse $a^{-1}$ is in the subgroup, and hence $a^n$ is in the subgroup as well by closure.
As the powers of $a$ is already a subgroup from the above, it is the smallest one containing $a$, i.e. is in fact $\left<a\right>$.

### Additive group R

The additive group $\mathbb{R}$ is not cyclic. A subgroup of $(\mathbb{R}, +)$ is cyclic if and only if it has a smallest positive element $h$, in which is the generator.

_[Proof]_ Let $H$ be a cyclic group, say $H = \set{nh : n \in \mathbb{Z}}$, then $\|h\|$ is the smallest positive element.

If $H$ has a smallest positive element $h$, then by closure, $nh \in H$ for $n \in \mathbb{Z}$.
For an element $a = nh + r \in H$, where $0 \le r < h$. As $-nh \in H$, we have $a - nh = r \in H$, but $h$ is the smmalest positive element in $H$ so $r = 0$.
Hence, $H = \set{nh : n \in \mathbb{Z}}$.

## Order of an element

For $a \in G$, $\text{ord}(a) = \|\left<a\right>\|$.

_[Proof]_ If $\text{ord}(a) = \infty$, then $a^n \not= e$ for any $n$ and $a^m \not = a^n$ for all $m \not = n$, hence $\left<a\right>$ has infinite order.

If $\text{ord}(a) = n$, then $\left<a\right> = \set{a^0 = e, a, a^1, ..., a^{n-1}}$, as $a^n = e$, $a^{n+1} = a$, and so on, also $a^{-1} = a^{n-1}$ etc.
So $\|\left<a\right>\| = n$.

## Isomorphism

Any two cyclic groups of the same finite order $n$ are isomorphic, and hence isomorphic to $(\mathbb{Z}_n, +)$.

_[Proof]_ Let $G$ be a cyclic group of order $n$ and $g \in G$ be the generator.
Consider the map $f: \mathbb{Z}_n \to G$ defined by $f(n) = g^n$.

$$
f(m + n) = g^{m+n} = (g^m)(g^n) = f(m)f(n)
$$

so $f$ is a homomorphism. As $G = \set{g^0, g^1, g^2, ..., g^{n-1}}$, $f$ is surjective. As $\|G\| = \|\mathbb{Z}_n\| = n$, surjectivity implies injectivity.
Hence, $f$ is a isomorphism and $G$ is isomorphic to $\mathbb{Z}_n$, and therefore to each other.

Any two infinite cyclic groups are isomorphic, and hence isomorphic to $(\mathbb{Z}, +)$

_[Proof]_ Let $G$ be an infinite cyclic group generated by $g \in G$.
Consider the map $f: \mathbb{Z} \to G$ defined by $f(n) = g^n$. Similarily,

$$
f(m + n) = g^{m+n} = (g^m)(g^n) = f(m)f(n)
$$

so $f$ is a homomorphism. $f$ is surjective by definition. If $f(m) = f(n)$, then $g^m = g^n$, which implies $m = n$, otherwise $g^{m-n}=e$ and $G$ would be finite.
Hence, $f$ is a isomorphism and $G$ is isomorphic to $(\mathbb{Z}, +)$.

So to conclude, there is only one cyclic group of order $n$, and is usually denoted by $C_n$.

## Cyclic groups are abelian

All cyclic groups are abelian.

_[Proof]_ Let $G$ be a cyclic group and $g \in G$ generates $G$.
For any two elements $a = g^m$ and $b = g^n$, we have

$$
ab = (g^m)(g^n) = g^{m+n} = g^{n+m} = (g^n)(g^m) = ba
$$

Hence, $G$ is abelian.

In short, as $C_n \cong \mathbb{Z}_n$, $C_n$ shares the commutativity with additive group $\mathbb{Z}_n$.

## Subgroups of cyclic group

A subgroup of cyclic group is cyclic.

_[Proof]_ Let $G$ be a cyclic group and $H \le G$ and $g \in G$ be the generator.
Therefore, $g^n \in H$ for some $n$. Let $d$ be the smallest positive integer such that $g^d \in H$,
by closure $g^{md} \in H$ for $m \in \mathbb{Z}$.
For an element $g^{md + r} \in H$, where $0 \le r < d$. As $g^{-md} \in H$, $g^r \in H$, which is only possible when $r = 0$.
Hence, $H = \set{g^{md} : m \in \mathbb{Z}}$ is cyclic.

## Prime order cyclic group

**A group of prime order is cyclic**, and is generated by any of its elements other than the identity element.

_[Proof]_ Let $G$ be a group with order $p$ where $p$ is prime.
For any $g \in G$, by Lagrange Theorem, $\text{ord}(g) \mid p$.
If $\text{ord}(g) = 1$, $g = e$. Otherwise, $\text{ord}(g) = p$ and generates $G$.
Hence, $G$ is cyclic and is generated by any elements other than $e$.

## Product of cyclic groups

$C_m \times C_n \cong C_{mn}$ if and only if $m$ and $n$ are relatively prime.

_[Proof]_ Let $C_m$ be generated by $a$ and $C_n$ is generated by $b$.
We have $(a, b)^k = (a^k, b^k) = e$ if and only if $a^k = e$ and $b^k = e$.
If $m$ and $n$ are relatively prime, it happens for the first time when $k = mn$.
Hence, the order of $(a, b)$ is $mn$ and generates $C_{mn}$

If $(m, n) = d$, for $k = mn/d$, $(a, b)^k = (e, e) = e$ for all element $(a, b)$.
So, there is no element of order $mn$ and $C_m \times C_n \not \cong C_{mn}$.

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Section 12.5
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 1](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)