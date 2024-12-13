---
layout: base
title: Groups &#124; Groups
---

# Group Actions
{: .page-title}

[Groups](groups.md) are symmetries of something, so far we abstract away the "things" part and focus on studying the properties of different kinds of groups.
_Group actions_ recapture the idea by making each group element correspond to some function to the "things".

> *Definition.*{: .def}
> An **action** of a group $G$ on a set $X$ is a homomorphism $\varphi: G \to \text{Sym}\,X$.

It means for each group element $g \in G$, the function $\varphi$ gives us a permutation $\varphi(g)$ of $X$.
The group structure of $G$ is preserved in the way that if $g, h \in G$,
the permutation $\varphi(gh)$ is equal to the composition $\varphi(g)\varphi(h)$ because $\varphi$ is a homomorphism.
To simplify, we will write $g(x)$ instead of $\varphi(g)(x)$ and the above rule becomes $gh(x) = g(h(x))$.

> *Theorem.*{: .thm}
> Let $X$ be a set and $G$ be a group. Then $\varphi: G \to \text{Sym} X$ is a homomorphism
> iff $\theta: G \times X \to X$ defined by $\theta(g, x) = \theta_g(x) = \varphi(g)(x)$ satisfies the axioms:
>
> 0\. $(\forall g \in G)(\forall x \in X)\;\theta(g, x) \in X$
>
> 1\. $(\forall x \in X)\;\theta(e, x) = x$
>
> 2\. $(\forall g,h \in G)(\forall x \in X)\;\theta(g, \theta(h, x)) = \theta(gh, x)$
>
> *Proof.*{: .prf}
>
> ($\Leftarrow$) For each $g \in G$, as $\theta(g^{-1}, \theta(g, x)) = \theta(g^{-1}g, x) = \theta(e, x) = x$ and $\theta(g, \theta(g^{-1}, x)) = x$ for all $x \in X$,
> $\theta_g: X \to X$ is a bijection (with $\theta_{g^{-1}}$ as inverse). So indeed $\theta_g \in \text{Sym}\,X$.
> As
>
> $$
  \varphi(gh) = \theta_{gh} = \theta_g\theta_h = \varphi(g)\varphi(h)
  $$
>
> $\varphi$ is a homomorphism.
>
> ($\Rightarrow$) If $\varphi$ is a group homomorphism, then for the $\theta$ defined above,
>
> 0\. $\theta_g = \varphi(g) \in \text{Sym}\,X$, so $\theta_g(x) \in X$.
>
> 1\. $\theta_e = \varphi(e) = 1_X$, so $\theta_e(x) = x$.
>
> 2\. $\theta_gh = \varphi(gh) = \varphi(g)\varphi(h) = \theta_g\theta_h$, so $\theta_{gh}(x) = \theta_g(\theta_h(x))$.

$\varphi: G \to \text{Sym}\,X$ is a mapping of $g$ to a permutation of $X$ (not element of $X$).
$\theta: G \times X \to X$ is a mapping of the pair $(g, x)$ to an element of $X$.
$\theta_g: X \to X$ is a relabeling of subset of pairs in $G \times X \to X$ and is a permutation of $X$.
For example, let $G = \set{e, a}$, $X = \set{1, 2, 3}$ and
$\theta = \set{((e, 1), 1), ((e, 2), 2), ((e, 3), 3), ((a, 1), 2), ((a, 2), 1), ((a, 3), 3)}$,
we have $\varphi = \set{(e, 1_X), (a, (1\,2))}$ and $\theta_a = (1\,2)$.
Obviously $\theta(g, x) \in X$ and $\theta(e, x) = x$, and particularly we have $\theta(a, \theta(a, 1)) = \theta(a, 2) = 1$,
so $\theta$ satisfies the 3 conditions above which implies $\varphi$ is a homomorphism (in particular $\varphi(a^2) = \varphi(e) = 1_X = (1\,2)(1\,2) = \varphi(a)\varphi(a)$).
Conversely, if $\varphi$ is a homomorphism, for example $\varphi = \set{(e, 1_X), (a, (1\,3))}$,
we have $\theta = \set{((e, 1), 1), ((e, 2), 2), ((e, 3), 3), ((a, 1), 3), ((a, 2), 2), ((a, 3), 1)}$
which satisfies the 3 conditions.

> *Definition.*{: .def}
> The _kernel_ of an action is the kernal of the homomorphism $\varphi: G \to \text{Sym}\,X$.

> *Definition.*{: .def}
> An action is **faithful** if $\varphi$ is injective, i.e. $\varphi(g) = \varphi(h) \implies g = h$ and kernel of action is $\set{e}$.

It means the elements of $g$ is distinguishable by their action of $X$ alone.

## Orbits and Stabilizers

> *Definition.*{: .def}
> Given $G$ acts on $X$, the **orbit** of an element $x \in X$ is
>
> $$
  \text{orb}(x) = G(x) = \set{y \in X : \exists g \in G, g(x) = y} \subseteq X
  $$

It is a subset of elements in $X$ that $x$ can get mapped to by $G$.

> *Definition.*{: .def}
> Given $G$ acts on $X$, the **stabilizer** of an element $x \in X$ is
>
> $$
  \text{stab}(x) = G_x = \set{g \in G : g(x) = x} \subseteq G
  $$

It is the subset of elements in $G$ that fixes $x$.

> *Lemma.*{: .lem}
> $\text{stab}(x) \le G$.
>
> *Proof.*{: .prf}
>
> By definition, $e_G \in \text{stab}(x)$.
> For $a, b \in \text{stab}(x)$, $b^{-1}$ fixes $x$ and so as $ab^{-1}$, so $ab^{-1} \in \text{stab}(x)$.

> *Definition.*{: .def}
> An action is **transitive** if for all $x \in X$, $\text{orb}(x) = X$.

> *Lemma.*{: .lem}
> The orbits of an action partition $X$, i.e. they cover all elements in $X$ and are either the same or disjoint.
>
> *Proof.*{: .prf}
>
> $\forall x \in X$, $x \in \text{orb}(x)$ as $e(x) = x$ ($x$ is always in its own orbit because of the identity of $G$).
>
> Suppose $z \in \text{orb}(x)$ and $z \in \text{orb}(y)$, we have $z = g_1(x) = g_2(y)$ for some $g_1, g_2 \in G$ and $y = g_2^{-1}g_1(x)$.
> So for any $w \in \text{orb}(y)$, $w = g(y) = g(g_2^{-1}g_1(x)) \in \text{orb}(x)$, so $\text{orb}(y) \subseteq \text{orb}(x)$.
> Similarily, $\text{orb}(x) \subseteq \text{orb}(y)$ so $\text{orb}(x) = \text{orb}(y)$.

It means any element can reach any element in $X$.

## References

* [Dexter Chua _Part IA - Groups_, 2014 - Chapter 5](https://dec41.user.srcf.net/notes/IA\_M/groups.pdf)
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 6](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
