---
layout: base
title: Determinants &#124; Linear Algebra
---

# Determinants
{: .page-title}

In calculus, we can learn something about the behaviour of a function by computing the derivative.
For example, if $f'$ is positive on an interval $[a, b]$ then $f$ is one-to-one on the interval.
The determinant plays a similar role in linear algebra.

> *Definition.*{: .def}
> A **determinant** is a function $D: \mathbb{F}^n \times \cdots \times \mathbb{F}^n \to \mathbb{F}$
> that assigns each $n$-tuple $\Set{a_1, ..., a_n}$ of vectors in $\mathbb{F}^n$ to an element of $\mathbb{F}$,
> i.e. $D = D(a_1, ..., a_n)$ such that
>
> + $D(..., a_i + a_j, ...) = D(..., a_i, ...)$ for $i \not= j$;
>
> + $D(..., \lambda a_i, ...) = \lambda D(..., a_i, ...)$;
>
> + $D(e_1, ..., e_n) = 1$ for unit vectors $\Set{e_i}$.

> *Proposition.*{: .prop}
> Let $D$ be a determinant function on $\mathbb{F}^n$. Then
>
> + $D(..., a_i, ..., a_j, ...) = - D(..., a_j, ..., a_i, ...)$ in which two of the vectors ($i \not= j$) are interchanged;
>
> + $D(..., a_i, ..., a_i, ...) = 0$ in which two of the vectors are equal;
>
> + $D(..., a_i + \sum_{i \not= j} \lambda_j a_j, ...) = D(..., a_i, ...)$;
>
> + $D = 0$ if $\Set{a_1, ..., a_n}$ is linearly dependent;
>
> + $D(..., a_i + a_i', ...) = D(..., a_i, ...) + D(..., a_i', ...)$.
>
> *Proof.*{: .prf}
>
> + By the axioms,
>
>   $$
    \begin{align*}
    D(..., a_i, ..., a_j, ...)
    &= -D(..., -a_i, ..., a_j, ...) \\
    &= -D(..., -a_i, ..., -a_i + a_j, ...) \\
    &= D(..., -a_i, ..., a_i - a_j, ...) \\
    &= D(..., -a_j, ..., a_i - a_j, ...) \\
    &= -D(..., a_j, ..., a_i - a_j, ...) \\
    &= -D(..., a_j, ..., a_i, ...)
    \end{align*}
    $$
>
> + Interchanging the two rows we have $D(..., a_i, ..., a_i, ...) = - D(..., a_i, ..., a_i, ...)$ so $D = 0$.
>
> + For each $\lambda_j a_j$ with $j \not= i$ and $\lambda_j \not= 0$,
>
>   $$
    \begin{align*}
    D(..., a_i, ..., a_j, ...)
    &= \lambda_j^{-1} D(..., a_i, ..., \lambda_j a_j, ...) \\
    &= \lambda_j^{-1} D(..., a_i + \lambda_j a_j, ..., \lambda_j a_j, ...) \\
    &= D(..., a_i + \lambda_j a_j, ..., a_j, ...)
    \end{align*}
    $$
>
> + Suppose that $a_i = \sum_{i \not= j} \lambda_j a_j$, then
>
>   $$
    \begin{align*}
    D(..., a_i, ...)
    &= - D(..., -a_i, ...) \\
    &= - D(..., -a_i + \sum_{i \not= j} \lambda_j a_j, ...) \\
    &= - D(..., 0, ...) \\
    &= 0
    \end{align*}
    $$
>
> + Extend the vectors $\Set{a_1, ... a_{i-1}, a_{i+1}, ..., a_n}$ to a basis by adding $\hat{a_i}$ to them, then
>
>   $$
    a_i + a_i' = (\lambda_i + \mu_i) \hat{a_i} + \sum_{i \not= j} (\lambda_j + \mu_j) a_j
    $$
>
>   Therefore, we have
>
>   $$
    \begin{align*}
    D(..., a_i + a_i', ...) &= (\lambda_i + \mu_i) D(..., \hat{a_i}, ...) \\
    D(..., a_i, ...) &= \lambda_i D(..., \hat{a_i}, ...) \\
    D(..., a_i', ...) &= \mu_i D(..., \hat{a_i}, ...)
    \end{align*}
    $$
>
>   and $D(..., a_i + a_i', ...) = D(..., a_i, ...) + D(..., a_i', ...)$ because $\mathbb{F}$ is distributive.

## Volume Form

There is another set of axioms we can use to define determinant.

> *Definition.*{: .def}
> A **volume form** $D$ on $\mathbb{F}^n$ is a function $\mathbb{F}^n \times \cdots \times \mathbb{F}^n \to \mathbb{F}$, $(a_1, ..., a_n) \mapsto D(a_1, ..., a_n)$ such that
>
> + $D$ is _multi-linear_, i.e. for each $1 \le i \le n$,
>
>   $$
    D(a_1, ..., a_{i-1}, -, a_{i+1}, ..., a_n) \in (\mathbb{F}^n)^\ast
    $$
>
> + $D$ is _alternating_, i.e. whenever $a_i = a_j$ for some $i \not= j$ then $D(..., a_i, ...) = 0$.

We can see that the conditions correspond to the fifth and second properties proved above.

> *Proposition.*{: .prop}
> Let $D$ be a volume form. Then
>
> + $D(..., a_i + a_j, ...) = D(..., a_i, ...)$ for $i \not= j$;
>
> + $D(..., \lambda a_i, ...) = \lambda D(..., a_i, ...)$.
>
> *Proof.*{: .prf}
>
> We have
>
> $$
  \begin{align*}
  D(..., a_i + a_j, ..., a_j, ...)
  &= D(..., a_i, ..., a_j, ...) + D(..., a_j, ..., a_j, ...) \\
  &= D(..., a_i, ..., a_j, ...)
  \end{align*}
  $$
>
> and $D(..., \lambda a_i, ...) = \lambda D(..., a_i, ...)$ follows immediately from the multi-linearity.

Since the other properties proved above doesn't rely on the third axiom so a volume form also satisfies them.

## Existence and Uniqueness

We can now construct the actual function that satisfies the above.
Before that, we would like to show that if such a function exists, it must be unique.

> *Proposition.*{: .prop}
> Let $D$ and $D'$ be two functions satisfying the axioms. Then for all $a_1, ..., a_n$ in $\mathbb{F}^n$,
>
> $$
  D(..., a_i, ...) = D'(..., a_i, ...)
  $$
>
> *Proof.*{: .prf}
>
> Consider the function
>
> $$
  \Delta(..., a_i, ...) = D(..., a_i, ...) - D'(..., a_i, ...)
  $$
>
> we have
>
> + $\Delta(e_1, ..., e_n) = 0$;
>
> + $\Delta$ changes sign if two of the vectors are interchanged and $\Delta = 0$ if $a_i = a_j$ for $i \not= j$;
>
> + $\Delta(..., \lambda a_i, ...) = \lambda \Delta(..., a_i, ...)$;
>
> + $\Delta(..., a_i + a_i', ...) = \Delta(..., a_i, ...) + \Delta(..., a_i', ...)$.
>
> Suppose that $(e_1, ..., e_n)$ is a basis of $\mathbb{F}^n$. Then
>
> $$
  \begin{align*}
  \Delta(a_1, ..., a_n)
  &= \Delta \left( \sum_{j_1} \lambda_{1 j_1} e_{j_1}, a_2, ..., a_n \right) \\
  &= \sum_{j_1} \lambda_{1 j_1} \Delta(e_{j_1}, a_2, ..., a_n) \\
  &= \sum_{j_1} \sum_{j_2} \lambda_{1 j_1} \lambda_{2 j_2} \Delta(e_{j_1}, e_{j_2}, ..., a_n) \\
  &= \cdots = \sum_{j_1, ..., j_n} \lambda_{1 j_1} \cdots \lambda_{2 j_n} \Delta(e_{j_1}, ..., e_{j_n})
  \end{align*}
  $$
>
> If any of $j_1, ..., j_n$ are equal, then $\Delta(e_{j_1}, ..., e_{j_n}) = 0$.
> If all $j_1, ..., j_n$ are distinct, by interchanging rows repeatedly we have $\Delta(e_{j_1}, ..., e_{j_n}) = \pm \Delta(e_1, ..., e_n) =0$.
> Hence, $\Delta(a_1, ..., a_n) = 0$ as required.

## References

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 5
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 5
