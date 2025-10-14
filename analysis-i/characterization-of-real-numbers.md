---
layout: base
title: Characterization of Real Numbers &#124; Analysis I
---

# Characterization of Real Numbers
{: .page-title}

In [Numbers and Sets](../numbers-and-sets/numbers.md#real-numbers), we addressed the limitations of rational numbers and the construction of real numbers from that.
More in-depth study will be conducted here about different ways of characterizing real numbers and proving them being equivalent.

Every real numbers study starts with this proposition.

> *Proposition.*{: .prop}
> $\sqrt{2}$ is irrational.
>
> *Proof.*{: .prf}
>
> Assume the rational $a/b = \sqrt{2}$, where $a, b$ have no common factors.
> Then
>
> $$
  a^2 = 2b^2
  $$
>
> $a$ is even and therefore $a = 2c$ for some integer $c$. Thus,
>
> $$
  2b^2 = (2c)^2 = 4c^2 \implies b^2 = 2c^2
  $$
>
> $b$ is also even and has a common factor $2$ with $a$ which is a contradiction.

## Dedekind's Axiom

The procedure of Dedekind can be applied to isolate a real number whose square is $2$.
Note that the positive rational numbers fall into two sets, where $L$ contains the rationals with squares less than $2$ and $R$ contains those with squares greater than $2$.
The limitation of rationals is that $L$ has no greatest member and $R$ has no least member, and the irrationals can be defined by cuts like this which leads to the axiom of completeness.

> *Definition.*{: .def}
> **[Axiom of Completeness/Dedekind's Axiom]**
> Suppose that the system of all real numbers is divided into two sets $L, R$,
> every member $l$ of $L$ being less than every member of $r$ of $R$ (and neither set being empty).
> Then there is a dividing member $\xi$ with the properties that every number less than $\xi$ belongs to $L$ and every member greater than $\xi$ belongs to $R$.
> The member $\xi$ itself may belong either to $L$ or to $R$.
> If it is in $L$, it is the greatest member of $L$. If it is in $R$, it is the least member of $R$.

Such a division of real numbers into two sets is called **Dedekind cut**.
It leads to a theorem which is one of the foundation-stones of analysis.

> *Theorem.*{: .thm}
> If $S$ is a (non-empty) set of numbers which is bounded above, then of all the upper bounds there is a least one.
>
> *Proof.*{: .prf}
>
> For all real numbers $x$, divide them into two sets $L$ and $R$ by
> putting $x$ in $L$ if there is a member $s \in S$ such that $s > x$ or
> putting $x$ in $R$ if for all members $s \in S$, $s \le x$.
>
> Then, neither $L$ nor $R$ is empty as $x = s - 1 \in L$ for a member $s \in S$ and $M \in R$ where $S$ is bounded above by $M$.
> By Dedekind's Axiom, there is dividing member $\xi$ such that for any $\varepsilon > 0$, $\xi - \varepsilon \in L$ and $\xi + \varepsilon \in R$,
> and $\xi$ may belong to $L$ or $R$.
>
> Assume $\xi \in L$, then $\xi$ is the greatest lower bound and there is a member $s \in S$ such that $s > \xi$.
> Consider $\eta = (s + \xi)/2$, $s > \eta > \xi$ so $\eta \in L$ and greater than $\xi$ which is a contradiction.
> Hence, $\xi \in R$ and is the least upper bound.

The least upper bound has a expressive and concise name.

> *Definition.*{: .def}
> Given a set $S$, the **supremum** of $S$, denoted by $\sup S$, is a number (not necessary in $S$) such that
>
> + $s \le \sup S$ for all $s \in S$,
>
> + for every positive $\varepsilon$, there is an $s \in S$ for which $s > \sup S - \varepsilon$, i.e. $\sup S - \varepsilon \in L$.

By reversing the signs, we have

> *Definition.*{: .def}
> Given a set $S$, the **infimum** of $S$, denoted by $\inf S$, is a number (not necessary in $S$) such that
>
> + $s \ge \inf S$ for all $s \in S$,
>
> + for every positive $\varepsilon$, there is an $s \in S$ for which $s < \inf S + \varepsilon$, i.e. $\inf S + \varepsilon \in R$.

Supremum and infimum are close to maximum and minimum, but are more useful in analysis in the sense of limits.
An infinite set of real numbers don't necessary have maximum or minimum but they can have supremum/infimum.
For example, $\mathbb{R}^+$ has no minimum value, but $0$ is the infimum.

## Monotone-sequence Property

Another way to characterize real numbers is by monotone-sequence property.
We have already proved that [bounded monotonic sequence converges](subsequences.md#bounded-monotonic-convergent) by the least upper bound property.
Now, we assume such property and derive the least upper bound property to show that they are equivalent.

> *Definition.*{: .def}
> **[Monotone-sequence Property]**
> An ordered field has the monotone-sequence property if every increasing sequence that is bounded above converges.

> *Proposition.*{: .prop}
> Monotone-sequence property implies Archimedean property.
>
> *Proof.*{: .prf}
>
> Since $1/n$ is decreasing and bounded below by $0$, it converges.
> Let $L$ be the limit. $L > 0$ is impossible as we can always find an $N$ such that $1/N < L$.
> Hence, $L = 0$ and $1/n \to 0$.

> *Proposition.*{: .prop}
> Monotone-sequence property implies least upper bound property.
>
> *Proof.*{: .prf}
>
> Let $S$ be a set that is bounded above. Pick $l_0$ and $r_0$ such that $l_0$ is not an upper bound and $r_0$ is an upper bound.
> By repeated bisection that if $(l_n + r_n)/2$ is an upper bound, then $l_{n+1} = l_n$ and $r_{n+1} = (l_n + r_n)/2$.
>
> Then, we have two sequences $(l_n)$ and $(r_n)$ such that
>
> $$
  l_0 \le l_1 \le l_2 \le \cdots \quad \text{and} \quad r_0 \ge r_1 \ge r_2 \ge \cdots
  $$
>
> and also
>
> $$
  r_n - l_n = {r_0 - l_0 \over 2^n} \to 0
  $$
>
> As $(l_n)$ is increasing and bounded above by $r_0$, $(l_n)$ converges and has a limit $L$.
> Also, as $r_n - l_n \to 0$, $r_n \to L$ as well.
>
> $L$ is an upper bound of $S$ otherwise there is a $s \in S$ such that $s > L$ and $r_n \to L$ will imply there is some $r_N < s$ which contradicts.
>
> $L$ has to be the least otherwise there is an upper bound $r < L$ and $l_n \to L$ will imply there is some $l_N > r$ which contradicts.

In other words, we can use repeated bisection to construct two sequences, one increasing and bounded above and another one decreasing and bounded below,
that converges to the same limit and the limit is the least upper bound.

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 1
