---
layout: base
title: Characterization of Real Numbers &#124; Analysis
---

# Characterization of Real Numbers
{: .page-title}

In [Numbers and Sets](../numbers-and-sets/numbers.md#real-numbers), we addressed the limitations of rational numbers and the construction of real numbers from that.
More in-depth study will be conducted here about different ways of real numbers constructions and proving them being equivalent.

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

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 1
