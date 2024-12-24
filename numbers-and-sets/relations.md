---
layout: base
title: Relations &#124; Numbers and Sets
---

# Relations
{: .page-title}

> *Definition.*{: .def}
> A **relation** $R$ on $X$ specifies some kind of relationship between two elements in the set.
> Formally, a relation is a subset $R \subseteq X \times X$.
> We write $xRy$ iff $(x, y) \in R$.

> *Definition.*{: .def}
> A relation is **reflexive** if
>
> $$
  (\forall x)\, xRx
  $$

> *Definition.*{: .def}
> A relation is **symmetric** if
>
> $$
  (\forall x, y)\, xRy \iff yRx
  $$

> *Definition.*{: .def}
> A relation is **transitive** if
>
> $$
  (\forall x, y, z)\, xRy \land yRz \implies xRz
  $$

## Equivalence Relation

> *Definition.*{: .def}
> An **equivalence relation** is a relation that is reflexive, symmetric and transitive.

> *Definition.*{: .def}
> Let $\sim$ be an equivalence relation on $X$.
> The **equivalence class**, denoted by $[x]$, is the set of all elements that are related to $x$ by $\sim$.

> *Lemma.*{: .lem}
> Any two equivalence classes are either the same or disjoint, i.e. if $x \sim y$, then $[x] = [y]$.
>
> *Proof.*{: .prf}
>
> Let $\sim$ be an equivalence relation with $x \sim y$ and $y \sim x$ (symmetric).
> For any $x' \in [x]$, $x' \sim x \land x \sim y \implies x' \sim y$ (transitive), so $x' \in [y]$ and $[x] \subseteq [y]$.
> For any $y' \in [y]$, $y' \sim y \land y \sim x \implies y' \sim x$ (transitive), so $y' \in [x]$ and $[y] \subseteq [x]$.
> Hence, $[x]$ and $[y]$ can only overlap if they coincide, otherwise they are disjoint.

> *Definition.*{: .def}
> A **partition** of a set $X$ is a decomposition of the set into non-empty subsets,
> no two of which overlaps and whose union is all of $X$.

> *Theorem.*{: .thm}
> The distinct equivalence classes of an equivalence relation on $X$ form a partition of $X$.
>
> *Proof.*{: .prf}
>
> Each equivalence class is non-empty because $[x]$ contains $x$ (reflexive).
> Also, $[x]$ and $[y]$ are either the same or disjoint.
> Furthermore, every $x \in X$ is in its own equivalence class $[x]$, so the union includes all of $X$.
> Hence, by definition, they form a partition of $X$.
{: #equivalence-classes-form-partition}

> *Definition.*{: .def}
> The **quotient map** maps each element in $X$ to the equivalence class containing $x$, i.e. $x \mapsto [x]$.

## References

* M.A. Armstrong _Groups and Symmetry_, 1988 - Chapter 12
* [Dexter Chua _Part IA - Numbers and Sets_, 2014 - Chapter 2](https://dec41.user.srcf.net/notes/IA_M/numbers_and_sets.pdf)
