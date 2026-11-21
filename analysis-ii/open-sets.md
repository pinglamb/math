---
layout: base
title: Open Sets &#124; Analysis II
---

# Open Sets

> *Definition.*{: .def}
> Let $(X, \rho)$ be a metric space and $a \in X$ and $r \in \mathbf{R}_{> 0}$.
> The **open ball** with centre $a$ and radius $r$ is defined by
>
> $$
  B_r(a) = \Set{x \in X : \rho(a, x) < r}
  $$

> *Definition.*{: .def}
> Given $E \subseteq X$, $a \in X$ is said to be a **limit point** of $E$ if
>
> $$
  (\forall \varepsilon > 0)(\exists e \in E)\; 0 < \rho(a, e) < \varepsilon
  $$
>
> i.e. $(B_\varepsilon(a) - \Set{a}) \cap E \not= \emptyset$ for all $\varepsilon > 0$.

> *Proposition.*{: .prop}
> Given $E \subseteq X$, $a \in X$ is a limit point of $E \subseteq X$ iff either
>
> + every open ball $B_\varepsilon(a)$ contains infinitely many points of $E$; or
>
> + there is a sequence of points $\Set{e_n \in E}$ such that $e_n \not= a$ and $e_n \to a$ as $n \to \infty$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) If $a$ is a limit point, then for every $n$, there exists a point $e_n \in E$ such that
>
> $$
  0 < \rho(a, e_n) < 1/n
  $$
>
> The sequence $\Set{e_n}$ satisfies the second condition, in which implies the first.
>
> ($\Leftarrow$) First condition obviously implies $a$ is a limit point. By definition, the second condition implies that
>
> $$
  (\forall \varepsilon > 0)(\exists N)(\forall n > N)\; \rho(a, e_n) < \varepsilon
  $$
>
> so there must be $e = e_n \not= a$ satisfying $0 < \rho(a, e) < \varepsilon$.

These conditions show that a finite set cannot have a limit point. Also, a limit point of $E$ may or may not belong to $E$.
Therefore, limit points of a subset, as the name suggested, are elements in the parent set such that they are limits of some sequences in the subset.

> *Definition.*{: .def}
> Given $E \subseteq X$, $e \in E$ is an **isolated point** of $E$ if it is not a limit point, i.e.
>
> $$
  (\exists \delta > 0)\; B_\delta(e) \cap E = \Set{e}
  $$

> *Definition.*{: .def}
> Given $E \subseteq X$, $e \in E$ is an **interior point** of $E$ if
>
> $$
  (\exists \delta > 0)\; B_\delta(e) \subset E
  $$

The property of being a limit point or interior point is not intrinsic to the subset but it is relative to the parent set $X$ and the choice of metric $\rho$.
For example, a subset of rational numbers has no interior points in $\mathbf{R}$ but all the points of the same subset are interior points in $\mathbf{Q}$.

> *Definition.*{: .def}
> A subset $F \subseteq X$ is **closed** if $F$ contains all its limit points.
> A subset $G \subseteq X$ is **open** if every point of $G$ is an interior point of $G$.

From the above, since finite sets have no limit points, they are closed. It is possible for a subset to be both open and closed or neither open nor closed.
For example, the empty set and the whole space is both open and closed and the interval $[0, 1)$ of $\mathbf{R}$ is neither open nor closed.

> *Proposition.*{: .prop}
> A set $F$ is closed iff whenever $(x_n)$ is a convergent sequence of points in $F$, $\lim_{n \to \infty} x_n \in F$.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Suppose that $F$ is closed and let $x_n \in F \to x$ as $n \to \infty$.
> If $x_n = x$ for some $n$ then for sure $x \in F$. Otherwise, $x$ is a limit point of $F$ and again $x \in F$.
>
> ($\Rightarrow$) Suppose that $F$ has the described property. If $F$ has no limit points, then for sure $F$ is closed.
> Otherwise, let $x$ be a limit point of $F$ then there is a sequence $x_n \to x$ such that $x \in F$, so $F$ contains all its limit points.

> *Proposition.*{: .prop}
> A set $G$ is open iff $G' = (X - G)$ is closed. A set $F$ is closed iff $F'$ is open.
>
> *Proof.*{: .prf}
>
> Let $G$ be open. If $G'$ has no limit points, then $G'$ is closed.
> Let $x$ be a limit point of $G'$. Then every open ball $B_\varepsilon(x)$ contains a point in $G'$ so $x$ cannot be an interior point of $G$ and $x \in G'$.
>
> Let $F$ be closed. If $F'$ is empty, then $F'$ is open.
> For any point $x \in F'$, $x$ is not a limit point of $F$ and there exists $\delta$ such that $B_\delta(x)$ contains no point in $F$.
> Thus, $B_\delta(x) \subset F'$ and $x$ is an interior point of $F'$.

Since convergence of sequences to the same limit is preserved between equivalent metrics, together with the above two propositions,
we can see that metric spaces with equivalent metrics have the same set of open and closed sets, and therefore preserve the topological properties.

> *Proposition.*{: .prop}
> The union of any collection of open sets is open. The intersection of any collection of closed sets is closed.
>
> *Proof.*{: .prf}
>
> Let $x \in \bigcup G$, then $x$ is an interior point of at least one of the open set, say $G^\ast$.
> Thus, $B_\delta(x) \subset G^\ast$ which implies $B_\delta(x) \subset \bigcup G$ and every point is an interior point.
>
> If $F$ is closed, $F'$ is open. Therefore, the complement of the intersection of closed sets, i.e.
>
> $$
  \left( \bigcap F \right)' = \bigcup F'
  $$
>
> is a collection of open sets which is open. Hence the intersection itself is closed.

> *Proposition.*{: .prop}
> The intersection of finite collection of open sets is open. The union of finite collection of closed sets is closed.

> *Proposition.*{: .prop}
> Let $(Y, \sigma)$ be a metric subspace of $(X, \rho)$. Then a set is open in $(Y, \sigma)$ iff there exists an open set $G$ in $(X, \rho)$ such that $E = Y \cap G$.
> A similar result holds for closed sets.
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) Let $E$ be a open set in $Y$. For every $x \in E$, there exists $\delta_x$ such that $B_{\delta\_x}(x) \subset E$.
> It means that these open balls only contain elements in $E$, and therefore the set
>
> $$
  G = \bigcup_{x \in E} B_{\delta_x}(x)
  $$
>
> is open in $X$ and $E = Y \cap G$.
>
> ($\Leftarrow$) Let $G$ be open in $X$. For every $x \in Y \cap G$, there exists $\delta_x$ such that $B_{\delta\_x}(x) \subset G$.
> Therefore $B_{\delta\_x}(x) \cap Y \subset Y \cap G$ and $x$ is an interior point of $Y \cap G$.

> *Corollary.*{: .cor}
> If $Y$ is open/closed in $X$, then $Z$ is open/closed in $Y$ iff it is open/closed in $X$.

> *Definition.*{: .def}
> The **interior** of $E \subseteq X$, denoted by $E^\circ$, is the set of interior points of $E$.

> *Definition.*{: .def}
> The **closure** of $E \subseteq X$, denoted by $\bar{E}$, is the union of $E$ and the set of limit points of $E$.
> Thus, $\bar{E}$ is the set of $x$ such that every $B_\varepsilon(x)$ contains at least one point of $E$ or $x \in \bar{E}$ iff $x$ is the limit of a sequence of points of $E$.

Alternatively, $E^\circ$ is the union of all open sets contained in $E$ and so is the _largest_ open set contained in $E$
and $\bar{E}$ is the intersection of all closed sets containing $E$ and so is the _smallest_ closed set containing $E$.

> *Proposition.*{: .prop}
> $(\bar{E})' = (E')^\circ$.
>
> *Proof.*{: .prf}
>
> By definition, $x \in \bar{E}$ iff for all $\varepsilon > 0$, $B_\varepsilon(x) \cap E \not= \emptyset$, so if $y \in (\bar{E})'$ then $B_\varepsilon(y) \cap E = \emptyset$.
> Therefore, $y \in E'$ and there exists $\delta$ such that $B_\delta(y) \subset E'$ so $y \in (E')^\circ$.

> *Proposition.*{: .prop}
> For any $E \subseteq X$, $E^\circ$ is open and $\bar{E}$ is closed.
>
> *Proof.*{: .prf}
>
> If $E^\circ$ is empty, it is open. For any $x \in E^\circ$, there exists $\delta$ such that $B_\delta(x) \subset E$.
> Since every $y \in B_\delta(x)$ is an interior point of $B_\delta(x)$ so of $E$, $B_\delta(x) \subset E^\circ$ and $x$ is an interior point of $E^\circ$.
> By $(\bar{E})' = (E')^\circ$, $\bar{E}$ is closed.

We can also define open and closed sets by interiors and closures, $G$ is open iff $G^\circ = G$ and $F$ is closed iff $\bar{F} = F$.

> *Definition.*{: .def}
> A **frontier** of $E \subseteq X$, denoted by $\text{fr}\, E$, is the set of points such that every open ball $B_\varepsilon(x)$ contains at least one point of $E$ and at least one point of $E'$.

In other words, since a point $x$ cannot be in both $E$ and $E'$, $x$ is either a point in $E$ and a limit point in $E'$ or vice versa, so

$$
\text{fr}\, E = \bar{E} - E^\circ
$$

We also have $X = E^\circ \cup \text{fr}\, E \cup (E')^\circ$, where $(E')^\circ$ is called the _exterior_ of $E$.

## References

* J C Burkill _A Second Cource in Mathematical Analysis_, 1970 - Chapter 2.3
