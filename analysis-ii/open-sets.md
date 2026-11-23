---
layout: base
title: Open Sets &#124; Analysis II
---

# Open Sets

Open sets generalize the idea of open ball that will more widely applicable to the study of topology.

> *Definition.*{: .def}
> Let $(X, \rho)$ be a metric space and $a \in X$ and $r \in \mathbf{R}_{> 0}$.
> The **open ball** with centre $a$ and radius $r$ is defined by
>
> $$
  B_r(a) = \Set{x \in X : \rho(a, x) < r}
  $$

The open ball might not be exactly a ball, for example the open "ball" of $B\_\varepsilon(f)$ in $C[a, b]$ with $\sup$ metric is a strip with width $2\varepsilon$.

> *Definition.*{: .def}
> Let $(X, \rho)$ be a metric space and $U \subseteq X$.
> Then $U$ is **open** if for every $x \in U$ there exists $\varepsilon_x > 0$ such that $B_{\varepsilon_x}(x) \subseteq U$.

> *Proposition.*{: .prop}
> Every open ball is an open set.
>
> *Proof.*{: .prf}
>
> By definition, for every $x \in B\_r(a)$, we have $\rho(a, x) < r$. Therefore, by having $0 < \varepsilon < r - \rho(a, x)$,
> every $y \in B\_\varepsilon(x)$ has $\rho(a, y) \le \rho(a, x) + \rho(x, y) < r$ so $y \in B\_r(a)$.
> Hence, $B\_\varepsilon(x) \subseteq B\_r(a)$.

The geometric meaning of open set is that there are no "boundary" points, i.e. any point in the set can go some positive distance without going outside.
A set being open or not is with respect to the underlying metric space (the set and the metric).
For example, the interval $[0, 1)$ is not open in $\mathbb{R}$ but open in $[0, 1)$.

> *Proposition.*{: .prop}
> The intersection of a finite number of open sets is open.
>
> *Proof.*{: .prf}
>
> Let $U\_1, ..., U\_n$ be open sets. For any $x \in \bigcap U\_i$, there exists $\varepsilon_i > 0$ such that $B\_{\varepsilon_i}(x) \subseteq U\_i$.
> Take $\varepsilon = \min \varepsilon\_i > 0$, for any $y \in B\_{\varepsilon}(x)$, $d(x, y) < \varepsilon \le \varepsilon_i$ so $y \in U\_i$ for all $i$ and $y$ is in the intersection.
> Hence, $B\_{\varepsilon}(x) \subseteq \bigcap U\_i$.

It is generally not true for infinite number of open sets. For example, the intervals $(-1/n, 1/n)$ is open in $\mathbb{R}$ while their intersection $\set{0}$ is not open.

> *Proposition.*{: .prop}
> The union of any collection of open sets is open.
>
> *Proof.*{: .prf}
>
> Let $I$ be an indexing set. For any $x \in \bigcup_{i \in I} U\_i$, we have $x \in U\_{i_0}$ for some $i\_0 \in U\_i$
> so there exists $\varepsilon > 0$ such that $B\_\varepsilon(x) \subseteq U\_i$ and hence $B\_\varepsilon(x) \subseteq \bigcup U\_i$.

It shows that open sets are more flexible then open balls since union or intersection of open balls need not be open ball again.

## Closed Sets

> *Definition.*{: .def}
> A subset $U \subseteq X$ is **closed** in $X$ if its complement $X \setminus U$ is open in $X$.

Intuitively, a set is closed if it contains all its "boundary" points.
Note that a set can be both open and closed such as $\emptyset$ and $X$ in $X$ or neither open or closed such as $[0, 1)$ in $\mathbb{R}$.

Apart from typical example like $[0, 1]$ being closed in $\mathbb{R}$, we also have subset $\set{f \in C[0, 1] : f(1) = 0}$ being closed in $C[0, 1]$ under $\sup$ metric.
It is because for any function $f \in \set{f \in C[0, 1] : f(1) \not= 0}$, $g \in B\_{\vert g(1) \vert / 2}(f)$ also satisfies $g(1) \not= 0$.

> *Proposition.*{: .prop}
> The union of a finite number of closed sets is closed.
> The intersection of any collection of closed sets is closed.
>
> *Proof.*{: .prf}
>
> By taking complements and De Morgan's Laws.

## Closure

Since general subsets of a metric space $X$ is likely to be neither open or closed in $X$, we shall discuss how we can derive the related open and closed sets.

> *Definition.*{: .def}
> Suppose that $U$ is a subset of a metric space $X$ and $x \in X$.
> Then $x$ is a **point of closure** of $U$ in $X$ if for any $\varepsilon > 0$, we have $B\_\varepsilon(x) \cap U \not= \emptyset$.
> The **closure** of $U$ in $X$, denoted by $\overline{U}$, is the set of all points of closure of $U$ in $X$.

The following concept is often important in analysis.

> *Definition.*{: .def}
> A subset $U$ of a metric space $X$ is said to be **dense** in $X$ if $\overline{U} = X$.

> *Proposition.*{: .prop}
> Let $U, V$ be subsets of a metric space $X$. Then
>
> + $U \subseteq \overline{U}$;
>
> + $U \subseteq V$ implies $\overline{U} \subseteq \overline{V}$;
>
> + $U$ is closed in $X$ iff $\overline{U} = U$;
>
> + $\overline{\overline{U}} = \overline{U}$;
>
> + $\overline{U}$ is closed in $X$;
>
> + $\overline{U}$ is the smallest closed subset of $X$ containing $U$.

## Limit Points

## Bounded Sets


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
