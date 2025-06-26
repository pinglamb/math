---
layout: base
title: Differentiation Theorems &#124; Analysis
---

# Differentiation Theorems
{: .page-title}

> *Theorem.*{: .thm}
> **[Rolle's Theorem]**
> Suppose $f$ is continuous in the closed interval $[a, b]$ and $f'$ exists in open interval $(a, b)$.
> If $f(a) = f(b)$, then there is a value $c$, with $a < c < b$, for which $f'(c) = 0$.
>
> *Proof.*{: .prf}
>
> Let $M = \sup f(x)$ and $m = \inf f(x)$ for $a \le x \le b$.
> Let $f(a) = k$
>
> If $M = m = k$, then $f$ is a constant function and $f'(c) = 0$ for all $c \in (a, b)$.
>
> Suppose $M > k$. By extreme value theorem, there exists $c$ such that $f(c) = M$.
> If $f'(c) > 0$, then $f$ is strictly increasing at $c$ and there are some values on the right such that $f(x) > f(c)$, which contradicts with $f(c)$ being the supremum.
> If $f'(c) < 0$, similarily there are some values on the left such thath $f(x) > f(c)$.
> Therefore, $f'(c) = 0$.

> *Theorem.*{: .thm}
> **[Mean Value Theorem]**
> Suppose $f$ is continuous in the closed interval $[a, b]$ and $f'$ exists in open interval $(a, b)$.
> Then there is a value $c$ with $a < c < b$, for which
>
> $$
  f(b) - f(a) = (b - a) f'(c)
  $$
>
> *Proof.*{: .prf}
>
> Let $\phi(x) = f(x) - kx$. In order to have $\phi(a) = \phi(b)$,
>
> $$
  k = {f(b) - f(a) \over b - a}
  $$
>
> By Rolle's Theorem, there exists $c$ such that
>
> $$
  \phi'(c) = f'(c) - k = 0 \quad \implies \quad f'(c) = k = {f(b) - f(a) \over b - a}
  $$

Let $0 < \theta < 1$ and $b = a + h$, we can write the result as

$$
f(a + h) = f(a) + hf'(a + \theta h)
$$

> *Corollary.*{: .cor}
> If $f'(x) = 0$ for all $x \in (a, b)$, then $f(x)$ is constant for $[a, b]$.
>
> *Proof.*{: .prf}
>
> For any two points $x_1$ and $x_2$ with $a \le x_1 < x_2 \le b$, there exists $x_1 < x_3 < x_2$ such that
>
> $$
  f(x_2) - f(x_1) = (x_2 - x_1)f'(x_3) = 0
  $$
>
> Hence, $f(x_1) = f(x_2)$.

> *Corollary.*{: .cor}
> If $f'(x) > 0$ for $x \in (a, b)$, then $f(x)$ is strictly increasing in $[a, b]$.
>
> *Proof.*{: .prf}
>
> For any two points $x_1$ and $x_2$ with $a \le x_1 < x_2 \le b$, there exists $x_1 < x_3 < x_2$ such that
>
> $$
  f(x_2) - f(x_1) = (x_2 - x_1)f'(x_3) > 0
  $$
>
> Hence, $f(x_2) > f(x_1)$ and $f$ is strictly increasing in $[a, b]$.
>
> The corollary still holds if $f$ is continuous at $c$ but $f'(c)$ doesn't exist.
> By applying the theorem to two intervals $(a, c)$ and $c, b$, with $x_1 \in (a, c)$ and $x_2 \in (c, b)$,
> we still have $f(x_1) < f(c) < f(x_2)$.

> *Theorem.*{: .thm}
> **[Cauchy's Mean Value Theorem]**
> Suppose both $f$ and $g$ are continuous in $[a, b]$ and differentiable in $(a, b)$.
> Suppose $g'(x)$ doesn't vanish for all $x \in (a, b)$.
> Then there exists $c$ with $a < c < b$ such that
>
> $$
  {f(b) - f(a) \over g(b) - g(a)} = {f'(c) \over g'(c)}
  $$
>
> *Proof.*{: .prf}
>
> Similarily to the proof of Mean Value Theorem, let
>
> $$
  \phi(x) = f(x) - kg(x)
  $$
>
> Choose $k$ such that $\phi(a) = \phi(b)$ and therefore
>
> $$
  k = {f(b) - f(a) \over g(b) - g(a)}
  $$
>
> By Rolle's Theorem, there exists $c$ such that
>
> $$
  \phi'(c) = f'(c) - kg'(c) = 0 \quad \implies \quad {f(b) - f(a) \over g(b) - g(a)} = {f'(c) \over g'(c)}
  $$

> *Corollary.*{: .cor}
> **[L'Hôpital's Rule]**
> Suppose that $f$ and $g$ are continuous in $[a, b]$ and differentiable in $(a, b)$, and $f(a) = g(a) = 0$ and $g'(x) \not= 0$ for all $x \in (a, b)$.
> If $f'(x) / g'(x) \to l$ as $x \to a^{+}$, then $f(x) / g(x) \to l$ as $x \to a^{+}$.
>
> *Proof.*{: .prf}
>
> Suppose $\varepsilon > 0$.
> Since $f'(x)/g'(x) \to l$, there exists $\delta$ such that $\vert f'(x) / g'(x) - l \vert < \varepsilon$ for all $x$ with $a < x < a + \delta$.
> For each $x$, by Cauchy's M.V.T., there exists $c$ with $a < c < x$ such that
>
> $$
  {f(x) - f(a) \over g(x) - g(a)} = {f(x) - 0 \over g(x) - 0} = {f(x) \over g(x)} = {f'(c) \over g'(c)}
  $$
>
> Hence, for all $x$ with $a < x < a + \delta$,
>
> $$
  \left| {f(x) \over g(x)} - l \right| = \left| {f'(c) \over g'(c)} - l \right| < \varepsilon
  $$

> *Theorem.*{: .thm}
> **[Theorem of Darboux]**
> Suppose that $f$ is differentiable in $I$.
> If $[a, b] \subseteq I$, then for every $y$ between $f'(a)$ and $f'(b)$, there exists an $x$ in $[a, b]$ such that $f'(x) = y$.
>
> *Proof.*{: .prf}
>
> If $y$ equals $f'(a)$ or $f'(b)$, then $x$ equals $a$ or $b$.
>
> If not, suppose $f'(a) > y > f'(b)$. Consider the function $g(t) = f(t) - yt$, $g'(t) = f'(t) - y$.
> Since $g$ is continuous in $[a, b]$, by Extreme Value Theorem, $g$ attains its maximum somewhere in the interval.
> Since $g'(a) = f'(a) - y > 0$, $g$ is increasing at $a$ so $g(a)$ can't be maximum.
> Since $g'(b) = f'(b) - y < 0$, $g$ is decreasing at $b$ so $g(b)$ can't be maximum as well.
> Therefore, there exists $x \in (a, b)$ such that $g(x)$ is maximum, which implies $g'(x) = f'(x) - y = 0$ and $f'(x) = y$.
>
> Similar arguments can be used for the case $f'(a) < y < f'(b)$.

## Taylor's Theorem
{: #taylor-theorem}

If $f$ is differentiable at $a$, then $f_a(x) = f(a) + (x - a)f'(a)$ is a good linear approximation to $f$.
We can generalize it to see if the function that has higher derivatives can be better approximated by means of a polynomial.

Let

$$
p_n(x) = f(a) + (x - a)f'(a) + {(x - a)^2 \over 2!} f''(a) + \cdots + {(x - a)^n \over n!} f^{(n)}(a)
$$

Then $p_n(x)$ is a polynomial of degree at most $n$, with $p_n(a) = f(a)$ and

$$
p_n^{(s)}(x) = f^{(s)}(a) + (x - a)f^{(s + 1)}(a) + \cdots + {(x - a)^{n - s} \over (n - s)!} f^{(n)}(a)
$$

so $p_n^{(s)}(a) = f^{(s)}(a)$ for $1 \le s \le n$.
We then have $r_{n+1}(x) = f(x) - p_n(x)$ being the remainder term in which we hope to be small so that $p_n(x)$ is a good approximation.
We will need to following lemma to prove the desired results.

> *Lemma.*{: .lem}
> **[Higher-order Rolle's Theorem]**
> Let $f$ be continuous on $[a, b]$ and $n$-times differentiable on an open interval containing $[a, b]$.
> Suppose that
>
> $$
  f(a) = f'(a) = f''(a) = \cdots = f^{(n-1)}(a) = f(b) = 0
  $$
>
> Then there exists $c$, with $a < c < b$ such that $f^{(n)}(c) = 0$.
>
> *Proof.*{: .prf}
>
> When $n = 0$, it is just Rolle's Theorem.
> Suppose $k < n$. There exists $c_k \in (a, b)$ such that $f^{(k)}(c_k) = 0$.
> As $f^{(k)}(a) = 0$, by Rolle's Theorem, there exists $c_{k+1} \in (a, c_k)$ such that $f^{(k+1)}(c_{k+1}) = 0$.
> By induction, there exists $c_n$, with $a < c_n < c_{n-1} < \cdots < c_1 < b$ such that $f^{(n)})(c_n) = 0$.

Base on different conditions that are placed on $f$ and its derivatives, we can get different results about the remainder term.

> *Theorem.*{: .thm}
> **[Taylor's Theorem with Lagrange's Remainder]**
> Suppose $f$ is a continuous function on $[a, b]$ which is $n$-times differentiable on $[a, b)$.
> Then there exists $c \in (a, b)$ such that
>
> $$
  \begin{align*}
  f(b) &= f(a) + (b - a) f'(a) + \cdots + {(b - a)^{n-1} \over (n - 1)!} f^{(n-1)}(a) + {(b - a)^{n} \over n!} f^{(n)}(c) \\
  &= p_{n-1}(b) + {(b - a)^{n} \over n!} f^{(n)}(c)
  \end{align*}
  $$
>
> Let $b = a + h$, it becomes
>
> $$
  f(a + h) = f(a) + hf'(a) + \cdots + {h^{n-1} \over (n-1)!} f^{(n-1)}(a) + {h^n \over n!} f^{(n)}(c)
  $$
>
> *Proof.*{: .prf}
>
> The theorem is like the mean value theorem for higher order and the proof is similar.
>
> Let
>
> $$
  \phi(x) = f(x) - p_{n-1}(x) - k {(x - a)^n \over n!}
  $$
>
> where $k$ is a real number chosen so that $\phi(b) = 0$.
>
> Then we have $\phi(a) = \phi'(a) = \cdots = \phi^{(n-1)}(a) = \phi(b) = 0$.
> By the higher-order Rolle's Theorem, there exists $c \in (a, b)$ such that
>
> $$
  \phi^{(n)}(c) = f^{(n)}(c) - k = 0 \quad \implies \quad k = f^{(n)}(c)
  $$
>
> Hence,
>
> $$
  f(b) = p_{n-1}(b) + {(b - a)^n \over n!} f^{(n)}(c)
  $$

> *Theorem.*{: .thm}
> **[Taylor's Theorem with Cauchy's Remainder]**
> Suppose $f$ is a continuous function on $[a, b]$ which is $n$-times differentiable on $[a, b)$,
> and for which the derivatives are bounded on $[a, b)$.
> Suppose that $k \in \mathbb{R}$ and that $k > 0$.
> Then there exists $c \in (a, b)$ such that
>
> $$
  \begin{align*}
  f(b) &= p_{n-1}(b) + {(b - c)^{n-k}(b - a)^{k} \over k(n - 1)!} f^{(n)}(c)
  \end{align*}
  $$
>
> Let $c = (1 - \theta_n)a + \theta_n b$, it becomes
>
> $$
  \begin{align*}
  f(b) &= p_{n-1}(b) + {(1 - \theta_n)^{n-k}(b - a)^{n} \over k(n - 1)!} f^{(n)}(c)
  \end{align*}
  $$
>
> *Proof.*{: .prf}
>
> Let
>
> $$
  h(x) = f(x) + \sum_{s=1}^{n-1} {(b - x)^s \over s!} f^{(s)}(x)
  $$
>
> We have $h(a) = p_{n-1}(b)$ and $h(b) = f(b)$ and
>
> $$
  {\mathrm{d} \over \mathrm{d}x}\left( {(b - x)^s \over s!} f^{(s)}(x) \right) = - {(b - x)^{s-1} \over (s-1)!} f^{(s)}(x) + {(b - x)^s \over s!} f^{(s + 1)}(x)
  $$
>
> so that
>
> $$
  h'(x) = {(b - x)^{n-1} \over (n - 1)!} f^{(n)}(x)
  $$
>
> as all the other terms are cancelling in pairs.
>
> Let
>
> $$
  g(x) = - (b - x)^k
  $$
>
> so that $g(b) - g(a) = (b - a)^k$ and $g'(x) = k(b - x)^{k-1} \not= 0$ for $x \in (a, b)$.
>
> By Cauchy's mean value theorem, there exists $c \in (a, b)$ such that
>
> $$
  {h(b) - h(a) \over g(b) - g(a)} = {h'(c) \over g'(c)}
  $$
>
> Hence,
>
> $$
  \begin{align*}
  f(b) &= h(b) = h(a) + (h(b) - h(a)) \\
  &= h(a) + (g(b) - g(a)) {h'(c) \over g'(c)} \\
  &= p_{n-1}(b) +  {(b - c)^{n-1}(b - a)^k \over k(b - c)^{k-1}(n - 1)! } f^{(n)}(c) \\
  &= p_{n-1}(b) +  {(b - c)^{n-k}(b - a)^k \over k(n - 1)! } f^{(n)}(c)
  \end{align*}
  $$

When $k = n$, we have Cauchy's remainder being the same as Lagrange's remainder.

> *Definition.*{: .def}
> Suppose that $f$ is infinitely differentiable and let $f(x) = p_n(x) + r_{n+1}(x)$.
> If $r_n(x) \to 0$ as $n \to \infty$, we can write
>
> $$
  f(x) = f(a) + \sum_{j=1}^{\infty} {(x - a)^j \over j!} f^{(j)}(a)
  $$
>
> which is called the **Taylor series** for $f$.

Taylor's theorem requires $f$ to be differentiable in an interval but we don't need that for the linear approximation $f(x) = f(a) + (x - a)f'(a) + o(\vert x - a \vert)$.
Therefore, we have the following corresponding result.

> *Theorem.*{: .thm}
> **[Young's Theorem]**
> Suppose that $f$ is $(n - 1)$-times differentiable in an interval $I$ and $f^{(n)}$ is differentiable at $a \in I$.
> Then $r_{n+1}(x) = f(x) - p_n(x) = o(\vert x - a \vert^n)$.
>
> *Proof.*{: .prf}
>
> Let $u(x) = r_{n+1}(x) / (x - a)^n$ for $x \not= a$.
> For any $\varepsilon > 0$, let
>
> $$
  v_\varepsilon(x) = r_{n+1}(x) + \varepsilon(x - a)^n
  $$
>
> Since $r_{n+1}(a) = r_{n+1}'(a) = \cdots = r_{n+1}^{(n)}(a) = 0$,
>
> $$
  v_\varepsilon(a) = v_\varepsilon'(a) = \cdots = v_\varepsilon^{(n-1)}(a) = 0 \quad \text{and} \quad v_\varepsilon^{(n)}(a) = n!\varepsilon > 0
  $$
>
> Thus, $v_\varepsilon^{(n-1)}(x)$ is strictly increasing at $x = a$ and there exists an interval $[a, a + \delta) \subseteq I$ such that $v_\varepsilon^{(n-1)}(x) > 0$ for $x \in [a, a + \delta)$.
> It implies $v_\varepsilon^{(n-2)}(x)$ is strictly increasing in the inteval $[a, a + \delta)$.
> By iterating the argument, it follows that $v_\varepsilon(x) > 0$
>
> Since $v_\varepsilon(x) = (u(x) + \varepsilon)(x - a)^n$, $u(x) > -\varepsilon$ for $x \in (a, a + \delta)$.
> Applying the same argument to $w_\varepsilon(x) = - r_{n+1}(x) + \varepsilon(x - a)^n$, we can conclude $u(x) < \varepsilon$
> Therefore, $u(x) \to 0$ as $x \to a^+$. Similarily, $u(x) \to 0$ as $x \to a^-$.
> Hence, $r_{n+1}(x) / (x - a)^n \to 0$ and $r_{n+1}(x) = o(\vert x - a \vert^n)$.

## References

* J C Burkill _A First Cource in Mathematical Analysis_, 1978 - Chapter 4
* D. J. H. Garling _A Course in Mathematical Analysis Vol.1_, 2013 - Chapter 7.6
