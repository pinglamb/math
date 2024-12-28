---
layout: base
title: Divisibility &#124; Numbers and Sets
---

# Divisibility
{: .page-title}

The concept of the divisibility of one integer by another is central in number theory.

> *Definition.*{: .def}
> If $a$ and $b$ are integers with $a \not = 0$, we say $a$ **divides** $b$ (or $b$ is **divisible** by $a$)
> if there is an integer $c$ such that $b = ac$.
> We write $a \mid b$.

> *Lemma.*{: .lem}
> If $a \mid b$ and $b \mid c$, then $a \mid c$.
> In order words, the relation of divisibility is transitive.
>
> *Proof.*{: .prf}
>
> $b = am$ and $c = bn$, so $c = a(mn)$ and $a \mid c$.

> *Lemma.*{: .lem}
> If $c \mid a$ and $c \mid b$, then $c \mid (ma + nb)$ for all integers $m, n$.
> In order words, divisibility is linear.
>
> *Proof.*{: .prf}
>
> $a = ce$ and $b = cf$, so $ma + nb = c(me + nf)$ and $c \mid (ma + nb)$.

## Division Algorithm

> *Theorem.*{: .thm}
> If $a$ and $b$ are integers such that $b > 0$, then there are unique integers $q$ and $r$ such that $a = bq + r$ with $0 \le r < b$.
>
> *Proof.*{: .prf}
>
> Consider the set $S = \set{a - bk : k \in \mathbb{Z}, a - bk \ge 0}$.
> The set is non-empty as $a - bk$ is positive when $k < a/b$.
> By the well-ordering principle, $S$ has a least element $r = a - bq$ for some $q \in \mathbb{Z}$.
> $r \ge 0$ by construction. If $r \ge b$, then $r > r - b = a - b(q + 1) \ge 0$, which contradicts with $r$ being the least element.
> Hence, $a = bq + r$ with $0 \le r < b$.
>
> Assume $a = bq + r = bq' + r'$, we have $b(q - q') = r' - r$.
> So $b \mid r' - r$ and it is only possible when $r' - r = 0$ and thus $r' = r$.
> Substituding it back, we have $q = q'$ as well and hence $q$ and $r$ are unique.

## Greatest Common Divisors

> *Definition.*{: .def}
> The **greatest common divisor** of two integers $a, b$, denoted by $(a, b)$, is the largest integer that divides both $a$ and $b$.

> *Definition.*{: .def}
> The integers $a$ and $b$ are **relatively prime** if $a$ and $b$ have greatest common divisor $(a, b) = 1$.

> *Theorem.*{: .thm}
> Suppose $(a, b) = d$, then $(a/d, b/d) = 1$, i.e. $a/d$ and $b/d$ are relatively prime.
>
> *Proof.*{: .prf}
>
> Assume $e \mid a/d$ and $e \mid b/d$, $a = edm$ and $b = edn$, we have $(a, b) = ed = d$.
> Hence, $(a/d, b/d) = 1$.

> *Corollary.*{: .cor}
> The rational $a/b = p/q$ for some integers $p, q$ where $(p, q) = 1$.
> $p/q$ is said to be in _lowest terms_.
>
> *Proof.*{: .prf}
>
> Suppose $(a, b) = d$, then set $p = a/d$ and $q = b/d$ we have $p/q = (a/d)/(b/d) = a/b$ with $(p, q) = 1$.

> *Theorem.*{: .thm}
> $(a + bc, b) = (a, b)$.
>
> *Proof.*{: .prf}
>
> Let $d$ be a common divisor of $a$ and $b$, then $d$ divides $a + bc$ and is a common disivor of $a + bc$ and $b$.
> Let $e$ be a common divisor of $a + bc$ and $b$, then $e$ divides $(a + bc) - bc = a$ and is a common divisor of $a$ and $b$.
> Hence, they have the same set of common divisors and $(a + bc, b) = (a, b)$.

> *Theorem.*{: .thm}
> $(a, b)$ is the least positive integer that is linear combination of $a$ and $b$.
>
> *Proof.*{: .prf}
>
> Let $S = \set{ma + nb \ge 0 : m, n \in \mathbb{Z}}$, $S$ is non-empty as either $a + 0b$ or $-a + 0b$ is positive so $S$ has a least element $d = ma + nb$.
>
> By division algorithm, $a = dq + r$, where $0 \le r < d$. We have
>
> $$
  r = a - dq = a - q(ma + nb) = a(1 - qm) - b(qn)
  $$
>
> so $r$ is also a linear combination of $a$ and $b$. As $d$ is the least, $r = 0$ and $d \mid a$.
> Similarily, we have $d \mid b$.
>
> Thus, $d$ is a common divisor of $a$ and $b$. As any $c$ that $c \mid a$ and $c \mid b$, $c \mid ma + nb$ and $c \mid d$, so $d = (a, b)$.

> *Corollary.*{: .cor}
> **[Bezout's Identity]** $ma + nb = (a, b)$ for some integers $m, n$.

> *Corollary.*{: .cor}
> $a$ and $b$ are relatively prime iff there are integers $m$ and $n$ such that $ma + nb = 1$.

> *Theorem.*{: .thm}
> All linear combinations of $a$ and $b$ are multiples of $(a, b)$.
>
> *Proof.*{: .prf}
>
> For $d = (a, b)$, by definition, $d \mid a$ and $d \mid b$. Hence, $d \mid ma + nb$ and all linear combinations are multiples of $(a, b)$.
>
> As there are integers $m$ and $n$ such that $d = ma + nb$, so we have $kd = (km)a + (kn)b$ for $k \in \mathbb{Z}$ and all multiples of $(a, b)$ can be expressed as linear combination.

There is an alternative definition of greatest common divisor without depending on ordering, which is useful in the study of algebraic number theory.

> *Theorem.*{: .thm}
> A positive integer $d = (a, b)$ iff
>
> + $d \mid a$ and $d \mid b$
>
> + $\forall c \in \mathbb{Z}, c \mid a \land c \mid b \implies c \mid d$
>
> *Proof.*{: .prf}
>
> ($\Rightarrow$) If $d = (a, b)$, $d \mid a$ and $d \mid b$ by definition.
> As $d = ma + nb$, any common divisior $c$ of $a$ and $b$ divides $d$.
>
> ($\Leftarrow$) $d$ is a common divisor of $a$ and $b$ and for any other common divisor $c$, we have $d = ck$ for some integer $k$.
> Hence, $c = d/k \le d$ so $d$ is the greatest commmon divisor.

In other words, it means that the greatest common divisor is divisible by all other common divisors.

## Euclidean Algorithm

> *Lemma.*{: .lem}
> If $e = dq + r$, then $(e, d) = (d, r)$.
>
> *Proof.*{: .prf}
>
> As $(a + bc, b) = (a, c).


The Euclidean Algorithm is an extremely fast way to find greatest common divisors.



## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 1, 3.3
* [Dexter Chua _Part IA - Numbers and Sets_, 2014 - Chapter 3](https://dec41.user.srcf.net/notes/IA_M/numbers_and_sets.pdf)
