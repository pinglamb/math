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

The **sieve of Eratosthenes** is a method to find all the primes less than or equal to a given positive integer $n$.
By listing all the positive integers less than or equal to $n$, we continue to cross out multiples of $2$ (except $2$ itself), then $3$ and so on, all the one that are not crossed out are primes.
The following lemma shows that we can stop when we reach $\sqrt{n}$.

> *Lemma.*{: .lem}
> If $n$ is a composite, then $n$ has a prime factor not exceeding $\sqrt{n}$.
>
> *Proof.*{: .prf}
>
> For $n = ab$ where $1 < a \le b < n$, we must have $a \le \sqrt{n}$ otherwise $ab > n$.
> As $a$ must have a prime divisor, $n$ must have a prime divisor not exceeding $\sqrt{n}$.

## Special Primes

### Mersenne Primes

> *Definition.*{: .def}
> **Mersenne primes** are primes of the form $2^p - 1$, where $p$ is prime.

> *Theorem.*{: .thm}
> If $2^m - 1$ is prime, $m$ must be prime.
>
> *Proof.*{: .prf}
>
> Assume $m = ab$, then
>
> $$
  2^m - 1 = 2^{ab} - 1 = (2^a - 1)(2^{a(b -1)} + 2^{a(b-2)} + ... + 1)
  $$
>
> which is composite, so $m$ must be prime.

Conversely, it is not true though, for example, $p = 11$ is prime but $2^{11} - 1 = 2047 = 23 \cdot 199$ is composite.

### Fermat Primes

> *Definition.*{: .def}
> **Fermat primes** are primes of the form $2^{2^n} + 1$.

> *Theorem.*{: .thm}
> $2^m + 1$ is composite if $m$ has an odd divisor.
>
> *Proof.*{: .prf}
>
> If $m$ is a odd prime, then
>
> $$
  2^m + 1 = (2 + 1)(2^{m-1} - 2^{m-2} + 2^{m-3} + ... + 1)
  $$
>
> which is composite.
>
> If $m = ab$ where $a$ is odd, then
>
> $$
  2^{ab} + 1 = (2^b + 1)(2^{b(a-1)} - 2^{b(a-2)} + 2^{b(a-3)} + ... + 1)
  $$
>
> which is also composite.

Not all of number of this form are primes though, for example, $2^{2^5} + 1$ is divisible by $641$.

## Fundamental Theorem of Arithmetic

The fundamental theorem of arithmetic shows that primes are the multiplicative building blocks of the integers.

> *Lemma.*{: .lem}
> If $(a, b) = 1$ and $a \mid bc$, then $a \mid c$.
>
> *Proof.*{: .prf}
>
> As $(a, b) = 1$, there are integers such that $ma + nb = 1$, multiplying both sides by $c$ we have $mac + nbc = c$.
> As $a \mid mac + nbc$, $a \mid c$.

> *Lemma.*{: .lem}
> If $p$ is a prime divides $a_1a_2...a_n$, which are positive integers, then there is an $a_i$ such that $p \mid a_i$ .
>
> *Proof.*{: .prf}
>
> When $n = 1$, it is trivial.
> Assume it is true for $n$.
> Consider the case $a_1a_2...a_na_{n+1}$ that is divisible by $p$, either $(p, a_1a_2...a_n) = 1$ or $(p, a_1a_2...a_n) = p$.
> If $(p, a_1a_2...a_n) = 1$, then $p \mid a_{n+1}$. If $(p, a_1a_2...a_n) = p$, then by assumption, $p$ divides one of the $a_i$.
> By induction, it is true for all $n$.

> *Theorem.*{: .thm}
> Every positive integer greater than $1$ can be written uniquely as a product of primes, up to order.
>
> *Proof.*{: .prf}
>
> Assume there are some positive integers that cannot be written as product of primes, let $n$ be the least one.
> $n$ must be composite otherwise $n$ is obviously a product of primes.
> Let $n = ab$, as $a < n$ and $b < n$, $a$ and $b$ are products of primes, so is $n$, which contradicts with the assumption.
> Hence, every positive integer can be written as product of primes.
>
> Assume there are two different factorization into primes, i.e.
>
> $$
  n = p_1p_2...p_s = q_1q_2...q_t
  $$
>
> where $p_i$ and $q_j$ are all primes.
> Assume one of the $p_i$ on the left hand side doesn't appear on the right hand side,
> by the above lemma, $p_i$ has to divide one of the $q_j$, which is not possible as they are all primes
> Hence, $p_i$ must equal to some $q_j$ and vice verse, and the factorization is unique.

The unique factorization is a special property of the set of integers that might not be shared by some systems of numbers.
For example, the set of numbers of the form $a + b\sqrt{5}$.
A prime in this form is the numbers that cannot be written as a product of two other numbers other thatn $\pm 1$, for example, $1 \pm \sqrt{5}$.
Note that $6 = 2 \cdot 3 = (1 + \sqrt{5})(1 - \sqrt{5})$, where the factorization is not unique.

The other way of expressing the theorem by Euler is base on the following factorization of _Riemann Zeta Function_:

$$
\begin{align*}
\zeta(s) &= {1 \over 1^s} + {1 \over 2^s} + {1 \over 3^s} + ... \\
         &= \begin{aligned}
            &(1 + 1/2^s + 1/4^s + 1/8^s + ...) \\
            &(1 + 1/3^s + 1/9^s + ...) \\
            &(1 + 1/5^s + 1/25^s + ...) \\
            &\vdots
            \end{aligned} \\
         &= {1 \over 1 - 2^{-s}}{1 \over 1 - 3^{-s}}{1 \over 1 - 5^{-s}} ...
\end{align*}
$$

As an example, as $12 = 2^2 \cdot 3$, we can see that $1/12^s$ is the product of the terms $1/4^s$, $1/3^s$ and many $1$s.
Therefore, the above factorization is true when every integers can be written as product of primes.

It also implies that there are infinitely many primes because by substituting $s = 1$, $\zeta(1)$ is the harmonic series which is infinite.
However, if there are finite number of terms, the factorized form will equal to a finite value.
Hence, there are infinitely many primes.

## Distribution of Primes

> *Definition.*{: .def}
> The function $\pi(x)$, where $x$ is a positive real number, denotes the number of primes not exceeding $x$.

> *Theorem.*{: .thm}
> **[Prime Number Theorem]**
> The ratio of $\pi(x)$ to $x/log(x)$ approaches $1$ as $x$ grows without bound.

The proof involves the use of complex analysis.

## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 3.1, 3.2
