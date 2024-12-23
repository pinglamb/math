---
layout: base
title: Sets &#124; Numbers and Sets
---

# Sets
{: .page-title}

> *Definition.*{: .def}
> A **set** is a collection of different things, without regards to order.
> Same elements in a set are only counted once.
> It is denoted by
>
> $$
  X = \set{a, b, c}
  $$
>
> and we write $x \in X$ if $x$ is a member of the set $X$.

> *Definition.*{: .def}
> Two sets $A, B$ are equal, denoted by $A = B$, if they have the same elements, i.e.
>
> $$
  (\forall x)\, x \in A \iff x \in B
  $$

> *Definition.*{: .def}
> $A$ is a subset of $B$, denoted by $A \subset B$, if all elements in $A$ are in $B$, i.e.
>
> $$
  (\forall x)\, x \in A \implies x \in B
  $$

> *Theorem.*{: .thm}
> $A = B$ iff $A \subseteq B$ and $B \subseteq A$.

It is commonly used for proving two sets are equal, by showing all elements in $A$ are in $B$ and vice verse.

## Operations

Given two sets $A$ and $B$,

> *Definition.*{: .def}
> The **intersection** is defined by
>
> $$
  A \cap B = \set{x : x \in A \text{ and } x \in B}
  $$

> *Definition.*{: .def}
> The **union** is defined by
>
> $$
  A \cup B = \set{x : x \in A \text{ or } x \in B}
  $$

> *Definition.*{: .def}
> The **difference** is defined by
>
> $$
  A \setminus B = \set{x : x \in A \text{ and } x \not \in B}
  $$

> *Definition.*{: .def}
> The **symmetric difference** is defined by
>
> $$
  A \Delta B = \set{x : x \in A \text{ xor } x \in B}
  $$
>
> i.e. the element is either in $A$ or $B$ but not both.

All sets form a [group](../groups/groups.md) under symmetric difference.

> *Definition.*{: .def}
> The **power set** of $X$ is defined by
>
> $$
  \mathcal{P}(X) = \set{A : A \subseteq X}
  $$
>
> i.e. the set of all subsets.

## Ordered Pairs

> *Definition.*{: .def}
> An **ordered pair** $(a, b)$ is a pair of two items in which order matters. In terms of sets,
>
> $$
  (a, b) = \set{\set{a}, \set{a, b}}
  $$

> *Definition.*{: .def}
> The **Cartesian product** of $A$ and $B$ is defined by
>
> $$
  A \times B = \set{(a, b) : a \in A, b \in B}
  $$
>
> which can be extend to $n$ products.

## References

* [Dexter Chua _Part IA - Numbers and Sets_, 2014 - Chapter 2](https://dec41.user.srcf.net/notes/IA_M/numbers_and_sets.pdf)
