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
> The elements of the set $\Set{1, c_n, s_n}_{n=1}^\infty$ are mutually orthogonal to each other, with
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
  (c_n, s_m) &= {1 \over 2} \int_0^L \sin \left( 2\pi (m+n)\theta \over L \right) + \sin \left( 2\pi (m-n)\theta \over L \right) d\theta = 0 \\
  (c_n, c_m) &= {1 \over 2} \int_0^L \cos \left( 2\pi (m-n)\theta \over L \right) + \cos \left( 2\pi (m+n)\theta \over L \right) d\theta = {1 \over 2} L \delta_{m,n} \\
  (s_n, s_m) &= {1 \over 2} \int_0^L \cos \left( 2\pi (m-n)\theta \over L \right) - \cos \left( 2\pi (m+n)\theta \over L \right) d\theta = {1 \over 2} L \delta_{m,n} \\
  \end{align*}
  $$

Now, we can apply the same technique to find the coefficients as in [finite dimensional inner product spaces](../linear-algebra/inner-product-spaces.md), i.e.

$$
\lambda_i = (v, e_i) / (e_i, e_i)
$$

> *Definition.*{: .def}
> For a periodic function $f(\theta)$ of period $L$, the **real Fourier coefficients** are given by
>
> $$
  \begin{align*}
  a_n = {2 \over L} \int_0^L f(\theta) \cos \left( 2\pi n\theta \over L \right) d\theta \\
  b_n = {2 \over L} \int_0^L f(\theta) \sin \left( 2\pi n\theta \over L \right) d\theta \\
  \end{align*}
  $$
>
> with
>
> $$
  f(\theta) = {a_0 \over 2} + \sum_{n=1}^\infty \left[ a_n \cos \left( 2\pi n\theta \over L \right) + b_n \sin \left( 2\pi n\theta \over L \right) \right]
  $$

The expansion above contains both sine and cosine terms so it is naturally to write it more compactly using complex exponential expansion.

> *Proposition.*{: .prop}
> Define
>
> $$
  e_n = \exp \left( 2\pi in\theta \over L \right)
  $$
>
> The elements of the set $\Set{1, e_n}_{n=-\infty}^\infty$ are mutually orthogonal to each other, with
>
> $$
  (e_n, e_m) = L \delta_{m,n}
  $$
>
> with $(f, g) = \int_0^L f(\theta)^\ast g(\theta) d\theta$.
>
> *Proof.*{: .prf}
>
> When $m \not= n$,
>
> $$
  \begin{align*}
  (e_n, e_m) &= \int_0^L \exp \left( 2\pi i(m-n)\theta \over L \right) d\theta \\
  &= \left[ {L \over 2\pi i (m-n)} \exp \left( {2\pi i(m-n)\theta \over L} \right) \right]_0^L = 0
  \end{align*}
  $$
>
> When $m = n$, $(e_n, e_n) = \int_0^L d\theta = L$.

> *Definition.*{: .def}
> For a periodic function $f(\theta)$ of period $L$, the **complex Fourier coefficients** are given by
>
> $$
  c_n = {1 \over L} \int_0^L f(\theta) \exp \left( -2\pi in\theta \over L \right) d\theta
  $$
>
> with
>
> $$
  f(\theta) = \sum_{n=-\infty}^\infty c_n \exp \left( 2\pi in\theta \over L \right)
  $$

> *Proposition.*{: .prop}
> Let $a_n, b_n$ be the real Fourier coefficients and $c_n$ be the complex Fourier coefficients of the same function $f$.
> Then
>
> $$
  c_n = {1 \over 2} (a_n - i b_n) \,,\quad c_{-n} = {1 \over 2} (a_n + i b_n)
  $$
>
> and $c_{-n} = c_n^\ast$ if $f$ is real-valued.
>
> *Proof.*{: .prf}
>
> By de Moivre's theorem, $\exp(in\theta) = \cos n\theta + i \sin n\theta$. Therefore,
>
> $$
  \begin{align*}
  c_n &= {1 \over L} \int_0^L f(\theta) \exp \left( -2\pi in\theta \over L \right) d\theta \\
  &= {1 \over 2} \left( {2 \over L} \int_0^L f(\theta) \cos \left( -2\pi n\theta \over L \right) d\theta +  {2i \over L} \int_0^L f(\theta) \sin \left( -2\pi n\theta \over L \right) d\theta \right) \\
  &= {1 \over 2} (a_n - i b_n)
  \end{align*}
  $$
>
> If $f$ is real-valued, $a_n = a_n^\ast$ and $b_n = b_n^\ast$ so $c_n^\ast = c_{-n}$.

A full discussion about the possiblity to expand a function as sum of mutually orthogonal functions will be provided later.

## Convergence

> *Theorem.*{: .thm}
> **[Dirichlet Conditions]**
> If a function $f(x)$ fulfills the following conditions:
>
> + the function must be periodic;
>
> + it must be single-valued and continuous except possibly at a finite number of finite discontinuities;
>
> + it must have only a finite number of maxima and minima within one period;
>
> + the integral over one period of $\vert f(x) \vert$ must converge,
>
> then the Fourier series converges to $f(x)$ at all points where $f(x)$ is continuous.

The behaviour of the Fourier series at the point of discontinuity is stated below.

> *Proposition.*{: .prop}
> Suppose that $f(\theta)$ is discontinuous at $\theta_0$, then its Fourier series converges to
>
> $$
  {1 \over 2} f(\theta_0^+) + f(\theta_0^-)
  $$
>
> *Proof.*{: .prf}
>
> Consider the _sawtooth function_ defined by
>
> $$
  g(\theta) = \theta \quad \text{for} \quad \theta \in [-\pi, \pi)
  $$
>
> which is discontinuous at $\theta = -\pi$. We then found that
>
> $$
  g(\theta) = 2 \sum_{n=1}^\infty {(-1)^{n+1} \over n} \sin n\theta
  $$
>
> which converges to $0$ at $\theta = -\pi$. Suppose that $f(\theta)$ is a function that is discontinuous, say at $\theta = \pi$.
> Define
>
> $$
  F(\theta) = \begin{cases}
  f(\theta) + \dfrac{f(\pi^+) - f(\pi^-)}{2\pi} g(\theta) & \text{for } \theta \not= \pi \\[2ex]
  \dfrac{f(\pi^+) + f(\pi^-)}{2} & \text{for } \theta = \pi
  \end{cases}
  $$
>
> and it is continuous at $x = \pi$.
> Since $F(\theta)$ is a linear combination of $f$ and $g$ so its Fourier series converges as long as those of $f$ and $g$ converges,
> and it converges to $F(\pi)$ at $x = \pi$. Let $S_n F$, $S_n f$ and $S_n g$ be the corresponding partial Fourier series, we have
>
> $$
  S_n F(\pi) = S_n f(\pi) + \dfrac{f(\pi^+) - f(\pi^-)}{2\pi} S_n g(\pi) = S_n f(\pi)
  $$
>
> since $S_n g(\pi) = 0$ as shown above. Hence, $S_n f(\pi) \to (f(\pi^+) + f(\pi^-))/2$ as $n \to \infty$.

For function that is not periodic, we can first restirct the domain to a certain interval, e.g. $[-\pi, \pi)$ and define $f(\theta) = f(\theta + 2n\pi)$ so to make it $2\pi$-periodic.
There are two points to consider when doing so. We might want to choose the interval in a way that the endpoints are continuous when it got extended.
As shown above, if that is not the case, the Fourier series will converge to the average instead of the original value.
Also, we would want to extend it in the way that the resulting function is either odd or even so to make the Fourier series contain only sine (odd) or cosine (even) terms for simplicity.

Integration and differentiation can be used to derive new Fourier series from known ones.
Since integration is a smoothing operation, the new series is guaranteed to converge to the integral as long as original function converges.
However, for differentiation, the resulting series might not converge as each time we are adding an extra $n$ to each term.
In general, the convergence of series we got after differentiation is related to the rate of decay of Fourier coefficients of the original function.
Through integration by parts, we will find that if we meet a discontinuity after differentiating $k$ times then the Fourier coefficients decays at $O(1/n^{k+1})$.

## Parseval's Theorem

Parseval's theorem states that the sum of moduli squared of the complex Fourier coefficients is equal to the average value of $\vert f(\theta) \vert^2$ over one period.

> *Theorem.*{: .thm}
> **[Parseval's Theorem]**
>
> $$
  {1 \over L} \int_0^L \vert f(\theta) \vert^2 d\theta = \sum_{n=-\infty}^\infty |c_n|^2 = \left({a_0 \over 2}\right)^2 + {1 \over 2} \sum_{n=1}^\infty (a_n + b_n)^2
  $$
>
> *Proof.*{: .prf}
>
> Let $f(\theta)$ and $g(\theta)$ be two periodic functions with period $L$ in which
>
> $$
  \begin{align*}
  f(\theta) &= \sum_{n=-\infty}^\infty c_r \exp \left( {2\pi in\theta \over L} \right) \\
  g(\theta) &= \sum_{n=-\infty}^\infty \gamma_r \exp \left( {2\pi in\theta \over L} \right) \\
  \end{align*}
  $$
>
> Thus,
>
> $$
  f(\theta)g^\ast(\theta) = \sum_{n=-\infty}^\infty c_r g^\ast(\theta) \exp \left( {2\pi in\theta \over L} \right) \\
  $$
>
> and
>
> $$
  \begin{align*}
  {1 \over L} \int_0^L f(\theta)g^\ast(\theta) d\theta
  &= \sum_{n=-\infty}^\infty c_r { 1 \over L } \int_0^L g^\ast(\theta) \exp \left( {2\pi in\theta \over L} \right) d\theta \\
  &= \sum_{n=-\infty}^\infty c_r \left[ { 1 \over L } \int_0^L g(\theta) \exp \left( {-2\pi in\theta \over L} \right) d\theta \right]^\ast \\
  &= \sum_{n=-\infty}^\infty c_r \gamma_r^\ast
  \end{align*}
  $$
>
> By having $g(\theta) = f(\theta)$, we obtain Parseval's Theorem.

Parseval's theorem can be viewed as an infinite dimensional version of Pythagoras' theorem, and it can be used to find the sum of some series, e.g. $\sum 1/n^4 = \pi^4/90$.


## Refernces

* K.F. Riley _Mathematical Methods for Physics and Engineering, 2006 - Chapter 12
* David Skinner _Methods Lecture Notes_, 2016 - Chapter 1
