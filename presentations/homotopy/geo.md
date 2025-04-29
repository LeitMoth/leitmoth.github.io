# Homotopy

<p style="text-align: center">
Colin Phillips
</p>



<p style="text-align: center">
Homotopy is a concept from Topology
</p>



# Topology
<p style="text-align: center">
Colin Phillips
</p>


## What is topology?

When we deform a shape, certain properties stay the same.
The study of these properties is topology.


## Why is topology?

If we prove a theorem that only relies
on a toplogical property, we get
that theorem for free for every shape
that has that property.

This allows for more general theorems
about shapes.

Note: 
The more general the theorem the more powerful

We understand this intuitively, because we have
been using the triangle congruence theorems
across different geometries, without
reproving them every time.

It would not be incorrect to say that
we identified a more general structure
of a "first 4 axiom gemometry"
then got the first 28 postulates,
then identified that same structure
across euclidean, hyperbolic and sphereical, and got
those triangle congruences and other basics for free.

Hopefully this gives insight into why mathematicians
look for weird abstract or general structures,
it is that general proofs are generally useful.


## Exmpale: Euler Characteristic

$$V - E + F$$
- Probably the first ever topological property
- Classifies many shape in a way that isn't affected by distortions



# Homotopy

<p style="text-align: center">
Colin Phillips
</p>



## Paths and Loops

Let $I$ be the unit interval $[0,1] \subseteq \R$.

A path is a continouos function from $I$ to some space $T$.

A loop is a path $f$ such that $f(0) = f(1)$.


### Example

<div style="display: flex">
    <div style="text-align: left">
Consider the function:

$$
\begin{align*}
    f &: I \rightarrow \R^2  \\\\
    f & (x) = (\cos(2\pi x), \sin(2\pi x))  \\\\
\end{align*}
$$

This is a path because it is continuous.
Furthermore, this is a loop, because $f(0) = f(1)$
    </div>
    <div style="flex: 55%">
        <img src="/dist/img/loop.png"></img>
    </div>
</div>



## Homotopy

Let $f : I \rightarrow T$ and $g : I \rightarrow T$ be paths that have
the same starting point $P$ and same ending point $Q$.

A *homotopy* between these paths is a **continuous** function:
$$
\begin{align*}
    H& : I \times I \rightarrow T  \\\\
    H&(0,x) = f(x) & H&(1, x) = g(x)  \\\\
    H&(t,0) = P & H&(t, 1) = Q  \\\\
\end{align*}
$$

If a homotopy $H$ exists, $f$ and $g$ are *homotopic*.


### A much needed visual

<div style="display: flex">
    <div style="text-align: left">
    <br><br>
A homotopy can be thought of as a continuous family of functions,
where $t$ is selecting which particular function we want:
$$H_t(x) := H(t,x)$$
    </div>
    <div style="width: 4em"></div>
    <div style="flex: 150%">
        <img src="/dist/img/homotopy1.svg"></img>
    </div>
</div>



## Circle $\leftrightarrow$ Square

A square and a circle can both be though of as loops in $\R^2$.
$$
\begin{align*}
\text{Circle}(x) &= (\sqrt{2}\cos(2\pi x + 2\pi/8), \sqrt{2}\sin(2\pi x + 2\pi / 8)) \\\\
\text{Square}(x) &= 
    \begin{cases} 
        (1-8x, 1) & 0 \le x \le 1/4 \\\\
        (-1, 1-8(x-1/4)) & 1/4 < x \le 2/4 \\\\
        (-1+8(x-2/4), -1) & 2/4 < x \le 4/4 \\\\
        (1, -1+8(x-3/4)) & 4/4 < x \le 1
    \end{cases}
\end{align*}
$$

Can we prove that these are homotopic?

Note: we need to show that the Square is contiuous, just trust me



## A Specific Homotopy

$$
\begin{align*}
H_t(x) &= \lambda_t (2\pi x + 2\pi / 8)\sqrt{2}\begin{bmatrix}
    \cos(2\pi x + 2\pi / 8) \\\\
    \sin(2\pi x + 2\pi / 8) \\\\
\end{bmatrix} \\\\
\lambda_t(\theta) &= \begin{cases}
1-t+\frac{t}{\sqrt{2}}\csc\theta & 0 \le \theta \le 2\pi/4 \\\\
1-t-\frac{t}{\sqrt{2}}\sec\theta & 2\pi/4 < \theta \le 2\pi2/4 \\\\
1-t-\frac{t}{\sqrt{2}}\csc\theta & 2\pi2/4 < \theta \le 2\pi3/4 \\\\
1-t+\frac{t}{\sqrt{2}}\sec\theta & 2\pi3/4 < \theta \le 2\pi 
\end{cases}
\end{align*}
$$

Then we need to prove that it is continuous.

Or...


## infinite pairs of birds with one stone

Any 2 paths with the same start and end points are homotopic in $\R^2$!

Let $f$ and $g$ be paths with $P=f(0)=g(0)$ and $Q=f(1)=g(1)$:

$$
\begin{align*}
H_t(x) &= (1-t)f(x) + t g(x) \\\\
\\\\
H_0(x) &= (1-0)f(x) + 0 g(x) = f(x) \\\\
H_1(x) &= (1-1)f(x) + 1 g(x) = g(x) \\\\
H_t(0) &= (1-t)P + tP = (1 - t + t)P = P \\\\
H_t(1) &= (1-t)Q + tQ = (1 - t + t)Q = Q \\\\
\end{align*}
$$

Note:
Sometimes, trying to solve the more general problem can give you insight
into a specific problem! It is good to look for general truths



## Are two paths always homotopic?

You might think that from the previous homotopy.

But, the "proof" of that implicitly used the fact that
$\R^2$ is closed under addition and scalar multiplication.
If this were not the case, then we couldn't be sure if that $H$
is defined everywhere. And for $H$ to be a homotopy, we need
to be sure it is a function, not a partial function.

Lets look at 2 loops in $\R^2 - \\{(0,0)\\}$

Note: 
Also, addition and scalar multiplication
both preserve continuity, so $H$ is continuous because $f$ and $g$ are.


<div style="height: 600px">
<img src="/dist/img/nohomotopy.svg"></img>
</div>


## Fundamental Groups

Notice how in $\R^2$ all of the loops (given a shared "*base point*")
were homotopic. So *in a sense*, we can say all of the loops in $\R^2$
are the same.

And in $\R^2 - \\{(0,0)\\}$, there are many loops which are homotopic,
but many which are not.

If we bundle together all the loops which are homotopic to each other,
in a space, we get the fundamental group, which is an important
topological property of a space.

In $\R^2$ there is only one bundle, and but in $\R^2 - \\{(0,0)\\}$,
there are many.


There is more to say about fundamental groups and what they can do,
but that requires too much algebra and topology to fit in here.

Note:
One application is showing that every continuous map from a disk
to itself has a fixed point



The End

Sources:
- Introduction to Topology and Geometry, Saul Stahl
- Introduction to Category Theory, Peter Smith, ($\S29.4$)<br>
  (For the discussion of fundamendtal groups and their applications)
