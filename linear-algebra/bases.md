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
> Since $S$ spans $V$, all $v$ can be written as linear combinations of $S$ in at least one way so we just need to show that there is at most one way.
>
> ($\Rightarrow$) If $v = \sum_{s \in S} \lambda_s s = \sum_{s \in S} \mu_s s$, then $\sum_{s \in S} (\lambda_s - \mu_s) = 0$.
> Since $S$ is linearly independent, $\lambda_s - \mu_s = 0$ for all $s \in S$ and therefore $\lambda_s = \mu_s$.
>
> ($\Leftarrow$) If every element $v \in V$ can be written in at most one way, then $\sum_{s \in S} \lambda_s s = 0$ implies $\lambda_s = 0$ and $S$ is linearly independent.

After knowing the set of linearly independent vectors being able to represent all other vectors uniquely in a vector space, we can now address the properties of the order of these bases.

> *Theorem.*{: .thm}
> **[Steinitz Exchange Lemma]**
> Suppose that $V$ is a vector space over $\mathbb{F}$ and $S = \Set{e_1, ..., e_n}$ is a linearly independent subset of $V$ and $T \subset V$ spans $V$.
> Then there is a subset $D \subset T$ of order $n$ such that $(T \setminus D) \cup S$ spans $V$.
> In particular, $\vert S \vert \le \vert T \vert$.
>
> *Proof.*{: .prf}
>
> Suppose that we have found a subset $D_r \subset T$ of order $0 \le r < n$ such that $T_r = (T \setminus D_r) \cup \Set{e_1, ... e_r}$ spans $V$.
> Obviously the statement is true for $r = 0$ with $D_r = \emptyset$.
> Assume it is true for $r = k - 1$, we can therefore write
>
> $$
  e_k = \sum_{i = 1}^{k-1} \lambda_i e_i + \sum_{j=k}^{n} \mu_j t_j
  $$
>
> Since $\Set{e_1, ... e_k}$ is linearly independent, there exists $\mu_j \not= 0$ with $k \le j \le n$.
> By reordering the terms in the second part of R.H.S., we can assume $\mu_k \not= 0$ and therefore
>
> $$
  t_k = {1 \over \mu_k} \left( e_k - \sum_{i=1}^{k-1} \lambda_i e_i - \sum_{j=k+1}^{n} \mu_j t_j \right)
  $$
>
> With $T_k = T_{k-1} \setminus \Set{t_k} \cup \Set{e_k} = \Set{e_1, e_2, ..., e_k, t_{k+1}, ..., t_n}$,
> since $t_k \in \langle T_k \rangle$, by the inductive hypothesis, $\langle T_k \rangle = V$.

> *Corollary.*{: .cor}
> If $\Set{e_1, ..., e_n} \subset V$ is linearly independent and $\Set{f_1, ..., f_m}$ spans $V$.
> Then $n \le m$ and possibly after reordering $\Set{e_1, ..., e_n, f_{n+1}, ..., f_m}$ spans $V$.
>
> *Proof.*{: .prf}
>
> If $m < n$, by Steinitz exchange lemma, we can replace $\Set{f_1, ..., f_m}$ with $\Set{e_1, ..., e_m}$ that still spans $V$.
> Therefore, we have $e_{m+1} \in \langle \Set{e_1, ..., e_m} \rangle$ which contradicts with $\Set{e_1, ..., e_n}$ being linearly independent.

> *Corollary.*{: .cor}
> Every basis of a vector space $V$ has the same order.
>
> *Proof.*{: .prf}
>
> Let $S$ and $T$ be two bases of $V$.
> Since $S$ spans $V$ and $T$ is linearly independent, $\vert T \vert \le \vert S \vert$.
> Similarily, since $T$ spans $V$ and $S$ is linearly independent, $\vert S \vert \le \vert T \vert$.
> Hence, $\vert S \vert = \vert T \vert$.

> *Corollary.*{: .cor}
> Suppose that $V$ is a vector space with a basis of order $n$. Then
>
> + any $n$ linearly independent vectors in $V$ form a basis for $V$;
>
> + any $n$ vectors in $V$ that span $V$ form a basis for $V$;
>
> + any set of linearly independent vectors in $V$ can be extended to a basis for $V$;
>
> + any finite spanning set in $V$ contains a basis for $V$.
>
> *Proof.*{: .prf}
>
> Let $S$ be a basis of $V$.
>
> + We can replace the elements of $S$ with the $n$ linearly independent vectors and it still spans $V$ so they form a basis.
>
> + If the $n$ vectors are linearly dependent, we can remove one of them and the $n-1$ vectors still spans $V$.
>   Then we have $\vert S \vert = n > n - 1$ which is a contradiction.
>
> + Direct consequence of Steinitz exchange lemma.
>
> + For any finite spanning set $T$, if it is linearly independent, then it is a basis for $V$.
>   If not, it means there exists $t \in T$ such that $T' = T \setminus \Set{t_j}$ still spans $V$ and we can repeat this process.
>   Since $S$ spans $V$, it terminates when $\vert T' \vert = n$ which form a basis for $V$.

## Dimensions

Since all the bases are of the same order, we can know define the dimension of a vector space.

> *Definition.*{: .def}
> If a vector space $V$ over $\mathbb{F}$ is finite-dimensional with basis $S$, the **dimension** of $V$ is defined by
>
> $$
  \dim_{\mathbb{F}} = \dim V = |S|
  $$

Note that although the dimension is independent on the choice of $S$, it does depend on the field $\mathbb{F}$.

> *Proposition.*{: .prop}
> If $V$ is finite dimensional vector space and $U$ is a proper subspace of $V$ then $U$ is also finite dimensional and
>
> $$
  \dim U < \dim V
  $$
>
> *Proof.*{: .prf}
>
> Let $S \subset U$ be a linearly independent subset of maximal possible size.
> If there exists $u \in U \setminus \langle S \rangle$ then $S \cup \Set{u}$ is linearly independent which contradicts the maximality of $S$.
> Therefore, $\langle S \rangle = U$ and $\dim U = \vert S \vert$.
>
> Since $U$ is a proper subspace, there exists $v \in V \setminus U$ such that $S \cup \Set{v}$ is linearly independent subset of $V$.
> Hence,
>
> $$
  \dim U < \dim U + 1 = |S| + 1 = |S \cup \Set{v}| \le \dim V
  $$

> *Proposition.*{: .prop}
> If $V$ is a finite dimensional vector space and $U$ is a subspace then
>
> $$
  \dim V = \dim U + \dim V/U
  $$
>
> *Proof.*{: .prf}
>
> Let $\Set{u_1, ..., u_m}$ be a basis for $U$ which extended to a basis $\Set{u_1, ..., u_m, v_{m+1}, ..., v_{n}}$ for $V$.
>
> For any vector $v + U \in V/U$, we have
>
> $$
  v = \sum_{i = 1}^m \lambda_i u_i + \sum_{j=m+1}^n \mu_j v_j
  $$
>
> and therefore
>
> $$
  v + U = \sum_{i = 1}^m \lambda_i (u_i + U) + \sum_{j=m+1}^n \mu_j (v_j + U) = 0 + \sum_{j=m+1}^n \mu_j (v_j + U)
  $$
>
> It implies $\langle S = \Set{v_{m+1} + U, ..., v_n + U} \rangle = V/U$.
>
> Suppose that
>
> $$
  \sum_{j=m+1}^n \mu_j (v_j + U) = 0 + U
  $$
>
> Then $\sum_{j=m+1}^n \mu_j v_j \in U$ so we can write
>
> $$
  \sum_{j=m+1}^n \mu_j v_j = \sum_{i=1}^m \lambda_i u_i
  $$
>
> for some $\lambda_i \in \mathbb{F}$.
> Since $\Set{u_i, ... u_m, v_{m+1}, ..., v_n}$ is linearly independent, all $\lambda_i$ and $\mu_j$ must be zero and therefore $S$ is linearly independent in $V/U$.
> Hence, $\dim V/U = \vert S \vert = \dim V - \dim U$.

> *Proposition.*{: .prop}
> If $U$ and $W$ are finite dimensional subspaces of a vector space $V$ then $U \cap W$ and $U + W$ are finite dimensional subspaces and
>
> $$
  \dim (U + W) + \dim (U \cap W) = \dim U + \dim W
  $$

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 1.2
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 2.4, 2.5
