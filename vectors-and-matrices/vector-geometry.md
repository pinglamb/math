---
layout: base
title: Vector Geometry &#124; Vectors and Matrices
---

# Vector Geometry
{: .page-title}

Vectors provide a convenient way for describing geometry in $\mathbf{R}^3$.

## Lines

> *Theorem.*{: .thm}
> Let $L$ be a line through a point $A: \vec{OA} = \mathbf{a}$ and parallel to a vector $\mathbf{t}$, then
>
> $$
  L: (\mathbf{x} - \mathbf{a}) \times \mathbf{t} = \mathbf{0}
  $$
>
> *Proof.*{: .prf}
>
> Let $P: \vec{OP} = \mathbf{x}$ be a point on $L$.
> As $\vec{AP} = \vec{OP} - \vec{OA} = \mathbf{x} - \mathbf{a}$, for $\lambda \in \mathbb{R}$,
>
> $$
  \mathbf{x} - \mathbf{a} = \lambda \mathbf{t}
  $$
>
> We can eliminate $\lambda$ by taking cross product on both side with $\mathbf{t}$, i.e.
>
> $$
  (\mathbf{x} - \mathbf{a}) \times \mathbf{t} = \mathbf{0}
  $$

> *Corollary.*{: .cor}
> Let $L$ be a line through two points $A: \vec{OA} = \mathbf{a}$ and $B: \vec{OB} = \mathbf{b}$, then
>
> $$
  L: (\mathbf{x} - \mathbf{a}) \times (\mathbf{b} - \mathbf{a}) = \mathbf{0}
  $$
>
> or alternatively, for $\lambda \in \mathbb{R}$,
>
> $$
  L: \mathbf{x} = (1 - \lambda)\mathbf{a} + \lambda\mathbf{b}
  $$
>
> *Proof.*{: .prf}
>
> $L$ is parallel to $\mathbf{t} = \vec{AB} = \vec{OB} - \vec{OA} = \mathbf{b} - \mathbf{a}$ and then by the point-slope form.
>
> Alternatively, we can write $\mathbf{x} = \mathbf{a} + \lambda (\mathbf{b} - \mathbf{a})$ to derive the second form.

> *Theorem.*{: .thm}
> The equation $\mathbf{x} \times \mathbf{t} = \mathbf{u}$ has many solutions when $\mathbf{t} \cdot \mathbf{u} = 0$,
> in which is a line in direction $\mathbf{t}$ through $(\mathbf{t} \times \mathbf{u} / \vert \mathbf{t} \vert^2$, i.e.
>
> $$
  \mathbf{x} = {\mathbf{t} \times \mathbf{u} \over \vert \mathbf{t} \vert^2} + \lambda \mathbf{t}
  $$
>
> It has no solutions if $\mathbf{t} \cdot \mathbf{u} \not = 0$.
>
> *Proof.*{: .prf}
>
> By dotting with $\mathbf{t}$, we have
>
> $$
  \mathbf{t} \cdot \mathbf{u} = \mathbf{t} \cdot (\mathbf{x} \times \mathbf{t}) = 0
  $$
>
> which there are no solutions unless $\mathbf{t} \cdot \mathbf{u} = 0$.
> Geometrically, it is due to the fact that the vector product $\mathbf{x} \times \mathbf{t}$ has to be perpendicular to $\mathbf{t}$.
>
> By crossing with $\mathbf{t}$, we have
>
> $$
  \mathbf{t} \times \mathbf{u} = \mathbf{t} \times (\mathbf{x} \times \mathbf{t}) = (\mathbf{t} \cdot \mathbf{t})\mathbf{x} - (\mathbf{t} \cdot \mathbf{x})\mathbf{t}
  $$
>
> Hence,
>
> $$
  \mathbf{x} = {\mathbf{t} \times \mathbf{u} \over \vert \mathbf{t} \vert^2} + {(\mathbf{t} \cdot \mathbf{x}) \over \vert \mathbf{t} \vert^2 }\mathbf{t}
  = {\mathbf{t} \times \mathbf{u} \over \vert \mathbf{t} \vert^2} + \lambda \mathbf{t}
  $$

It provides a way to convert a line $L: \mathbf{x} \times \mathbf{t} = \mathbf{u}$ to other forms we know.

## Planes

> *Theorem.*{: .thm}
> Let $\Pi$ be a plane contains the point $A: \vec{OA} = \mathbf{a}$ and has normal in the direction of a vector $\mathbf{n}$, then
>
> $$
  \Pi: (\mathbf{x} - \mathbf{a}) \cdot \mathbf{n} = 0
  $$
>
> *Proof.*{: .prf}
>
> Let $P: \vec{OP} = \mathbf{x}$ be a point on $\Pi$, then $\vec{PA} \perp \mathbf{n}$ and hence
>
> $$
  (\mathbf{x} - \mathbf{a}) \cdot \mathbf{n} = 0
  $$

> *Corollary.*{: .cor}
> Let $\Pi$ be a plane through three points $A: \vec{OA} = \mathbf{a}$, $B: \vec{OB} = \mathbf{b}$ and $C: \vec{OC} = \mathbf{c}$, then
>
> $$
  \Pi: (\mathbf{x} - \mathbf{a}) \cdot [(\mathbf{b} - \mathbf{a}) \times (\mathbf{c} - \mathbf{a})] = [\mathbf{x} - \mathbf{a}, \mathbf{b} - \mathbf{a}, \mathbf{c} - \mathbf{a}] = 0
  $$
>
> or
>
> $$
  \Pi: [\mathbf{x}, \mathbf{b}, \mathbf{c}] + [\mathbf{a}, \mathbf{x}, \mathbf{c}] + [\mathbf{a}, \mathbf{b}, \mathbf{x}] = [\mathbf{a}, \mathbf{b}, \mathbf{c}]
  $$
>
> or alternatively, for $\lambda, \mu \in \mathbb{R}$,
>
> $$
  \Pi: \mathbf{x} = (1 - \lambda - \mu)\mathbf{a} + \lambda\mathbf{b} + \mu\mathbf{c}
  $$

> *Theorem.*{: .thm}
> The distance between the origin and the plane $\Pi: (\mathbf{x} - \mathbf{a}) \cdot \mathbf{\hat{n}} = 0$ is
>
> $$
  d = \mathbf{a} \cdot \mathbf{\hat{n}}
  $$
>
> *Proof.*{: .prf}
>
> Let $\mathbf{x_O}$ be the position vector of the closest point on the plane $\Pi$ to the origin, we have
>
> $$
  (\mathbf{x_O} - \mathbf{a}) \cdot \mathbf{\hat{n}} = 0
  $$
>
> $\mathbf{x_O}$ must be orthogonal to the plane and therefore parallel to $\mathbf{\hat{n}}$, i.e.
>
> $$
  \mathbf{x_O} = d\mathbf{\hat{n}}
  $$
>
> where $\vert d \vert $ is the distance from the origin to the plane.
>
> Hence,
>
> $$
  d = \vert \mathbf{x_O} \cdot \mathbf{\hat{n}} \vert = \vert \mathbf{a} \cdot \mathbf{\hat{n}} \vert
  $$

> *Corollary.*{: .cor}
> Let $\Pi$ be a plane which has unit normal $\mathbf{\hat{n}}$ and has distance $d$ from the origin, then
>
> $$
  \Pi: \mathbf{x} \cdot \mathbf{\hat{n}} = d
  $$

It provides a way to convert a plane $\Pi: \mathbf{x} \cdot \mathbf{\hat{n}} = d$ to other forms we know and gives a geometric meaning to it.

## Geometry Problems

### Distance between Point and Line

> *Proposition.*{: .prop}
> The distance between a point $Y: \vec{OY} = \mathbf{y}$ and a line $L: (\mathbf{x} - \mathbf{a}) \times \mathbf{t} = \mathbf{0}$ is
>
> $$
  d = {|(\mathbf{y} - \mathbf{a}) \times \mathbf{t}| \over |\mathbf{t}|}
  $$
>
> *Proof.*{: .prf}
>
> Let $\theta$ be the non-reflex angle between $\vec{AY}$ and $\mathbf{t}$, we have
>
> $$
  d = |\mathbf{y} - \mathbf{a}|\sin\theta
  $$
>
> Since
>
> $$
  \vert (\mathbf{y} - \mathbf{a}) \times \mathbf{t} \vert = \vert (\mathbf{y} - \mathbf{a}) \vert \vert \mathbf{t} \vert \sin\theta = d\vert t \vert
  $$
>
> Hence,
>
> $$
  d = {|(\mathbf{y} - \mathbf{a}) \times \mathbf{t}| \over |\mathbf{t}|}
  $$

### Distance between Parallel Lines

> *Proposition.*{: .prop}
> The distance between two parallel lines $L_1: (\mathbf{x} - \mathbf{a}) \times \mathbf{t} = \mathbf{0}$ and $L_2: (\mathbf{x} - \mathbf{b}) \times \mathbf{t} = \mathbf{0}$ is
>
> $$
  d = {|(\mathbf{b} - \mathbf{a}) \times \mathbf{t}| \over |\mathbf{t}|}
  $$
>
> *Proof.*{: .prf}
>
> As $\mathbf{b}$ is a point on $L_2$, we can find the distance by substituting $\mathbf{y} = \mathbf{b}$ to the above.


### Distance between Skew Lines

> *Definition.*{: .def}
> Two lines in $\mathbb{R}^3$ are said to be **skew** if they do not lie in any plane.

> *Proposition.*{: .prop}
> The distance between two skew lines $L_1: (\mathbf{x} - \mathbf{a}) \times \mathbf{t} = \mathbf{0}$ and $L_2: (\mathbf{x} - \mathbf{b}) \times \mathbf{u} = \mathbf{0}$ is
>
> $$
  d = {|(\mathbf{b} - \mathbf{a}) \cdot (\mathbf{t} \times \mathbf{u})| \over |\mathbf{t} \times \mathbf{u}|}
  $$
>
> *Proof.*{: .prf}
>
> $L_1$ and $L_2$ are skew if they lie in a pair of parallel planes.
> Consider the planes
>
> $$
  \Pi_1: (\mathbf{x} - \mathbf{a}) \cdot (\mathbf{t} \times \mathbf{u}) = 0
  \quad \text{and} \quad
  \Pi_2: (\mathbf{x} - \mathbf{b}) \cdot (\mathbf{t} \times \mathbf{u}) = 0
  $$
>
> $L_1$ is on $\Pi_1$ and $L_2$ is on $\Pi_2$. Also, $\Pi_1$ and $\Pi_2$ are parallel because they have common normal $\mathbf{t} \times \mathbf{u}$.
> Hence, the distance between $L_1$ and $L_2$ is equal to the distance between $\Pi_1$ and $\Pi_2$, which is
>
> $$
  d = {|(\mathbf{b} - \mathbf{a}) \cdot (\mathbf{t} \times \mathbf{u})| \over |\mathbf{t} \times \mathbf{u}|}
  $$

### Intersection between Lines

> *Proposition.*{: .prop}
> Two lines $L_1: (\mathbf{x} - \mathbf{a}) \times \mathbf{t} = \mathbf{0}$ and $L_2: (\mathbf{x} - \mathbf{b}) \times \mathbf{u} = \mathbf{0}$ intersects
> iff $\mathbf{t} \times \mathbf{u} \not = \mathbf{0}$ and the intersection is
>
> $$
  \mathbf{x} = \mathbf{a} + {[\mathbf{t} \times \mathbf{u}, \mathbf{b} - \mathbf{a}, \mathbf{u}] \over |\mathbf{t} \times \mathbf{u}|^2}\mathbf{t}
  $$
>
> *Proof.*{: .prf}
>
> The two lines are parallel if $ \mathbf{t} \times \mathbf{u} = \mathbf{0}$. Hence, either they are the same line or there is no intersection.
>
> If $ \mathbf{t} \times \mathbf{u} \not = \mathbf{0}$, consider a line $L_2'$ through $\mathbf{a}$ and parallel to $L_2$,
> $L_1$ and $L_2'$ forms a plane $\Pi$ with normal vector $\mathbf{t} \times \mathbf{u}$.
> Therefore, we have
>
> $$
  \Pi: (\mathbf{x} - \mathbf{a}) \cdot (\mathbf{t} \times \mathbf{u}) = 0
  $$
>
> As $L_2$ is parallel to $L_2'$, either $L_2$ intersects $\Pi$ nowhere (in which $L_1$ and $L_2$ has no intersection) or $L_2$ is on $\Pi$.
> Therefore, the condition for $L_1$ and $L_2$ to intersect is
>
> $$
  (\mathbf{b} - \mathbf{a}) \cdot (\mathbf{t} \times \mathbf{u}) = 0
  $$
>
> Conversely, if the above is true, the plane $\Pi$ passes through the origin as the distance of the plane from origin is $0$,
> and we can express $\mathbf{b} - \mathbf{a}$ as
>
> $$
  \mathbf{b} - \mathbf{a} = \mathbf{0} + \lambda \mathbf{t} + \mu \mathbf{u}
  $$
>
> for some $\lambda, \mu \in \mathbb{R}$.
>
> Consier
>
> $$
  \mathbf{x} = \mathbf{a} + \lambda\mathbf{t} = \mathbf{b} - \mu\mathbf{u}
  $$
>
> $\mathbf{x}$ is on both $L_1$ and $L_2$ and therefore it is the intersection of $L_1$ and $L_2$.
>
> By some vector manipulations, we have
>
> $$
  \begin{gather}
  \mathbf{a} + \lambda\mathbf{t} = \mathbf{b} - \mu\mathbf{u} \\
  \lambda(\mathbf{t} \times \mathbf{u}) = (\mathbf{b} - \mathbf{a}) \times \mathbf{u} \\
  \lambda |\mathbf{t} \times \mathbf{u}|^2 = [\mathbf{t} \times \mathbf{u}, \mathbf{b} - \mathbf{a}, \mathbf{u}] \\
  \end{gather}
  $$
>
> Hence,
>
> $$
  \mathbf{x} = \mathbf{a} + {[\mathbf{t} \times \mathbf{u}, \mathbf{b} - \mathbf{a}, \mathbf{u}] \over |\mathbf{t} \times \mathbf{u}|^2}\mathbf{t}
  $$

### Distance between Point and Plane

> *Proposition.*{: .prop}
> The distance between a point $Y: \vec{OY} = \mathbf{y}$ and a plane $\Pi: (\mathbf{x} - \mathbf{a}) \cdot \mathbf{\hat{n}} = 0$ is
>
> $$
  d = \vert \mathbf{a} \cdot \mathbf{n} - \mathbf{y} \cdot \mathbf{\hat{n}} \vert
  $$
>
> *Proof.*{: .prf}
>
> $P: \vec{OP} = \mathbf{y} + d\mathbf{\hat{n}}$ is a point on $\Pi$, where $\vert d \vert$ is the distance from $Y$ to $\Pi$, i.e.
>
> $$
  (\mathbf{y} + d\mathbf{\hat{n}} - \mathbf{a}) \cdot \mathbf{\hat{n}} = 0
  $$
>
> Hence,
>
> $$
  d = \vert \mathbf{a} \cdot \mathbf{\hat{n}} - \mathbf{y} \cdot \mathbf{\hat{n}} \vert
  $$

### Distance between Parallel Planes

> *Proposition.*{: .prop}
> The distance between two parallel planes $\Pi_1: (\mathbf{x} - \mathbf{a}) \cdot \mathbf{\hat{n}} = 0$ and $\Pi_2: (\mathbf{x} - \mathbf{b}) \cdot \mathbf{\hat{n}} = 0$ is
>
> $$
  d = \vert (\mathbf{b} - \mathbf{a}) \cdot \mathbf{\hat{n}} \vert
  $$
>
> *Proof.*{: .prf}
>
> $\mathbf{b}$ is a point on $\Pi_2$ hence
>
> $$
  d = \vert \mathbf{b} \cdot \mathbf{\hat{n}} - \mathbf{a} \cdot \mathbf{\hat{n}} \vert = \vert (\mathbf{b} - \mathbf{a}) \cdot \mathbf{\hat{n}} \vert
  $$

### Intersection between Line and Plane

> *Proposition.*{: .prop}
> Given a line $L: (\mathbf{x} - \mathbf{a}) \times \mathbf{t} = \mathbf{0}$ and a plane $\Pi: (\mathbf{x} - \mathbf{b}) \cdot \mathbf{n} = 0$.
> If $\mathbf{n} \cdot \mathbf{t} = 0$, there is either no intersection or $L$ is on the plane $\Pi$.
> If $\mathbf{n} \cdot \mathbf{t} \not = 0$, then the intersection is
>
> $$
  \mathbf{x} = \mathbf{a} + {\mathbf{n} \cdot \mathbf{b} - \mathbf{n} \cdot \mathbf{a} \over \mathbf{n} \cdot \mathbf{t}} \mathbf{t}
  $$
>
> *Proof.*{: .prf}
>
> If $\mathbf{n} \cdot \mathbf{t} = 0$, $L$ and $\Pi$ are parallel.
> If $\mathbf{a}$ is on $\Pi$, i.e. $(\mathbf{a} - \mathbf{b}) \cdot \mathbf{n} = 0$, then $L$ is on $\Pi$, otherwise, there is no intersection.
>
> If $\mathbf{n} \cdot \mathbf{t} \not = 0$, by crossing by $\mathbf{n}$ on both side, we have
>
> $$
  \begin{align*}
  \mathbf{n} \times (\mathbf{x} \times \mathbf{t}) &= \mathbf{n} \times (\mathbf{a} \times \mathbf{t}) \\
  (\mathbf{n} \cdot \mathbf{t}) \mathbf{x} - (\mathbf{n} \cdot \mathbf{x}) \mathbf{t} &= (\mathbf{n} \cdot \mathbf{t}) \mathbf{a} - (\mathbf{n} \cdot \mathbf{a}) \mathbf{t} \\
  (\mathbf{n} \cdot \mathbf{t}) \mathbf{x} &= (\mathbf{n} \cdot \mathbf{t}) \mathbf{a} + (\mathbf{n} \cdot \mathbf{b}) \mathbf{t} - (\mathbf{n} \cdot \mathbf{a}) \mathbf{t} \\
  \end{align*}
  $$
>
> Hence,
>
> $$
  \mathbf{x} = \mathbf{a} + {\mathbf{n} \cdot \mathbf{b} - \mathbf{n} \cdot \mathbf{a} \over \mathbf{n} \cdot \mathbf{t}} \mathbf{t}
  $$

### Intersection of Two Planes (Line)

> *Proposition.*{: .prop}
> Given two planes $\Pi_1: \mathbf{x} \cdot \mathbf{n_1} = d_1$ and $\Pi_2: \mathbf{x} \cdot \mathbf{n_2} = d_2$.
> If $\mathbf{n_1} \times \mathbf{n_2} = \mathbf{0}$, then there are no intersections unless $d_1 = d_2$.
> If $\mathbf{n_1} \times \mathbf{n_2} \not = \mathbf{0}$, then the intersections are
>
> $$
  \mathbf{x} \times (\mathbf{n_1} \times \mathbf{n_2}) = d_2\mathbf{n_1} - d_1\mathbf{n_2}
  $$
>
> *Proof.*{: .prf}
>
> Their line of intersection $L$ must be in the direction that is orthogonal to both $\mathbf{n_1}$ and $\mathbf{n_2}$, i.e. $\mathbf{n_1} \times \mathbf{n_2}$.
>
> Therefore, the equation of $L$ is of the form
>
> $$
  \mathbf{x} \times (\mathbf{n_1} \times \mathbf{n_2}) = \mathbf{c}
  $$
>
> Expanding the L.H.S. we have
>
> $$
  \begin{align*}
  \mathbf{c} &= \mathbf{x} \times (\mathbf{n_1} \times \mathbf{n_2}) \\
             &= (\mathbf{x} \cdot \mathbf{n_2}) \mathbf{n_1} - (\mathbf{x} \cdot \mathbf{n_1}) \mathbf{n_n} \\
  \end{align*}
  $$
>
> Hence, as $\mathbf{x}$ is on $\Pi_1$ and $\Pi_2$, the intersections are
>
> $$
  \mathbf{x} \times (\mathbf{n_1} \times \mathbf{n_2}) = d_2\mathbf{n_1} - d_1\mathbf{n_2}
  $$

### Intersection of Three Planes (Point)

> *Proposition.*{: .prop}
> Given three planes $\Pi_1: \mathbf{x} \cdot \mathbf{n_1} = d_1$, $\Pi_2: \mathbf{x} \cdot \mathbf{n_2} = d_2$, $\Pi_3: \mathbf{x} \cdot \mathbf{n_3} = d_3$.
> If $[\mathbf{n_1}, \mathbf{n_2}, \mathbf{n_3}] \not = 0$, their intersection is
>
> $$
  \mathbf{x} = {d_1(\mathbf{n_2} \times \mathbf{n_3}) + d_2(\mathbf{n_3} \times \mathbf{n_1}) + d_3(\mathbf{n_1} \times \mathbf{n_2}) \over [\mathbf{n_1}, \mathbf{n_2}, \mathbf{n_3}]}
  $$
>
> *Proof.*{: .prf}
>
> For the three planes to intersect at one point, their normals can't be co-planar, i.e. $[\mathbf{n_1}, \mathbf{n_2}, \mathbf{n_3}] \not = 0$.
>
> As any point $\mathbf{p}$ in the 3D space can be expressed as
>
> $$
  \mathbf{p} =
    {\mathbf{p} \cdot \mathbf{n_1} \over [\mathbf{n_1}, \mathbf{n_2}, \mathbf{n_3}]} (\mathbf{n_2} \times \mathbf{n_3})
  + {\mathbf{p} \cdot \mathbf{n_2} \over [\mathbf{n_1}, \mathbf{n_2}, \mathbf{n_3}]} (\mathbf{n_3} \times \mathbf{n_1})
  + {\mathbf{p} \cdot \mathbf{n_3} \over [\mathbf{n_1}, \mathbf{n_2}, \mathbf{n_3}]} (\mathbf{n_1} \times \mathbf{n_2})
  $$
>
> Hence, their intersection is
>
> $$
  \mathbf{x} = {d_1(\mathbf{n_2} \times \mathbf{n_3}) + d_2(\mathbf{n_3} \times \mathbf{n_1}) + d_3(\mathbf{n_1} \times \mathbf{n_2}) \over [\mathbf{n_1}, \mathbf{n_2}, \mathbf{n_3}]}
  $$

## References

* Alan F. Beardon _Algebra and Geometry_, 2005 - Section 4.7
* [Stephen J. Cowley _Algebra and Geometry Lectures Notes_, 2006 - Section 2.13](https://www.damtp.cam.ac.uk/user/sjc1/teaching/AandG/notes.pdf)
