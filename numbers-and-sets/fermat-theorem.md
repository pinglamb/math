---
layout: base
title: Fermat's Theorem &#124; Numbers and Sets
---

# Fermat's Theorem
{: .page-title}

The Fermat's Little Theorem, together with Wilson's Theorem and Euler's Theorem, are some of the most important congruences in number theory.

## Wilson's Theorem

> *Theorem.*{: .thm}
> **[Wilson's Theorem]**
> If $p$ is prime, then
>
> $$
  (p - 1)! \equiv -1 \pmod p
  $$
>
> *Proof.*{: .prf}
>
> When $p = 2$, $1! \equiv 1 \equiv -1 \pmod 2$.
>
> When $p \ge 3$, consider the congruence $x^2 \equiv 1 \pmod p$.
> It implies $p \mid (x + 1)(x - 1)$ and the only solution to it is $x \equiv \pm 1 \pmod p$.
> It means that the positive integers $2, 3, ..., p - 2$ can be grouped in pairs so that their product is congruent to $1$ modulo $p$.
> Hence,
>
> $$
  (p - 1)! \equiv (1)(p-1) \equiv -1 \pmod p
  $$

> *Theorem.*{: .thm}
> Conversely, if $(n - 1)! \equiv -1 \pmod n$, then $n$ is prime.
>
> Assume $n$ is composite, $n = ab$ and we have $a \mid (p - 1)!$.
> As $a \mid n$ and $n \mid (n-1)! + 1$, $a \mid (p-1)! + 1$.
> Thus, we have $a \mid (p-1)! + 1 - (p-1)! = 1$, which is a contradiction.

## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 6
* [Richard E Borcherds _Introduction to number theory_ - Lecture 10](https://youtu.be/fgHEKAdErbU
