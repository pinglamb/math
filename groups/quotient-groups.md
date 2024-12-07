---
layout: base
title: Quotient Groups &#124; Groups
---

# Quotient Groups
{: .page-title}

The theory about quotient groups is one of the most important idea about groups.

## Normal Subgroups

> *Definition.*{: .def}
> A subgroup $K$ of $G$ is a **normal** subgroup if for all $a \in G$ and for all $k \in K$, we have $aka^{-1} \in K$.
> It is denoted by $K \trianglelefteq G$.

> *Lemma.*{: .lem}
> $K \trianglelefteq G \iff \forall a \in G, aK = Ka$.
>
> *Proof.*{: .prf}
>
> ($\Leftarrow$) If the left cosets of $K$ are equal to its right cosets,
> for all $a \in G$ and some $k, k' \in K$, we have
>
> $$
  \begin{align*}
  ak &= k'a \\
  aka^{-1} &= k'
  \end{align*}
  $$
>
> so $aka^{-1} \in K$ and $K \trianglelefteq G$.
>
> ($\Rightarrow$) If $K \trianglelefteq G$, for all $a \in G$ and $k \in K$, $aka^{-1} \in K$,
> we have $aka^{-1} = k'$ for some $k' \in K$ so $ak = k'a$ and $aK \subseteq Ka$.
> Also, we have $a^{-1}k(a^{-1})^{-1} = a^{-1}ka = k'$ for some $k' \in K$, so $ka = ak'$ and $Ka \subseteq aK$.
> Hence, $aK = Ka$.

## References

* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 5](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
