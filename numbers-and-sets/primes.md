---
layout: base
title: Primes &#124; Numbers and Sets
---

# Primes
{: .page-title}

Prime number is the central concept of number theory, which is an integer with precisely two positive integer divisors, $1$ and itself.

> *Definition.*{: .def}
> A **prime** is an integer greater than $1$ that is divisible by no positive integers other than $1$ and itself.

> *Definition.*{: .def}
> A **composite** is an integer greater than $1$ that is not prime.

## Infinitude of Primes

> *Lemma.*{: .lem}
> Every integer greater than $1$ has a prime divisor.
>
> *Proof.*{: .prf}
>
> Assume the set of positive integers greater than $1$ that has no prime divisor is non-empty, by well-ordering principle, it has a least element $n$.
> As $n$ has no prime divisor, $n$ is not prime ($n \mid n$), so $n = ab$.
> But $a$ has prime divisor as $a < n$, and any divisor of $a$ is a divisor of $n$, so $n$ must have a prime divisor.
> It is contradicting with the assumption and hence every integer greater than $1$ has at least one prime divisor.

> *Theorem.*{: .thm}
> There are infinitely many primes.
>
> *Proof.*{: .prf}
>
> Suppose there are finitely many primes, namely $p_1, p_2, ..., p_n$.
>
> Consider the integer $m = p_1p_2...p_n + 1$, which has a prime divisor $p$.
> However, $p$ cannot be one of the known primes because if $p$ is one of them, $p \mid p_1p_2...p_n$ and $p$ has to divide $1$, which is not possible.
> Hence, $p$ has to be a new prime and there are infinitely many primes.

In the proof, $p_1p_2...p_n + 1$ has a new prime divisor but itself is not necessarily a prime, for example, $2 \cdot 3 \cdot 7 \cdot 43 + 1 = 1807 = 13 \cdot 139$.

> *Theorem.*{: .thm}
> **[Dirichlet's Theorem on Arithmetic Progressions]**
> Suppose $a$ and $b$ are relatively prime, then the arithetic progression $an + b$, $n = 1, 2, 3, ...$, contains infinitely primes.

No simple proof is known, but some of arithmetic progression can be proved using similar method as the above, for example:

> *Theorem.*{: .thm}
> There are infinitely many primes of the form $3n + 2$.
>
> *Proof.*{: .prf}
>
> Suppose there are finitely many primes of the form $3n + 2$, namely $p_1, p_2, ..., p_n$.
>
> Consider the integer $m = 3p_1p_2...p_n - 1$, which is of the form $3n + 2$.
> If $m$ is prime, then $m$ is a new prime not listed above.
> If $m$ is not a prime, as the products of $(3a + 1)(3b + 1) = 3(3ab + a + b) + 1$ is always of the form $3n + 1$, so $m$ must have a prime divisor $p$ of the form $3n + 2$.
> $p$ cannot be one of the known primes because if $p$ is one of them, $p \mid 3p_1p_2...p_n$ and $p$ has to divide $-1$, which is not possible.
> Hence, $p$ has to be a new prime of the form $3n + 2$.

## Sieve of Eratosthenes

## Special Primes

## Fundamental Theorem of Arithmetic

## Distribution of Primes

## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 3.1, 3.2
