---
layout: base
title: Group Actions &#124; Groups
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

## Orbits and Stabilisers

> *Definition.*{: .def}
> Given $G$ acts on $X$, the **orbit** of an element $x \in X$ is
>
> $$
  \text{orb}(x) = G(x) = \set{y \in X : \exists g \in G, g(x) = y} \subseteq X
  $$

It is a subset of elements in $X$ that $x$ can get mapped to by $G$.

> *Definition.*{: .def}
> Given $G$ acts on $X$, the **stabiliser** of an element $x \in X$ is
>
> $$
  \text{Stab}(x) = G_x = \set{g \in G : g(x) = x} \subseteq G
  $$

It is the subset of elements in $G$ that fixes $x$.

> *Lemma.*{: .lem}
> $\text{Stab}(x) \le G$.
>
> *Proof.*{: .prf}
>
> By definition, $e_G \in \text{Stab}(x)$.
> For $a, b \in \text{Stab}(x)$, $b^{-1}$ fixes $x$ and so as $ab^{-1}$, so $ab^{-1} \in \text{Stab}(x)$.

In fact, conversely, every subgroup is a stabiliser that fixes some elements in $X$.

> *Definition.*{: .def}
> An action is **transitive** if for all $x \in X$, $\text{orb}(x) = X$.

It means any element can reach any element in $X$.

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

> *Lemma.*{: .lem}
> Suppose that $G$ acts on $X$ and that $g(x) = y$, where $x, y \in X$ and $g \in G$, then
>
> $$
  g\text{Stab}(x) = \set{h \in G : h(x) = y} = \text{Stab}(x)g
  $$
>
> *Proof.*{: .prf}
>
> Let $H = \set{h \in G : h(x) = y}$.
> For any $h \in g\text{Stab}(x)$, $gh(x) = g(x) = y$, so $h \in H$ and $g\text{Stab}(x) \subseteq H$.
> For any $h \in H$, $g^{-1}h(x) = x$, so $h = g(g^{-1}h) \in g\text{Stab}(x)$ and $H \subseteq g\text{Stab}(x)$.

> *Theorem.*{: .thm}
> **Orbit-Stabiliser Theorem**. Let $G$ be a finite group acting on a finite set $X$. Then, for any $x \in X$,
>
> $$
  \vert \text{orb}(x) \vert \vert \text{Stab}(x) \vert = \vert G \vert
  $$
>
> *Proof.*{: .prf}
>
> For any $x \in X$, let the orbit of $x$ be $\set{g_1(x), g_2(x), ..., g_k(x)}$, so $\vert \text{orb}(x) \vert = k$.
> According to the above, $g_i\text{Stab}(x)$ is the subset of $G$ that maps $x$ to $g_i(x)$, so
>
> $$
  G = g_1\text{Stab}(x) \cup g_2\text{Stab}(x) \cup \dots \cup g_k\text{Stab}(x)
  $$
>
> in which they are pairwise disjoint. Thus,
>
> $$
  \vert G \vert = k \vert \text{Stab}(x) \vert = \vert \text{orb}(x) \vert \vert \text{Stab}(x) \vert
  $$

The orbit and stabilisers provide a geometric view of [subgroups, cosets and Lagrange's Theorem](subgroups-cosets-lagrange-theorem.md).
Let $H = \set{h \in G : h(x) = y}$, $H$ is the subset of elements in $G$ that maps $x$ to $y$.
From the above, we have $H = g\text{Stab}(x)$, which is a coset of the subgroup $\text{Stab}(x)$,
so a coset is actually the subset of elements in $G$ that maps a certain $x$ to the same $y$.
Conversely, for any $h_1, h_2 \in H$, we have $h_1^{-1}(h_2(x)) = x$,
which means if we apply $h_2$ then $h_1^{-1}$ to $x$ we will get back to $x$ as both of them maps $x$ to $y$,
so we can say the subgroup $\text{Stab}(x)$ is formed by elements in $H$ and every subgroup is a stablizer of some elements in $X$ formed in this way.
The orbit of $x$ is the set of $y$ that $x$ can reach, it can map bijectively to one of the element in the set $\set{g_1\text{Stab}(x), g_2\text{Stab}(x), ...}$.
By construction, the set is obviously pairwise disjoint (equivalently cosets are pairwise disjoint), has the same size as $\text{orb}(x)$ and any $g \in G$ is in one of its element.
Thus, the orbit-stabiliser theorem concluded from it is a geometric form of Lagrange's Theorem.

> *Corollary.*{: .cor}
> If the action is transitive, then all the stabilisers have the same size.
>
> *Proof.*{: .prf}
>
> For any $x \in X$, $\vert \text{orb}(x) \vert = \vert X \vert$, so $\vert \text{Stab}(x) \vert = \vert G \vert / \vert X \vert$.

## Left Multiplication Actions

### Left regular action

> *Lemma.*{: .lem}
> Every group $G$ acts on itself by left multiplication faithfully and transitively.
>
> *Proof.*{: .prf}
>
> 0\. $\forall g \in G, x \in G, gx \in G$ (closure)
>
> 1\. $\forall x \in G, ex = x$ (identity)
>
> 2\. $g(hx) = (gh)x$ (associativity)
>
> So it is an action.
> By the uniqueness of identity, $gx = x$ iff $g = e$, so the action is faithful.
> For any $x, y \in G$, as $yx^{-1} \in G$, $(yx^{-1})x = y$ so the action is transitive.

> *Theorem.*{: .thm}
> **Cayley's Theorem**.
> Every group is isomorphic to a subgroup of some symmetric group.
>
> *Proof.*{: .prf}
>
> As $G$ actis on itself by left multiplication, there is a homomorphism $\varphi: G \to \text{Sym}\,G$ with $\ker \varphi = \set{e}$.
> By the Isomorphism Theorem, $G \cong \text{Im}\,\varphi \le \text{Sym}\,G$.

### Left coset action

> *Lemma.*{: .lem}
> Let $H \le G$. Then $G$ acts on the left cosets of $H$ by left multiplication transitively.
>
> *Proof.*{: .prf}
>
> 0\. $g(aH) = gaH$ is a left coset of $H$
>
> 1\. $e(aH) = aH$ for all $aH$
>
> 2\. $g_1(g_2(aH)) = g_1(g_2aH) = (g_1g_2)aH$ by associativity of group
>
> So it is an action.
> For any $aH$ and $bH$, as $ba^{-1} \in G$, $ba^{-1}aH = bH$ so the action is transitive.

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Chapter 14
* [Dexter Chua _Part IA - Groups_, 2014 - Chapter 5](https://dec41.user.srcf.net/notes/IA\_M/groups.pdf)
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 6](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
