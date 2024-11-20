---
layout: base
title: Permutations &#124; Groups
---

# Permutations

## Definition

A _permutation_ of $X$ is an invertible/bijective map $f: X \to X$.

## Two row notation

For finite set $X = \set{1, 2, ..., n}$, it is convenient to write out the permutation $\sigma$ in two rows,
$1, 2, ..., n$ on the top and corresponding images below, i.e.

$$
\sigma = \begin{pmatrix}
1 & 2 & \cdots & n \\
\sigma(1) & \sigma(2) & \cdots & \sigma(n) \\
\end{pmatrix}
$$

Composition can be done by reordering the next permutation, e.g.

$$
\begin{pmatrix}
1 & 2 & 3 \\
2 & 3 & 1
\end{pmatrix} \circ
\begin{pmatrix}
1 & 2 & 3 \\
2 & 1 & 3
\end{pmatrix} =
\begin{pmatrix}
2 & 1 & 3 \\
3 & 2 & 1
\end{pmatrix} \circ
\begin{pmatrix}
1 & 2 & 3 \\
2 & 1 & 3
\end{pmatrix} =
\begin{pmatrix}
1 & 2 & 3 \\
3 & 2 & 1
\end{pmatrix}
$$

## Cycle notation

## Sign of permutation

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Section 1.3, 1.4
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 2](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
