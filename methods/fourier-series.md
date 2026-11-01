---
layout: base
title: Fourier Series &#124; Methods
---

# Fourier Series
{: .page-title}

[Power Series](../differential-equations/power-series.md) has been discussed before which can be used to represent complicated functions.
Similarily, _Fourier series_ is another kind of representation with the use of sine and cosine terms.
The advantages include the target functions need not be continuous and/or differentiabile everywhere and the final expression is easy to differentiate and integrate.
It is often used to represent the response of a system to a periodic input, e.g. vibrations of finite string.

## Function Vector Spaces

Consider the set of complex valued functions on some domain $\Omega$. It can be thought as an infinite dimensional vector space,
with addition being pointwise addition of the functions and multiplication by scalar is just the usual multiplication in $\mathbb{C}$, i.e. for $x \in \Omega$,

$$
\begin{align*}
(f + g)(x) &= f(x) + g(x) \\
(\lambda f)(x) &= \lambda f(x)
\end{align*}
$$

We can extend it to be an inner product space by having

$$
(f, g) \equiv \int_{\Omega} f(x)^\ast g(x) \,d\mu
$$

where $d\mu$ is some choice of integration measure.
It is like the generalization of inner product between finite dimensional vectors by labeling "compoents" of the function by different point $x$,
then we multiple the "components" of two functions and sum them up using integration.
The measure $d\mu$ is the choice of weight to assign to each point of the domain.

## Fourier Coefficients

The possiblity of representation by Fourier series begins with having the sine and cosine terms being mutually orthogonal to each other with respect to the defined inner product,
so they form a basis of the function vector space.

> *Proposition.*{: .prop}
> Define
>
> $$
  c_n = \cos \left( 2\pi n\theta \over L \right) \,,\qquad s_n = \sin \left( 2\pi n\theta \over L \right)
  $$
>
> The elements of the set $\Set{1, c_n, s_n}$ are mutually orthogonal to each other, with
>
> $$
  (c_n, c_m) = (s_n, s_m) = {1 \over 2} L \delta_{m,n} \,,\qquad (1, c_n) = (1, s_m) = (c_n, s_m) = 0
  $$
>
> with $(f, g) = \int_0^L f(\theta)^\ast g(\theta) d\theta$.
>
> *Proof.*{: .prf}
>
> By trigonometric identities, we have
>
> $$
  \begin{align*}
  (1, c_n) &= \int_0^L \cos \left( 2\pi n\theta \over L \right) d\theta = \left[ {L \over 2\pi n } \sin \left( 2\pi n\theta \over L \right) \right]^L_0 = 0 \\
  (1, s_n) &= \int_0^L \sin \left( 2\pi n\theta \over L \right) d\theta = \left[ -{L \over 2\pi n } \cos \left( 2\pi n\theta \over L \right) \right]^L_0 = 0 \\
  (c_n, s_m) &= {1 \over 2 } \int_0^L \sin \left( 2\pi (m+n)\theta \over L \right) + \sin \left( 2\pi (m-n)\theta \over L \right) d\theta = 0 \\
  (c_n, c_m) &= {1 \over 2 } \int_0^L \cos \left( 2\pi (m-n)\theta \over L \right) + \cos \left( 2\pi (m+n)\theta \over L \right) d\theta = {1 \over 2} L \delta_{m,n} \\
  (s_n, s_m) &= {1 \over 2 } \int_0^L \cos \left( 2\pi (m-n)\theta \over L \right) - \cos \left( 2\pi (m+n)\theta \over L \right) d\theta = {1 \over 2} L \delta_{m,n} \\
  \end{align*}
  $$

Now, we can apply the same technique to find the coefficients as in [finite dimensional inner product spaces](../linear-algebra/inner-product-spaces.md), i.e.

$$
\lambda_i = (v, e_i) / (e_i, e_i)
$$

> *Definition.*{: .def}
> For a periodic function $f(x)$ of period $L$, the **Fourier coefficients** are given by
>
> $$
  \begin{align*}
  a_n = {2 \over L} \int_0^L f(x) \cos \left( 2\pi n\theta \over L \right) d\theta \\
  b_n = {2 \over L} \int_0^L f(x) \sin \left( 2\pi n\theta \over L \right) d\theta \\
  \end{align*}
  $$
>
> with
>
> $$
  f(x) = {a_0 \over 2} + \sum_{n=1}^\infty \left[ a_n \cos \left( 2\pi n\theta \over L \right) + b_n \sin \left( 2\pi n\theta \over L \right) \right]
  $$

A full discussion about the possiblity to expand a function as sum of mutually orthogonal functions will be provided later.

## Refernces

* K.F. Riley _Mathematical Methods for Physics and Engineering, 2006 - Chapter 12
* David Skinner _Methods Lecture Notes_, 2016 - Chapter 1
