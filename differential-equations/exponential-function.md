---
layout: base
title: Exponential Function &#124; Differential Equations
---

# Exponential Function
{: .page-title}

The exponential function $\exp(x) = e^x$ plays an important role in differential equations because it is the unqiue function satisfying

$$
f'(x) = f(x) \quad \text{and} \quad f(0) = 1
$$

We call it an **eigenfunction** of the differential operator.

## From Calculus

Let $f(x) = a^x$, where $a > 0$ is a constant. We have

$$
\begin{align*}
f'(x) &= \lim_{h \to 0} {a^{x + h} - a^x \over h} \\
&= a^x \lim_{h \to 0} {a^h - 1 \over h} \\
&= \lambda f(x)
\end{align*}
$$

So the derivative of $f(x)$ is a multiple of itself.

Let $e$ be the solution of $\lambda = 1$, and let $k = {1 \over h}$, we have

$$
\begin{gather}
\lim_{k \to \infty} {e^{1 \over k} - 1 \over {1 \over k}} = 1 \\
e = \lim_{k \to \infty} \left( 1 + {1 \over k} \right)^k
\end{gather}
$$

Thus, let $n = kx$, ${1 \over k} = {x \over n}$, and

$$
\begin{align*}
e^x &= \lim_{k \to \infty} \left( 1 + {1 \over k} \right)^{kx} \\
&= \lim_{n \to \infty} \left( 1 + {x \over n} \right)^{n}
\end{align*}
$$

Expanding that we have

$$
\begin{align*}
e^x &= \lim_{n \to \infty} \sum_{r=0}^\infty {n \choose r} \left( {x \over n} \right)^r \\
&= \lim_{n \to \infty} \sum_{r=0}^n {n(n-1)...(n-r+1) \over n^r} {x^r \over r!} \\
&= \lim_{n \to \infty} \sum_{r=0}^n \left({n \over n}\right) \left(1-{1 \over n}\right) ... \left(1-{r+1 \over n}\right) {x^r \over r!} \\
&= \sum_{n=0}^{\infty} {x^n \over n!} \\
&= 1 + x + {x^2 \over 2!} + ...
\end{align*}
$$

which matches the [power series definition](../vectors-and-matrices/exponential-cosine-sine-functions.md) of $\exp(x)$.
