---
layout: base
title: Subsequences &#124; Analysis
---

# Subsequences
{: .page-title}

## Partial Order

> *Definition.*{: .def}
> An order $\le$ on is a **partial order** relation if
>
> + $a \le b$ and $b \le c$ implies $a \le c$, and
>
> + $a \le b$ and $b \le a$ iff $a = b$.
>
> A partial order is therefore reflexive, antisymmetric and transitive.

A partial order doesn't require every pair of elements to be comparable. If they do, we have the total order.

> *Definition.*{: .def}
> A **total order** is a partial order where $\forall x \not= y$, exactly one of $x \le y$ or $y \le x$ holds.
> This means that every two elements must be related.

Suppose that $\le$ is a partial order on a set $A$ and $a \in A$ and $B \subseteq A$.

> *Definition.*{: .def}
> $a$ is an **upper bound** of $B$ if $b \le a$ for all $b \in B$.

Note that an upper bound of $B$ need to belong to $B$. If it does, it is the greatest element.

> *Definition.*{: .def}
> $a$ is the **greatest** element of $B$ if $a$ is an upper bound and $a \in B$.

> *Definition.*{: .def}
> $a$ is a **maximal** element of $B$ if $a \in B$ and if $b \in B$ and $a \le b$ then $a = b$.

The greatest element has to be the maximal element, but the converse is not true.
It is because partial order does not require every element to be related to each other,
so the maximal element of certain subset of $B$ needs not be the greatest of the whole subset $B$.
In the case of total order, we will have the maximal element being the greatest element.

> *Definition.*{: .def}
> $a$ is an **supremum** of $B$ if $a$ is an upper bound and if $c$ is also an upper bound then $a \le c$.

The definition of **lower bound**, **least** and **minimal** element and **infimum** is the same except for the sign.

## Subsequences

To avoid recursive definition, we first define subsequences of $\mathbb{N}$.

> *Definition.*{: .def}
> A _subsequence_ of $\mathbb{N}$ is a strictly increasing function from $\mathbb{N}$ to $\mathbb{N}$.
> The set $\Set{n_k : k \in \mathbb{N}}$ is the _image_ of the subsequence.

> *Lemma.*{: .lem}
> Suppose that $(m_k)$ and $(n_k)$ are subsequences of $\mathbb{N}$, with images $A$ and $B$ respectively.
> If $A \subseteq B$, then $m_k \ge n_k$ for all $k \in \mathbb{N}$.
>
> *Proof.*{: .prf}
>
> The key is $A \subseteq B$ so if they are arranged in strictly increasing order, each element of $A$ must be at least as large as $B$ at the same index.
>
> Formally, we have $n_1 = \inf(A) \le \inf(B) = m_1$. Assume $m_k \ge n_k$.
>
> If $m_k = n_k$, $n_{k+1} = \inf(\Set{a \in A : a > n_k}) \le \inf(\Set{b \in B : b > m_k}) = m_{k+1}$.
>
> If $m_k > n_k$, $n_{k+1} = \inf(\Set{a \in A : a > n_k}) \le m_k < m_{k+1}$ (because $m_k$ not yet appear yet on the $n_k$ side).
>
> By induction, it is true for all $k \in \mathbb{N}$.

> *Theorem.*{: .thm}
> **[Diagonal Procedure]**
> Suppose that $((n_{jk}))$ is a sequence of subsequences of $\mathbb{N}$ and $A_j$ is the image of $(n_{jk})$.
> If $(A_j)$ is a decreasing sequence, i.e. $A_1 \supseteq A_2 \supseteq \cdots$,
> then $(n_{kk})$ is a subsequence of $\mathbb{N}$ and $n_{kk} \in A_l$ for $l \le k$.
>
> *Proof.*{: .prf}
>
> $n_{kk} < n_{k\,k+1}$ as subsequences are strictly decreasing and $n_{k\,k+1} \le n_{k+1\,k+1}$ by the above lemma.
> Therefore,
>
> $$
  n_{kk} < n_{k\,k+1} \le n_{k+1\,k+1}
  $$
>
> and the sequence $(n_{kk})$ is strictly decreasing so it is a subsequence of $\mathbb{N}$.
> Also, $n_{kk} \in A_k \subseteq A_l$ for $l \le k$.

The diagonal procedure constructs new subsequence from a sequence of subsequences, which can be used to prove certain fundamental results.

> *Definition.*{: .def}
> A **subsequence** of a sequence $(a_n)$ is the composite $(a_{n_k})$ where $(n_k)$ is a subsequence of $\mathbb{N}$.
> It is more accurate to define it as $((a_n), (n_k))$ and $(n_k)$ is called the **support** of the subsequence.

> *Theorem.*{: .thm}
> Suppose that $(a_n)$ is a sequence in a totally ordered set $A$.
> Then there exists a strictly monotonic subsequence $(a_{n_k})$, i.e. it is either strictly increasing, strictly decreasing or constant.
>
> *Proof.*{: .prf}
>
> An index $N$ is a _high point_ if $a_N > a_n$ for for all $n > N$.
> If the sequence has infinitely many high points $h_1 < h_2 < \cdots$, then $(a_{h_k})$ is strictly decreasing subsequence.
> If the sequence has finitely many high points, there exists a $N$ such that there are no high points for all $n \ge N$.
> Starting from $n_1 = N$, we can recursively pick an $n_{k+1}$ in which $n_{k+1}$ is the least element such that $n_{k+1} \ge n_k$.
> There are always such elements to pick otherwise $n_k$ will be a high point.
> Therefore, for the subsequence $(a_{n_k})$, either we have an element $a_N$ such that $a_n = a_N$ for all $n > N$ and we have a constant subsequence,
> or we exclude the successively equal elements and got a strictly increasing subsequence.

## Bolzano-Weierstrass Theorem

> *Theorem.*{: .thm}
> **[Bolzano-Weierstrass Theorem]**
> Suppose that $(a_n)$ is a bounded sequence of $\mathbb{R}$. Then there is a subsequence $(a_{n_k})$ which converges.
>
> *Proof.*{: .prf}
>
> Base on the above theorem, any sequence $(a_n)$ has a monotonic subsequence. The subsequence is bounded as well and therefore converges.
>
> Alternatively, we can prove this by repeated bisection. As $(a_n)$ is bounded, we have $b_0 \le a_n \le c_0$ for all $n$.
> Let $m_0 = (b_0 + c_0) / 2$. There are infinitely many $a_n$ in either the interval $[b_0, m_0]$ or $[m_0, c_0]$ (can be both).
> We then have a new interval $[b_1, c_1]$ such that it is half of the length and have infinitely many $a_n$ in it.
> By repeating this process of having $m_k = (b_k + c_k)/2$, we can constructe a sequence of subsequences in which their images are $[b_0, c_0] \supseteq [b_1, c_1] \supseteq \cdots$.
> By the diagonal procedure, we can construct a subsequence $(a_{kk})$ from it and we have $b_k \le a_{kk} \le c_k$ for each $k$.
> As $(b_k)$ is increasing and bounded by $c_0$, $(b_k)$ converges to a limit $L$.
> $c_k = b_k + (b_0 + c_0)/2^k$ which also converges to $L$.
> By the sandwich principle, the subsequence $(a_{kk})$ converges to $L$.


## References

* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 1.3, 2.4, 3.4
