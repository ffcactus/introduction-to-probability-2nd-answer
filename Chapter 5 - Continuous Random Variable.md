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




