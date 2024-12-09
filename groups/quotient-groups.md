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

> *Lemma.*{: .lem}
> $K \trianglelefteq G \iff \forall a \in G, aKa^{-1} = K$.
>
> *Proof.*{: .prf}
>
> ($\Leftarrow$) If for all $a \in G$, $aKa^{-1} = K$,
> then for all $k \in K$, $aka^{-1} = k'$ for some $k' \in K$. By definition, $K \trianglelefteq G$.
>
> ($\Rightarrow$) If $K \trianglelefteq G$, for all $a \in G$ and $k \in K$, $aka^{-1} \in K$,
> we have $aka^{-1} \in K$ so $aKa^{-1} \subseteq K$.
> Also, we have $a^{-1}ka \in K$, so $a(a^{-1}ka)a^{-1} = k \in aKa^{-1}$ and $K \subseteq aKa^{-1}$.
> Hence, $aKa^{-1} = K$.

> *Theorem.*{: .thm}
> Any subgroup of index $2$ is normal.
>
> *Proof.*{: .prf}
>
> If $K \le G$ is of index $2$, the only possible cosets are $K$ and $G \setminus K$ because $eK$/$Ke$ is one of the cosets and cosets are disjoint.
> As $eK = Ke$, the other right coset is also $G \setminus K$. So the left cosets and right cosets of $K$ are the same and $K \trianglelefteq G$.

> *Theorem.*{: .thm}
> Any subgroup of an abelian group is normal.
>
> *Proof.*{: .prf}
>
> For a subgroup $K \le G$, for all $a \in G$ and $k \in K$, $aka^{-1} = aa^{-1}k = k \in K$.
> Also, as $K$ is abelian, obviously $aK = Ka$ for all $a \in G$.

> *Theorem.*{: .thm}
> Every kernel is a normal subgroup.
>
> *Proof.*{: .prf}
>
> Let $f: G \to H$ be a homomorphism, $K = \ker f$ are the elements $k \in G$ such that $f(k) = e_H$.
> Therefore, for all $a \in G$, $f(aka^{-1}) = f(a)f(k)f(a^{-1}) = f(a)f(a)^{-1} = e_H$, so $aka^{-1} \in K$ and $\ker f \trianglelefteq G$.

## Quotients

The left cosets of normal subgroups form a group in a natural way.

> *Definition.*{: .def}
> If $X$ and $Y$ are subsets of $G$, the product $XY$ of them is the set of all products $xy$ where $x \in X$ and $y \in Y$.

> *Lemma.*{: .lem}
> The product of two left cosets of a normal subgroup is again a left coset, i.e.
>
> $$
  (xK)(yK) = xyK
  $$
>
> *Proof.*{: .prf}
>
> Each element of $(xK)(yK)$ has the form $xkyk'$ for some $k, k' \in K$. Rewrite this as
>
> $$
  xy(y^{-1}ky)k'
  $$
>
> As $K$ is a normal subgroup, by definition, $y^{-1}ky = k'' \in K$. Hence,
>
> $$
  xkyk' = xy(y^{-1}ky)k' = xy(k''k')
  $$
>
> and therefore $(xK)(yK) \subseteq xyK$.
>
> Conversely, for any $xyk \in xyK$, $xyk = (xe)(yk) \in (xK)(yK)$. Hence, $xyK \subseteq (xK)(yK)$.

> *Theorem.*{: .thm}
> If $K$ is a normal subgroup of $G$, the set of all left cosets of $K$ in $G$ forms a group under multiplication.
>
> *Proof.*{: .prf}
>
> The above lemma shows that the multiplication of left cosets is closed.
> $(eK)(aK) = aK$ is the identity element.
> $(a^{-1}K)(aK) = eK$ so $a^{-1}K$ is the inverse of $aK$.
> Associativity is inherited from associativity in $G$.
> Hence, it is a group.

> *Definition.*{: .def}
> The **quotient group** (of factor group) of $G$ by $K$ is the group of left cosets of $K$ under multiplication, denoted by $G/K$.

## Isomorphism Theorem

The isomorphism theorem is about the relationship between normal subgroups, homomorphisms and quotients.

![Isomorphism Theorem](../images/isomorphism-theorem.png)

## References

* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 5](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
