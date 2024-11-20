---
layout: base
title: Symmetric Groups &#124; Groups
---

# Symmetric Groups

## Definition

The set of all [permutations](permutations.md) of $X$ is denoted by $\text{Sym} X$ or $\mathbb{P}(X)$.

$\text{Sym} X$ with composition forms a group.

_[Proof]_

If $X$ is finite, say $\|X\| = n$, we usually write $X = \set{1, 2, ..., n}$ and $\text{Sym} X = S_n$,
and the _degree_ of the symmetric group is $n$.

The order of $S_n$, denoted by $\|S_n\|$ is $n!$.

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
