---
layout: base
title: Matrices &#124; Linear Algebra
---

# Matrices
{: .page-title}

With matrices being a representation of linear maps, we can study their properties leveraging that.

> *Definition.*{: .def}
> Let $B$ be a $m \times r$ matrix and $C$ be a $r \times n$ matrix. Then their product $A = BC$ is a $m \times n$ matrix such that
>
> $$
  A_{ij} = \sum_{k=1}^{r} B_{ik} C_{kj}
  $$

We have seen that this matches the properties of composite of linear maps.
But on the other hand, if we consider each column of $A$ as a vector $A^{(j)} \in \mathbb{F}^m$ then by the multiplication formula, we have

$$
A^{(j)} = C_{1j} B^{(1)} + C_{2j} B^{(2)}  + ... + C_{rj} B^{(r)} = B C^{(j)}
$$

The first expansion means $A^{(j)}$ are linear combinations of column vectors of $B$ with $C_{kj}$ as coefficients.
The second expansion means $A^{(j)}$ are the image of $C^{(j)}$ under the linear map $B$.

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

The change of basis $P$ will be confusing when we are dealing with coordinates. For example, in some cases we might be able to express the coordinates under new basis in terms of that of old basis
in the form of system of linear equations, i.e.

$$
\begin{cases}
x' = ax + by \\
y' = cx + dy \\
\end{cases}
\qquad \implies \qquad
\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}
$$

and it looks like we have found the change of basis $P$ we need. However, it is wrong because the equations represent the relationship between coordinates but not the basis vectors.
To find the right change of basis matrix, we should consider a vector $v$ that is expected to be equal under both basis, i.e.

$$
v = x' f_1 + y' f_2 = x e_1 + y e_2
$$

Substituting the equations into the equality we have

$$
(ax + by) f_1 + (cx + dy) f_2 = x e_1 + y e_2
$$

and by setting the coefficients of each $f_i$ to $1$ with others being $0$ we will be able to find the right matrix $P$ satisfying $f_i = \sum P_{ki} e_k$.

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

The column/row ranks are also the number of linearly independent column/row vectors of the matrix.
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

> *Proposition.*{: .prop}
> Let $A$ be a $m \times r$ matrix and $B$ be a $r \times n$ matrix. Then
>
> $$
  r(AB) \le \min(r(A), r(B))
  $$
>
> *Proof.*{: .prf}
>
> Let $v$ be a vector in the span of the column vectors of $AB$, i.e.
>
> $$
  v = \sum_{i = 1}^n \lambda_i (AB)^{(i)} = \sum_{i = 1}^n \lambda_i A B^{(i)} = A \left( \sum_{i=1}^n \lambda_i B^{(i)} \right) = \sum_{j=1}^r \lambda_j' A^{(j)}
  $$
>
> and $v$ is also in the span of column vectors of $A$ so $r(AB) \le r(A)$.
>
> Similarily, by considering $(AB)^\intercal = B^\intercal A^\intercal$, any vectors in the span of row vectors of $AB$ are also in the span of row vectors of $B$ and $r(AB) \le r(B)$.

> *Proposition.*{: .prop}
> Let $A$ be a $m \times r$ matrix and $B$ be a $r \times r$ matrix of full-rank. Then
>
> $$
  r(AB) = r(A)
  $$
>
> *Proof.*{: .prf}
>
> Let $a$ be a vector in the span of column vectors of $A$, we have $a = Av$ where $v$ is a $r \times 1$ column matrix of coefficients.
> Since the $r$ column vectors of $B$ are linearly independent, $v$ is in the span of $B$ with $v = Bu$ where $u$ is also a $r \times 1$ column matrix of coefficients.
> Thus, we have $a = Av = (AB)u$ and $a$ is also in the span of column vectors of $AB$, i.e. $r(A) \le r(AB)$.
> Combining with the above conclusion that $r(AB) \le r(A)$, we therefore have $r(AB) = r(A)$.

Similarily, we have $r(AB) = r(B)$ with $A$ being a $r \times r$ matrix of full-rank and $B$ being a $r \times n$ matrix.

> *Corollary.*{: .cor}
> Let $A$ and $B$ be $n \times n$ matrices of full-rank. Then $AB$ and $BA$ are full-rank.

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

The elementary matrix represents a column operation when it is on the right and a row operation when it is on the left, base on the matrix multiplication rule that

$$
B^{(k)} = AS_{ij} = (S_{ij})_{1k} A^{(1)} + (S_{ij})_{2k} A^{(2)} + ... + (S_{ij})_{nk} A^{(n)}
$$

> *Proposition.*{: .prop}
> If $A \in \text{Mat}\_{n,m}(\mathbb{F})$ then there are elementary matrices $E_1^n, ... E_a^n$ and $F_1^m, ..., F_b^m$ such that
>
> $$
  E_a^n \cdots E_1^n A F_1^m \cdot F_b^m
  = \begin{pmatrix}
    I_r & 0 \\
    0 & 0 \\
    \end{pmatrix}
  $$
>
> *Proof.*{: .prf}
>
> If $A = 0$ there is nothing to do. Otherwise, we can ensure $A_{11} \not= 0$ by swapping rows $1$ and $i$ and columns $1$ and $j$ so that $A_{ij} \not= 0 \to A_{11}$.
> We can further ensure $A_{11} = 1$ by multiplying row $1$ by $\lambda = 1 / A_{11}$.
> We can then add $-A_{1j}$ times column $1$ to column $j$ for each $j$ and add $-A_{i1}$ times row $1$ to row $i$ for each $i$ so the matrix is of the form
>
> $$
  \begin{pmatrix}
  1 & 0 \\
  0 & B \\
  \end{pmatrix}
  $$
>
> We can then do the same to matrix $B$ and by induction we can reduce $A$ to the required form.

This process can be used to actually find $P$ and $Q$ that $Q^{-1}AP$ is of the canonical form.
Also, since the three elementary matrix operations do not alter $r(A)$ and $r(A^\intercal)$, it implies that $r(A) = r(A^\intercal) = r(\alpha)$ is independent of the choices of bases.

## Reference

* Simon Wadsley _Linear Algebra Lectures Notes_, 2016 - Chapter 2
