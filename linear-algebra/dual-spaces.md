---
layout: base
title: Dual Spaces &#124; Linear Algebra
---

# Dual Spaces
{: .page-title}

The other way to construct is base on the idea that every vector space $V$ and linear map $\alpha$,
there is a vector space $V^\ast$ which mirrors $V$, and a linear map $\alpha^\ast$ of $V^\ast$ which mirrors $\alpha$.

> *Definition.*{: .def}
> Let $V$ be a finite dimensional vector space over $\mathbb{F}$.
> The **dual space** $V^\ast$ of $V$ is defined to be the vector space $\mathcal{L}(V, \mathbb{F})$.
> The elements of $V^\ast$ are **linear forms/functions** from $V$ into $\mathbb{F}$,
> i.e. $f: V \to \mathbb{F} \in V^\ast$ such that $f(v_1 + v_2) = f(v_1) + f(v_2)$ and $f(\lambda v) = \lambda f(v)$.
> The addition and scalar multiplication of $V^\ast$ are $(f_1 + f_2)(v) = f_1(v) + f_2(v)$ and $(\lambda f)(v) = f(\lambda v)$.

> *Proposition.*{: .prop}
> Suppose that $V$ is finite dimensional vector space over $\mathbb{F}$ with basis $(e_1, ..., e_n)$.
> Then $V^\ast$ has a basis $(f_1, ..., f_n)$ such that $f_i(e_j) = \delta_{ij}$.
>
> *Proof.*{: .prf}
>
> The linear functions ${f_i}$ exist because we can always map the basis vectors to arbitrary vectors in the codomain.
> For $(f_1, ..., f_n)$ to be a basis, we need to show that it is linearly independent and spans $V^\ast$.
> Since they are linear functions, we just need to care about how they transform the basis vectors $(e_1, ..., e_n)$ as
> $f = f'$ iff $f(e_j) = f'(e_j)$ for $j = 1, ..., n$.
>
> Suppose that $\sum \lambda_i f_i = 0$, in which $0$ is the zero function $0(v) = 0$ for all $v \in V$.
> Since
>
> $$
  \sum_i \lambda_i f_i(e_j) = \sum_i \lambda_i \delta_{ij} = \lambda_j = 0(e_j) = 0
  $$
>
> for all $j$, $\Set{f_i}$ is linearly independent.
>
> For any linear function $f \in V^\ast$, let $f(e_i) = \lambda_i$ for $i = 1, ..., n$. Then
>
> $$
  \sum_i \lambda_i f_i(e_j) = \lambda_j = f(e_j)
  $$
>
> and $\langle f_i \rangle = V^\ast$.

> *Definition.*{: .def}
> The basis $(f_1, ..., f_n)$ is called the **dual basis** of $V^\ast$ with respect to $(e_1, ..., e_n)$.

> *Corollary.*{: .cor}
> If $V$ is finite dimensional, then $\dim V = \dim V^\ast$.

## Annihilator

> *Definition.*{: .def}
> If $U \subset V$ then the **annihilator** of $U$ is defined by
>
> $$
  U^\circ = \Set{f \in V^\ast : \forall u \in U, f(u) = 0} \subset V^\ast
  $$

> *Proposition.*{: .prop}
> Suppose that $V$ is finite dimensional and $U \subset V$ is a subspace.
> Then $\dim U + \dim U^\circ = \dim V$.
>
> *Proof.*{: .prf}
>
> Let $(e_1, ..., e_k)$ be a basis for $U$ extend to a basis $(e_1, ..., e_n)$ for $V$, and $(f_1, ..., f_n)$ be the corresponding dual basis for $V^\ast$.
> Since $f_{k+1}(e_j) = ... = f_n(e_j) = 0$ for $j = 1, ..., k$, we have $f_{k+1}, ..., f_n \in U^\circ$.
> For any $f \in U^\circ$, $f = \sum_{i=1}^n \lambda_i f_i$. Since $f(e_j) = 0$ for $j = 1, ..., k$, we have $\lambda_1 = ... = \lambda_k = 0$.
> Therefore, $f = \sum_{i=k+1}^n \lambda_i f_i$ and $\langle f_{k+1}, ..., f_n \rangle = U^\circ$.
> Hence, $\Set{f_{k+1}, ..., f_n}$ is a basis of $U^\circ$ and $\dim U^\circ = n - k$.

## Dual Maps

> *Definition.*{: .def}
> Let $V$ and $W$ be vector spaces over $\mathbb{F}$ and suppose that $\alpha: V \to W$ is a linear map.
> The **dual map** to $\alpha$ is the map $\alpha^\ast: W^\ast \to V^\ast$ given by $f \to f\alpha$.

> *Proposition.*{: .prop}
> The dual map $\alpha^\ast: W^\ast \to V^\ast$ is linear.
>
> *Proof.*{: .prf}
>
> $f\alpha$ is the composite of two linear maps so $f\alpha: V \to \mathbb{F} \in \mathcal{L}(V, \mathbb{F})$.
> Also, for $f_1, f_2 \in W^\ast$ and $v \in V$, we have
>
> $$
  \alpha^\ast(\lambda f_1 + \mu f_2)(v) = (\lambda f_1 + \mu f_2)\alpha(v) = \lambda f_1 \alpha(v) + \mu f_2 \alpha(v) = (\lambda \alpha^\ast(f_1) + \mu \alpha^\ast(f_2))(v)
  $$
>
> so $\alpha^\ast \in \mathcal{L}(W^\ast, V^\ast)$.

> *Proposition.*{: .prop}
> Suppose that $V$ and $W$ are finite dimensional with bases $(v_1, ..., v_n)$ and $(w_1, ..., w_m)$.
> Let $(f_1, ..., f_n)$ and $(g_1, ..., g_m)$ be the corresponding dual bases.
> If $\alpha: V \to W$ is represented by $A$ with respect to $(v_1, ..., v_n)$ and $(w_1, ..., w_m)$,
> then $\alpha^\ast: W^\ast \to V^\ast$ is represented by $A^\intercal$ with respect to $(g_1, ..., g_m)$ and $(f_1, ..., f_n)$.
>
> *Proof.*{: .prf}
>
> Given $\alpha(v_j) = \sum A_{kj} w_k$, we have
>
> $$
  \alpha^\ast(g_i)(v_j) = g_i(\alpha(v_j)) = g_i \left( \sum_k A_{kj} w_k \right) = \sum_k A_{kj} g_i(w_k) \\ = \sum_k A_{kj} \delta_{ik} = A_{ij} = \sum_k A_{ik} f_k(v_j)
  $$
>
> Hence, $\alpha^\ast(g_i) = \sum_k A^\intercal_{ki} f_k$.

> *Corollary.*{: .cor}
> Suppose that $V$ is a finite dimensional vector space over $\mathbb{F}$.
> If $P$ is the change of basis matrix from $(e_1, ..., e_n)$ to $(e_1', ..., e_n')$ for $V$,
> Then $(P^{-1})^\intercal$ is the change of basis matrix from $(f_1, ..., f_n)$ to $(f_1', ..., f_n')$ for $V^\ast$.
>
> *Proof.*{: .prf}
>
> Let $\iota_V: V \to V$ be the identity map, then $\iota_V^\ast: V^\ast \to V^\ast$ such that $\iota_V^\ast(f) = f\iota_V = f$ is also an identity map.
> Therefore, if $P$ is a matrix representation of $\iota_V$ for bases $(e_i)$ to $(e_i')$, then $P^\intercal$ is that of $\iota_V^\ast$ for bases $(f_i')$ to $(f_i)$.
> Hence, $(P^{-1})^\intercal$ is that for bases $(f_i)$ to $(f_i')$.

> *Proposition.*{: .prop}
> If $\alpha: U \to V$ and $\beta: V \to W$ are linear maps then $(\beta \alpha)^\ast = \alpha^\ast \beta^\ast$.
>
> *Proof.*{: .prf}
>
> By definition, for $f \in W^\ast$, $(\beta \alpha)^\ast(f)$ = $f(\beta \alpha)$ and $\alpha^\ast(\beta^\ast(f)) = \alpha^\ast(f(\beta)) = (f\beta)(\alpha) = f(\beta\alpha)$.

> *Proposition.*{: .prop}
> Suppose that $\alpha \in \mathcal{L}(V, W)$ with $V, W$ finite dimensional over $\mathbb{F}$. Then
>
> + $\ker \alpha^\ast = (\text{Im}\, \alpha)^\circ$;
>
> + $r(\alpha^\ast) = r(\alpha)$;
>
> + $\text{Im}\,\alpha^\ast = (\ker \alpha)^\circ$.
>
> *Proof.*{: .prf}
>
> For $f \in W^\ast$, $f \in \ker \alpha^\ast$ iff $\alpha^\ast(f) = 0$ iff $f(\alpha(v)) = f(w) = 0$ for all $w \in \text{Im}\, \alpha$ iff $f \in (\text{Im}\, \alpha)^\circ$.
>
> We have
>
> $$
  r(\alpha) + \dim (\text{Im}\,\alpha)^\circ = \dim W = \dim W^\ast = r(\alpha^\ast) + n(\alpha^\ast)
  $$
>
> and from the above $n(\alpha^\ast) = \dim(\ker \alpha^\ast) = \dim (\text{Im}\,\alpha)^\circ$ so $r(\alpha^\ast) = r(\alpha)$.
>
> Suppose that $g \in \text{Im}\, \alpha^\ast$. Then there exist $f \in W^\ast$ such that $\alpha^\ast f = f\alpha = g$.
> For all $v \in \ker \alpha$, $g(v) = f\alpha(v) = f(0) = 0$ so $g \in (\ker \alpha)^\circ$ and $\text{Im}\,\alpha^\ast \subseteq (\ker \alpha)^\circ$.
> We have
>
> $$
  \dim (\ker \alpha)^\circ = \dim V - n(\alpha) = r(\alpha) = r(\alpha^\ast) = \dim(\text{Im}\,\alpha^\ast)
  $$
>
> so $\text{Im}\,\alpha^\ast = (\ker \alpha)^\circ$.

The last equality makes use of the [dimension counting argument](bases.md#dimension-counting-argument).
The second equality gives a more in-depth reason for why the row rank is equal to column rank.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 3
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 8.26
