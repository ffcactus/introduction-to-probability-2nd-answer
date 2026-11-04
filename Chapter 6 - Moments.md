# Moments

## Means, Medians, Modes, and Moments

### Q1

Let $U \sim \operatorname{Unif}(a,b)$. Find the median and mode of $U$.

Answer:

By definition, we say $c$ is the median of the r.v. $X$ if $P(X \le c) \ge 1/2$ and $P(X \ge c) \ge 1/2$

Let $c$ be the median of $U$, we have:
$$
P(U \le c) = \frac{c-a}{b-a} \ge \frac{1}{2}
$$

So we have
$$
2(c - a) \ge b - a \\
2c - 2a \ge b - a \\
2c \ge b+a \\
c \ge \frac{a+b}{2}
$$

And we also have
$$
P(U \ge c) = 1 - (U \le c) = 1 - \frac{c-a}{b-a} \ge \frac{1}{2}
$$

So we have
$$
\frac{b-a -c + a}{b-a} \ge \frac{1}{2} \\

2b - 2c \ge b - a \\

b + a \ge 2c \\

c \le \frac{a+b}{2}
$$

Because
$$
c \ge \frac{a+b}{2}, \quad \text{and} \quad c \le \frac{a+b}{2}
$$

We have the median of $U \sim \operatorname{Unif}(a, b)$ is
$$
\frac{a+b}{2}
$$

By the definition, for a continuous r.v. with PDF $f$, we say $c$ is the mode of if it maximizes the PDF: $f(c) \ge f(x)$ for all $x$. Since the PDF is constant on its support, every point in the support is a mode of the Uniform distribution.

### Q2

Let $X \sim \operatorname{Expo}(\lambda)$. Find the median and mode of X.

Answer:

Let $c$ be the median of $X \sim \operatorname{Expo}(\lambda)$, we have
$$
P(X \le c) \ge \frac{1}{2} \quad \text{and} \quad P(X \ge c) \ge \frac{1}{2}
$$

That is
$$
1- e^{-\lambda c} \ge \frac{1}{2} \quad \text{and} \quad e^{-\lambda c} \ge \frac{1}{2}
$$

That is
$$
-\lambda c \le \log \frac{1}{2} \quad \text{and} \quad -\lambda c \ge \log \frac{1}{2} 
$$

Therefore, we have
$$
c = - \frac{1}{\lambda} \log \frac{1}{2}
$$

For the mode of $X$, consider the PDF if it is
$$
\lambda e^{-\lambda x},
$$
and it decreases as $x$ increases. Therefore the mode is $0$.

### Q3

Let $X$ have the Pareto distribution with parameter $a \gt 0$; this means that X has PDF
$$
f(x) = \frac{a}{x^{a+1}}
$$
for $x \ge 1$ (and 0 otherwise). Find the median and mode of $X$.

Answer:

Let $c$ be the median of $X$. To find $c$, we first get the CDF of $X$.
$$
\begin{aligned}
F_X(t)
&= \int_1^t \frac{a}{x^{a+1}} dx
&= - x^{-a} \Big|_1^t \\
&= 1-t^{-a} 
\end{aligned}
$$

So we have
$$
1 - c^{-a} \ge \frac{1}{2} \quad \text{and} \quad c^{-a} \ge \frac{1}{2}
$$

So
$$
c = \sqrt[a]{2}
$$

Because the PDF of $X$ decreases as $x$ increases, the mode is $1$.

### Q4

Let $X \sim \operatorname{Bin}(n,p)$.

(a) For $n = 5, p = 1/3$, find all medians and all modes of $X$. How do they compare to the mean?

(b) For $n = 6, p = 1/3$, find all medians and all modes of $X$. How do they compare to the mean?

Answer:

(a)

The PMF of $X$ is
$$
f_X(k) = \binom{5}{k} \left( \frac{1}{3} \right)^k \left( \frac{2}{3} \right)^{5-k}
$$

and we have
$$
\begin{aligned}
&f_X(0) \approx 0.1317 \\
&f_X(1) \approx 0.3292 \\
&f_X(2) \approx 0.3292 \\
&f_X(3) \approx 0.1646 \\
\end{aligned}
$$

Therefore, the median of $X$ is 2, because
$$
P(X \le 2) \approx 0.1317 + 0.3292 + 0.3292 = 0.7901 \ge 0.5 \\
P(X \ge 2) \approx 1 -  0.1317 - 0.3292 = 0.5391 \ge 0.5
$$

Since $X$ takes only integers, for $c \lt 2$, we have
$$
P(X \le c) \le P(X \lt 2) = f_X(0) + f_X(1) \lt 0.5
$$
and for $c > 2$, we have
$$
P(X \ge c) \le P(X \gt 2) = 1 - f_X(0) - f_X(1) - f_X(2) \lt 0.5
$$
So $c=2$ is the unique median.

And obviously, both the 1 and 2 are the mode of $X$. We know that
$$
\mathbb{E}[X] = np = \frac{5}{3} \approx 1.6667
$$

It shows that the median is higher than the mean. 

(b)

We have
$$
\begin{aligned}
&f_X(0) \approx 0.08779 \\
&f_X(1) \approx 0.26337 \\
&f_X(2) \approx 0.32922 \\
&f_X(3) \approx 0.21948 \\
&f_X(4) \approx 0.08230 \\
\end{aligned}
$$

For the same reason, we have median equals to 2, mode equals to 2, and mean equals to 2.

### Q5

Let $X$ be Discrete Uniform on $1,2,\ldots,n$. Find all medians and all modes of X (your answer can depend on whether $n$ is even or odd).

Answer:

Since all outcomes have the same possibility, all of them are the mode of $X$.

Let $c$ be the median of $X$. This can be separated into two cases.

Case 1, $n$ is even. 

We can show that both $\frac{n}{2}$ and $\frac{n}{2} + 1$ are the median.

For $\frac{n}{2}$, since each value has the probability $\frac{1}{n}$, we have
$$
P(X \le \frac{n}{2}) = \frac{1}{n} \cdot \frac{n}{2} = \frac{1}{2}
$$

and
$$
P(X \ge \frac{n}{2}) = \frac{1}{n} (\frac{n}{2} + 1) = \frac{1}{2} + \frac{1}{n} \gt \frac{1}{2}
$$

Similarly, for $\frac{n}{2} + 1$ we have
$$
P(X \le \frac{n}{2} + 1) = \frac{1}{n} (\frac{n}{2} + 1) = \frac{1}{2} + \frac{1}{n} \gt \frac{1}{2}
$$

and
$$
P(X \ge \frac{n}{2} + 1) = \frac{1}{n} \cdot \frac{n}{2} = \frac{1}{2}
$$

Therefore, when $n$ is even, the value in the interval $[\frac{n}{2}, \frac{n}{2} +1]$ are the median.

And the median can't exceed this range. Suppose $m$ is a median and $m \lt \frac{n}{2}$, we have
$$
P(X \le m) \le P(X \le \frac{n}{2} - 1) = \frac{1}{n} (\frac{n}{2} - 1) = \frac{1}{2} - \frac{1}{n} \lt \frac{1}{2}
$$

And if $m \gt \frac{n}{2} + 1$, we have
$$
P(X \ge m) \le P(X \ge \frac{n}{2} + 2) = \frac{1}{n}(\frac{n}{2} - 1) = \frac{1}{2} - \frac{1}{n} \lt \frac{1}{2}
$$

Case 2, $n$ is odd.

In this case only $\frac{n+1}{2}$ is the median.

For $\frac{n+1}{2}$, we have
$$
P(X \le \frac{n+1}{2}) = \frac{1}{n} \frac{n+1}{2} = \frac{1}{2} + \frac{1}{2n} \gt \frac{1}{2} \\
$$

and
$$
P(X \ge \frac{n+1}{2}) = \frac{1}{n} \frac{n+1}{2} = \frac{1}{2} + \frac{1}{2n} \gt \frac{1}{2} \\
$$

It can't be any other value. Suppose $m$ is a median and $m \lt \frac{n+1}{2}$, we have
$$
P(X \le m) \le P(X \le \frac{n+1}{2} - 1) = \frac{1}{n} (\frac{n+1}{2} - 1) = \frac{1}{2} - \frac{1}{2n} \lt \frac{1}{2}
$$

And if $m \gt \frac{n+1}{2}$ we have
$$
P(X \ge m) \le P(X \ge \frac{n+1}{2} + 1) = \frac{1}{n} (\frac{n+1}{2} - 1) = \frac{1}{2} - \frac{1}{2n} \lt \frac{1}{2}
$$

### Q6

Suppose that we have data giving the amount of rainfall in a city each day in a certain year. We want useful, informative summaries of how rainy the city was that year. On the majority of days in that year, it did not rain at all in the city. 

Discuss and compare the following six summaries: the mean, median, and mode of the rainfall on a randomly chosen day from that year, and the mean, median, and mode of the rainfall on a randomly chosen rainy day from that year (where by “rainy day” we mean that it did rain that day in the city).

Answer:

For the mean, obviously, the mean from randomly chosen day will be lower than the mean from randomly chosen rainy day.

For the median, in the randomly chosen day from the year, let $X$ be the sampling value. Because the majority of days in that year did not rain at all, we have
$$
P(X = 0) \gt \frac{1}{2}
$$

Therefore, 0 is the median, since we have
$$
P(X \ge 0) \ge \frac{1}{2}, \quad \text{and} \quad P(X \le 0) \ge \frac{1}{2}
$$

For any other value $m \gt 0$, we have
$$
P(X \ge m) \lt \frac{1}{2}
$$

So no other value than $0$ can be the median.

In the randomly chosen rainy day, we have
$$
P(X = 0) = 0
$$
So, 0 can't be the median.

For the mode, in the randomly chosen day from the year, we have
$$
P(X = 0) \gt \frac{1}{2}
$$
Any other values other than 0 have the probability less than $\frac{1}{2}$, so the mode is $0$.

In the randomly chosen rainy day, because $P(X=0) = 0$, the mode can't be 0.

### Q7

Let $a$ and $b$ be positive constants. The _Beta distribution_ with parameters $a$ and $b$, which we introduce in detail in Chapter 8, has PDF proportional to
$$
x^{a−1}(1−x)^{b−1}
$$
for $0 \lt x \lt 1$ (and the PDF is 0 outside this range). Show that for $a \gt 1$, $b \gt 1$, the mode of the distribution is
$$
\frac{a−1}{a+b−2}
$$.

Hint: Take the log of the PDF first (note that this does not affect where the maximum
is achieved).

Answer:

We need to
$$
\operatorname*{arg \, max}_{0 \lt x \lt 1} f_X(x)
$$
where
$$
f_X(x) = x^{a−1}(1−x)^{b−1}.
$$

Since
$$
\log f_X(x_1) \gt \log f_X(x_2) \iff f_X(x_1) \gt f_X(x_2)
$$

It is equivalent to solve
$$
\operatorname*{arg \, max}_{0 \lt x \lt 1} \log f_X(x).
$$

We have
$$
\begin{aligned}
\log f_X(x)
&= \log x^{a-1} + \log (1-x)^{b-1}.
\end{aligned}
$$

Since the maximum occurs at an interior point, its first derivative must be zero. We therefore solve for the stationary point.
$$
\frac{a-1}{x^{a-1}} x^{a-2} + \frac{b-1}{(1-x)^{b-1}} (1-x)^{b-2} (-1) = 0
$$

This simplified as
$$
\frac{a-1}{x} - \frac{b-1}{1-x} = 0,
$$

$$
\frac{a-1}{x} = \frac{b-1}{1-x}
$$

we have
$$
x = \frac{a-1}{a+b-2}
$$

To verify that this stationary point is a maximum, we examine the second derivative.
$$
\frac{d}{dx} (\frac{a-1}{x} - \frac{b-1}{1-x}) = - \frac{a-1}{x^2} - \frac{b-1}{(1-x)^2}
$$

Because $a \gt 1$, $b \gt 1$ and $0 \lt x \lt 1$, we have the second derivate less than 0. Therefore, 
$$
x = \frac{a-1}{a+b-2} 
$$
is the mode.

### Q8

Find the median of the Beta distribution with parameters $a = 3$ and $b = 1$ (see the
previous problem for information about the Beta distribution).

Answer:

Q7 shows that
$$
f_X(x) = C x^2, \quad 0 \lt x \lt 1.
$$

Solve $C$ from
$$
\int_0^1 C x^2 = 1
$$
we have $C=3$.

Suppose $m$ is the median, we have
$$
\begin{aligned}
3\int_0^m x^2 \, dx
&= x^3 \Big|_0^m \\
&= m^3 \\
&\ge \frac{1}{2}
\end{aligned}
$$

and
$$
\begin{aligned}
3 \int_m^1 x^2 \, dx
&= x^3 \Big|_m^1 \\
&= 1 - m^3 \\
&\ge \frac{1}{2}
\end{aligned}
$$

We have
$$
\frac{1}{2} \le m^3 \le \frac{1}{2}
$$

Therefore the median is
$$
\sqrt[3]{\frac{1}{2}}.
$$

### Q9

Let $Y$ be Log-Normal with parameters $\mu$ and $\sigma^2$. So $Y= e^X$ with $X \sim \mathcal{N}(\mu,\sigma^2)$. Three students are discussing the median and the mode of $Y$. Evaluate and explain whether or not each of the following arguments is correct.

(a) Student A: The median of $Y$ is $e^\mu$ because the median of $X$ is $\mu$ and the exponential function is continuous and strictly increasing, so the event $Y \lt e^\mu$ is the same as the event $X \le \mu$.

(b) Student B: The mode of $Y$ is $e^\mu$ because the mode of $X$ is $\mu$, which corresponds to $e^\mu$ for $Y$ since $Y= e^X$.

(c) Student C: The mode of $Y$ is $\mu$ because the mode of $X$ is $\mu$ and the exponential function is continuous and strictly increasing, so maximizing the PDF of $X$ is equivalent to maximizing the PDF of $Y= e^X$
.

Answer:

(a)

Let $m$ be the median of $Y$, we have
$$
\begin{aligned}
P(Y \le m)
&= P(e^X \le m) \\
&= P(X \le \log m) \\
&\le \frac{1}{2}
\end{aligned}
$$

and
$$
\begin{aligned}
P(Y \ge m)
&= P(e^X \ge m) \\
&= P(X \ge \log m) \\
&\le \frac{1}{2}
\end{aligned}
$$

So we have
$$
\log m = \mu
$$
And $m = e^\mu$.

But I have no idea if the reasoning of student A is correct.

(b)

The reasoning is incorrect. The the maximum of the input not always end up with the maximum of the output.

(c)

The reasoning is correct.