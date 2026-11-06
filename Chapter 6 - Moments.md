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

Let $m$ be the median of $Y$, since $e^x$ is strictly increasing, we have
$$
\begin{aligned}
P(Y \le m)
&= P(e^X \le m) \\
&= P(X \le \log m) \\
&\ge \frac{1}{2}
\end{aligned}
$$

and
$$
\begin{aligned}
P(Y \ge m)
&= P(e^X \ge m) \\
&= P(X \ge \log m) \\
&\ge \frac{1}{2}
\end{aligned}
$$

From $P(X \le \log m) \ge \frac{1}{2}$ and $P(X \ge \log m) \ge \frac{1}{2}$ we have
$$
\log m = \mu
$$
And
$$
m = e^\mu
$$.

Student A's explanation make sense. Because the transformation $Y=e^X$ is strict increasing, the event $\{ X \le \mu \}$, which occupy the left half of the probability, becomes the event $\{ Y \le e^\mu \}$, they are the same event.

(b)

Let $m$ be the mode of $Y$ we have
$$
m = \operatorname*{arg \, max}_{y \gt 0} f_Y(y)
$$

To find $f_Y$ we first consider the CDF.
$$
\begin{aligned}
F_Y(y)
&=P(Y \le y) \\
&=P(e^X \le y) \\
&= P(X \le \log y) \\
&= \Phi(\frac{\log y - \mu}{\sigma})
\end{aligned}
$$

That derivative to $F_Y$ we have
$$
f_Y(y) = \frac{1}{\sigma y} \varphi(\frac{\log y - \mu}{\sigma}) 
$$

When $y=e^\mu$
$$
\varphi(\frac{\log y - \mu}{\sigma})
$$
has the maximum value. But due to the $1/y$, it does not necessary make the $f_Y$ maximum.

Instead of find the maximum of
$$
\operatorname*{arg \, max}_{y \gt 0} f_Y(y)
$$

We can find the maximum of
$$
\operatorname*{arg \, max}_{y \gt 0} \log f_Y(y)
$$
which is
$$
\begin{aligned}
\log (\frac{1}{\sigma y} \varphi(\frac{\log y - \mu}{\sigma}) )
&= \log \frac{1}{\sigma y} + \log \varphi(\frac{\log y - \mu}{\sigma}) \\
&= \log \frac{1}{\sigma y} + \log \frac{1}{\sqrt{2\pi}} - \frac{1}{2} (\frac{\log y - \mu}{\sigma})^2
\end{aligned}
$$

Take the derivative and solve for the stationary point.
$$
\begin{aligned}
\frac{d}{dy} \left( \log \frac{1}{\sigma y} + \log \frac{1}{\sqrt{2\pi}} - \frac{1}{2} (\frac{\log y - \mu}{\sigma})^2 \right)
&= -\frac{1}{y} -\frac{1}{2} 2 \frac{\log y - \mu}{\sigma} \frac{1}{\sigma} \frac{1}{y} \\
&= -\frac{1}{y} - \frac{\log y - \mu}{\sigma^2 y} \\
&= - \frac{\sigma^2  + \log y - \mu}{\sigma^2 y} \\
&= 0
\end{aligned}
$$

We have
$$
y = e^{\mu - \sigma^2}
$$

Since $\sigma^2 \gt 0$, this stationary point differs from $e^\mu$, so Student B's proposed mode is incorrect.

Unlike the median, mode is about the heights of the PDF the heights can change under the transformation.

(c)

Student C's statement is incorrect. The value that maximize the PDF of $X$ does not necessarily maximize the PDF of the transformed $X$.

### Q10

A distribution is called _symmetric unimodal_ if it is symmetric (about some point) and has a unique mode. For example, any Normal distribution is symmetric unimodal. Let
$X$ have a continuous symmetric unimodal distribution for which the mean exists. Show
that the mean, median, and mode of $X$ are all equal.

Answer:

Suppose the distribution is symmetric about the point $m$. $m$ must be the mode, or there will be two mode which conflict the definition. Because it is symmetric about $m$, the left and right side of $m$ must both occupy $1/2$ of the probability, $m$ must be the median.

Because the distribution is symmetric about the point $m$, we have
$$
f_X(x) = f_X(2m-x)
$$

Let $Y = 2m - X$, we have
$$
Y \overset{d}= X
$$

So we have
$$
\mathbb{E}[Y] = 2m - \mathbb{E}[X] = \mathbb{E}[X]
$$

Therefore, $\mathbb{E}[X] = m$.

### Q11

Let $X_1,\ldots,X_n$ be i.i.d. r.v.s with mean $\mu$, variance $\sigma^2$, and skewness $\gamma$.

(a) Standardize the $X_j$ by letting
$$
Z_j = \frac{X_j - \mu}{\sigma}.
$$

Let $\bar{X}_n$ and $\bar{Z}_n$ be the sample means of the $X_j$ and $Z_j$, respectively. Show that $Z_j$ has the same skewness as $X_j$, and $\bar{Z}_n$ has the same skewness as $\bar{X}_n$.

(b) Show that the skewness of the sample mean $\bar{X}_n$ is $\gamma / \sqrt{n}$. You can use the fact, shown in Chapter 7, that if $X$ and $Y$ are independent then $\mathbb{E}[XY] = \mathbb{E}[X] \mathbb{E}[Y]$.

Hint: By (a), we can assume $\mu= 0$ and $\sigma^2 = 1$ without loss of generality; if the $X_j$ are not standardized initially, then we can standardize them. If $(X_1 + X_2 + \ldots + X_n)^3$ is expanded out, there are 3 types of terms: terms such as $X_1^3$, terms such as $3X_1^2 X_2$, and terms such as $6 X_1 X_2 X_3$.

(c) What does the result of (b) say about the distribution of $\bar{X}_n$ when $n$ is large?

Answer:

(a)

The skewness of $X_j$ is

$$
\operatorname{Skew}(X_j) = \frac{\mathbb{E}[(X_j - u)^3]}{\sigma^3}
$$

Let $\mu_Z$ be the mean of $Z_j$, we have
$$
\mu_Z = \mathbb{E}[Z_j] = \frac{\mathbb{E}[X_j] - \mu}{\sigma} = 0
$$

Let $\sigma_Z^2$ be the variance of $Z_j$, we have
$$
\begin{aligned}
\sigma_Z^2
&= \frac{1}{\sigma^2} \operatorname{Var}(X_j - \mu) \\
&= \frac{1}{\sigma^2} \operatorname{Var}(X_j) \\
&= \frac{1}{\sigma^2} \sigma^2 \\
&= 1
\end{aligned}
$$ 

The skewness of $Z_j$ is
$$
\begin{aligned}
\operatorname{Skew}(Z_j)
&= \frac{\mathbb{E}[(Z_j - \mu_Z)^3]}{\sigma_Z^3} \\
&= \mathbb{E}[Z_j^3] \\
&= \mathbb{E}[(\frac{X_j - \mu}{\sigma})^3] \\
&= \frac{\mathbb{E}[(X_j - \mu)^3]}{\sigma^3} \\
&= \operatorname{Skew}(X_j)
\end{aligned}
$$

Therefore, the skewness of $Z_j$ and $X_j$ is the same. Next, we check the skewness of $\bar{Z}_n$ and $\bar{X}_n$.

$\bar{Z}_n$ is defined as
$$
\begin{aligned}
\bar{Z}_n
&= \frac{1}{n} \sum_{j=1}^n Z_j \\
&= \frac{1}{n} \sum_{j=1}^n (\frac{X_j - \mu}{\sigma}) \\
&= \frac{1}{n} \frac{\sum_{j=1}^n(X_j - \mu)}{\sigma} \\
&= \frac{1}{n} \frac{\sum_{j=1}^n X_j - n \mu}{\sigma} \\
&= \frac{1}{n} \frac{n \bar{X}_n - n \mu}{\sigma} \\
&= \frac{\bar{X}_n - \mu}{\sigma}
\end{aligned}
$$

As what we've showed above, that from
$$
Z_j = \frac{X_j - \mu}{\sigma}.
$$
we have 
$$
\operatorname{Skew}(Z_j) = \operatorname{Skew}(X_j)
$$

Similarly, we have
$$
\operatorname{Skew}(\bar{Z}_n) = \operatorname{Skew}(\bar{X}_n)
$$

(b)

From part (a) we know that the standardization doesn't change the skewness, so we can assume $\mu = 0$ and $\sigma = 1$, so we have
$$
\mathbb{E}[\bar{X}_n] = \mu = 0, \quad \text{and} \quad \operatorname{Var}(\bar{X}_n) = \sigma^2 / n = 1 / n
$$

By definition the skewness of the $\bar{X}_n$ is
$$
\begin{aligned}
\operatorname{Skew}(\bar{X}_n)
&= \frac{\mathbb{E}[(\bar{X}_n - \mathbb{E}[\bar{X}_n])^3]}{\operatorname{Var}(\bar{X}_n)^{3/2}} \\
&= n^{3/2} \mathbb{E}[\bar{X}_n^3] \\
&= n^{3/2} \mathbb{E}[\frac{1}{n^3}(X_1 + X_2 + \ldots + X_n)^3] \\
&= \frac{1}{n^{3/2}} \mathbb{E} [(X_1 + X_2 + \ldots + X_n)^3] \\
\end{aligned}
$$

After expand
$$
(X_1 + X_2 + \ldots + X_n)^3
$$

We have terms like $X_1^3$, $3X_1^2 X_2$, $6 X_1 X_2 X_3$. Note that if the term has random variable with power 1, the expectation of the term equals 0, this is because $\mathbb{E}[X_n] = 0$
Therefore
$$
\begin{aligned}
\mathbb{E} [(X_1 + X_2 + \ldots + X_n)^3]
&= \mathbb{E}[X_1^3] + \mathbb{E}[X_2^3] + \ldots + \mathbb{E}[X_n^3] \\
&= n \gamma
\end{aligned}
$$

Therefore
$$
\operatorname{Skew}(\bar{X}_n) = n^{-3/2} n \gamma = \frac{\gamma}{\sqrt{n}}
$$

(c)

The sampling distribution of $\bar{X}_n$ becomes less skewed as the sample size increases, in the sense that its skewness approaches zero.

### Q12

Let $c$ be the speed of light in a vacuum. Suppose that $c$ is unknown, and scientists wish to estimate it. But even more so than that, they wish to estimate $c^2$, for use in the famous equation $E = mc^2$.

Through careful experiments, they obtain i.i.d. measurements $X_1,\ldots,X_n \sim \mathcal{N}(c,\sigma^2)$. Using these data, there are various possible ways to estimate $c^2$. Two natural ways are:

(1) estimate $c$ using the average of the $X_j$’s and then square the estimated c, and 
(2) average the $X_j^2$’s. So let
$$
\bar{X}_n = \frac{1}{n} \sum_{j=1}^n X_j,
$$
and consider the two estimators
$$
T_1 = \bar{X}_n^2 \quad \text{and} \quad T_2 = \frac{1}{n} \sum_{j=1}^n X_j^2.
$$

Note that $T_1$ is the square of the first sample moment and $T_2$ is the second sample moment.

(a) Find $P(T_1 \lt T_2)$.

Hint: Start by comparing $(\frac{1}{n} \sum_{j=1}^n x_j)^2$ and $\frac{1}{n} \sum_{j=1}^n x_j^2$ when $x_1,\ldots,x_n$ are numbers, by considering a discrete r.v. whose possible values are $x_1,\ldots,x_n$.

(b) When an r.v. $T$ is used to estimate an unknown parameter $\theta$, the bias of the estimator $T$ is defined to be $\mathbb{E}(T) - \theta$. Find the bias of $T_1$ and the bias of $T_2$.

Hint: First find the distribution of $X_n$. In general, for finding $\mathbb{E}(Y^2)$ for an r.v. Y, it is often useful to write it as $\mathbb{E}[Y^2] = \operatorname{Var}(Y) + (\mathbb{E}[Y])^2$.

Answer:

(a)

Suppose the experiment realized to
$$
X_1 = x_1, X_2 = x_2,\ldots,X_n = x_n
$$

Let
$$
\bar{x}_n = \frac{1}{n} \sum_{j=1}^n x_j.
$$

Consider the sum of the squared deviations.
$$
\begin{aligned}
\sum_{j=1}^n(x_j - \bar{x}_n)^2
&= \sum_{j=1}^n x_j^2 - 2 \bar{x}_n \sum_{j=1}^n x_j + n \bar{x}_n^2 \\
&= \sum_{j=1}^n x_j^2 - 2 n \bar{x}_n^2 + n \bar{x}_n^2 \\
&= \sum_{j=1}^n x_j^2 - n \bar{x}_n^2 \\
&\ge 0
\end{aligned}
$$

Divide by $n$, we have
$$
\begin{aligned}
\frac{1}{n} \sum_{j=1}^n x_j^2 - \bar{x}_n^2
&= \frac{1}{n} \sum_{j=1}^n x_j^2 - (\frac{1}{n} \sum_{j=1}^n x_j)^2 \\
&\ge 0
\end{aligned}
$$

It means that no matter how the experiment realize we have $T_1 \le T_2$. Therefore,
$$
P(T_1 \le T_2) = P(T_1 \lt T_2) + P(T_1 = T_2) = 1
$$

Consider the realized experiment, $T_1 = T_2$ means
$$
\frac{1}{n} \sum_{j=1}^n(x_j - \bar{x}_n)^2 = 0
$$

It only happens when all the observed value have the same value, which is not the case from the description. So $P(T_1 = T_2) = 0$. Therefore,
$$
P(T_1 \lt T_2) = 1
$$

(b)

$$
\begin{aligned}
\mathbb{E}[T_1]
&= \mathbb{E}[(\frac{1}{n} \sum_{j=1}^n X_j)^2] \\
&= \frac{1}{n^2} \mathbb{E}[X_1^2 + \ldots + X_n^2 + 2X_1 X_2 + \ldots + 2 X_{n-1} X_n] \\
&= \frac{1}{n} \mathbb{E}[X_1^2] + \frac{2}{n^2} \binom{n}{2} c^2 \\
&= \frac{1}{n} (\operatorname{Var}(X_1) + (\mathbb{E}[X_1])^2) + \frac{n-1}{n} c^2 \\
&= \frac{1}{n} (\sigma^2 + c^2) + \frac{n-1}{n} c^2 \\
&= \frac{\sigma^2}{n} + c^2
\end{aligned}
$$

Therefore,
$$
\operatorname{Bias}(T_1) = \frac{\sigma^2}{n}
$$

$$
\begin{aligned}
\mathbb{E}[T_2]
&= \mathbb{E}[\frac{1}{n} \sum_{j=1}^n X_j^2] \\
&= \frac{1}{n} \sum_{j=1}^n \mathbb{E}[X_j^2] \\
&= \frac{1}{n} \sum_{j=1}^n (\sigma^2 + c^2) \\
&= \sigma^2 + c^2
\end{aligned}
$$

Therefore,
$$
\operatorname{Bias}(T_2) = \sigma^2
$$

## Moment Generating Functions

### Q13

A fair die is rolled twice, with outcomes $X$ for the first roll and $Y$ for the second roll. Find the moment generating function $M_{X+Y}(t)$ of $X + Y$ (your answer should be a function of $t$ and can contain unsimplified finite sums).

Answer:

$$
\begin{aligned}
M_{X+Y}(t)
&= M_X(t) M_Y(t) \\
&= (\frac{1}{6} (e^t + e^{2t} + e^{3t} + e^{4t} + e^{5t} + e^{6t}))^2 \\
&= \frac{1}{36} (e^t + e^{2t} + e^{3t} + e^{4t} + e^{5t} + e^{6t})^2
\end{aligned}
$$

### Q14

Let $U_1,U_2,\ldots,U_{60}$ be i.i.d. $\operatorname{Unif}(0,1)$ and $X= U_1 + U_2 + \ldots + U_{60}$. Find the MGF of $X$.

Answer:
$$
\begin{aligned}
M_X(t)
&=(M_{U_1}(t))^{60} \\
&= (\mathbb{E}[e^{t U_1}])^{60} \\
&= \left( \int_0^1 e^{tx} \, dx \right)^{60} \\
&= \left( \frac{1}{t}(e^t - 1) \right)^{60} \\
\end{aligned}
$$

Note that
$$
\lim_{t \to 0} \frac{e^t - 1}{t} = 1
$$
Therefore 
$$
M_X(0) = 1
$$

### Q15

Let $W = X^2 +Y^2$, with $X,Y$ i.i.d. $\mathcal{N}(0,1)$. The MGF of $X^2$ turns out to be $(1−2t)^{−1/2}$ for $t<1/2$ (you can assume this).

(a) Find the MGF of $W$.

(b) What famous distribution that we have studied so far does $W$ follow (be sure to
state the parameters in addition to the name)? In fact, the distribution of $W$ is also a special case of two more famous distributions that we will study in later chapters!

Answer:

(a)

$$
\begin{aligned}
M_W(t)
&= \mathbb{E}[e^{t (X^2+Y^2)}] \\
&= \mathbb{E}[e^{t X^2} e^{t Y^2}] \\
&= \mathbb{E}[e^{t X^2}] \mathbb{E}[e^{t Y^2}] \\
&= (\mathbb{E}[e^{t X^2}])^2 \\
&= \frac{1}{1-2t}
\end{aligned}
$$
for $t \lt 1/2$. And we have $M_W(0) = 1$.

(b)

Note that if $Y \sim \operatorname{Expo}(\lambda)$, we have
$$
M_Y(t) = \frac{\lambda}{\lambda - t} \quad \text{for $t \lt \lambda$.}
$$

Therefore,
$$
W \sim \operatorname{Expo}(\frac{1}{2})
$$