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
> The **complement** is defined by
>
> $$
  A^\mathsf{c} = \set{x : x \not \in A}
  $$

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
> The **power set** of $X$ is defined by
>
> $$
  \mathcal{P}(X) = \set{A : A \subseteq X}
  $$
>
> i.e. the set of all subsets.

## Identities

> *Theorem.*{: .thm}
> _Distributive Laws_
>
> $$
  \begin{align*}
  A \cup (B \cap C) &= (A \cup B) \cap (A \cup C) \\
  A \cap (B \cup C) &= (A \cap B) \cup (A \cap C)
  \end{align*}
  $$

> *Theorem.*{: .thm}
> _De Morgan's Laws_
>
> $$
  \begin{align*}
  (A \cup B)^\mathsf{c} &= A^\mathsf{c} \cap B^\mathsf{c} \\
  (A \cap B)^\mathsf{c} &= A^\mathsf{c} \cup B^\mathsf{c}
  \end{align*}
  $$

> *Theorem.*{: .thm}
> _Absorption Laws_
>
> $$
  \begin{align*}
  A \cup (A \cap B) = A \\
  A \cap (A \cup B) = A
  \end{align*}
  $$

> *Theorem.*{: .thm}
> _Set Difference Law_
>
> $$
  A \setminus B = A \cap B^\mathsf{c}
  $$

## Symmetric Difference

> *Definition.*{: .def}
> The **symmetric difference** is defined by
>
> $$
  A \Delta B = \set{x : x \in A \text{ xor } x \in B}
  $$
>
> i.e. the element is either in $A$ or $B$ but not both.

> *Theorem.*{: .thm}
> Alternatively, we have
>
> $$
  \begin{align*}
  A \Delta B &= (A \setminus B) \cup (B \setminus A) = (A \cap B^\mathsf{c}) \cup (A^\mathsf{c} \cap B) \\
             &= (A \cup B) \cap (A^\mathsf{c} \cup B^\mathsf{c})
  \end{align*}
  $$

> *Theorem.*{: .thm}
> Symmetric difference is associative, i.e. $A \Delta (B \Delta C) = (A \Delta B) \Delta C$.
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  A \Delta (B \Delta C) &= (A \cap ((B \cup C) \cap (B^\mathsf{c} \cup C^\mathsf{c}))^\mathsf{c}) \cup (A^\mathsf{c} \cap ((B \cap C^\mathsf{c}) \cup (B^\mathsf{c} \cap C))) \\
  &= (A \cap B \cap C) \cup (A \cap B^\mathsf{c} \cap C^\mathsf{c}) \cup (A^\mathsf{c} \cap B \cap C^\mathsf{c}) \cup (A^\mathsf{c} \cap B^\mathsf{c} \cap C) \\
  &= (((A \cup B) \cap (A^\mathsf{c} \cup B^\mathsf{c}))^\mathsf{c} \cap C) \cup (((A \cap B^\mathsf{c}) \cup (A^\mathsf{c} \cap B)) \cap C^\mathsf{c}) \\
  &= (A \Delta B) \Delta C
  \end{align*}
  $$

All sets form a [group](../groups/groups.md) under symmetric difference.

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

## Counting

> *Definition.*{: .def}
> Let $X$ be a set. For each $A \subseteq X$, the **indicator function** or **characteristic function** of $A$ is the function
> $i_A : X \to \set{0, 1}$ such that
>
> $$
  i_A(x) = \begin{cases}
  1 & \text{if } x \in A \\
  0 & \text{otherwise}
  \end{cases}
  $$
>
> Therefore, we also have $\vert A \vert = \sum_{x \in X} i_A(x)$.

> *Lemma.*{: .lem}
> Let $A$ and $B$ be two sets, we have
>
> + $i_A = i_B \iff A = B$
>
> + $i_{A \cap B} = i_A i_B$
>
> + $i_{A^\mathsf{c}} = 1 - i_A$
>
> + $i_{A \cup B} = 1 - i_{A^\mathsf{c} \cap B^\mathsf{c}} = 1 - (1 - i_A)(1 - i_B) = i_A + i_B - i_{A \cap B}$
>
> + $i_{A \setminus B} = i_{A \cap B^\mathsf{c}} = i_A(1 - i_B) = i_A - i_{A \cap B}$

> *Theorem.*{: .thm}
> $\vert A \cup B \vert = \vert A \vert + \vert B \vert - \vert A \cap B \vert$
>
> *Proof.*{: .prf}
>
> $$
  \begin{align*}
  \vert A \cup B \vert &= \sum_{x \in X} i_{A \cup B}(x) \\
  &= \sum_{x \in X} i_A(x) + i_B(x) - i_{A \cap B}(x) \\
  &= \vert A \vert + \vert B \vert - \vert A \cap B \vert
  \end{align*}
  $$

> *Theorem.*{: .thm}
> **[Inclusion-Exclusion Principle]**
> Let $A_i$ be the subsets of a finite set $X$, for $1 \le i \le n$. Then
>
> $$
  \vert A_1 \cup \cdots \cup A_n \vert = \sum_i \vert A_i \vert - \sum_{i < j} \vert A_i \cap A_j \vert + \cdots + (-1)^{n-1} \vert A_1 \cap \cdots \cap A_n \vert
  $$
>
> or
>
> $$
  \vert A_1^\mathsf{c} \cap \cdots \cap A_n^\mathsf{c} \vert = \vert X \vert - \sum_i \vert A_i \vert + \sum_{i < j} \vert A_i \cap A_j \vert + \cdots + (-1)^{n} \vert A_1 \cap \cdots \cap A_n \vert
  $$
>
> since $\vert A_1 \cup \cdots \cup A_n \vert = \vert X \vert - \vert A_1^\mathsf{c} \cap \cdots \cap A_n^\mathsf{c} \vert$.
>
> *Proof.*{: .prf}
>
> Using the indicator functions,
>
> $$
  \begin{align*}
  i_{A_1^\mathsf{c} \cap \cdots \cap A_n^\mathsf{c}} &= \prod_j i_{A_j^\mathsf{c}} \\
  &= \prod_j (1 - i_{A_j}) \\
  &= 1 - \sum_i i_{A_i} + \sum_{i < j} i_{A_i}i_{A_j} + \cdots + (-1)^n i_{A_1}i_{A_2}...i_{A_n} \\
  &= 1 - \sum_i i_{A_i} + \sum_{i < j} i_{A_i \cap A_j} + \cdots + (-1)^n i_{A_1 \cap \cdots \cap A_n}
  \end{align*}
  $$
>
> Hence,
>
> $$
  \begin{align*}
  \vert A_1^\mathsf{c} \cap \cdots \cap A_n^\mathsf{c} \vert &=
  \sum_{x \in X} i_{A_1^\mathsf{c} \cap \cdots \cap A_n^\mathsf{c}}(x) \\
  &= \sum_x 1 - \sum_i i_{A_i} + \sum_{i < j} \sum_x i_{A_i \cap A_j}(x) + \cdots + (-1)^n \sum_x i_{A_1 \cap \cdots \cap A_n}(x) \\
  &= \vert X \vert - \sum_i \vert A_i \vert + \sum_{i < j} \vert A_i \cap A_j \vert + \cdots + (-1)^{n} \vert A_1 \cap \cdots \cap A_n \vert
  \end{align*}
  $$

## References

* [Dexter Chua _Part IA - Numbers and Sets_, 2014 - Chapter 2, 3](https://dec41.user.srcf.net/notes/IA_M/numbers_and_sets.pdf)
