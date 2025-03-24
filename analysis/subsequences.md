---
layout: base
title: Subsequences &#124; Analysis
---

# Subsequences
{: .page-title}

## Partial Order

> *Definition.*{: .def}
> An order $\le$ on is a **partial order** relation if
>
> + $a \le b$ and $b \le c$ implies $a \le c$, and
>
> + $a \le b$ and $b \le a$ iff $a = b$.
>
> A partial order is therefore reflexive, antisymmetric and transitive.

> *Definition.*{: .def}
> A **total order** is a partial order where $\forall x \not= y$, exactly one of $x \le y$ or $y \le x$ holds.
> This means that every two elements must be related.

Suppose that $\le$ is a partial order on a set $A$ and $a \in A$ and $B \subseteq A$.

> *Definition.*{: .def}
> $a$ is an **upper bound** of $B$ if $b \le a$ for all $b \in B$.

Note that an upper bound of $B$ need to belong to $B$. If it does:

> *Definition.*{: .def}
> $a$ is the **greatest** element of $B$ if $a$ is an upper bound and $a \in B$.

> *Definition.*{: .def}
> $a$ is a **maximal** element of $B$ if $a \in B$ and if $b \in B$ and $a \le b$ then $a = b$.

The greatest element has to be the maximal element, but the converse is not true.
It is because partial order does not require every element to be related to each other,
so the maximal element of certain subset of $B$ needs not be the greatest of the whole subset $B$.
In the case of total order, we will have the maximal element being the greatest element.

> *Definition.*{: .def}
> $a$ is an **supremum** of $B$ if $a$ is an upper bound and if $c$ is also an upper bound then $a \le c$.

The definition of **lower bound**, **least** and **minimal** element and **infimum** is the same except for the sign.

## References

* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 1.3
