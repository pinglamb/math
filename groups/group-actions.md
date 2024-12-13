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

## References

* [Dexter Chua _Part IA - Groups_, 2014 - Chapter 5](https://dec41.user.srcf.net/notes/IA\_M/groups.pdf)
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 6](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
