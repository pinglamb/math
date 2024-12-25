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
> Let $a$ and $b$ be integers with $(a, b) = d$, then $(a/d, b/d) = 1$, i.e. $a/d$ and $b/d$ are relatively prime.
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

## References

* Kenneth H Rosen _Elementary Number Theory_, 2011 - Chapter 1, 3.3
* [Dexter Chua _Part IA - Numbers and Sets_, 2014 - Chapter 3](https://dec41.user.srcf.net/notes/IA_M/numbers_and_sets.pdf)
