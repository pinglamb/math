---
layout: base
title: Bases &#124; Linear Algebra
---

# Bases
{: .page-title}

> *Definition.*{: .def}
> Let $\Set{s_1, s_2, ..., s_m}$ be a set of vectors in $V$.
> Then $s$ is a **linear combination** of $\Set{s_1, s_2, ..., s_m}$ if there exists $\lambda_i \in \mathbb{F}$ such that
>
> $$
  s = \sum_{i=1}^m \lambda_i s_i
  $$

> *Proposition.*{: .prop}
> If $S$ is a subspace of $V$, then every linear combination of $\Set{s_i}$ belongs to $S$.
>
> *Proof.*{: .prf}
>
> It can derived by induction using the axioms.

The process of forming linear combinations leads to a method of constructing subspaces.

> *Definition.*{: .def}
> Let $V$ be a vector space over $\mathbb{F}$ and $S \subset V$.
> Then the **span** of $S$ in $V$ is the set of all _finite_ linear combinations of elements of $S$, i.e.
>
> $$
  \langle S \rangle = \Set{\sum_{i = 1}^n \lambda_i s_i : \lambda_i \in \mathbb{F}, s_i \in S, n \ge 0}
  $$

> *Proposition.*{: .prop}
> The span $\langle S \rangle$ is the smallest subspace containing the set $S$, i.e.
> if $U$ is a subspace containing $S$ then $\langle S \rangle \subset U$.
>
> *Proof.*{: .prf}
>
> $$
  \lambda \sum_{i=1}^n \lambda_i s_i + \mu \sum_{i=1}^n \mu_i s_i = \sum_{i=1}^n (\lambda \lambda_i + \mu \mu_i) s_i
  $$
>
> which is again a linear combination of $\Set{s_i}$.

Conversely, given a vector space $V$, we want to know what and how many vectors to include such that $\Set{s_i}$ is the smallest set that spans $V$.
It leads to the following ideas.

> *Definition.*{: .def}
> An arbitrary finite subset $S \subset V$ is **linearly independent** iff
>
> $$
  \sum_{i=1}^n \lambda_i s_i = 0 \quad \implies \quad \lambda_i = 0
  $$

If the subset $S$ is linearly dependent, it implies that some vectors in the set can be expressed as linear combination of other vectors and are redundant.

> *Definition.*{: .def}
> $S \subset V$ is a **basis** for $V$ if $S$ spans $V$ and is linearly independent.

> *Definition.*{: .def}
> The **components** of $v \in V$ respect to a ordered basis $S$ are the scalars $\lambda_s \in \mathbb{F}$ such that
>
> $$
  v = \sum_{s \in S} \lambda_s s
  $$
>
> with all but finitely many $\lambda_s = 0$.

Note that the term "all but finitely many $\lambda_s = 0$" means that there are finitely many non-zero $\lambda_s$ so that we are summing over finite terms.

> *Proposition.*{: .prop}
> Suppose that $V$ is a vector space over $\mathbb{F}$.
> Then $S \subset V$ is a basis for $V$ iff the component representation of every element $v \in V$ is unique.
>
> *Proof.*{: .prf}
>
>
> Since $S$ spans $V$, all $v$ can be written as linear combinations of $S$ in at least one way so we just need to show that there is at most one way.
>
> ($\Rightarrow$) If $v = \sum_{s \in S} \lambda_s s = \sum_{s \in S} \mu_s s$, then $\sum_{s \in S} (\lambda_s - \mu_s) = 0$.
> Since $S$ is linearly independent, $\lambda_s - \mu_s = 0$ for all $s \in S$ and therefore $\lambda_s = \mu_s$.
>
> ($\Leftarrow$) If every element $v \in V$ can be written in at most one way, then $\sum_{s \in S} \lambda_s s = 0$ implies $\lambda_s = 0$ and $S$ is linearly independent.

It is not yet clear if a basis is the smallest, which can be proved by showing all bases must have the same size.

> *Theorem.*{: .thm}
> **[Steinitz Exchange Lemma]**
> Suppose that $V$ is a vector space over $\mathbb{F}$ and $S = \Set{e_1, ..., e_n}$ is a linearly independent subset of $V$ and $T \subset V$ spans $V$.
> Then there is a subset $D \subset T$ of order $n$ such that $(T \setminus D) \cup S$ spans $V$.
> In particular, $\vert S \vert \le \vert T \vert$.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 1.2
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 2.4, 2.5
