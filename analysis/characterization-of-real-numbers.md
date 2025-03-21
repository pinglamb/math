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
The limitation of rationals is that $L$ has no greatest member and $R$ has no least member, and the irrationals can be defined by cuts like this.

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 1
