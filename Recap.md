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