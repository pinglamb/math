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

## Refernces

* K.F. Riley _Mathematical Methods for Physics and Engineering, 2006 - Chapter 12
* David Skinner _Methods Lecture Notes_, 2016 - Chapter 1
