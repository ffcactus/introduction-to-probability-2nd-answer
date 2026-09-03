# Expectation

## Expectations and variances

### Q1

Bobo, the amoeba from Chapter 2, currently lives alone in a pond. After one minute Bobo will either die, split into two amoebas, or stay the same, with equal probability.
Find the expectation and variance for the number of amoebas in the pond after one
minute.

Answer:

Let $X$ be the number of amoebas in the pond after one minute, we have
$$
P(X=0) = \frac{1}{3} \\
P(X=1) = \frac{1}{3} \\
P(X=2) = \frac{1}{3} \\
$$

By the definition of expectation we have:
$$
E(X) = 0 \cdot \frac{1}{3} + 1 \cdot \frac{1}{3} + 2 \cdot \frac{1}{3} = 1
$$

For variance, we have:
$$
\begin{aligned}
\operatorname{Var}(X) 
&= \mathbb{E}[X^2] - (\mathbb{E}[X])^2 \\
\end{aligned}
$$

By LOTUS, we have
$$
\mathbb{E}[X^2] = \sum_x x^2 P(X=x) = 0 \cdot \frac{1}{3} + 1 \cdot \frac{1}{3} + 4 \cdot \frac{1}{3} = \frac{5}{3}
$$

Therefore
$$
\operatorname{Var}(X) = \frac{5}{3} - 1^2 = \frac{2}{3}
$$

### Q2

In the Gregorian calendar, each year has either 365 days (a normal year) or 366 days
(a leap year). A year is randomly chosen, with probability 3/4 of being a normal year
and 1/4 of being a leap year. Find the mean and variance of the number of days in the
chosen year.

Answer:

Let $X$ be the number of days in the chosen year.
$$
\mathbb{E}[X] = 365 \cdot \frac{3}{4} + 366 \cdot \frac{1}{4} = \frac{1461}{4}
$$

And
$$
\begin{aligned}
\operatorname{Var}(X) 
&= \mathbb{E}[X^2] - (\mathbb{E}[X])^2 \\
&= 365^2 \cdot \frac{3}{4} + 366^2 \frac{1}{4} - (\frac{1461}{4})^2 \\
&= \frac{3}{16}
\end{aligned}
$$

### Q3

(a) A fair die is rolled. Find the expected value of the roll.

(b) Four fair dice are rolled. Find the expected total of the rolls.

Answer:

(a)

Let $X$ be the value of the roll.

$$
\mathbb{E}[X] = \sum_x x P(X=x) = \sum_{x=1}^6 x \cdot \frac{1}{6} = 3.5 
$$

(b)

Let $X_i$ be the value of the $i$-th roll, and $X=X_1 + X_2 + X_3 + X_4$ be the total of the rolls. By the linearity of expectation, we have
$$
\mathbb{E}[X] = \mathbb{E}[X_1] + \mathbb{E}[X_2] + \mathbb{E}[X_3] + \mathbb{E}[X_4] = 14
$$

### Q4

A fair die is rolled some number of times. You can choose whether to stop after 1, 2, or 3 rolls, and your decision can be based on the values that have appeared so far. You receive the value shown on the last roll of the die, in dollars. What is your optimal strategy (to maximize your expected winnings)? Find the expected winnings for this strategy.

Hint: Start by considering a simpler version of this problem, where there are at most 2
rolls. For what values of the first roll should you continue for a second roll?

Answer:

Suppose there are at most 2 rolls, since the expected value of a single roll is 3.5, if the first roll is less than 4, we should roll again.

Let $X$ be the final amount received, and let $X_1$ and $X_2$ be the values of the first and second rolls, respectively.
$$
P(X=k) = P(X_2=k \mid X_1 \lt 4) P(X_1 \lt 4) + P(X_1=k \mid X_1 \ge 4) P(X_1 \ge 4) 
$$

$$
P(X=1) = \frac{1}{6} \cdot \frac{3}{6} + 0 \cdot \frac{3}{6} = \frac{3}{36}
$$

$$
P(X=2) = \frac{1}{6} \cdot \frac{3}{6} + 0 \cdot \frac{3}{6} = \frac{3}{36}
$$

$$
P(X=3) = \frac{1}{6} \cdot \frac{3}{6} + 0 \cdot \frac{3}{6} = \frac{3}{36}
$$

$$
P(X=4) = \frac{1}{6} \cdot \frac{3}{6} + \frac{1}{3} \cdot \frac{3}{6} = \frac{9}{36}
$$

$$
P(X=5) = \frac{1}{6} \cdot \frac{3}{6} + \frac{1}{3} \cdot \frac{3}{6} = \frac{9}{36}
$$

$$
P(X=6) = \frac{1}{6} \cdot \frac{3}{6} + \frac{1}{3} \cdot \frac{3}{6} = \frac{9}{36}
$$

Therefore
$$
\begin{aligned}
\mathbb{E}[X] &= 1 \cdot \frac{3}{36} + 2 \cdot \frac{3}{36} + 3 \cdot \frac{3}{36} + 4 \cdot \frac{9}{36} + 5 \cdot \frac{9}{36} + 6 \cdot \frac{9}{36} \\
&=\frac{17}{4}
\end{aligned}
$$

Now suppose there are at most $3$ rolls. As we showed previously, with at most two rolls remaining, the optimal expected winnings are $17/4$. Therefore, if the first roll is less than $5$, we should roll again. So if your first roll is below 5, you should try to roll again.

Let $X$ be the final amount received, let $X_1$ be the value of the first roll, and let $B$ be the final amount obtained by playing the remaining two-roll game optimally..

$$
P(X=k) = P(B=k \mid X_1 \lt 5) P(X_1 \lt 5) + P(X_1=k \mid X_1 \ge 5) P(X_1 \ge 5) 
$$

Based on our previous calculation, we have
$$
P(X=1) = \frac{3}{36} \cdot \frac{4}{6} + 0 \cdot \frac{2}{6} = \frac{1}{18}
$$
$$
P(X=2) = \frac{3}{36} \cdot \frac{4}{6} + 0 \cdot \frac{2}{6} = \frac{1}{18}
$$
$$
P(X=3) = \frac{3}{36} \cdot \frac{4}{6} + 0 \cdot \frac{2}{6} = \frac{1}{18}
$$
$$
P(X=4) = \frac{9}{36} \cdot \frac{4}{6} + 0 \cdot \frac{2}{6} = \frac{1}{6}
$$
$$
P(X=5) = \frac{9}{36} \cdot \frac{4}{6} + \frac{1}{2} \cdot \frac{2}{6} = \frac{1}{3}
$$
$$
P(X=6) = \frac{9}{36} \cdot \frac{4}{6} + \frac{1}{2} \cdot \frac{2}{6} = \frac{1}{3}
$$

Therefore, with at most three rolls and using the optimal strategy, the expected winnings are
$$
\begin{aligned}
\mathbb{E}[X]
&= 1 \cdot \frac{1}{18}+ 2 \cdot \frac{1}{18} + 3 \cdot \frac{1}{18} + 4 \cdot \frac{1}{6} + 5 \cdot \frac{1}{3} + 6 \cdot \frac{1}{3} \\
&= \frac{14}{3}
\end{aligned}
$$

### Q5

Find the mean and variance of a Discrete Uniform r.v. on $1,2,\ldots,n$.

Hint: See the math appendix for some useful facts about sums.

Answer:
By the definition of expectation we have:
$$
\mathbb{E}[X] = \sum_{x=1}^n x P(X=x) = \frac {1}{n} \sum_{x=1}^n x = \frac{1}{n} \frac{(1+n)n}{2} = \frac{1+n}{2}
$$

### Q6

Two teams are going to play a best-of-7 match (the match will end as soon as either
team has won 4 games). Each game ends in a win for one team and a loss for the other
team. Assume that each team is equally likely to win each game, and that the games
played are independent. Find the mean and variance of the number of games played.

Answer:

By the definition of expectation we have:
$$
\mathbb{E}[X] = 4 P(X=4) + 5 P(X=5) + 6 P(X=6) +7 P(X=7)
$$

Let $p$ be the probability that team A wins an individual game., and $q = 1-p$. Suppose the game ends team A wins after $X$ matches. Team A must win the last match, and in the previous $X-1$ matches A must win 3 times. The same pattern can happen at team B. Suppose team A has $p = 1/2$ probability to win and $q = 1 - p$ probability to lose. We have
$$
P(X=k) = 2 p \binom{k-1}{3} p^3 q^{k-1-3} = \binom{k-1}{3} (\frac{1}{2})^{k-1}\qquad \text{for $k=4,5,6,7$.}
$$

$$
P(X=4) = \frac{1}{8}
$$

$$
P(X=5) = \frac{1}{4}
$$

$$
P(X=6) = \frac{5}{16}
$$

$$
P(X=7) = \frac{5}{16}
$$

Therefore
$$
\begin{aligned}
\mathbb{E}[X] = 4 \frac{1}{8} + 5 \frac{1}{4} + 6 \frac{5}{16} +7 \frac{5}{16} = \lceil \frac{93}{16} \rceil = 6
\end{aligned}
$$

For variance we have
$$
\operatorname{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2 = 16 \frac{1}{8} + 25 \frac{1}{4} + 36 \frac{5}{16} + 49 \frac{5}{16} - (\frac{93}{16})^2 \approx 1.03
$$
