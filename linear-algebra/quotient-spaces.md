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
> The equivalence classes $[v]$ are denoted by $v + Y$ and therefore $(v + Y) + (v' + Y) = v + v' + Y$ and $\lambda (v + Y) = \lambda v + Y$.

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

We can now investigate what this construction means to linear transformations and matrices.

> *Proposition.*{: .prop}
> Let $\alpha \in \mathcal{L}(V, V)$ and $Y$ be a subspace of $V$ that is invariant relative to $\alpha$, i.e. $\alpha(Y) \subset Y$.
> Then the mappings
>
> $$
  \alpha_Y : Y \to Y, \alpha_Y(y) = \alpha(y) \qquad \text{and} \qquad \alpha_{V/Y} : V/Y \to V/Y, \alpha_{V/Y}(v + Y) = \alpha(v) + Y
  $$
>
> are linear, i.e. $\alpha_Y \in \mathcal{L}(Y, Y)$ and $\alpha_{V/Y} \in \mathcal{L}(V/Y, V/Y)$.
>
> *Proof.*{: .prf}
>
> $\alpha_Y \in \mathcal{L}(Y, Y)$ since $Y$ is invariant relative to $\alpha$.
>
> If $v + Y = v' + Y$, then $v - v' \in Y$ implies $\alpha(v) - \alpha(v') = \alpha(v - v') \in Y$, so $\alpha(v) + Y = \alpha(v') + Y$ and $\alpha_{V/Y}$ is well-defined.
> Also,
>
> $$
  \begin{align*}
  \alpha_{V/Y}(\lambda (v + Y) + \mu (v' + Y)) &= \alpha_{V/Y}(\lambda v + \mu v' + Y) \\
  &= \alpha(\lambda v + \mu v') + Y \\
  &= \lambda \alpha(v) + \mu \alpha(v') + Y \\
  &= \lambda \alpha_{V/Y}(v + Y) + \mu \alpha_{V/Y}(v' + Y)
  \end{align*}
  $$
>
> so $\alpha_{V/Y} \in \mathcal{L}(V/Y, V/Y)$.

> *Definition.*{: .def}
> The linear map $\alpha_Y : Y \to Y, \alpha_Y(y) = \alpha(y)$ is called the **restriction** of $I$ to $Y$.

> *Definition.*{: .def}
> The linear map $\alpha_{V/Y} : V/Y \to V/Y, \alpha_{V/Y}(v + Y) = \alpha(v) + Y$ is called the transformation on $V/Y$ **induced** by $\alpha$.

> *Proposition.*{: .prop}
> Let $Y$ be a nonzero subspace of a finite dimensional vector space $V$ which is invariant relative to a linear map $\alpha \in \mathcal{L}(V, V)$.
> Let $\Set{e_1, ..., e_k}$ be a basis of $Y$ and extend it to $\Set{e_1, ..., e_n}$ as a basis for $V$.
> If $Y \not= V$, then $k < n$ and $\Set{e_{k+1} + Y, ..., e_n + Y}$ is a basis of $V/Y$.
> Let $A$ be the matrix of $\alpha$ with respect to the basis $\Set{e_1, ..., e_n}$.
> Then $A$ has the form
>
> $$
  A = \begin{pmatrix}
  A_1 & A_3 \\
  0 & A_2 \\
  \end{pmatrix}
  $$
>
> where $A_1$ is the $k$-by-$k$ matrix of $\alpha_Y$ with respect to $\Set{e_1, ..., e_k}$ and
> $A_2$ is the $(n-k)$-by-$(n-k)$ matrix of $\alpha_{V/Y}$ with respect to $\Set{e_{k+1} + Y, ..., e_n + Y}$.
>
> *Proof.*{: .prf}
>
> For any $v \in V$, we have $v = \sum \lambda_i e_i$, therefore
>
> $$
  [v] = \sum_{i=1}^n \lambda_i [e_i] = \sum_{i=k+1}^n \lambda_i [e_i]
  $$
>
> and $\langle [e_{k+1}], ..., [e_n] \rangle = V/Y$.
>
> Suppose that $\sum_{i=k+1}^n \lambda_i [e_i] = [0]$. Then $\sum_{i=k+1}^n \lambda_i e_i \in Y$ and we have
>
> $$
  \sum_{i=k+1}^n \lambda_i e_i = \sum_{j=1}^k \mu_j e_j
  $$
>
> which implies $\lambda_i = \mu_j = 0$ and $\Set{e_{k+1} + Y, ..., e_n + Y}$ are linearly independent.
>
> The matrix of $\alpha$ is the mapping of basis vectors between domain and codomain.
> For $Y$ to be invariant, we must have $\alpha(e_i) = \sum_{j=1}^k A_{ji} e_j$ for $1 \le i \le k$ which results with the form of first column.
> For $k+1 \le i \le n$, $\alpha(e_i) = \sum_{j=1}^k A_{ji} e_j + \sum_{j=k+1}^n A_{ji} e_j$ so $\alpha_{V/Y}([e_i]) = [\alpha(e_i)] = \sum_{j=k+1}^n A_{ji} [e_j]$ which is $A_2$.

## Reference

* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 8.26
