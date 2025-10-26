---
layout: base
title: Quotient Spaces &#124; Linear Algebra
---

# Quotient Spaces
{: .page-title}

New vector spaces can be constructed from other vector spaces.
One of the important contructions is the quotient spaces which is base on equivalence relation of sets.

> *Definition.*{: .def}
> Let $\sim$ be an equivalence relation on a set $X$.
> The set of equivalence classes $X/{\sim} = \Set{[a] : a \in X}$ is called the **quotient set** of $X$ by $\sim$.

> *Proposition.*{: .prop}
> Let $V$ be a vector space over $\mathbb{F}$ and $Y$ be a subspace of $V$.
> Then the relation $\sim$ on the set $V$ defined by
>
> $$
  v \sim v' \qquad \text{if} \qquad v - v' \in Y
  $$
>
> is an equivalence relation.
> The quotient set $V/{\sim}$ is a vector space over $\mathbb{F}$, with addition $[v] + [v'] = [v + v']$
> and scalar multiplication $\lambda [v] = [\lambda v]$.
>
> *Proof.*{: .prf}
>
> $v - v = 0 \in Y$ so $\sim$ is reflexive.
> $v - v' = -(v' - v) \in Y$ so $\sim$ is symmetric.
> $v - v', v' - v'' \in Y$ implies $v - v' + v' - v'' = v - v'' \in Y$ so $\sim$ is transitive.
>
> For $[v] = [w]$ and $[v'] = [w']$, $v - w, v' - w' \in Y$. $v - w + v' - w' = (v + v') - (w + w') \in Y$ so $[v + v'] = [w + w']$ and addition is well-defined.
>
> For $[v] = [v']$, $v - v' \in Y$. $\lambda (v - v') = \lambda v - \lambda v' \in Y$ so $[\lambda v] = [\lambda v'$ and scalar multiplication is well-defined.
>
> The vector space axioms can be easily verified using the definitions.

> *Definition.*{: .def}
> The vector space $V/{\sim}$ defined above is called the **quotient space** of $V$ by $Y$, denoted by $V/Y$.

> *Proposition.*{: .prop}
> Suppose that $Y$ is finite dimensional, then
>
> $$
  \dim V = \dim Y + \dim V/Y
  $$
>
> *Proof.*{: .prf}
>
> The mapping $\alpha: V \to V/Y$ defined by $\alpha(v) = [v]$ is linear and surjective.
> Obviously, $n(\alpha) = \dim Y$ and $r(\alpha) = \dim V/Y$.
> Hence, by rank-nullity theorem (base on direct proof), $\dim V = \dim Y + \dim V/Y$.

## Reference

* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 8.26
