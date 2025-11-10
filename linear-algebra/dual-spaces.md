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
> i.e. $\theta: V \to \mathbb{F} \in V^\ast$ such that $\theta(v_1 + v_2) = \theta(v_1) + \theta(v_2)$ and $\theta(\lambda v) = \lambda \theta(v)$.
> The addition and scalar multiplication of $V^\ast$ are $(\theta_1 + \theta_2)(v) = \theta_1(v) + \theta_2(v)$ and $(\lambda \theta)(v) = \lambda\theta(v)$.

> *Proposition.*{: .prop}
> Suppose that $V$ is finite dimensional vector space over $\mathbb{F}$ with basis $(e_1, ..., e_n)$.
> Then $V^\ast$ has a basis $(\epsilon_1, ..., \epsilon_n)$ such that $\epsilon_i(e_j) = \delta_{ij}$.
>
> *Proof.*{: .prf}
>
> The linear forms $\Set{\epsilon_i}$ exist because we can always map the basis vectors to arbitrary vectors in the codomain.
> For $(\epsilon_1, ..., \epsilon_n)$ to be a basis, we need to show that it is linearly independent and spans $V^\ast$.
>
> Since $\Set{\epsilon_i}$ are linear maps, they are determined by how they trasform the basis vectors $\Set{e_i}$ which are the only ones we need to care about.
>
> Because of that, for linear independence, we just need to show that $\sum \lambda_i \epsilon_i(e_j) = 0$ implies $\lambda_i = 0$ for all $\Set{e_j}$.
> Suppose that $\sum \lambda_i \epsilon_i = 0$, in which $0$ is the zero function $0(v) = 0$ for all $v \in V$.
> Since
>
> $$
  \begin{align*}
  \sum_i \lambda_i \epsilon_i(e_j) &= 0(e_j) \\
  \sum_i \lambda_i \delta_{ij} &= 0 \\
  \lambda_j &= 0
  \end{align*}
  $$
>
> for all $\Set{e_j}$ therefore $\Set{\epsilon_i}$ is linearly independent.
>
> For any linear form $\theta \in V^\ast$, suppose that $\theta(e_i) = \lambda_i$ for $i = 1, ..., n$. Then $\theta = \sum \lambda_i \epsilon_i$ since
>
> $$
  \sum_i \lambda_i \epsilon_i(e_j) = \sum_i \lambda_i \delta_{ij} = \lambda_j = \theta(e_j)
  $$
>
> for all $\Set{e_j}$ and therefore $\langle \epsilon_i \rangle = V^\ast$.

> *Definition.*{: .def}
> The basis $(\epsilon_1, ..., \epsilon_n)$ is called the **dual basis** of $V^\ast$ with respect to $(e_1, ..., e_n)$.

> *Corollary.*{: .cor}
> If $V$ is finite dimensional, then $\dim V = \dim V^\ast$.

## Annihilator

> *Definition.*{: .def}
> If $U \subset V$ then the **annihilator** of $U$ is defined by
>
> $$
  U^\circ = \Set{\theta \in V^\ast : \forall u \in U, \theta(u) = 0} \subset V^\ast
  $$

> *Proposition.*{: .prop}
> Suppose that $V$ is finite dimensional and $U \subset V$ is a subspace.
> Then $\dim U + \dim U^\circ = \dim V$.
>
> *Proof.*{: .prf}
>
> Let $(e_1, ..., e_k)$ be a basis for $U$ extend to a basis $(e_1, ..., e_n)$ for $V$, and $(\epsilon_1, ..., \epsilon_n)$ be the corresponding dual basis for $V^\ast$.
>
> By the definition $\epsilon_i(e_j) = \delta_{ij}$, we have $\epsilon_{k+1}(e_j) = ... = \epsilon_n(e_j) = 0$ for $j = 1, ..., k$ and therefore $\epsilon_{k+1}, ..., \epsilon_n \in U^\circ$.
>
> For any $\theta \in U^\circ$, suppose that $\theta = \sum_{i=1}^n \lambda_i \epsilon_i$ so $\theta(e_j) = \lambda_j$.
> Since $\theta(e_1) = ... = \theta(e_k) = 0$, we have $\lambda_1 = ... = \lambda_k = 0$.
> Therefore, $\theta = \sum_{i=k+1}^n \lambda_i \epsilon_i$ and $\langle \epsilon_{k+1}, ..., \epsilon_n \rangle = U^\circ$.
> Hence, $\Set{\epsilon_{k+1}, ..., \epsilon_n}$ is a basis of $U^\circ$ and $\dim U^\circ = n - k$.

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

## Canonical Maps

> *Definition.*{: .def}
> Suppose that $V$ is a vector space over $\mathbb{F}$.
> The **canonical map** is defined by $\text{ev}: V \to V^{\ast\ast}$ where $\text{ev}(v)(f) = f(v)$ for each $f \in V^\ast$.

The name "canonical" means it is a map arises natually from the definition of $V$ and $V^{\ast\ast}$ that preserves the widest amount of structure.

> *Proposition.*{: .prop}
> The canonical map is well-defined and linear.
>
> *Proof.*{: .prf}
>
> For $f_1, f_2 \in V^\ast$, we have
>
> $$
  \text{ev}(v)(\lambda f_1 + \mu f_2) = (\lambda f_1 + \mu f_2)(v) = \lambda f_1(v) + \mu f_2(v) = \lambda \text{ev}(v)(f_1) + \mu \text{ev}(v)(f_2)
  $$
>
> so $\text{ev}(v) \in \mathcal{L}(V^\ast, \mathbb{F}) = V^{\ast\ast}$.
> $\text{ev}$ is well-defined since $f \in V^\ast$ is well-defined.
>
> For $v_1, v_2 \in V$, we have
>
> $$
  \text{ev}(\lambda v_1 + \mu v_2)(f) = f(\lambda v_1 + \mu v_2) = \lambda f(v_1) + \mu f(v_2) = (\lambda \text{ev}(v_1) + \mu \text{ev}(v_2))(f)
  $$
>
> so $\text{ev}$ is linear.

> *Proposition.*{: .prop}
> Suppose that $V$ is finite dimensional vector space over $\mathbb{F}$.
> Then the canonical linear map $\text{ev}$ is an isomorphism.
>
> *Proof.*{: .prf}
>
> Suppose that $\text{ev}(v) = 0 \in V^{\ast\ast}$. Then $\text{ev}(v)(f) = f(v) = 0$ for all $f \in V^\ast$.
> Thus,
>
> $$
  \langle v \rangle^\circ = \Set{f \in V^\ast : \forall v \in V, f(v) = 0} = V^\ast
  $$
>
> which means $\dim \langle v \rangle^\circ = \dim V^\ast = \dim V$ and $\dim \langle v \rangle = 0$ and $v = 0$.
> Therefore, $\ker \text{ev} = 0$ and $\text{ev}$ is injective.
> As $\dim V^{\ast\ast} = \dim V^\ast = \dim V$, injectivity of $\text{ev}$ implies isomorphism.

$\text{ev}$ is generally not an isomorphism if $V$ is not finite dimensional.

> *Proposition.*{: .prop}
> Suppose that $V$ and $W$ are finite dimensional and $\alpha \in \mathcal{L}(V, W)$ then $\alpha^{\ast\ast} \circ \text{ev}_V = \text{ev}_W \circ \alpha$.
>
> *Proof.*{: .prf}
>
> Note that $\alpha^{\ast\ast}: V^{\ast\ast} \to W^{\ast\ast}$ so $\alpha^{\ast\ast} \circ \text{ev}_V$ and $\text{ev}_W \circ \alpha$ are both linear maps $V \to W^{\ast\ast}$.
> Also, $\text{ev}_V$ on the L.H.S. is $V \to V^{\ast\ast}$ and $\text{ev}_W$ on the R.H.S. is $W \to W^{\ast\ast}$.
>
> For $v \in V$ and $f \in W^\ast$, we have
>
> $$
  \alpha^{\ast\ast}(\text{ev}_V(v))(f) = \text{ev}_V(v)(\alpha^\ast f) = \text{ev}_V(v)(f \alpha) = f(\alpha(v)) = \text{ev}_W(\alpha(v))(f)
  $$
>
> as required.

> *Proposition.*{: .prop}
> Suppose that $V$ is finite dimensional and $U, U_1, U_2$ are subspaces of $V$. Then
>
> + $U^{\circ \circ} = \text{ev}(U)$;
>
> + $\text{ev}(U)^\circ = \text{ev}(U^\circ)$;
>
> + $(U_1 + U_2)^\circ = U_1^\circ \cap U_2^\circ$;
>
> + $(U_1 \cap U_2)^\circ = U_1^\circ + U_2^\circ$.
>
> *Proof.*{: .prf}
>
> Note that $U^\circ = \Set{f \in V^\ast : \forall u \in U, f(u) = 0}$ so $U^{\circ\circ} = \Set{g \in V^{\ast\ast} : \forall f \in U^\circ, g(f) = 0}$.
>
> Let $g' = \text{ev}(u)$ for $u \in U$. Then $\forall f \in U^\circ$, $g'(f) = f(u) = 0$ so $g' \in U^{\circ\circ}$ and $\text{ev}(U) \subseteq U^{\circ\circ}$. Moreover,
>
> $$
  \dim \text{ev}(U) = \dim U = \dim V - \dim U^\circ = \dim V^\ast - \dim U^\circ = \dim U^{\circ\circ}
  $$
>
> so $U^{\circ\circ} = \text{ev}(U)$.
>
> By the above, $\text{ev}(U)^\circ = (U^{\circ\circ})^\circ = (U^\circ)^{\circ\circ} = \text{ev}(U^\circ)$.
>
> Note that
>
> $$
  (U_1 + U_2)^\circ = \Set{f \in V^\ast : \forall u_1 \in U_1, \forall u_2 \in U_2, f(u_1 + u_2) = 0}
  $$
>
> and
>
> $$
  U_1^\circ \cap U_2^\circ = \Set{f \in V^\ast : \forall u_1 \in U_1, \forall u_2 \in U_2, f(u_1) = f(u_2) = 0}
  $$
>
> If $f(u_1 + u_2) = 0$ for all $u_1, u_2$, by having $u_2 = 0$, we have $f(u_1 + 0) = f(u_1) = 0$ for all $u_1 \in U_1$.
> Similarily, $f(u_2) = 0$ for all $u_2 \in U_2$. Therefore, $(U_1 + U_2)^\circ \subseteq U_1^\circ \cap U_2^\circ$.
> $U_1^\circ \cap U_2^\circ \subseteq (U_1 + U_2)^\circ$ is obvious.
>
> Finally, consider
>
> $$
  (U_1^\circ + U_2^\circ)^\circ = U_1^{\circ\circ} \cap U_2^{\circ\circ} = \text{ev}(U_1) \cap \text{ev}(U_2)
  $$
>
> Hence, since $\text{ev}$ is an isomorphism, we have
>
> $$
  \text{ev}((U_1 \cap U_2)^\circ) = \text{ev}((U_1 \cap U_2))^\circ = (\text{ev}(U_1) \cap \text{ev}(U_2))^\circ = (U_1^\circ + U_2^\circ)^{\circ\circ} = \text{ev}(U_1^\circ + U_2^\circ)
  $$
>
> so $(U_1 \cap U_2)^\circ = U_1^\circ + U_2^\circ$.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 3
* Charles W. Curtis _Linear Algebra - An Introductory Approach_, 1984 - Chapter 8.26
