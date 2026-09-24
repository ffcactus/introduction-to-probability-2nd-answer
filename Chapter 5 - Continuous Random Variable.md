# Continuous Random Variable

## Recap

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

If $Z \sim \mathcal{N}(0, 1)$, then
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

### Derivatives

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

## PDFs and CDFs

### Q1

The Rayleigh distribution from Example 5.1.7 has PDF
$$
f(x) = x e^{- x^2 /2}
$$

Let $X$ have Rayleigh distribution

(a) Find $P(1 \lt X  \lt 3)$.

(b) Find the first quartile, median, and third quartile of $X$; these are defined to be the values $q_1, q_2, q_3$ (respectively) such that $P(X \le q_j) = j/4$ for $j = 1,2,3$.

Answer:

(a)

$$
\begin{aligned}
P(1 \lt X \lt 3)
&= F_X(3) - F_X(1) \\
&= (1 - e^{-9/2}) - (1 - e^{-1/2}) \\
&\approx 0.595
\end{aligned}
$$

(b)

For the first quartile, we have
$$
1 - e^{- x^2 / 2} = \frac{1}{4}
$$

We have
$$
- \frac{x^2}{2} = \ln(\frac{3}{4})
$$

$$
x \approx 0.759
$$

For the median we have
$$
1 - e^{- x^2 / 2} = \frac{2}{4}
$$

We have
$$
- \frac{x^2}{2} = \ln(\frac{2}{4})
$$

$$
x \approx 1.177
$$

For the third quartile we have
$$
1 - e^{- x^2 / 2} = \frac{3}{4}
$$

We have
$$
- \frac{x^2}{2} = \ln(\frac{1}{4})
$$

$$
x \approx 1.665
$$

### Q2

(a) Make up a PDF $f$, with an application for which that PDF would be plausible, where $f(x) \gt 1$ for all $x$ in a certain interval.

(b) Show that if a PDF $f$ has $f(x) \gt 1$ for all $x$ in a certain interval, then that interval must have length less than $1$.

Answer:

(a)

$$
f(x) =
\begin{cases}
2 & \text{for $0 \lt x \lt 0.5$}, \\
0 & \text{otherwise.}
\end{cases}
$$

(b)

Or the integral will be greater than 1 and makes the CDF invalid.

### Q3

Let $F$ be the CDF of a continuous r.v., and $f= F'$ be the PDF.

(a) Show that $g$ defined by $g(x) = 2 F(x) f(x)$ is also a valid PDF.

(b) Show that $h$ defined by $h(x) = \frac{1}{2} f(−x) + \frac{1}{2} f(x)$ is also a valid PDF.

Answer:

(a)

If $f$ is a valid PDF and $F$ is a corresponding CDF, we have
$$
F(x)f(x) \ge 0
$$

Also we have
$$
\begin{aligned}
\int_{-\infty}^{\infty} g(x) dx
&= \int_{-\infty}^{\infty} 2 F(x) F'(x) dx \\
&= [F(x)]^2 \Big|_{-\infty}^{+\infty} \\
&= 1 - 0\\
&= 1
\end{aligned}
$$

Therefore, $g$ is a valid PDF.

(b)

If $f$ is valid PDF we have
$$
h(x) = \frac{1}{2} f(−x) + \frac{1}{2} f(x) \ge 0
$$

Also we have
$$
\begin{aligned}
\int_{-\infty}^{\infty} h(x) dx
&= \int_{-\infty}^{\infty} (\frac{1}{2} f(−x) + \frac{1}{2} f(x)) dx \\
&= \int_{-\infty}^{\infty} \frac{1}{2} f(−x) dx + \int_{-\infty}^{\infty} \frac{1}{2} f(x) dx \\
&= \frac{1}{2} + \frac{1}{2} \\
&= 1
\end{aligned}
$$

Therefore, $h$ is also a valid PDF.

### Q4

Let $X$ be a continuous r.v. with CDF $F$ and PDF $f$.

(a) Find the conditional CDF of $X$ given $X \gt c$, for $c$ a constant with $P(X \gt c)  \ne 0$. That is, find $P(X \le x\mid X \gt c)$ for all c, in terms of $F$.

(b) Find the conditional PDF of $X$ given $X \gt c$ (this is the derivative of the conditional CDF).

(c) Check that the conditional PDF from (b) is a valid PDF, by showing directly that it is nonnegative and integrates to $1$.

Answer:

(a)

By conditional probability we have
$$
P(X \le x \mid X \gt c) = \frac{P(X \le x, X \gt c)}{P(X \gt c)}
$$

if $x \ge c$, we have
$$
\begin{aligned}
\frac{P(X \le x, X \gt c)}{P(X \gt c)}
&= \frac{P(c \lt X \le x)}{P(X \gt c)} \\
&= \frac{F(x) - F(c)}{1-F(c)} \\
\end{aligned}
$$

if $x \lt c$, $P(X \le x \mid X \gt c) = 0$

Therefore,
$$
F_{X \mid X \gt c} =
\begin{cases}
\frac{F(x) - F(c)}{1-F(c)} & \text{for $x \ge c$,} \\
0 & \text{otherwise.}
\end{cases}
$$

(b)

$$
\begin{aligned}
f_{X \mid X \gt c}
&=
\begin{cases}
\frac{1}{1-F(c)} f(x) & \text{for $x \gt c$,} \\
0 & \text{otherwise.}
\end{cases}
\end{aligned}
$$

(c)

Obviously
$$
\frac{1}{1-F(c)} f(x) \ge 0
$$

And
$$
\begin{aligned}
\int_{c}^\infty \frac{1}{1-F(c)} f(x) dx
&= \frac{1}{1-F(c)} \int_{c}^\infty f(x) dx \\
&= \frac{1}{1-F(c)} \cdot F(x) \Big|_c^\infty \\
&= \frac{1}{1-F(c)} (1 - F(c)) \\
&= 1
\end{aligned}
$$

So $f_{X \mid X \gt c}$ is a valid PDF.

### Q5

A circle with a random radius $R \sim \operatorname{Unif}(0,1)$ is generated. Let $A$ be its area.

(a) Find the mean and variance of $A$, without first finding the CDF or PDF of $A$.

(b) Find the CDF and PDF of $A$.

Answer:

(a)

$A=\pi R^2$, By LOTUS, we have

$$
\begin{aligned}
\mathbb{E}[A]
&= \int_0^1 \pi x^2 dx
&= \pi \int_0^1 x^2 dx \\
&= \pi \frac{1}{3} x^3 \Big|_0^1 \\
&= \frac{\pi}{3}
\end{aligned}
$$

$$
\begin{aligned}
\mathbb{E}[A^2]
&= \int_0^1 \pi^2 x^4 dx \\
&= \frac{\pi^2}{5} x^5 \Big|_0^1 \\
&= \frac{\pi^2}{5}
\end{aligned}
$$

$$
\operatorname{Var}[A] = \mathbb{E}[A^2] - (\mathbb{E}[A])^2 = \frac{\pi^2}{5} - \frac{\pi^2}{9} 
$$

(b)

$$
\begin{aligned}
F_A (x)
&= P(A \le x) \\
&= P(\pi R^2 \le x) \\
&= P(R \le \sqrt{\frac{x}{\pi}}) \\
&= \sqrt{\frac{x}{\pi}} & \text{for $0 \le x \le \pi$.}
\end{aligned}
$$

$$
f_A = \frac{d}{dx} \sqrt{\frac{x}{\pi}} = \frac{1}{2\sqrt{\pi x}}
$$
for $0 \le x \le \pi$, and otherwise $f_A = 0$.A

### Q6

The $68-95-99.7\%$ rule gives approximate probabilities of a Normal r.v. being within
$1$, $2$, and $3$ standard deviations of its mean. Derive analogous rules for the following distributions.

(a) $\operatorname{Unif}(0,1)$

(b) $\operatorname{Expo}(1)$.

(c) $\operatorname{Expo}(1/2)$. Discuss whether there is one such rule that applies to all Exponential distributions, just as the $68-95-99.7\%$ rule applies to all Normal distributions, not just to the standard Normal.

Answer:

(a)

For $U \sim \operatorname{Unif}(0, 1)$, we have the mean and standard deviation below:

$$
\mathbb{E}[U] = \frac{1}{2}
$$

$$
\sigma = \sqrt{\operatorname{Var}(U)} = \sqrt{\frac{1}{12}} = \frac{\sqrt{3}}{6} 
$$

However, $\mu + 2 \sigma \gt 1$ and $\mu - 2 \sigma \lt 0$

So the r.v. will always within $2$ and $3$ standard deviations of its mean.

(b)

For $X \sim \operatorname{Expo}(1)$, we have
$$
\mathbb{E}[X] = \frac{1}{\lambda} = 1, \qquad \sigma=\sqrt{\frac{1}{\lambda^2}} = 1
$$

The support of Exponential is $x \gt 0$.

For $1$ standard deviations of its mean, we have
$$
\begin{aligned}
F_X(1+1) - F_X(0)
&= 1 - e^{-2} - (1 - e^{0}) \\
&\approx 0.865
\end{aligned}
$$

For $2$ standard deviations of its mean, we have
$$
\begin{aligned}
F_X(1+2) - F_X(0)
&= 1 - e^{-3} - (1 - e^{0}) \\
&\approx 0.95
\end{aligned}
$$

For $3$ standard deviations of its mean, we have
$$
\begin{aligned}
F_X(1+3) - F_X(0)
&= 1 - e^{-4} - (1 - e^{0}) \\
&\approx 0.982
\end{aligned}
$$

(c)

For $X \sim \operatorname{Expo}(\frac{1}{2})$, we have
$$
\mathbb{E}[X] = \frac{1}{\lambda} = 2, \qquad \sigma=\sqrt{\frac{1}{\lambda^2}} = 2
$$

The support of Exponential is $x \gt 0$.

For $1$ standard deviations of its mean, we have
$$
\begin{aligned}
F_X(2+2) - F_X(0)
&= 1 - e^{-2} - (1 - e^{0}) \\
&\approx 0.865
\end{aligned}
$$

For $2$ standard deviations of its mean, we have
$$
\begin{aligned}
F_X(2+4) - F_X(0)
&= 1 - e^{-3} - (1 - e^{0}) \\
&\approx 0.95
\end{aligned}
$$

For $3$ standard deviations of its mean, we have
$$
\begin{aligned}
F_X(2+6) - F_X(0)
&= 1 - e^{-4} - (1 - e^{0}) \\
&\approx 0.982
\end{aligned}
$$

The rule requires that all the distributions in the family have the same shape and differ only by location/scale transformations. As a counterexample, for $X \sim \operatorname{Gamma}(\alpha, \theta)$, changing $\alpha$ changes the shape.

### Q7

Let
$$
F(x) = \frac{2}{\pi} \sin^{-1}(\sqrt{x}), \quad \text{for $0 \lt x \lt 1$},
$$
$F(x) = 0$ for $x \le 0$, and $F(x) = 1$ for $x \ge 1$.

(a) Check that $F$ is a valid CDF, and find the corresponding PDF $f$. This distribution is called the _Arcsine distribution_, though it also goes by the name $\operatorname{Beta}(1/2,1/2)$ (we will explore the Beta in depth in Chapter 8).

(b) Explain how it is possible for $f$ to be a valid PDF even though $f(x)$ goes to $\infty$ as $x$ approaches $0$ from the right and as $x$ approaches $1$ from the left.

Answer:

(a)

$$
\frac{d}{dx} \sin^{-1}(u) = \frac{u'}{\sqrt{1 - u^2}}
$$

Let $u = \sqrt{x}$, $u'= \frac{1}{2\sqrt{x}}$, we have

$$
\frac{d}{dx}\sin^{-1}(\sqrt{x}) = \frac{\frac{1}{2\sqrt{x}}}{\sqrt{1-x}} = \frac{1}{2 \sqrt{x(1-x)}}
$$

So

$$
f = \frac{2}{\pi} \frac{1}{2 \sqrt{x(1-x)}} = \frac{1}{\pi \sqrt{x(1-x)}} \gt 0, \quad \text{for $0 \lt x \lt 1$.}
$$

Check if the integral of PDF is $1$:
$$
\begin{aligned}
F = \int_0^1 \frac{1}{\pi \sqrt{x(1-x)}} dx
&= \frac{1}{\pi} \int_0^1 \frac{1}{\sqrt{x(1-x)}} dx \\
\end{aligned}
$$

Let $x=\sin^2(\theta)$, we have
$$
\begin{aligned}
F
&= \frac{1}{\pi} \int_0^\frac{\pi}{2} \frac{1}{\sin \theta \cos \theta} 2 \sin \theta \cos \theta d\theta \\
&= \frac{2}{\pi} \int_0^\frac{\pi}{2} d \theta \\
&= 1
\end{aligned}
$$

So $F$ is a valid CDF.

(b)

Why? The calculus shows why.


### Q8

The Beta distribution with parameters $a=3$, $b=2$ has PDF
$$
f(x) = 12 x^2 (1−x), \quad \text{for $0 \lt x \lt 1$}.
$$

(We will discuss the Beta in detail in Chapter 8.) Let $X$ have this distribution.

(a) Find the CDF of $X$.

(b) Find $P(0 \lt X \lt 1/2)$.

(c) Find the mean and variance of $X$ (without quoting results about the Beta distribution).

Answer:

(a)

$$
F(x) = 
\begin{cases}
0 & \text{$x \le 0$,} \\
4 x^3 - 3 x^4 & \text{for $0 \lt x \lt 1$,} \\
1 & \text{$x \ge 1$.}
\end{cases}
$$

(b)

$$
P(0 \lt X \lt 1/2) = F(1/2) - F(0) = \frac{5}{16}
$$

(c)

$$
\begin{aligned}
\mathbb{E}[X]
&= \int_0^1 x f(x) dx \\
&= 12 \int_0^1 (x^3-x^4) dx \\
&= 3 x^4 \Big|_0^1 - \frac{12}{5} x^5 \Big|_0^1 \\
&= \frac{3}{5}
\end{aligned}
$$

$$
\begin{aligned}
\mathbb{E}[X^2]
&= \int_0^1 x^2 f(x) dx \\
&= 12 \int_0^1 (x^4-x^5) dx \\
&= \frac{12}{5} x^5 \Big|_0^1 - 2 x^6 \Big|_0^1 \\
&= \frac{2}{5}
\end{aligned}
$$

$$
\operatorname{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2 = \frac{1}{25}
$$

### Q9

The Cauchy distribution has PDF
$$
f(x) = \frac{1}{\pi (1 + x^2)},
$$
for all real $x$. (We will introduce the Cauchy from another point of view in Chapter 7.)

Find the CDF of a random variable with the Cauchy PDF.

Hint: Recall that the derivative of the inverse tangent function
$$
\arctan(x) = \frac{1}{1+x^2}.
$$

Answer:

$$
\begin{aligned}
F(x)
&= \int_{-\infty}^x  \frac{1}{\pi (1 + t^2)} dt \\
&= \frac{1}{\pi} \int_{-\infty}^x \frac{1}{1 + t^2} dt \\
&= \frac{1}{\pi} \arctan(t) \Big|_{-\infty}^x \\
&= \frac{1}{\pi} (\arctan(x) + \frac{\pi}{2}), & \text{for all real $x$.}
\end{aligned}
$$

## Uniform and Universality of Uniform

### Q10

Let $U \sim \operatorname{Unif}(0,8)$.

(a) Find $P(U \in (0,2) \cup (3,7))$ without using calculus.

(b) Find the conditional distribution of $U$ given $U \in (3,7)$.

Answer:

(a)

The length of $(0,2) \cup (3,7)$ is $6$, so the
$$
P(U \in (0,2) \cup (3,7)) = \frac{6}{8} = \frac{3}{4}
$$

(b)

$$
\begin{aligned}
F_U(x)
&= P(U \le x \mid U \in (3,7)) \\
&= \frac{P(U \le x, U \in (3,7))}{P(U \in (3,7))} \\
&=
\begin{cases}
0 & \text{if $x \le 3$,} \\
\frac{\frac{x-3}{8}}{\frac{7-3}{8}} = \frac{x-3}{4} & \text{if $3 \lt x \lt 7$,} \\
1 & \text{if $x \ge 7$.} \\
\end{cases}
\end{aligned}
$$

### Q11

Let $U$ be a Uniform r.v. on the interval $(−1,1)$ (be careful about minus signs).

(a) Compute $\mathbb{E}[U]$, $\operatorname{Var}(U)$, and $\mathbb{E}[U^4]$.

(b) Find the CDF and PDF of $U^2$. Is the distribution of $U^2$ Uniform on $(0,1)$?

Answer:

(a)

Since the interval is $(-1, 1)$, we have
$$
f_U(u) = \frac{1}{2}, \quad -1 \lt u \lt 1.
$$

$$
\mathbb{E}[U] = \int_{-1}^1 t \frac{1}{2} dt = 0
$$

$$
\mathbb{E}[U^2] = \int_{-1}^1 t^2 \frac{1}{2} dt = \frac{1}{3}
$$

$$
\operatorname{Var}(U) = \mathbb{E}[U^2] - (\mathbb{E}[U])^2 = \frac{1}{3}
$$

$$
\mathbb{E}[U^4] = \int_{-1}^1 t^4 \frac{1}{2} dt = \frac{1}{5}
$$

(b)

$$
\begin{aligned}
F_{U^2}(x)
&= P(U^2 < x) \\
&= P(-\sqrt{x} \lt U \lt \sqrt{x}) \\
&= F_U(\sqrt{x}) - F_U(-\sqrt{x}) \\
&= \frac{\sqrt{x} - (-1)}{2} - \frac{-\sqrt{x} - (-1)}{2} \\
&= 
\begin{cases}
0 & \text{if $x \le 0$,} \\
\sqrt{x} & \text{if $0 \lt x \lt 1$,} \\
1 & \text{if $x \ge 1$.}
\end{cases}
\end{aligned}
$$

$$
\begin{aligned}
f_{U^2}(x)
&= F_{U^2}'
&= 
\begin{cases}
\frac{1}{2 \sqrt{x}} & \text{if $0 \lt x \lt 1$,} \\
0 & \text{otherwise.}
\end{cases}
\end{aligned}
$$

So $U^2$ is not uniform.

