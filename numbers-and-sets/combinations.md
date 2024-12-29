---
layout: base
title: Combinations &#124; Numbers and Sets
---

# Combinations
{: .page-title}

> *Definition.*{: .def}
> Let $X$ be a set containing exactly $n$ elements.
> For any non-negative integer $k$, the number of subsets of $X$ containing precisely $k$ elements is ${n \choose k}$, pronounced as "$n$ choose $k$".

> *Theorem.*{: .thm}
> **[Binomial Thoerem]** For $n \in \mathbb{N}$, and any real numbers $x$ and $y$,
>
> $$
  (x + y)^n = {n \choose 0}x^n + {n \choose 1}x^{n-1}y + ... + {n \choose n}y^n
  $$
>
> and ${n \choose k}$ is called a **binomial coefficient**.
>
> *Proof.*{: .prf}
>
> The L.H.S can be expressed as
>
> $$
  (x + y)^n = (x + y)(x + y)...(x + y)
  $$
>
> Consider the coefficients of $x^{n-k}y^k$, it is like choosing $y$ from $k$ terms out of $n$ terms and choosing $x$ from the remaining $n - k$ terms.
> By definition, there are ${n \choose k}$ ways to do that.
> Hence, the coefficient of $x^{n-k}y^k$ is ${n \choose k}$ and
>
> $$
  (x + y)^n = \sum_{k = 0}^n {n \choose k} x^{n-k}y^k
  $$

> *Theorem.*{: .thm}
> **[Pascal Identity]** For $n, k \in \mathbb{N}$,
>
> $$
  {n \choose k} + {n \choose k+1} = {n+1 \choose k+1}
  $$
>
> *Proof.*{: .prf}
>
> When we are choose $k + 1$ elements from $n + 1$ elements, we can mark the first element as a special element.
> Then, we can choose $k$ elements from the remaining $n$ elements and include the special one, which is ${n \choose k}$,
> or choose $k+1$ elements from $n$ elements and don't include the special one, which is ${n \choose k+1}$.
> Hence, there are ${n \choose k} + {n \choose k+1}$ ways in total.

The identity can be used to construct the _Pascal Triangle_:

$$
\begin{gather*}
& & & &  1 \\
& & & 1 & & 1 \\
& & 1 & & 2 & & 1 \\
& 1 & & 3 & & 3 & & 1 \\
1 & & 4 & & 6 & & 4 & & 1
\end{gather*}
$$

> *Theorem.*{: .thm}
> For $n, k \in \mathbb{N}$,
>
> $$
  {n \choose k} = {n! \over (n-r)!r!} = {n(n-1)(n-2)...(n-r+1) \over r(r-1)(r-2)...1}
  $$
>
> *Proof.*{: .prf}
>
> There are $n(n-1)(n-2)...(n-r+1)$ choices to pick $k$ elements from $n$ elements in order,
> and there are $r(r-1)(r-2)...1$ ways to order them.

The above four ways to interpret ${n \choose k}$ are therefore equivalent.
