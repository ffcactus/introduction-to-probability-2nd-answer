# Continuous Random Variable

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

### Q12

A stick is broken into two pieces, at a uniformly random breakpoint. Find the CDF and average of the length of the longer piece.

Answer:

Without lose the generality, we can suppose the stick is of length $1$ and the breakpoint is uniformly random in range $(0.5, 1)$. To make a valid CDF, we do a normalization on the PDF that
$$
f_X =
\begin{cases}
2 & \text{for $0.5 \le x \le 1$,} \\
0 & \text{otherwise.}
\end{cases}
$$

Therefore, the CDF is
$$
F_X =
\begin{cases}
0 & \text{for $x \lt 0.5$,} \\
2x-1 & \text{for $0.5 \le x \le 1$,} \\
1 & \text{for $1 \lt x$.}
\end{cases}
$$

For the average length, we have
$$
\mathbb{E}[X] = \int_{0.5}^1 2 x dx = 2 \frac{1}{2} x^2 \big|_{0.5}^1 = 1 - 0.25 = 0.75
$$

### Q13

A stick of length $1$ is broken at a uniformly random point, yielding two pieces. Let $X$ and $Y$ be the lengths of the shorter and longer pieces, respectively, and let $R= X/Y$ be the ratio of the lengths $X$ and $Y$.

(a) Find the CDF and PDF of $R$.

(b) Find the expected value of $R$ (if it exists).

(c) Find the expected value of $1/R$ (if it exists).

Answer:

(a)

Let $U$ be the broken point, we have $U \sim \operatorname{Unif}(0, 1)$, and
$$
R = \frac{X}{Y} =
\begin{cases}
\frac{U}{1-U} & \text{for $0 \lt U \le 0.5$,} \\
\frac{1-U}{U} & \text{for $0.5 \lt U \lt 1$.} \\
\end{cases}
$$

Because $0 \lt U \le 0.5$ and $0.5 \lt U \lt 1$ are disjoint events, we have
$$
\begin{aligned}
F_R(r) 
&= P(\frac{U}{1-U} \le r, U \le 0.5) + P(\frac{1-U}{U} \le r, U \gt 0.5) \\
&= P(U \le \frac{r}{1+r}, U \le 0.5) + P(U \ge \frac{1}{1+r}, U \gt 0.5) \\
\end{aligned}
$$

Since $0 \lt r \lt 1$, we have $0 \lt \frac{r}{1+r} \lt 0.5$, and $0.5 \lt \frac{1}{1+r} \lt 1$ so
$$
P(U \le \frac{r}{1+r}, U \le 0.5) = \frac{r}{1+r} \\
P(U \ge \frac{1}{1+r}, U \gt 0.5) = 1 - \frac{1}{1+r} = \frac{r}{1+r}
$$

Substitute them we have
$$
\begin{aligned}
F_R(r) 
&= P(\frac{U}{1-U} \le r, U \le 0.5) + P(\frac{1-U}{U} \le r, U \gt 0.5) \\
&= P(U \le \frac{r}{1+r}, U \le 0.5) + P(U \ge \frac{1}{1+r}, U \gt 0.5) \\
&= \frac{2r}{1+r}
\end{aligned}
$$


Therefore, we have
$$
F_R(r) =
\begin{cases}
0 & \text{for $r \le 0$,} \\
\frac{2r}{1+r} & \text{for $0 \lt r \lt 1$,} \\
1 & \text{for $1 \le r$.} \\
\end{cases}
$$

and
$$
f_R(r) = F_R'(r) =
\begin{cases}
\frac{2}{(1+r)^2} & \text{for $0 \lt r \lt 1$,} \\
0 & \text{otherwise.}
\end{cases}
$$

(b)
$$
\begin{aligned}
\mathbb{E}[R]
&= \int_0^1 \frac{2r}{(1+r)^2} dr
\end{aligned} 
$$

Let $u = 1+r$, we have $du = dr$, so
$$
\begin{aligned}
\int_0^1 \frac{2r}{(1+r)^2} dr
&= \int_1^2 \frac{2(u-1)}{u^2} du \\
&= \int_1^2 \frac{2}{u} du - \int_1^2 \frac{2}{u^2} du \\
&= 2 \ln(u) \Big|_1^2 - 2 (-\frac{1}{u}) \Big|_1^2 \\
&= 2 \ln(2) -1
\end{aligned}
$$

(c)

By LOTUS we have
$$
\mathbb{E}[g(R)] = \int_{-\infty}^{+\infty} g(r)f_R(r) dr
$$

Therefore, we have
$$
\begin{aligned}
\mathbb{E}[1/R]
&= \int_0^1 \frac{1}{r} \frac{2}{(1+r)^2} dr \\
\end{aligned}
$$

For $0 \lt r \lt 1$, we have $0 \lt (1+r)^2 \lt 4$.

Since $r > 0$,
$$
\frac{2}{r(1+r)^2} \ge \frac{1}{2r}
$$

$$
\begin{aligned}
\mathbb E\left[\frac1R\right]
&=\int_0^1\frac{2}{r(1+r)^2}\,dr\\
&\ge\int_0^1\frac1{2r}\,dr\\
&=+\infty.
\end{aligned}
$$

### Q14

Let $U_1,\ldots,U_n$ be i.i.d. $\operatorname{Unif}(0,1)$, and $X = \max(U_1,\ldots,U_n)$. What is the PDF of $X$? What is $\mathbb{E}[X]$?

Hint: Find the CDF of $X$ first, by translating the event $X \le x$ into an event involving $U_1,\ldots,U_n$.

Answer:

Since they are i.i.d Uniforms, we have
$$
\begin{aligned}
F_X(x)
&= P(X \le x) \\
&= P(U_1 \le x \cap U_2 \le x \cap \ldots \cap U_n \le x) \\
&= P(U_1 \le x) P(U_2 \le x) \dots P(U_n \le x) \\
&= x^n
\end{aligned}
$$

We can get the PDF
$$
f_X(x) = F_X'(x) = n x^{n-1}
$$

By definition the expectation of $X$ is
$$
\begin{aligned}
\mathbb{E}[X]
&= \int_0^1 n x^n dx \\
&= \frac{n}{n+1} x^{n+1} \big|_0^1 \\
&= \frac{n}{n+1}
\end{aligned}
$$

### Q15

Let $U \sim \operatorname{Unif}(0,1)$. Using $U$, construct $X \sim \operatorname{Expo}(\lambda)$.

Answer:

Let $F$ be a CDF which is a continuous function and strictly increasing on the support of the distribution. In the universality of Uniform, we have a theorem that

Let $U \sim \operatorname{Unif}(0,1)$ and $X=F^{-1}(U)$. Then $X$ is an r.v. with CDF $F$.

The CDF of Exponential is
$$
F_X(x) = 1 - e^{-\lambda x}, \qquad \text{$x \gt 0$.}
$$

From
$$
y = 1 - e^{-\lambda x}
$$

we have
$$
e^{-\lambda x} = 1-y
$$

and
$$
x = -\frac{\ln(1-y)}{\lambda}.
$$

So
$$
X = F^{-1}(U) = -\frac{\ln(1-U)}{\lambda}.
$$

### Q16

Let $U \sim \operatorname{Unif}(0,1)$, and
$$
X = \log(\frac{U}{1-U})
$$

Then $X$ has the Logistic distribution, as defined in Example 5.1.6.

(a) Write down (but do not compute) an integral giving $\mathbb{E}(X^2)$.

(b) Find $\mathbb{E}[X]$ without using calculus.

Hint: A useful symmetry property here is that $1−U$ has the same distribution as $U$.

Answer

(a)

By LOTUS we have
$$
\mathbb{E}[X^2] = \int_0^1 \log^2(\frac{x}{1-x}) \,dx
$$

(b)

$$
X = \log(U) - \log(1-U)
$$

By symmetry $U$ and $1-U$ has the same distribution, $\mathbb{E}[X] = 0$.

### Q17

Let $U \sim \operatorname{Unif}(0,1)$. As a function of $U$, create an r.v. $X$ with CDF $F(x) = 1−e^{−x^3}$ for $x \gt 0$.

Answer:

Since $e^{−x^3}$ strictly decrease, $1−e^{−x^3}$ strictly increase. Let
$$
y = 1−e^{−x^3}
$$

we have
$$
x = \sqrt[3]{-\ln(1-y)}
$$

So 
$$
X = F^{-1}(U) = \sqrt[3]{-\ln(1-U)}
$$

### Q18

The _Pareto distribution_ with parameter $a \gt 0$ has PDF $f(x) = a/x^{a+1}$ for $x \ge 1$ (and $0$ otherwise). This distribution is often used in statistical modeling.

(a) Find the CDF of a Pareto r.v. with parameter $a$; check that it is a valid CDF.

(b) Suppose that for a simulation you want to run, you need to generate i.i.d. Pareto(a) r.v.s. You have a computer that knows how to generate i.i.d. Unif(0,1) r.v.s but does not know how to generate Pareto r.v.s. Show how to do this.

Answer:

(a)

The CDF of Pareto r.v. is
$$
\begin{aligned}
F_X(x)
&= \int_1^x \frac{a}{t^{a+1}} dt \\
&= - \frac{1}{t^a} \Big|_1^x \\
&= 1 - \frac{1}{x^a}
\end{aligned}
$$

To check it's a valid CDF, when $x \ge 1$ and $a \gt 0$, we have $1/x^a \le 1$, so $F_X(x) \ge 0$. And
$$
\begin{aligned}
F_X(t)
&= \int_1^{+\infty} \frac{a}{t^{a+1}} \, dt \\
&= - \frac{1}{t^a} \Big|_1^{+\infty} \\
&= 0 + 1 \\
&= 1
\end{aligned}
$$

(b)

Because $F_X(x)$ is strictly increasing for $a \gt 0$ and $x \ge 1$, by the universality of Uniform, we have
$$
X = F^{-1}_X(U) = \sqrt[a]{\frac{1}{1-U}}
$$
where $X$ has the Pareto distribution and $U$ is standard uniform. Since $U$ and $1-U$ has the same distribution, it can be simplified as
$$
X = F^{-1}_X(U) = \sqrt[a]{\frac{1}{U}}
$$

## Normal

### Q19

Let $Z \sim \mathcal{N}(0,1)$. Create an r.v. $Y \sim \mathcal{N}(1,4)$, as a simple-looking function of $Z$. Make sure to check that your $Y$ has the correct mean and variance.

Answer:

$Y$ can be considered a location-scale transformation from standard normal, it's mean moved to $\mu = 1$ and variance become $\sigma^2 = 4$
$$
Y = \mu + \sigma Z = 1 + 2Z.
$$

By linearity of expectation we have
$$
\mathbb{E}[1+2Z] = 1 + 2\mathbb{E}[Z] = 1
$$

Also by the properties of variance we have
$$
\operatorname{Var}(1+2Z) = \operatorname{Var}(2Z) = 4 \operatorname{Var}[Z] = 4.
$$

### Q20

Engineers sometimes work with the “error function”
$$
\operatorname{erf}(z) = \frac{2}{\sqrt{\pi}} \int_0^z e^{-x^2} dx
$$
instead of standard Normal CDF $\Phi$.

(a) Show that the following conversion between $\Phi$ and $\operatorname{erf}$ holds for all $z$:
$$
\Phi(z) = \frac{1}{2} + \frac{1}{2} \operatorname{erf}(\frac{z}{\sqrt{2}}).
$$

(b) Show that $\operatorname{erf}$ is an odd function, i.e., $\operatorname{erf}(-z) = −\operatorname{erf}(z)$.

Answer:

(a)

Because of the symmetry of standard Normal, we have
$$
\begin{aligned}
\Phi(z)
&= \int_{-\infty}^0 \frac{1}{\sqrt{2 \pi}} e^{-t^2/2} \,dt + \int_{0}^z \frac{1}{\sqrt{2 \pi}} e^{-t^2/2} \,dt \\
&= \frac{1}{2} + \int_{0}^z \frac{1}{\sqrt{2 \pi}} e^{-t^2/2} \,dt
\end{aligned}
$$

Let $u = \frac{t}{\sqrt{2}}$, we have $du = \frac{1}{\sqrt{2}} dt$, so
$$
\begin{aligned}
\Phi(z)
&= \frac{1}{2} + \int_{0}^z \frac{1}{\sqrt{2 \pi}} e^{-t^2/2} \,dt \\
&= \frac{1}{2} + \int_{0}^{\frac{z}{\sqrt{2}}} \frac{1}{\sqrt{2 \pi}} e^{-u^2} \sqrt{2}\,du \\
&= \frac{1}{2} + \int_{0}^{\frac{z}{\sqrt{2}}} \frac{1}{\sqrt{\pi}} e^{-u^2} \,du \\
&= \frac{1}{2} + \frac{1}{2}\operatorname{erf}(\frac{z}{\sqrt{2}})
\end{aligned}
$$

(b)

Because $e^{-x^2}$ is symmetric at $0$, we have $\operatorname{erf}(-z) = −\operatorname{erf}(z)$.

### Q21

(a) Find the points of inflection of the $\mathcal{N}(0,1)$ PDF $\varphi$, i.e., the points where the curve switches from convex (second derivative positive) to concave (second derivative negative) or vice versa.

(b) Use the result of (a) and a location-scale transformation to find the points of inflection of the $\mathcal{N}(\mu,\sigma^2)$ PDF.

Answer:

For standard normal we have
$$
\varphi(x) = \frac{1}{\sqrt{2 \pi}} e^{-x^2/2}
$$

Take the first derivative we have
$$
\varphi'(x) = -\frac{x}{\sqrt{2 \pi}} e^{-x^2/2} = - \frac{1}{\sqrt{2 \pi}} x e^{-x^2/2}
$$

Take the second derivative we have
$$
\begin{aligned}
\varphi''(x)
&= - \frac{1}{\sqrt{2 \pi}} (e^{-x^2/2} + e^{-x^2/2} \cdot (-x) \cdot x) \\
&= - \frac{1-x^2}{\sqrt{2 \pi}} e^{-x^2/2}
\end{aligned}
$$

So when $x = \pm 1$ we have $\varphi''(x) = 0$. Since $e^a \gt 0$ for $a \in R$, 

* When $x \lt -1$, we have $x^2 - 1 \gt 0$ and $\varphi''(x) > 0$.
* When $-1 \lt x \lt 1$, we have $x^2 - 1 \lt 0$ and $\varphi''(x) \lt 0$.
* When $x \gt -1$, we have $x^2 - 1 \gt 0$ and $\varphi''(x) > 0$.

Therefore, for standard normal we have the curve is concave from $-1 \lt x \lt 1$, and convex in other regions.

(b)

For $\mathcal{N}(\mu, \sigma^2)$, by the location-scale transformation, the inflection points move to $\mu \pm \sigma$.

### Q22

The distance between two points needs to be measured, in meters. The true distance between the points is $10$ meters, but due to measurement error we can’t measure the distance exactly. Instead, we will observe a value of $10+\epsilon$, where the error $\epsilon$ is distributed $\mathcal{N}(0, 0.04)$. Find the probability that the observed distance is within $0.4$ meters of the true distance ($10$ meters). Give both an exact answer in terms of $\Phi$ and an approximate numerical answer.

Answer:

Let $X$ be the observed value, we have
$$
X \sim \mathcal{N}(10, 0.04).
$$

By the symmetry of Normal, we have
$$
\begin{aligned}
P(10-0.4 \le X \le 10+0.4)
&= 1 - 2(1 - F_X(10 + 0.4)) \\
&= 2 F_X(10.4) - 1 \\
&= 2 \Phi(\frac{10.4 - 10}{0.2}) - 1 \\
&= 2 \Phi(2) -1 \\
&\approx 2 \cdot 0.95 - 1 \\
&= 0.9
\end{aligned}
$$

### Q23

Alice is trying to transmit to Bob the answer to a yes-no question, using a noisy channel. She encodes “yes” as $1$ and “no” as $0$, and sends the appropriate value. However, the channel adds noise; specifically, Bob receives what Alice sends plus a $\mathcal{N}(0,\sigma^2)$ noise term (the noise is independent of what Alice sends). If Bob receives a value greater than $1/2$ he interprets it as “yes”; otherwise, he interprets it as “no”.

(a) Find the probability that Bob understands Alice correctly.

(b) What happens to the result from (a) if $\sigma$ is very small? What about if $\sigma$ is very
large? Explain intuitively why the results in these extreme cases make sense.

Answer:

(a) 

When the noise is less than $0.5$, Bob understands Alice correctly. By symmetry, suppose the value Alice send is "no",
$$
P(X \le 0.5) = \Phi(\frac{0.5}{\sigma})
$$

(b)

If the $\sigma$ is very small, they can transmit very reliably, if the $\sigma$ is very large it's hard to tell what the original information.

### Q24

A woman is pregnant, with a due date of January 10, 2020. Of course, the actual date on which she will give birth is not necessarily the due date. On a timeline, define time 0 to be the instant when January 10, 2020 begins. Suppose that the time $T$ when the woman gives birth has a Normal distribution, centered at 0 and with standard deviation 8 days. What is the probability that she gives birth on her due date? (Your answer should be in terms of $\Phi$, and simplified.)

Answer:

Suppose the women gives birth at instant $X$
$$
\begin{aligned}
P(\text{give birth on due date})
&= P(X \le 1) - P(X \le 0) \\
&= \Phi(\frac{1}{8}) - \frac{1}{2}
\end{aligned}
$$

### Q25

We will show in the next chapter that if $X_1$ and $X_2$ are independent with $X_i \sim \mathcal{N}(\mu_i,\sigma_i^2)$, then $X_1 + X_2 \sim \mathcal{N}(\mu_1 + \mu_2, \sigma_1^2 + \sigma_2^2)$. Use this result to find $P(X \lt Y)$ for $X \sim \mathcal{N}(a,b)$, $Y \sim \mathcal{N}(c,d)$ with $X$ and $Y$ independent.

Hint: Write $P(X \lt Y) = P(X − Y \lt 0)$ and then standardize $X−Y$. Check that your answer makes sense in the special case where $X$ and $Y$ are i.i.d.

Answer:

$$
\begin{aligned}
P(X \lt Y)
&= P(X + (-Y) \lt 0)
\end{aligned}
$$

By symmetry, we have $-Y \sim \mathcal{N}(-c, d)$, therefore
$$
X - Y \sim \mathcal{N}(a-c, b+d)
$$

And
$$
P(X \lt Y) = P(X-Y \lt 0) = \Phi(\frac{c-a}{\sqrt{b+d}})
$$

Suppose $X$ and $Y$ are both standard Normal r.v., we have $a = c = 0$ and $b = d = 1$, so $P(X \lt Y) = \Phi(0) = 0.5$ which makes sense by symmetry.

### Q26

Walter and Carl both often need to travel from Location A to Location B. Walter walks, and his travel time is Normal with mean $w$ minutes and standard deviation $\sigma$ minutes (travel time can’t be negative without using a tachyon beam, but assume that w is so much larger than $\sigma$ that the chance of a negative travel time is negligible).

Carl drives his car, and his travel time is Normal with mean $c$ minutes and standard deviation $2 \sigma$ minutes (the standard deviation is larger for Carl due to variability in traffic conditions). Walter’s travel time is independent of Carl’s. On a certain day, Walter and Carl leave from Location A to Location B at the same time.

(a) Find the probability that Carl arrives first (in terms of $\Phi$ and the parameters). For
this you can use the important fact, proven in the next chapter, that if $X_1$ and $X_2$ are
independent with $X_i \sim \mathcal{N}(\mu_i, \sigma_i^2)$, then $X_1 + X_2 \sim \mathcal{N}(\mu_1 + \mu_2,\sigma_1^2 + \sigma_2^2)$.

(b) Give a fully simplified criterion (not in terms of $\Phi$), such that Carl has more than
a $50\%$ chance of arriving first if and only if the criterion is satisfied.

(c) Walter and Carl want to make it to a meeting at Location B that is scheduled to begin $w+10$ minutes after they depart from Location A. Give a fully simplified criterion (not in terms of $\Phi$) such that Carl is more likely than Walter to make it on time for the meeting if and only if the criterion is satisfied.

Answer:

(a)

Let $X_w$ and $X_c$ be the travel times of Walter and Carl respectively. Then,
$$
\begin{aligned}
P(X_c \lt X_w)
&= P(X_c - X_w \lt 0) \\
&= P(X_c + (-X_w) \lt 0) \\
\end{aligned}
$$

By the symmetry of Normal distribution, we have $-X_w \sim \mathcal{N}(-w, \sigma^2)$, so we have
$$
X_c - X_w \sim \mathcal{N}(c-w, 5\sigma^2)
$$

Therefore,
$$
\begin{aligned}
P(X_c \lt X_w)
&= P(X_c - X_w \lt 0) \\
&= \Phi(\frac{w-c}{\sqrt{5} \sigma}).
\end{aligned}
$$

(b)

We want
$$
P(X_c \lt X_w) > 0.5.
$$
From (a), we know that 
$$
P(X_c \lt X_w) = \Phi(\frac{w-c}{\sqrt{5} \sigma}).
$$

Since $\Phi$ is strictly increasing, and $\Phi(0) = 0.5$, it follows that
$$
P(X_c \lt X_w) > 0.5 \iff w\gt c
$$

(c)

$$
\begin{aligned}
P(X_c \lt w + 10) \gt P(X_w \lt w + 10)
&\iff \Phi(\frac{w + 10 - c}{2 \sigma}) \gt \Phi(\frac{10}{\sigma}) \\
&\iff \frac{w + 10 - c}{2 \sigma} \gt \frac{10}{\sigma} \\
&\iff w-c \gt 10 
\end{aligned}
$$

### Q27

Let $Z \sim \mathcal{N}(0,1)$. We know from the $68-95-99.7\%$ rule that there is a $68\%$ chance of $Z$
being in the interval $(−1,1)$. Give a visual explanation of whether or not there is an interval $(a,b)$ that is shorter than the interval $(−1,1)$, yet which has at least as large a chance as $(−1,1)$ of containing $Z$.

Answer:

It's impossible, the area of under the PDF curve is $1$, because $69$, $95$, and $99.7$ are all greater than $0.5$, the corresponding remaining areas are less than half. And by the bell shape of Normal distributions, the remaining areas must have a larger intervals.

### Q28

Let $Y \sim \mathcal{N}(\mu,\sigma^2)$. Use the fact that $P(|Y - \mu| < 1.96 \sigma) \approx 0.95$ to construct a random interval $(a(Y),b(Y))$ (that is, an interval whose endpoints are r.v.s), such that the
probability that $\mu$ is in the interval is approximately $0.95$. This interval is called a confidence interval for $\mu$; such intervals are often desired in statistics when estimating unknown parameters based on data.

Answer:

From fact that $P(|Y - \mu| < 1.96 \sigma) \approx 0.95$, we know that
$$
P(\mu - 1.96 \sigma \lt Y \lt \mu + 1.96 \sigma) \approx 0.95.
$$

That is
$$
P(Y-1.96\sigma \lt \mu \lt Y + 1.96 \sigma) \approx 0.95.
$$

So we can say
$$
a(Y) = Y-1.96\sigma, \qquad b(Y) = Y+1.96\sigma.
$$

### Q29

Let $Y = |X|$, with $X \sim \mathcal{N}(\mu,\sigma^2)$. This is a well-defined continuous r.v., even though
the absolute value function is not differentiable at $0$ (due to the sharp corner).

(a) Find the CDF of $Y$ in terms of $\Phi$. Be sure to specify the CDF everywhere.

(b) Find the PDF of $Y$.

(c) Is the PDF of $Y$ continuous at $0$? If not, is this a problem as far as using the PDF to find probabilities?

Answer:

(a)

For $x \ge 0$, we have
$$
\begin{aligned}
F_Y(x)
&=P(Y \le x) \\
&=P(X \le x) - P(X \le -x) \\
&=\Phi(\frac{x-\mu}{\sigma}) - \Phi(\frac{-x-\mu}{\sigma})
\end{aligned}
$$

For $x \lt 0$, we have $F_Y(x) = 0$.

(b)

For $x \gt 0$, we have
$$
\begin{aligned}
f_Y(x)
&= F_Y'(x) \\
&= \varphi(\frac{x - \mu}{\sigma})\frac{1}{\sigma} + \varphi(\frac{-x-\mu}{\sigma})\frac{1}{\sigma}.
\end{aligned}
$$

For $x \lt 0$, we have $f_Y(x) = 0$.

(c)

$$
\lim_{x \to 0^+} f_Y(x) = \frac{2}{\sigma} \varphi(\frac{-\mu}{\sigma})
$$

But $f_Y(0^-) = 0$, so $f_Y(x)$ is not continuous at $0$. The discontinuity in a single point causes no problem when using PDF to calculate the probability.

### Q30

Let $Z \sim \mathcal{N}(0,1)$ and let $S$ be a random sign independent of $Z$, i.e., $S$ is $1$ with
probability $1/2$ and $−1$ with probability $1/2$. Show that $SZ \sim \mathcal{N}(0,1)$.

Answer:

$$
\begin{aligned}
P(SZ \le x)
&= P(SZ \le x \mid Z = 1) P(Z = 1) + P(SZ \le x \mid Z = -1) P(Z = -1) \\
&= \Phi(x) \cdot 0.5 + (1-\Phi(-x)) \cdot 0.5 \\
&= \Phi(x) \cdot 0.5 + \Phi(x) \cdot 0.5 \\
&= \Phi(x)
\end{aligned}
$$

### Q31

Let $Z \sim \mathcal{N}(0,1)$. Find $\mathbb{E}[\Phi(Z)]$ without using LOTUS, where $\Phi$ is the CDF of $Z$.

Answer:

The definition of the expectation of continuous r.v. is
$$
\mathbb{E}[X] = \int_{-\infty}^{+\infty} x f(x) dx
$$
in which $f(x)$ is the PDF of the r.v..

Suppose $Y = g(X)$, by LOTUS we have
$$
\mathbb{E}[Y] = \int_{-\infty}^{+\infty} g(x) f(x) dx
$$
But here we are not going to use LOTUS.

By the universality of Uniform, if the CDF $F_X(x)$ is a continuous strictly increasing function on the support of the distribution, we have
$$
F_X(X) \sim \operatorname{Unif}(0, 1)
$$

Therefore, if the CDF if $Z$ is $\Phi$, we have
$$
\Phi(Z) \sim \operatorname{Unif}(0, 1)
$$

So $\mathbb{E}[\Phi(Z)] = 0.5$.

### Q32

Let $Z \sim \mathcal{N}(0,1)$ and $X = Z^2$. Then the distribution of $X$ is called Chi-Square with $1$ degree of freedom. This distribution appears in many statistical methods.

(a) Find a good numerical approximation to $P(1 \le X \le 4)$ using facts about the Normal distribution, without querying a calculator/computer/table about values of the Normal CDF.

(b) Let $\Phi$ and $\varphi$ be the CDF and PDF of $Z$, respectively. Show that for any $t \gt 0$, $I(Z \gt t) \le (Z/t)I(Z \gt t)$. Using this and LOTUS, derive Mills’ inequality, which is the following lower bound on $\Phi$:
$$
\Phi(t) \ge 1 − \varphi(t)/t.
$$