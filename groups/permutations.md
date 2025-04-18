---
layout: base
title: Permutations &#124; Groups
---

# Permutations
{: .page-title}

> *Definition.*{: .def}
> A **permutation** of a set $X$ is an invertible/bijective map $f: X \to X$.

## Two Row Notation

For finite set $X = \set{1, 2, ..., n}$, it is convenient to write out the permutation $\sigma$ in two rows,
$1, 2, ..., n$ on the top and corresponding images below, i.e.

$$
\sigma = \begin{pmatrix}
1 & 2 & \cdots & n \\
\sigma(1) & \sigma(2) & \cdots & \sigma(n) \\
\end{pmatrix}
$$

Composition can be done by reordering the next permutation, e.g.

$$
\begin{pmatrix}
1 & 2 & 3 \\
2 & 3 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 2 & 3 \\
2 & 1 & 3
\end{pmatrix} =
\begin{pmatrix}
2 & 1 & 3 \\
3 & 2 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 2 & 3 \\
2 & 1 & 3
\end{pmatrix} =
\begin{pmatrix}
1 & 2 & 3 \\
3 & 2 & 1
\end{pmatrix}
$$

## Disjoint Permutations

> *Definition.*{: .def}
> A permutation $\sigma$ _fixes_ $a$ if $f(a) = a$.

> *Definition.*{: .def}
> Two permutations $\alpha$ and $\beta$ are _disjoint_ if for every $k \in \set{1, 2, ..., n}$,
> either $\alpha$ or $\beta$ fixes $k$, i.e. $\alpha(k) = k$ or $\beta(k) = k$.

> *Theorem.*{: .thm}
> Disjoint permutations _commute_, i.e. $\alpha\beta = \beta\alpha$.
>
> *Proof.*{: .prf}
>
> As $\alpha$ and $\beta$ are disjoint, for any $k$, let's say $\alpha(k) = k$ and $\beta(k) = k'$.
> We have
>
> $$
  \alpha(\beta(k)) = \alpha(k') \quad \text{and} \quad \beta(\alpha(k)) = \beta(k) = k'
  $$
>
> Suppose $\alpha(k') \not = k'$, as $\alpha$ and $\beta$ are disjoint, we need to have $\beta$ fixes $k'$, i.e. $\beta(k') = k' = \beta(k)$.
> It implies $k = k'$ as $\beta$ is a bijection, which is a contradiction.
> Hence, $\alpha$ has to fix $k'$, i.e. $\alpha(k') = k'$ and therefore $\alpha(\beta(k)) = \beta(\alpha(k))$.

## Disjoint Cycle Notation

> *Definition.*{: .def}
> A k-cycle $(a_1\;a_2\;...\;a_k)$ is the permutation
>
> $$
  (a_1\;a_2\;...\;a_k) = \begin{pmatrix}
  a_1 & a_2 & \cdots & a_{k-1} & a_k \\
  a_2 & a_3 & \cdots & a_k & a_1 \\
  \end{pmatrix}
  $$
>
> which has order $k$.

> *Definition.*{: .def}
> 2-cycles are called **transpositions**.

> *Definition.*{: .def}
> Two cycles are _disjoint_ if no numbers appear in both.

> *Theorem.*{: .thm}
> Every finite permutation can be written as a product of disjoint cycles (unique up to orders).
>
> *Proof.*{: .prf}
>
> Let $\sigma$ be a permutation. We start with
>
> $$
  (1\;\sigma(1)\;\sigma^2(1)\;\sigma^3(1)\;...)
  $$
>
> As $\sigma$ is finite, there is some $\sigma^p(1) = \sigma^q(1)$.
> As $\sigma$ is bijection, $\sigma^{p-q}(1) = 1$.
>
> Let $k$ be the smallest positive integer such that $\sigma^k(1) = 1$, and we will have
>
> $$
  (1\;\sigma(1)\;\sigma^2(1)\;...\;\sigma^{k-1}(1))
  $$
>
> being the first cycle.
>
> We then pick the next number that doesn't appear in the cycles and repeat the process until exhaustion.
> All the cycles formed are disjoint as $\sigma$ is a bijection.
>
> By construction, $\sigma$ is a product of disjoint cycles and is called the _standard representation_ of $\sigma$.

## Cycle Type of Permutation

> *Definition.*{: .def}
> The **cycle type** of a permutation $\sigma$ is the list of cycle lengths of $\sigma$ in disjoint cycle notation.
{: #cycle-type}

For example, $(1\,2)$ has cycle type $2$ and $(1\,2\,3)(4\,5)$ has cycle type $3,2$.

## Order of Permutation

> *Definition.*{: .def}
> The **order** of permutation $\sigma$ is the smallest positive integer $m$ such that $\sigma^m = I$, the identity map.

> *Theorem.*{: .thm}
> With the cycle represetnation, the order of $\sigma$ is the least common multiple of the different cycle lengths.
>
> *Proof.*{: .prf}
>
> Let $\sigma = \tau_1\tau_2...\tau_k$, as disjoint cycles commute, we have
>
> $$
  \sigma^m = \tau_1^m\tau_2^m...\tau_k^m
  $$
>
> If $\tau_i$ has length $l_i$, $\tau_i^{l_i} = e$. Therefore, for $\tau_i^m = e \implies l_i \mid m$.
>
> In order for $\sigma^m = e$, we need $l_i \mid m$ for all $i$ and hence $m = [l_1, l_2, ..., l_k]$.

## Sign of Permutation
{: #sign-of-permutation}

> *Lemma.*{: .lem}
> Every permutation is a product of transpositions.
>
> *Proof.*{: .prf}
>
> As any permutation can be represented by disjoint cycles, and for any cycle
>
> $$
  (a_1\;a_2\;a_3\;...\;a_k) = (a_1\;a_k)(a_1\;a_{k-1})...(a_1\;a_3)(a_1\;a_2)
  $$
>
> so every perumutation can be expressed as a product of transpositions.
{: #permutation-transpositions}

The representation by transpositions isn't unique. However,

> *Theorem.*{: .thm}
> The **sign/parity** of a permutation $\sigma$, denoted by $\text{sgn}(\sigma)$ or $\epsilon(\sigma)$, is well defined.
> It means a permutation is either a product of even or odd number of transpositions no matter how it is written.

> *Proof 1.*{: .prf}
> _Effect of a transpoition to the sign of permutation._
>
> Let $\phi(\sigma)$ be the number of cycles in disjoint cycle notation, including _singleton cycles_, i.e. $\phi(e) = n$ and $\phi((1\;2)) = n - 1$.
> Consider multiplying a transposition $\tau = (c\;d)$ to $\sigma$, either $c$ and $d$ are in the same cycle and
>
> $$
  (c\;\;a_2\;...\;a_{k-1}\;d\;a_{k+1}\;...\;a_{k+l})(c\;d) = (c\;a_{k+1}\;...\;a_{k+l})(d\;a_2\;...\;a_{k-1})
  $$
>
> and $\phi(\sigma\tau) = \phi(\sigma) + 1$ or $c$ and $d$ are in different cycles and
>
> $$
  (c\;a_2\;...\;a_{k-1})(d\;b_2\;...\;b_{l-1})(c\;d) = (c\;b_2\;...\;b_{l-1}\;d\;a_2\;...\;a_{k-1})
  $$
>
> and $\phi(\sigma\tau) = \phi(\sigma) - 1$. So, $\phi(\sigma\tau) = \phi(\sigma) + 1\;\text{(mod }2\text{)}$.
>
> Suppose $\sigma = \tau_1\tau_2...\tau_k = \rho_1\rho_2...\rho_l$, as $\phi(\sigma)$ is completely determined by the disjoint cycle notation of $\sigma$,
>
> $$
  \begin{align*}
  \phi(\sigma) &\equiv \phi(e) + k \equiv n + k \; \text{(mod }2\text{)} \\
  \phi(\sigma) &\equiv \phi(e) + l \equiv n + l \; \text{(mod }2\text{)}
  \end{align*}
> $$
>
> and hence $k \equiv l \; \text{(mod }2\text{)}$.

> *Proof 2.*{: .prf}
> _From $\text{sgn}(e)$ is even._
>
> When $n = 2$, suppose $e_2 = \tau_1\tau_2...\tau_k$, where $\tau_i$ is a transposition. As the only transposition is $(1\;2)$ for $S_2$, we have
>
> $$
  e_2 = (1\;2)^k
  $$
>
> and therefore $k$ must be even.
>
> Assume it is true for $n = m-1$, meaning $e_{m-1} = \tau_1\tau_2...\tau_k$ with $k$ being even.
>
> When $n = m$, suppose $e_m = \tau_1\tau_2...\tau_k$.
>
> Consider the rightmost transpositions, and assume $\tau_k$ doesn't fix $n$, there are 4 cases
>
> $$
  \tau_{k-1}\tau_k = \begin{cases}
  (a\;b)(n\;a) = (n\;b\;a) = (n\;b)(a\;b) \\
  (n\;b)(n\;a) = (n\;a\;b) = (n\;a)(a\;b) \\
  (b\;c)(n\;a) = (n\;a)(b\;c) \\
  (n\;a)(n\;a) = e = (a\;b)(a\;b) \\
  \end{cases}
  $$
>
> From the above, no matter which cases, we can also rewrite $\tau_k$ such that it fixes $n$ so we can assume it is the case, i.e. $\tau_k(n) = n$.
> We then repeat this process up to $\tau_2$, with $\tau_2,\tau_3,...,\tau_k$ all fixes $n$.
> However, as
>
> $$
  e(n) = \tau_1\tau_2...\tau_k(n) = n
  $$
>
> $\tau_1$ has to fix $n$ as well.
>
> As a result, for any transpositions of $e_m$, we can rewrite them such that all the transpositions fixes $m$ and only involves $1, 2, ..., m-1$.
> By the induction hypothesis, $\tau_1\tau_2...\tau_k$ has to be even and therefore $e_n$ is even.
>
> With this result, suppose $\sigma = \tau_1\tau_2...\tau_k = \rho_1\rho_2...\rho_l$, then
>
> $$
  \rho_l...\rho_2\rho_1\tau_1\tau_2...\tau_k = e
  $$
>
> Therefore, $l + k$ is even which means either both $k$ and $l$ are even or odd.

> *Definition.*{: .def}
> Suppose $\sigma = \tau_1\tau_2...\tau_k$, the **sign** of $\sigma$ is defined by
>
> $$
  \text{sgn}(\sigma) = (-1)^{k}
  $$
>
> $\text{sgn}(\sigma) = 1$ means even and $\text{sgn}(\sigma) = -1$ means odd.

> *Property.*{: .prop}
> $\text{sgn}$ is _multiplicative_, i.e. $\text{sgn}(\sigma_1\sigma_2) = \text{sgn}(\sigma_1)\text{sgn}(\sigma_2)$.
>
> *Proof.*{: .prf}
>
> $$
  \text{sgn}(\sigma_1\sigma_2) = (-1)^{k_1 + k_2} = (-1)^{k_1}(-1)^{k_2} = \text{sgn}(\sigma_1)\text{sgn}(\sigma_2)
  $$

> *Proposition.*{: .prop}
> The number of transpositions of $k$-cycle is $k-1$, so odd length cycles are even and even length cycles are odd.

> *Proposition.*{: .prop}
> A permutation is even iff the number of disjoint cycles of even length is even.
>
> *Proof.*{: .prf}
>
> Suppose $\sigma = \tau_1\tau_2...\tau_k$, where the length of $\tau_i$ is $l_i$, we have
>
> $$
  \text{sgn}(\sigma) = (-1)^{l_1 - 1}(-1)^{l_2 - 1}...(-1)^{l_k - 1}
  $$
>
> so it is even if there are even number of even length cycles.

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Section 1.3, 1.4
* [Julia Goedecke _Part IA - Groups_, 2017 - Chapter 2](https://www.julia-goedecke.de/pdf/GroupsNotes.pdf)
