---
layout: base
title: Symmetric Groups &#124; Groups
---

# Symmetric Groups

## Definition

The set of all [permutations](permutations.md) of $X$ is denoted by $\text{Sym} X$ or $\mathbb{P}(X)$.

$\text{Sym} X$ with composition forms a group.

_[Proof]_

## Properties

If $X$ is finite, say $\|X\| = n$, we usually write $X = \set{1, 2, ..., n}$ and $\text{Sym} X = S_n$,
and the _degree_ of the symmetric group is $n$.

The order of $S_n$, denoted by $\|S_n\|$ is $n!$.

$S_n$ can be viewed as subgroup of $S_m$ with $n \le m$, by fixing $n+1, n+2, ..., m$.

## sgn as homomorphism

We have $\text{sgn}: S_n \to \set{\pm 1}$ being a homomorphism as

$$
\text{sgn}(\sigma_1\sigma_2) = (-1)^{k_1 + k_2} = (-1)^{k_1}(-1)^{k_2} = \text{sgn}(\sigma_1)\text{sgn}(\sigma_2)
$$

It is surjective as we always have $\text{sgn}(e) = 1$ and $\text{sgn}((1\;2)) = -1$.

We can see that product of even permutations is even, and inverse is also even,
hence all even permutations form a subgroup, which is called the _alternating group_ $A_n$.

We also have

$$
\ker \text{sgn} = A_n
$$

## Subgroup of $S_n$

Any subgroup of $S_n$ contains either no odd permutations, or exactly half.

_[Proof]_ Let $G \le S_n$ and $a_1, a_2, ..., a_n$ be the even elements in $G$.

It is a subgroup of $A_n$ if there are no odd elements.

If there is an odd element $g \in G$, then the elements $ga_1, ga_2, ga_3, ..., ga_n$ are all odd.
Also, if $ga_i = ga_j$ for some $i, j$, $g^{-1}(ga_i) = g^{-1}(ga_j)$ and $a_i = a_j$. Thus, they are all distinct.
Hence, $G$ has either no odd elements, or exactly half of them are odd.

## Examples

### Symmetric group of degree 3 ($S_3$)

$$
S_3 = \set{e, (1\,2\,3) = r, (1\,3\,2) = r^2, (2\,3) = s, (1\,2) = rs, (1\,3) = r^2s }
$$

From the above, we can see $S_3 \cong D_6$.

There are 6 subgroups

$$
\begin{gather*}
\set{e} \\
\set{e, s} \quad \set{e, rs} \quad \set{e, r^2s} \\
\set{e, r, r^2} \\
\set{e, r, r^2, s, rs, r^2s}
\end{gather*}
$$

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Section 1.3, 1.4
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 2](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
