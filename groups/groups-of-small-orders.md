---
layout: base
title: Groups of Small Orders &#124; Groups
---

# Groups of Small Orders
{: .page-title}

We have developed lots of theories about groups.
We can see them in practice in the study of groups of small orders.

## Useful Lemmas

> *Lemma.*{: .lem}
> Let $G$ be a finite group in which every element except the identity has order $2$.
> Then $G$ is abelian, and has order $2^m$ for some integer $m$.
>
> *Proof.*{: .prf}
>
> For any $g, h \in G$, $gh \in G$ is also of order $2$, therefore $gh = (gh)^{-1} = h^{-1}g^{-1} = hg$ and $G$ is abelian.
>
> Let $H = \set{g_1, g_2, ..., g_m}$ be the minimal generating set for $G$, which means $H$ generates $G$ and no proper subset of $H$ can do so.
> Hence, every $g \in G$ is a power of elements in $H$, as $G$ is abelian, we have
>
> $$
  g = g_1^{p_1}g_2^{p_2}...{g_m}^{p_m}
  $$
>
> Suppose $g = g_1^{p_1}g_2^{p_2}...{g_m}^{p_m} = g_1^{q_1}g_2^{q_2}...{g_m}^{q_m}$ where $p_i$ and $q_i$ can only be $0$ or $1$.
> If $p_i \not = q_i$, we have $g_i = g_1^{r_1}g_2^{r_2}...g_{i-1}^{r_{i-1}}g_{i+1}^{r_{i+1}}...g_m^{r_m}$ which contradicts with the fact that $H$ is the minimal generating set.
> So the expression is unique and every combination of $p_1, p_2, ..., p_m$ is a distinct element in $G$.

> *Lemma.*{: .lem}
> Let $G$ be a group of even order. Then $G$ contains an element of order $2$.
>
> *Proof.*{: .prf}
>
> Suppose $G$ has $2n$ elements.
> By pairing every element in $G$ with its inverse, we will have at least 2 sets having only one element, one of which is $\set{e}$.
> The element in another set will have order $2$.

## Groups of order 3

> *Theorem.*{: .thm}
> Every group of order $3$ is cyclic.
>
> *Proof.*{: .prf}
>
> Every group of prime order is cyclic. But we will analyze it from first principles.
>
> Let $G = \set{e, x, y}$ be a group of order $3$.
> We have $yx \not = x$ and $yx \not = y$ so $yx = e$.
> By Langrange's Corollary, $x^3 = e$, so $y = yx^3 = x^2$.
> Hence, $G = \set{e, x, x^2}$ is a cyclic group.

## Groups of order 4

## Groups of order 6

> *Theorem.*{: .thm}
> Every group of order $6$ is either or dihedral.
>
> *Proof.*{: .prf}
>
> By Lagrange, the order of every element is either $1, 2, 3$ or $6$.
> If there is an element of order $6$, then $G \cong C_6$.
>
> If there is no element of order $6$, elements other than identity can only have orders $2$ or $3$.
> There must be an element $y$ of order $3$, otherwise every element is of order $2$ and the order of group has to be powers of $2$.
> $\langle y \rangle$ is a normal subgroup as it has index $2$.
> Also, there must be an element $x$ of order $2$ as the order of $G$ is even.
> Therefore, we have $xyx^{-1} \in \langle y \rangle$ and
>
> + $xyx^{-1} = e$, $y = e$ which is not possible, or
>
> + $xyx^{-1} = y$, $xy = yx$ so $(xy)^m$ = $x^my^m$ and $xy$ is of order $6$ (can't be $2$ or $3$) and $G \cong C_6$, or
>
> + $xyx^{-1} = y^2 = y^{-1}$, so $xy = y^{-1}x$, together with $x^2 = y^3 = e$, $G \cong D_6$.

## Groups of order p

> *Theorem.*{: .thm}
> Suppose $G$ is a finite group of order $p$, where $p$ is prime.
> Then $G$ is cyclic and the only subgroups are $\set{e}$ and $G$.
>
> *Proof.*{: .prf}
>
> For $H \le G$, by Lagrange's Theorem, $\|H\|$ divides $\|G\| = p$, hence $\|H\| = 1$ or $p$.
> When $\|H\| = 1$, $H = \set{e}$. When $\|H\| = p$, $H = G$. For any $a \in G$, $\text{ord}(a) = p$ and generates $G$.

## Groups of order 2p

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 12.1, 12.9
