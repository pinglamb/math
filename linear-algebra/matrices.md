---
layout: base
title: Matrices &#124; Linear Algebra
---

# Matrices
{: .page-title}

With matrices being a representation of linear maps, we can study their properties leveraging that.

> *Proposition.*{: .prop}
> Let $A$ be an $n \times n$ matrix over $\mathbb{F}$. The following are equivalent
>
> + there exists a matrix $B$ such that $BA = I_n$;
>
> + there exists a matrix $C$ such that $AC = I_n$.
>
> Moreover, if both holds then $B = C$ and we write $A^{-1} = B = C$ and $A$ is **invertible**.
>
> *Proof.*{: .prf}
>
> Let $\alpha, \beta, \gamma, \iota: \mathbb{F}^n \to \mathbb{F}^n$ be the linear maps represented by $A, B, C$ and $I_n$ with respect to the standard basis.
>
> $BA = I_n$ iff there exists $\beta$ such that $\beta \alpha = \iota$, which it implies $\alpha$ is injective and therefore an isomorphism.
> Conversely, if $\alpha$ is an isomorphism then there exists $\beta$ such that $\beta \alpha = \iota$ by definition.
> Therefore, $BA = I_n$ iff $\alpha$ is an isomorphism.
>
> $AC = I_n$ iff there exists $\gamma$ such that $\alpha \gamma = \iota$, which implies $\alpha$ is surjective and therefore an isomorphism.
> Similarily, $AC = I_n$ iff $\alpha$ is an isomorphism.
>
> If $\alpha$ is an isomorphism, then $\beta$ and $\gamma$ must both be the set-theoretic inverse of $\alpha$ and so $B = C$.

## Change of Basis

> *Proposition.*{: .prop}
> Suppose that $(e_1, ..., e_m)$ and $(u_1, ..., u_n)$ are two bases for $U$ over $\mathbb{F}$ and $(f_1, ..., f_m)$ and $(v_1, ..., v_n)$ are two bases for $V$.
> Let $\alpha: U \to V$ be a linaer map, $A$ be the matrix representation with respect to $(e_i)$ and $(f_j)$ and $B$ be that with respect to $(u_i)$ and $(v_j)$.
> Then
>
> $$
  B = Q^{-1}AP
  $$
>
> where
>
> $$
  u_i = \sum P_{ki} e_k \qquad \text{and} \qquad $v_j = \sum Q_{lj} f_l
  $$
>
> in which $P$ can be viewed as the matrix representing the identity map from $U$ with basis $(u_i)$ to $U$ with basis $(e_i)$ and
> $Q$ as that of the identity map from $V$ with basis $(v_j)$ to $(f_j)$.
>
> *Proof.*{: .prf}
>
> By defintion,
>
> $$
  \alpha(u_i) = \sum_j B_{ji} v_j = \sum_{j,l} B_{ji} Q_{lj} f_l = \sum_l (QB)_{li} f_l
  $$
>
> On the other hand,
>
> $$
  \alpha(u_i) = \alpha \left( \sum_k P_{ki} e_k \right) = \sum_{k,l} P_{ki} A_{lk} f_l = \sum_l (AP)_{li} f_l
  $$
>
> Hence, $QB = AP$. Since $Q$ is invertible, $B = Q^{-1}AP$.

> *Definition.*{: .def}
> Two matrices $A, B \in \text{Mat}\_{n,m}(\mathbb{F})$ are _equivalent_ if there are invertible matrices
> $P \in \text{Mat}_m(\mathbb{F})$ and $Q \in \text{Mat}_n(\mathbb{F})$ such that $Q^{-1}AP = B$.

Equivalent matrices can be interpreted as matrices representing the same linear map with respect to different bases.
One of the particular form among the equivalent matrices is worth a special mention.
Previously we have proved that there exists bases for domain and codomain such that the matrix representation is of the form

$$
\begin{pmatrix}
I_r & 0 \\
0 & 0 \\
\end{pmatrix}
$$

with $r = r(\alpha)$ being independent of the choices of bases. We can rephrase it as

> *Proposition.*{: .prop}
> If $A \in \text{Mat}\_{n,m}(\mathbb{F})$ then there are invertible matrices $P \in \text{Mat}\_m(\mathbb{F})$ and $Q \in \text{Mat}\_n(\mathbb{F})$
> such that $Q^{-1}AP$ is of the form
>
> $$
  \begin{pmatrix}
  I_r & 0 \\
  0 & 0 \\
  \end{pmatrix}
  $$
>
> with $r = r(\alpha)$ is uniquely determined by $A$, i.e. every equivalence class contains precisely one matrix of this form.

> *Definition.*{: .def}
> If $A \in \text{Mat}\_{n,m}(\mathbb{F})$ then
>
> + the **column rank** $r(A)$ of $A$ is the dimension of the subspace of $\mathbb{F}^n$ spanned by the columns of $A$;
>
> + the **row rank** of $A$ is the column rank of $A^\intercal$.

By definition, we can see that column rank is equal to the rank of the corresponding linear map, i.e. $r(A) = r(\alpha)$ and therefore is constant on equivalence classes.

> *Proposition.*{: .prop}
> If $A \in \text{Mat}\_{n,m}(\mathbb{F})$ then the row rank is equal to column rank, i.e.
>
> $$
  r(A) = r(A^\intercal)
  $$
>
> *Proof.*{: .prf}
>
> Let $r = r(A)$. There exists $P$ and $Q$ such that
>
> $$
  Q^{-1}AP = \begin{pmatrix}
             I_r & 0 \\
             0 & 0 \\
             \end{pmatrix}
  $$
>
> Hence,
>
> $$
  (Q^{-1}AP)^\intercal = P^\intercal A^\intercal (Q^{-1})^\intercal
  = \begin{pmatrix}
    I_r & 0 \\
    0 & 0 \\
    \end{pmatrix}
  $$
>
> and $r(A^\intercal) = r = r(A)$.

## Elementary Matrices

> *Definition.*{: .def}
> The three **elementary matrices** are the following invertible $n \times n$ matrices
>
> $$
  \begin{align*}
  S_{ij}^n &= \begin{pmatrix}
  1 & 0 & \cdots & 0 & \cdots & 0 & \cdots & 0 \\
  0 & 1 & \cdots & 0 & \cdots & 0 & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots & \ddots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & 0 & \cdots & 1 & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots & \ddots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & 1 & \cdots & 0 & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots & \ddots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & 0 & \cdots & 0 & \cdots & 1 \\
  \end{pmatrix} \\ \\
  E_{ij}^n(\lambda) &= \begin{pmatrix}
  1 & 0 & \cdots & 0 & \cdots & 0 & \cdots & 0 \\
  0 & 1 & \cdots & 0 & \cdots & 0 & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots & \ddots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & 1 & \cdots & \lambda & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots & \ddots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & 0 & \cdots & 1 & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots & \ddots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & 0 & \cdots & 0 & \cdots & 1 \\
  \end{pmatrix} \\ \\
  T_{i}^n(\lambda) &= \begin{pmatrix}
  1 & 0 & \cdots & 0 & \cdots & 0 & \cdots & 0 \\
  0 & 1 & \cdots & 0 & \cdots & 0 & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots & \ddots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & \lambda & \cdots & 0 & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots & \ddots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & 0 & \cdots & 1 & \cdots & 0 \\
  \vdots & \vdots & \ddots & \vdots & \ddots & \vdots & \ddots & \vdots \\
  0 & 0 & \cdots & 0 & \cdots & 0 & \cdots & 1 \\
  \end{pmatrix}
  \end{align*}
  $$
>
> If $A$ is an $m \times n$ matrix then
>
> + $AS_{ij}^n$ swaps the column $i$ and column $j$, $S_{ij}^mA$ swaps the row $i$ and row $j$;
>
> + $AE_{ij}^n(\lambda)$ adds $\lambda \cdot$(column $i$) to column $j$, $E_{ij}^m(\lambda)A$ adds $\lambda \cdot$(row $j$) to row $i$;
>
> + $AT_i(\lambda)^n$ multiplies column $i$ by $\lambda$, $T_i^m(\lambda)A$ multiplies column $i$ by $\lambda$.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 2
