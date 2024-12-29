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
> The L.H.S. can be expressed as
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

## Identities

> *Theorem.*{: .thm}
> For $n, k \in \mathbb{N}$,
>
> $$
  {n \choose k} = {n \choose n-k}
  $$
>
> *Proof.*{: .prf}
>
> Choosing $k$ elements from $n$ elements is the same as choosing $n-k$ elements to discard from $n$ elements.

> *Theorem.*{: .thm}
> For $n \in \mathbb{N}$, the sum
>
> $$
  {n \choose 0} + {n \choose 1} + \dots + {n \choose n} = 2^n
  $$
>
> *Proof.*{: .prf}
>
> The sum on the L.H.S. is equivalent to the total number of subsets of a set with $n$ elements, which is $2^n$.
>
> Alternatively,
>
> $$
  (1 + 1)^n = \sum_{k=0}^n {n \choose k}(1)^{n-k}(1)^n = 2^n
  $$

> *Theorem.*{: .thm}
> For $n \in \mathbb{N}$ with $n \ge 1$, the alternating sum
>
> $$
  {n \choose 0} - {n \choose 1} + {n \choose 2} - {n \choose 3 } + \dots + (-1)^n{n \choose n} = 0
  $$
>
> *Proof.*{: .prf}
>
> The alternating sum on the L.H.S. is equal to the number of even subsets minus the number of odd subsets.
> As there are exactly half of the subsets with even elements and half with odd elements, so the sum is $0$.
>
> Alternatively,
>
> $$
  (1 - 1)^n = \sum_{k=0}^n {n \choose k}(1)^{n-k}(-1)^n = 0
  $$

> *Theorem.*{: .thm}
> For $n, k \in \mathbb{N}$,
>
> $$
  {k \choose k} + {k + 1 \choose k} + \dots + {n \choose k} = {n+1 \choose k+1}
  $$
>

> *Theorem.*{: .thm}
> For $n, k, r \in \mathbb{N}$,
>
> $$
  {n \choose k} {k \choose r} = {n \choose r} {n-r \choose k-r}
  $$

> *Theorem.*{: .thm}
> For $m, n, k \in \mathbb{N}$,
>
> $$
  \sum_{i = 0}^k {m \choose k - i} {n \choose i} = {m + n \choose k}
  $$

## Polynomial in Binomial Coefficients

## References

* [Richard E Borcherds _Introduction to number theory_ - Lecture 7](https://youtu.be/TBolWCObRgg?list=PL8yHsr3EFj53L8sMbzIhhXSAOpuZ1Fov8)
* [Dexter Chua _Part IA - Numbers and Sets_, 2014 - Chapter 4](https://dec41.user.srcf.net/notes/IA_M/numbers_and_sets.pdf)
