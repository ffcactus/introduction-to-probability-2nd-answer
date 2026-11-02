# Recap

## Derivatives

| Function $f(x)$ | Derivative $f'(x)$ |
|---|---|
| $\sin x$ | $\cos x$ |
| $\cos x$ | $-\sin x$ |
| $\tan x$ | $\sec^2 x$ |
| $\cot x$ | $-\csc^2 x$ |
| $\sec x$ | $\sec x\tan x$ |
| $\csc x$ | $-\csc x\cot x$ |
| $\sin^2 x$ | $2\sin x\cos x$ |
| $\cos^2 x$ | $-2\sin x\cos x$ |
| $\tan^2 x$ | $2\tan x\sec^2 x$ |
| $\sin^{-1}x=\arcsin x$ | $\displaystyle \frac{1}{\sqrt{1-x^2}}$ |
| $\cos^{-1}x=\arccos x$ | $\displaystyle -\frac{1}{\sqrt{1-x^2}}$ |
| $\tan^{-1}x=\arctan x$ | $\displaystyle \frac{1}{1+x^2}$ |


## Integration

### Integration by Substitution

Suppose
$$
I = \int_{-\infty}^{a + t} f(2a - x) \, dx
$$

Step 1, transform the differential.

Let $w=2a-x$, differentiate to both side with respect to $x$ we have:
$$
\frac{dw}{dx} = -1
$$
Therefore,
$$
dw = -dx
$$

Step 2, transform the integration limits
$$
\begin{array}{c|c}
\text{Original $x$} & \text{New $w = 2a - x$} \\
\hline
x \to -\infty & w \to +\infty \\
x = a + t & w = 2a - (a + t) = a - t\\
\end{array}
$$

Step 3, substitute.
$$
I = \int_{a-t}^{+\infty} f(w)(-dw) = - \int_{a-t}^{+\infty} f(w) \, dw
$$


### Integration by Parts

Recall the product rules:
$$
\frac{d}{dx}[u(x)v(x)]=u'(x)v(x)+u(x)v'(x).
$$

Now integrate every term with respect to $x$:
$$
\int \frac{d}{dx}[u(x)v(x)]\,dx
=
\int u'(x)v(x)\,dx
+
\int u(x)v'(x)\,dx.
$$

Simplify the left side:
$$
\int \frac{d}{dx}[u(x)v(x)]\,dx
=u(x)v(x)+C.
$$

Therefore, we have
$$
u(x)v(x)
=
\int u'(x)v(x)\,dx
+
\int u(x)v'(x)\,dx,
$$
where we've omitted the arbitrary integration constant for the moment.

Introduce the shorthand $du$ and $dv$. By definition,
$$
du=u'(x)\,dx,\qquad dv=v'(x)\,dx.
$$

Consequently,
$$
\begin{aligned}
\int u'(x)v(x)\,dx&=\int v\,du,\\
\int u(x)v'(x)\,dx&=\int u\,dv.
\end{aligned}
$$

$$
uv=\int v\,du+\int u\,dv.
$$

Rearranging:
$$
\int u\,dv=uv-\int v\,du
$$

Here, $du = u'(x) dx$ and $dv = v'(x) dx$

**Example**

Suppose we want to calculate
$$
\int x e^x\,dx.
$$

Neither factor is difficult individually, but integrating their product directly isn't obvious.

Choose
$$
u=x,\qquad dv=e^x\,dx.
$$

Then
$$
du=dx,\qquad v=e^x.
$$

Using integration by parts,
$$
\begin{aligned}
\int xe^x\,dx
&=xe^x-\int e^x\,dx\\
&=xe^x-e^x+C.
\end{aligned}
$$

## Named Distributions

### Binomial

Perform $n$ independent Bernoulli trials, each with the same success probability $p$. Count the number of successes.

$$
X \sim \operatorname{Bin}(n, p)
$$

$$
P(X=k)=\binom{n}{k}p^k(1-p)^{n-k}
$$

$$
\mathbb{E}[X] = np
$$

$$
\operatorname{Var}
$$

### Hypergeometric

Suppose a population contains:
- $w$ white objects,
- $b$ black objects,

and you randomly choose $n$ objects without replacement.
Let $X$ be the number of white objects selected.

$$
X \sim \operatorname{HGeom}(w, b, n)
$$

$$
P(X=k) = \frac{\binom{w}{k} \binom{b}{n-k}}{\binom{w+b}{k}}
$$

$$
\mathbb{E}[X] = np
$$

$$
\operatorname{Var} = np(1-p)\frac{N-n}{N-1}
$$

### Discreted Uniform

$$
X\sim \operatorname{DUnif}(1,n)
$$

$$
P(X=k)=\frac{1}{n}
$$

$$
\mathbb{E}[X] = \frac{n+1}{2}
$$

$$
\operatorname{Var} = \frac{n^2-1}{12}
$$

### Geometric

Number of failures before the first success.

$$
X \sim \operatorname{Geom}(p)
$$

$$
P(X=k) = q^k p
$$

$$
\mathbb{E}[X] = \frac{q}{p}
$$

$$
\operatorname{Var} = \frac{q}{p^2}
$$

### Negative Binomial

Number of failures before the $r$-th success.

$$
X \sim \operatorname{NBin}(r, p)
$$

$$
P(X=k) = \binom{k+r-1}{r-1}p^r q^k
$$

$$
\mathbb{E}[X] = \frac{rq}{p}
$$

$$
\operatorname{Var} = \frac{rq}{p^2}
$$

### First Success

Number of trials that the first success appears.

$$
X \sim \operatorname{FS}(p)
$$

$$
P(X=k) = q^{k-1}p
$$

$$
\mathbb{E}[X] = \frac{1}{p}
$$

$$
\operatorname{Var}(X) = \frac{q}{p^2}
$$

### Negative Hypergeometric

An urn contains $w$ white balls and $b$ black balls, which are randomly drawn one by one without replacement, until $r$ white balls have been obtained. The number of black balls drawn before drawing the $r$-th white ball has a Negative Hypergeometric distribution with parameters $w,b,r$.

$$
X \sim \operatorname{NHGeom}(w,b,r)
$$

$$
P(X=k) = \frac{\binom{w}{r-1} \binom{b}{k}}{\binom{w+b}{r+k-1}} \cdot \frac{w-r+1}{w+b-r-k+1}
$$

Alternatively
$$
P(X=k) = \frac{\binom{r+k-1}{r-1} \binom{w+b-r-k}{w-r}}{\binom{w+b}{w}}
$$

$$
\mathbb{E}[X] = \frac{rb}{w+1}
$$

### Poisson

Count how many relatively rare events occur in some interval.

$$
X \sim \operatorname{Pois}(\lambda)
$$

$$
P(X=k) = e^{-\lambda} \frac{\lambda^k}{k!}
$$

$$
\mathbb{E}[X] = \lambda
$$

$$
\operatorname{Var} = \lambda
$$


## Continuous Random Variable

### Uniform

PDF:

$$
f(x) =
\begin{cases}
\frac{1}{b-a} & \text{$a \lt x \lt b$,} \\
0 & \text{otherwise.}
\end{cases}
$$

CDF:

$$
F(x) =
\begin{cases}
0 & \text{if $x \le a$,} \\
\frac{x-a}{b-a} & \text{if $a \lt x \lt b$,} \\
1 & \text{if $a \ge b$.}
\end{cases}
$$

Expectation:
$$
\operatorname{E}[U] = \frac{a+b}{2}
$$

Variance:
$$
\operatorname{Var}(U) = \frac{(b-a)^2}{12}
$$

### Logistic

PDF:

$$
f(x) = \frac{e^x}{(1+e^x)^2}, \qquad \text{$x \in \mathbb{R}$}
$$

CDF:

$$
F(x) = \frac{e^x}{1+e^x}, \qquad \text{$x \in \mathbb{R}$}
$$

Expectation:

$$
\mathbb{E}[X] = 0
$$

Variance:

$$
\operatorname{Var}(X) = \frac{\pi^2}{3}
$$


### Rayleigh Distribution

PDF:

$$
f(x) = x e^{- \frac{x^2}{2}}
$$

CDF:

$$
\begin{aligned}
F(x)
&= \int_0^x t e^{- \frac{t^2}{2}} dt
& \text{Rayleigh has support $x \ge 0$} \\
&= - \int_{0}^{- x^2/2} e^{u} du 
& \text{let $u=-\frac{t^2}{2}$, $du = -t dt$} \\
&= - e^u \Big|_0^{- x^2/2} \\
&=
\begin{cases}
1 - e^{- x^2 / 2} & \text{$x \ge 0$}, \\
0 & \text{$x \lt 0$}
\end{cases}
\end{aligned}
$$

Expectation:

$$
\mathbb{E}[X] = \sqrt{\frac{\pi}{2}}
$$

Variance:

$$
\operatorname{Var}(X) = \frac{4 - \pi}{2}
$$

### Normal

Standard Normal PDF:
$$
\varphi(z) = \frac{1}{\sqrt{2\pi}} e^{-z^2/2}, \qquad \text{for $-\infty \lt z \lt +\infty$.}
$$

Standard Normal CDF:
$$
\Phi(z) = \int_{-\infty}^z \frac{1}{\sqrt{2\pi}} e^{-t^2/2} \, dt.
$$

If $Z \sim \mathcal{N}(0, 1)$, then Normal is
$$
X = \mu + \sigma Z
$$

PDF:

$$
\begin{aligned}
f(x)
&= \varphi \left(\frac{x - \mu}{\sigma}\right) \frac{1}{\sigma} 
\end{aligned}
$$

CDF:

$$
\begin{aligned}
F(x)
&= \Phi \left(\frac{x - \mu}{\sigma}\right)
\end{aligned}
$$

### Exponential

PDF:

$$
f(x) = \lambda e^{- \lambda x}, \qquad \text{$x \gt 0$.}
$$

CDF:

$$
F(x) = 1 - e^{- \lambda x}, \qquad \text{$x \gt 0$.}
$$

Expectation:
$$
\mathbb{E}[X] = \frac{1}{\lambda}
$$

Variance:
$$
\operatorname{Var}(X) = \frac{1}{\lambda^2}
$$