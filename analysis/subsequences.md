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
> Then there exists a monotonic subsequence $(a_{n_k})$, i.e. it is either strictly increasing, strictly decreasing or constant.

## Bolzano-Weierstrass Theorem

## References

* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 1.3, 2.4, 3.4
