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

For variance we have:
$$
\begin{aligned}
\operatorname{Var}(X)
&= \mathbb{E}[X^2] - (\mathbb{E}[X])^2 \\
&= \frac{1}{n} \sum_{x=1}^n x^2 - (\frac{1+n}{2})^2 \\
&= \frac{1}{n} \frac{n (n+1)(2n+1)}{6} - (\frac{1+n}{2})^2 \\
&= \frac{n^2 - 1}{12}
\end{aligned}
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

### Q7

A certain small town, whose population consists of $100$ families, has $30$ families with $1$ child, $50$ families with $2$ children, and $20$ families with $3$ children. The birth rank of one
of these children is $1$ if the child is the firstborn, $2$ if the child is the secondborn, and $3$ if the child is the thirdborn.

(a) A random family is chosen (with equal probabilities), and then a random child within that family is chosen (with equal probabilities). Find the PMF, mean, and variance of the child’s birth rank.

(b) A random child is chosen in the town (with equal probabilities). Find the PMF,
mean, and variance of the child’s birth rank.

Answer:

(A)

Let $C$ be the number of children in the chosen family, and let $X$ be the birth rank of the chosen child.

Conditioning on the number of children in the chosen family, we have
$$
p_X = P(X=x \mid C=1)P(C=1) + P(X=x \mid C=2)P(C=2) + P(X=x \mid C=3)P(C=3)
$$
So we have
$$
P(X=1) = 1 \frac{30}{100} + \frac{1}{2} \frac{50}{100} + \frac{1}{3} \frac{20}{100} = \frac{37}{60}
$$
$$
P(X=2) = 0 \frac{30}{100} + \frac{1}{2} \frac{50}{100} + \frac{1}{3} \frac{20}{100} = \frac{19}{60}
$$
$$
P(X=3) = 0 \frac{30}{100} + 0 \frac{50}{100} + \frac{1}{3} \frac{20}{100} = \frac{4}{60}
$$
The support is $1,2,3$. This is a valid PMF as the sum is $1$.

By the definition of expectation we have:
$$
\begin{aligned}
\mathbb{E}[X]
&= \sum_x x P(X=x) \\
&= 1 \frac{37}{60} + 2 \frac{19}{60} + 3 \frac{4}{60} \\
&= 1.45
\end{aligned}
$$

And the variance is
$$
\operatorname{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2
$$

By LOTUS we have
$$
\mathbb{E}[X^2] = \sum_x x^2 P(X=x) = 1 \frac{37}{60} + 4 \frac{19}{60} + 9 \frac{4}{60} = \frac{149}{60}
$$

Therefore
$$
\operatorname{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2 = \frac{149}{60} - 1.45^2 \approx 0.38
$$

(b)

There are $100$, $70$, $20$ children with birthrank 1, 2 and 3, respectively. So we have
$$
P(X=1) = \frac{100}{190}, \quad P(X=2) = \frac{70}{190}, \quad P(X=3) = \frac{20}{190}.
$$

Therefore
$$
\mathbb{E}[X] = 1 \frac{100}{190} + 2 \frac{70}{190} + 3 \frac{20}{190} \approx 1.58
$$

$$
\operatorname{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2 \approx 0.45
$$

### Q8

A certain country has four regions: North, East, South, and West. The populations of these regions are $3$ million, $4$ million, $5$ million, and $8$ million, respectively. There are $4$ cities in the North, $3$ in the East, $2$ in the South, and there is only $1$ city in the West. Each person in the country lives in exactly one of these cities.

(a) What is the average size of a city in the country? (This is the arithmetic mean of the populations of the cities, and is also the expected value of the population of a city chosen uniformly at random.)

Hint: Give the cities names (labels).

(b) Show that without further information it is impossible to find the variance of the population of a city chosen uniformly at random. That is, the variance depends on how the people within each region are allocated between the cities in that region.

(c) A region of the country is chosen uniformly at random, and then a city within that region is chosen uniformly at random. What is the expected population size of this randomly chosen city?

Hint: First find the selection probability for each city.

(d) Explain intuitively why the answer to (c) is larger than the answer to (a).

Answer:

(a)

The arithmetic mean of the size of a city is
$$
\frac{3+4+5+8}{4+3+2+1} = 2 \text{(million)}
$$

(b)

The definition of variance is
$$
\operatorname{Var}(X) = \mathbb{E}[(X - \mathbb{E}[X])^2]
$$

We can find the $\mathbb{E}[X]$ as in (a), however, without knowing the actual population of each city, we don't know the squared deviation
$$
(X - \mathbb{E}[X])^2
$$
or equivalently we don't know
$$
\mathbb{E}[X^2]
$$
so we don't know the variance.

(c)

Suppose $n_1,n_2,n_3,n_4,e_1,e_2,e_3,s_1,s_2,w_1$ are the size of the cities in the north, east, south and west, respectively.

The probability for a city to be chosen is $\frac{1}{4} \frac{1}{4}$, $\frac{1}{4} \frac{1}{3}$, $\frac{1}{4} \frac{1}{2}$ and $\frac{1}{4} \frac{1}{1}$, respectively.

Let $X$ be the size of the chosen city, we have
$$
\begin{aligned}
\mathbb{E}[X]
&= \frac{1}{16} (n_1 + n_2 + n_3 + n_4) + \frac{1}{12} (e_1 + e_2 + e_3) + \frac{1}{8} (s_1 + s_2) + \frac{1}{4} w_1 \\
&= \frac{1}{16} 3 + \frac{1}{12} 4 + \frac{1}{8} 5 + \frac{1}{4} 8 \\
&\approx 3.16
\end{aligned}
$$

(d)

From North to East to South to West, the average city population increases. In part (a), every city is chosen with equal probability, so every city has the same weight. In part (c), every region is chosen with equal probability first. Therefore, cities in regions with fewer cities receive greater individual weight. Since these regions also have larger average city populations, the expected population in part (c) is larger.

### Q9

Consider the following simplified scenario based on _Who Wants to Be a Millionaire_?,
a game show in which the contestant answers multiple-choice questions that have 4
choices per question. The contestant (Fred) has answered 9 questions correctly already,
and is now being shown the 10th question. He has no idea what the right answers are
to the 10th or 11th questions are. He has one “lifeline” available, which he can apply
on any question, and which narrows the number of choices from 4 down to 2. Fred has
the following options available.

(a) Walk away with $16,000.

(b) Apply his lifeline to the 10th question, and then answer it. If he gets it wrong, he will leave with $1,000. If he gets it right, he moves on to the 11th question. He then
leaves with $32,000 if he gets the 11th question wrong, and $64,000 if he gets the
11th question right.

(c) Same as the previous option, except not using his lifeline on the 10th question, and
instead applying it to the 11th question (if he gets the 10th question right).

Find the expected value of each of these options. Which option has the highest expected value? Which option has the lowest variance?

Answer:

Let $X$ be the contestant's final winnings.

Obviously in option (a) we have:
$$
\mathbb{E}[X] = 16000, \quad \operatorname{Var}(X)=0
$$.

In option (b), the support value are $\{1000, 32000, 64000\}$, we have
$$
P(X=1000) = \frac{1}{2}
$$

$$
P(X=32000) = \frac{1}{2} \frac{3}{4} = \frac{3}{8}
$$

$$
P(X=64000) = \frac{1}{2} \frac{1}{4} = \frac{1}{8}
$$

This is a valid PMF as the sum is $1$.

By the definition of expectation we have
$$
\mathbb{E}[X] = 1000 \frac{1}{2} + 32000 \frac{3}{8} + 64000 \frac{1}{8} = 20500
$$

Using LOTUS and the variance formula, we have
$$
\operatorname{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2 = 476,250,000
$$

In option (c), the support is the same, we have
$$
P(X=1000) = \frac{3}{4}
$$

$$
P(X=32000) = \frac{1}{4} \frac{1}{2} = \frac{1}{8}
$$

$$
P(X=64000) = \frac{1}{4} \frac{1}{2} = \frac{1}{8}
$$

This is a valid PMF as the sum is $1$.

By the definition of expectation we have
$$
\mathbb{E}[X] = 1000 \frac{3}{4} + 32000 \frac{1}{8} + 64000 \frac{1}{8} = 12,750
$$

Using LOTUS and the variance formula, we have
$$
\operatorname{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2 = 478,187,500
$$

Therefore option (b) has the highest expected value, and option (a) has the lowest variance.

### Q10

Consider the St. Petersburg paradox (Example 4.3.14), except that you receive $\$n$ rather than $\$2^n$ if the game lasts for $n$ rounds. What is the fair value of this game? What if the payoff is $\$n^2$?

Example 4.3.14 (St. Petersburg paradox). Suppose a wealthy stranger offers to
play the following game with you. You will flip a fair coin until it lands Heads for
the first time, and you will receive $\$2$ if the game lasts for $1$ round, $\$4$ if the game lasts for $2$ rounds, $\$8$ if the game lasts for $3$ rounds, and in general, $\$2^n$ if the game lasts for $n$ rounds. What is the fair value of this game (the expected payoff)? How much would you be willing to pay to play this game once?

Answer:

Let $N$ be the number of rounds until the first head, and let $X$ be the value you win from the game, and hence is the fair value of this game.

If you receive $\$n$ if the game lasts for $n$ rounds, we have:
$$
\mathbb{E}[X] = \mathbb{E}[N] = \sum_{n=0}^\infty n P(X=n) = \sum_{n=1}^\infty n (\frac{1}{2})^n
$$

Start from infinite geometric series:
$$
\sum_{n=0}^\infty r^n = \frac{1}{1-r} \quad \text{when $|r| \lt 1$.}
$$

Differentiate with respect to $r$ we have:
$$
\sum_{n=1}^\infty n r^{n-1} = \frac{d}{dr}(\frac{1}{1-r})
$$

Multiply both sides by $r$ we have:
$$
\begin{aligned}
\sum_{n=1}^\infty n r^n
&= r \frac{d}{dr}(\frac{1}{1-r}) \\
&= \frac{r}{(1-r)^2} \\
\end{aligned}
$$

Now let $r=1/2$, we have:
$$
\mathbb{E}[X] = \mathbb{E}[N] = \sum_{n=1}^\infty n (\frac{1}{2})^n = \frac{\frac{1}{2}}{\frac{1}{4}} = 2
$$

If you receive $\$n^2$ if the game lasts for $n$ rounds, we have:
$$
\mathbb{E}[X] = \mathbb{E}[N^2] = \sum_{n=0}^\infty n^2 (\frac{1}{2})^n = \sum_{n=1}^\infty n^2 (\frac{1}{2})^n
$$

Also start from infinite geometric series:
$$
\sum_{n=0}^\infty r^n = \frac{1}{1-r} \quad \text{when $|r| \lt 1$.}
$$

Differentiate with respect to $r$ we have:
$$
\sum_{n=1}^\infty n r^{n-1} = \frac{d}{dr}(\frac{1}{1-r})
$$

Multiply both sides by $r$ we have:
$$
\begin{aligned}
\sum_{n=1}^\infty n r^n
&= r \frac{d}{dr}(\frac{1}{1-r}) \\
&= \frac{r}{(1-r)^2} \\
\end{aligned}
$$

Differentiate with respect to $r$ again:
$$
\sum_{n=1}^\infty n^2 r^{n-1} = \frac{(1-r)^2 + 2(1-r)r}{(1-r)^4}
$$

Multiply both sides by $r$ we have:
$$
\sum_{n=1}^\infty n^2 r^n = r \frac{(1-r)^2 + 2(1-r)r}{(1-r)^4}
$$

Now let $r=1/2$, we have:
$$
\mathbb{E}[X] = \mathbb{E}[N^2]= \sum_{n=1}^\infty n^2 (\frac{1}{2})^n = \frac{\frac{3}{8}}{\frac{1}{16}} = 6
$$

### Q11

Martin has just heard about the following exciting gambling strategy: bet $1 that a
fair coin will land Heads. If it does, stop. If it lands Tails, double the bet for the next toss, now betting $2 on Heads. If it does, stop. Otherwise, double the bet for the next toss to $4. Continue in this way, doubling the bet each time and then stopping right after winning a bet. Assume that each individual bet is fair, i.e., has an expected net winnings of 0. The idea is that
$$
1 + 2 + 2^2 + 2^3 +\ldots+ 2^n = 2^{n+1}−1
$$
so the gambler will be $1 ahead after winning a bet, and then can walk away with a
profit. Martin decides to try out this strategy. However, he only has $31, so he may end up walking away bankrupt rather than continuing to double his bet. On average, how much money will Martin win?

Answer:

Martin can at most play 5 times, because $1 + 2 + 2^2 + 2^3 + 2^4 = 31$.

Let $N$ be the round that lands head, and let $X$ be the money Martin wins.
$$
\begin{aligned}
\mathbb{E}[X]
&= \sum_{n=1}^5 1 \cdot P(N=n) - 31 (\frac{1}{2})^5 \\
&= \sum_{n=1}^5 1 \cdot (\frac{1}{2})^n - 31 (\frac{1}{2})^5 \\
&= \frac{31}{32} - \frac{31}{32} \\
&= 0
\end{aligned}
$$

The strategy gives a very high probability $31/32$ of making $1, but a very small probability $1/32$ of losing everything, and that rare large loss exactly cancels all those frequent $1 gains in expectation.

### Q12

Let $X$ be a discrete r.v. with support $−n,−n+1,\ldots,0,\ldots,n−1,n$ for some positive integer $n$. Suppose that the PMF of $X$ satisfies the symmetry property $P(X=−k) = P(X=k)$ for all integers k. Find $\mathbb{E}[X]$.

Answer:

Suppose $P(X=-k)=P(X=k)=p_k$. We have
$$
\mathbb{E}[X] = \sum_{i=1}^n p_i (i-i) + 0p_0 = 0
$$

### Q13

Are there discrete random variables $X$ and $Y$ such that $\mathbb{E}[X] \gt 100 \mathbb{E}[Y]$ but $Y$ is greater than $X$ with probability at least $0.99$?

Answer:

Yes.

Suppose $X$ has support $\{1,2,\ldots,99,10^{10}\}$ and each support is equally likely; and $Y$ has support $\{100\}$ also each support is equally likely.

### Q14

Let $X$ have PMF
$$
P(X=k) = \frac{c p^k}{k} \quad \text{for $k=1,2,\ldots$,}
$$
where $p$ is a parameter with $0 \lt p \lt 1$ and $c$ is a normalizing constant. We have
$$
c=\frac{−1}{\log(1−p)}
$$, as seen from the Taylor series
$$
-\log(1-p) = p + \frac{p^2}{2} + \frac{p^3}{3} + \ldots
$$

This distribution is called the _Logarithmic distribution_ (because of the log in the above
Taylor series), and has often been used in ecology. Find the mean and variance of $X$.

Answer:

By the definition of expectation we have:
$$
\mathbb{E}[X] = \sum_{k=1}^\infty k \frac{c p^k}{k} = \sum_{k=1}^\infty c p^k = c (\frac{1}{1-p} - 1) = \frac{cp}{1-p}
$$

By LOTUS we have:
$$
\begin{aligned}
\mathbb{E}[X^2]
&= \sum_{k=1}^\infty k^2 \frac{c p^k}{k} \\
&= c \sum_{k=1}^\infty k p^k \\
&= \frac{cp}{(1-p)^2}
\end{aligned}
$$

By the variance formula, we have:
$$
\operatorname{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2 = \frac{cp}{(1-p)^2} - \frac{c^2 p^2}{(1-p)^2} = \frac{cp - c^2 p^2}{(1-p)^2}
$$

### Q15

Player $A$ chooses a random integer between $1$ and $100$, with probability $p_j$ of choosing $j$ (for $j = 1,2,\ldots,100$). Player $B$ guesses the number that player $A$ picked, and receives from player $A$ that amount in dollars if the guess is correct (and $0$ otherwise).

(a) Suppose for this part that player $B$ knows the values of $p_j$. What is player $B$’s
optimal strategy (to maximize expected earnings)?

(b) Show that if both players choose their numbers so that the probability of picking $j$ is
proportional to $1/j$, then neither player has an incentive to change strategies, assuming
the opponent’s strategy is fixed. (In game theory terminology, this says that we have found a Nash equilibrium.)

(c) Find the expected earnings of player $B$ when following the strategy from (b). Express your answer both as a sum of simple terms and as a numerical approximation. Does the value depend on what strategy player $A$ uses?

Answer:

(a)

$B$ can only choose a single number, $B$'s expected earning is $x p_x$, where $x$ is the number he choose. Since he knows $p_x$, and $A$ chooses the number randomly, B should choose the number which makes $x p_x$ the largest.

(b)

1. From A's perspective

Using this strategy, the expected lose of $A$ is
$$
j \frac{c}{j} = c
$$
no matter which number B chooses.

2. From B's perspective

Suppose $A$ uses
$$
P(\text{$A$ choose $j$}) = \frac{c}{j}
$$

If $B$ always guesses $j$, then
$$
\mathbb{E}[\text{$B$'s earnings}] = j \cdot P(\text{$A$ choose $j$}) = j \cdot \frac{c}{j} = c
$$
And this is true for every guesses.

So using this strategy, both $A$ and $B$ have no willing to change.

(c)

Let $A$ use any distribution $p_1, p_2, \ldots, p_100$. Then
$$
\begin{aligned}
\mathbb{E}[\text{$B$'s earnings}]
&= \sum_{j=1}^{100} j P(\text{$A$ choose $j$}) P(\text{$B$ choose $j$}) \\
&= \sum_{j=1}^{100} j P(\text{$A$ choose $j$}) \frac{c}{j} \\
&= j \cdot \frac{c}{j} \sum_{j=1}^{100} P(\text{$A$ choose $j$}) \\
&= c
\end{aligned}
$$

So no matter what strategy $A$ use, $B$'s expected value keeps the same.

### Q16

The dean of Blotchville University boasts that the average class size there is $20$. But the reality experienced by the majority of students there is quite different: they find themselves in huge courses, held in huge lecture halls, with hardly enough seats or Haribo gummi bears for everyone. The purpose of this problem is to shed light on the situation. For simplicity, suppose that every student at Blotchville University takes only one course per semester.

(a) Suppose that there are $16$ seminar courses, which have $10$ students each, and $2$ large lecture courses, which have $100$ students each. Find the dean’s-eye-view average class size (the simple average of the class sizes) and the student’s-eye-view average class size (the average class size experienced by students, as it would be reflected by surveying students and asking them how big their classes are). Explain the discrepancy intuitively.

(b) Give a short proof that for any set of class sizes (not just those given above), the dean’s-eye-view average class size will be strictly less than the student’s-eye-view average class size, unless all classes have exactly the same size.

Hint: Relate this to the fact that variances are nonnegative.

Answer:

(a)

In the dean's-eye-view, the average class size is
$$
\frac{16 \cdot 10 + 2 \cdot 100}{16 + 2} = 20
$$

Let $X$ be the class size from a surveying student, and let $S$, $L$ be the events that the surveying student comes from the small and large lecture course respectively.

We have
$$
\begin{aligned}
\mathbb{E}[X]
&= 10 \cdot P(S) + 100 \cdot P(L)
&= 10 \cdot \frac{16 \cdot 10}{16 \cdot 10 + 2 \cdot 100} + 100 \cdot \frac{2 \cdot 100}{16 \cdot 10 + 2 \cdot 100} \\
&= 60
\end{aligned}
$$

Because the students take one course in a semester, in the student in the survey has higher probability coming from a large course, which gives higher weight to the class size with larger size.

(b)

Suppose there are $x$ students, and $y$ classes. The class sizes are $c_1, c_2, \ldots, c_y$, and $c_1 + c_2 + \ldots + c_y = x$.

From dean's-eye-view the mean of class size is $x/y$.

Let $C$ be the class size of a randomly selected student. The expected class size in student's-eye-view is
$$
\begin{aligned}
\mathbb{E}[C]
&= \sum_{i=1}^y c_i P(\text{student from $i$}) \\
&= \sum_{i=1}^y c_i \frac{c_i}{x} \\
&= \frac{1}{x} \sum_{i=1}^y c_i^2 \\
&\ge \frac{1}{x} \frac{x^2}{y}  \qquad \text{equality holds when $c_1, c_2, \ldots, c_y$ equals.}\\
&= \frac{x}{y}
\end{aligned}
$$

Alternatively, let $D$ be the size of a randomly selected class,
$$
\mathbb{E}[D] = \sum_{i=1}^y c_i \frac{1}{y} = \frac{1}{y} \sum_{i=1}^y c_i = \frac{x}{y}
$$

So we have
$$
\mathbb{E}[D^2] = \sum_{i=1}^y c_i^2 \frac{1}{y} = \frac{1}{y} \sum_{i=1}^y c_i^2
$$

Relating $\mathbb{E}[D^2]$ to $\mathbb{E}[C]$ we have
$$
\frac{y}{x} \mathbb{E}[D^2] = \mathbb{E}[C] = \frac{\mathbb{E}[D^2]}{\mathbb{E}[D]}
$$

Because
$$
\operatorname{Var}(D) = \mathbb{E}[D^2] - (\mathbb{E}[D])^2 \ge 0
$$

We have
$$
\begin{aligned}
\mathbb{E}[C]
&= \frac{\mathbb{E}[D^2]}{\mathbb{E}[D]} \\
&= \frac{\operatorname{Var}(D) + (\mathbb{E}[D])^2}{\mathbb{E}[D]} \\
&= \frac{\operatorname{Var}(D)}{\mathbb{E}[D]} + \mathbb{E}[D] \\
&\ge \mathbb{E}[D]
\end{aligned}
$$

Equality holds when $\operatorname{Var}(D)$ which means the class size must be equal.

### Q17

The sociologist Elizabeth Wrigley-Field posed the following puzzle [29]:

    American fertility fluctuated dramatically in the decades surrounding the Second World War. Parents created the smallest families during the Great Depression, and the largest families during the postwar Baby Boom. Yet children born during the Great Depression came from larger families than those born during the Baby Boom. How can this be?

(a) For a particular era, let $n_k$ be the number of American families with exactly $k$ children, for each $k \ge 0$. (Assume for simplicity that American history has cleanly been separated into eras, where each era has a well-defined set of families, and each family has a well-defined set of children; we are ignoring the fact that a particular family’s size may change over time, that children grow up, etc.) For each $j \ge 0$, let
$$
m_j = \sum_{k=0}^\infty k^j n_k
$$
For a family selected randomly in that era (with all families equally likely), find the expected number of children in the family. Express your answer only in terms of the $m_j$’s.

(b) For a child selected randomly in that era (with all children equally likely), find the expected number of children in the child’s family, only in terms of the $m_j$’s.

(c) Give an intuitive explanation in words for which of the answers to (a) and (b) is larger, or whether they are equal. Explain how this relates to the Wrigley-Field puzzle.

Answer:

(a)

Let $X$ be the number of children in a randomly selected family.
$$
\begin{aligned}
\mathbb{E}[X]
&= \sum_{i=0}^k i P(\text{randomly selected family has $i$ children})
\end{aligned}
$$

The total number of families is $n_0 + n_1 + \ldots + n_k$, which is
$$
m_0 = \sum_{k=0}^\infty k^0 n_k = \sum_{k=0}^\infty n_k
$$

So
$$
P(\text{randomly selected family has $i$ children}) = \frac{n_i}{m_0}
$$

Therefore
$$
\begin{aligned}
\mathbb{E}[X]
&= \sum_{i=0}^k i \frac{n_i}{m_0} = \frac{1}{m_0} \sum_{i=0}^k i n_i = \frac{m_1}{m_0}
\end{aligned}
$$

(b)

Let $Y$ be the number of children in the randomly selected child's family.
$$
\begin{aligned}
\mathbb{E}[Y]
&= \sum_{i=0}^k i P(\text{randomly selected child has a family with $i$ children})
\end{aligned}
$$

The total number of children is $0 n_0 + 1 n_1 + \ldots + k n_k$, which is
$$
m_1 = \sum_{k=0}^\infty k n_k
$$

So
$$
P(\text{randomly selected child has a family with $i$ children}) = \frac{i n_i}{m_1}
$$

Therefore
$$
\begin{aligned}
\mathbb{E}[Y]
&= \sum_{i=0}^k \frac{i^2 n_i}{m_1} = \frac{1}{m_1} \sum_{i=0}^k i^2 n_i = \frac{m_2}{m_1}
\end{aligned}
$$

(c)

The answer to (a) should be smaller than the answer to (b).

The number of families with less children is much greater than the number of families with more children. If we choose the family first equally likely, the chosen family has a much higher probability of few children. This means that those $i$ with small values are assigned with higher weight in
$$
\begin{aligned}
\mathbb{E}[X]
&= \sum_{i=0}^k i P(\text{randomly selected family has $i$ children})
\end{aligned}
$$

If we choose children randomly, the chosen children is more likely comes from a family with more children. This means that those $i$ with large values are assigned with higher weight in
$$
\begin{aligned}
\mathbb{E}[Y]
&= \sum_{i=0}^k i P(\text{randomly selected child has a family with $i$ children})
\end{aligned}
$$

So intuitively $\mathbb{E}[X] \lt \mathbb{E}[Y]$.

In Wrigley-Field puzzle, children are sampled randomly, so they are more likely be born in families with more children.

*NOTE my answer to (c) is not accurate*

## Named distributions

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

### Q18

A fair coin is tossed repeatedly, until it has landed Heads at least once and has landed Tails at least once. Find the expected number of tosses.

Answer:

Let $X$ be number of tosses at which it has landed Heads at least once and has landed Tails at least once. Suppose $X=k$, this can happen in two disjointed event that the $k$-th toss is Head others are Tails, or the $k$-th toss is Tail and others are Heads. That is
$$
P(X=k) = p q^{k-1} + q p^{k-1} = \frac{1}{2^{k-1}}, \qquad \text{for $k \gt 1$.}
$$

Therefore
$$
\mathbb{E}[X] = \sum_{k=2}^\infty \frac{k}{2^{k-1}}
$$

Let $r=1/2$, we have
$$
\mathbb{E}[X] = \sum_{k=2}^\infty k r^{k-1}
$$

Multiply both side by $r$:
$$
\begin{aligned}
r \mathbb{E}[X]
&= \sum_{k=2}^\infty k r^k \\
&= \sum_{k=1}^\infty k r^k - r \\
&= \frac{r}{(1-r)^2} -r
\end{aligned}
$$

Divide both side by $r$, and substitute $r$, we have 
$$
\begin{aligned}
\mathbb{E}[X]
&= \frac{1}{(1-r)^2} - 1 \\
&= 3
\end{aligned}
$$

### Q19

A coin is tossed repeatedly until it lands Heads for the first time. Let $X$ be the number of tosses that are required (including the toss that landed Heads), and let $p$ be the probability of Heads, so that $X \sim \operatorname{FS}(p)$. Find the CDF of $X$, and for $p = 1/2$ sketch its graph.

Answer:

Let $q=1-p$, we have the PMF as:
$$
P(X=k) = p q^{k-1} \qquad \text{for $k \ge 1$}
$$

So the CDF is
$$
P(X \le x) = \sum_{k=1}^{\lfloor x \rfloor} p q^{k-1} = p \sum_{k=1}^{\lfloor x \rfloor} q^{k-1}  \qquad \text{for $x \ge 1$}
$$

To simplify the expression, consider that
$$
\sum_{k=0}^n q^k = \frac{1-q^{n+1}}{1-q}
$$

$$
\sum_{k=0}^n q^{k-1} = \frac{1-q^{n+1}}{q (1-q)}
$$

$$
\sum_{k=1}^n q^{k-1} = \frac{1-q^{n+1}}{q (1-q)} - \frac{1}{q} = \frac{1-q^{n+1} -(1-q)}{pq} = \frac{q - q^{n+1}}{pq} = \frac{1-q^n}{p}
$$

Using it, we have
$$
\begin{aligned}
P(X \le x)
&= p \sum_{k=1}^{\lfloor x \rfloor} q^{k-1} \\
&= p \frac{1-q^{\lfloor x \rfloor}}{p} \\
&= 1 - q^{\lfloor x \rfloor}  \qquad \text{for $x \ge 1$} \\
\end{aligned}
$$

For $x \lt 1$, we have $P(X \le x) = 0$.

### Q20

Let $X \sim \operatorname{Bin}(100,0.9)$. For each of the following parts, construct an example showing that it is possible, or explain clearly why it is impossible. In this problem, $Y$ is a random variable on the same probability space as $X$; note that $X$ and $Y$ are not necessarily independent.

(a) Is it possible to have $Y \sim \operatorname{Pois}(0.01)$ with $P(X \ge Y) = 1$?

(b) Is it possible to have $Y \sim \operatorname{Bin}(100,0.5)$ with $P(X \ge Y) = 1$?

(c) Is it possible to have $Y \sim \operatorname{Bin}(100,0.5)$ with $P(X \le Y) = 1$?

Answer:

(a)

Impossible.

Because $X \sim \operatorname{Bin}(100, 0.9)$, the support of $X$ is $\{0,1,\ldots,100\}$, because $P(X \ge Y) = 1$, we have $Y \le 100$. However, if $Y \sim \operatorname{Pois}(0.01)$, the support of $Y$ is $\{0,1,\ldots,\infty\}$.

(b)

Possible.

Consider an example, in which $100$ people shipping from a website, each person has $0.9$ probability to buy something, after they buy something, it has $0.5 / 0.9$ probability to call for customer support later.

Let $X$ be the number of person that willing to buy something. Let $Y$ be the number of customer support they call.

(c)

Impossible.

Let $Z = Y - X$, If we have $P(X \le Y) = 1$, we have $\mathbb{E}[Z] \ge 0$. So we have
$$
\mathbb{E}[Z] = \mathbb{E}[Y] - \mathbb{E}[X] \ge 0
$$

But $\mathbb{E}[Y] = 100 \cdot 0.5 < \mathbb{E}[X] = 100 \cdot 0.9$.

### Q21

Let 
$$
X \sim \operatorname{Bin}(n,\frac{1}{2}) \quad \text{and} \quad Y \sim \operatorname{Bin}(n+1, \frac{1}{2}),
$$
independently.

(a) Let $V = \min(X,Y)$ be the smaller of $X$ and $Y$, and let $W = \max(X,Y)$ be the
larger of $X$ and $Y$. So if $X$ crystallizes to $x$ and $Y$ crystallizes to $y$, then $V$ crystallizes to $\min(x,y)$ and $W$ crystallizes to $\max(x,y)$. Find $E(V) + E(W)$.

(b) Show that $\mathbb{E}[|X−Y|]= \mathbb{E}[W]−\mathbb{E}[V]$, with notation as in (a).

Answer:

(a)

Note that, for any $x$ and $y$, we have
$$
\max(x, y) + \min(x, y) = x + y
$$

So, no matter what $X$ and $Y$ crystallize to, we have
$$
V + W = X + Y
$$

Therefore
$$
\mathbb{E}[V] + \mathbb{E}[W] = \mathbb{E}[X] + \mathbb{E}[Y] = \frac{2n + 1}{2}
$$

(b)

Note that, for any $x$ and $y$, we have
$$
\max(x, y) - \min(x, y) = |x - y|
$$

So, no matter what $X$ and $Y$ crystallize to, we have
$$
W - V = |X - Y|
$$

Therefore
$$
\mathbb{E}[|X−Y|]= \mathbb{E}[W]−\mathbb{E}[V]
$$

### Q22

Raindrops are falling at an average rate of $20$ drops per square inch per minute. What
would be a reasonable distribution to use for the number of raindrops hitting a particular region measuring $5$ square inches in $t$ minutes? Why? Using your chosen distribution, compute the probability that the region has no rain drops in a given $3$-second time interval.

Answer:

It's reasonable to use Poisson distribution, because:

1. We only knows the average rate in a interval.
2. Each raindrops can drop at any time.
3. Sum of Poisson is Poisson.

Let $X$ be the number of raindrops per square inch per minute. We have
$$
X \sim \operatorname{Pois}(20)
$$

Let $Y$ be the number of raindrops in $5$ square inches in $3$ seconds. We have
$$
Y \sim \operatorname{Pois}(20 \cdot 5 \cdot \frac{3}{60})
$$

Therefore
$$
p_Y(5) = e^{-5}\frac{5^0}{0!} = e^{-5}
$$

### Q23

Alice and Bob have just met, and wonder whether they have a mutual friend. Each
has $50$ friends, out of $1000$ other people who live in their town. They think that it’s unlikely that they have a friend in common, saying "each of us is only friends with $5\%$ of the people here, so it would be very unlikely that our two $5\%$’s overlap.”

Assume that Alice’s $50$ friends are a random sample of the $1000$ people (equally likely to be any $50$ of the $1000$), and similarly for Bob. Also assume that knowing who Alice’s friends are gives no information about who Bob’s friends are.

(a) Compute the expected number of mutual friends Alice and Bob have.

(b) Let $X$ be the number of mutual friends they have. Find the PMF of $X$.

(c) Is the distribution of $X$ one of the important distributions we have looked at? If so, which?

Answer:

Without lost generality, we can describe the story like this. Let Bob choose $50$ friends randomly in the $1000$ people, mark them. Then Alice sample $50$ people from the $1000$ as friend. We'd like to see how many marked people in Alice's sample. This is a Hypergeometric distribution.

Let $X$ be the number of mutual friends Alice and Bob have.
$$
X \sim \operatorname{HGeom}(50, 950, 50)
$$

(a)

$$
\mathbb{E}[X] = 50 \frac{50}{1000} = 2.5
$$

(b)
$$
P(X=k) = \frac{\binom{50}{k} \binom{950}{50-k}}{\binom{1000}{50}} \qquad \text{for $k = 0, 1, \ldots, 50$.}
$$

(c)

As stated above, it is Hypergeometric distribution.

### Q24

Let $X \sim \operatorname{Bin}(n,p)$ and $Y \sim \operatorname{NBin}(r,p)$. Using a story about a sequence of Bernoulli trials, prove that $P(X \lt r) = P(Y \gt n−r)$.

Answer:

In the negative binomial, $Y$ is the number of failures before the $r$-th success.
$$
P(Y \gt n - r) = P(Y + r \gt n)
$$

That is we are count the probability that fewer than $r$ successes occur in the first $n$ independent Bernoulli trials. That is $P(X \lt r)$.

### Q25

Calvin and Hobbes play a match consisting of a series of games, where Calvin has probability $p$ of winning each game (independently). They play with a "win by two" rule: the first player to win two games more than his opponent wins the match. Find the expected number of games played.

Hint: Consider the first two games as a pair, then the next two as a pair, etc.

Answer:

From Calvin's perspective, if the first two games are "win-win" or "lost-lost", the match ends. So we can take two games as a trail, the trial has $p^2 + (1-p)^2$ probability of success. We are trying to find the number of trials that the first success appears. This is First Success distribution.

Let $X$ be number of trials that the first success appears.
$$
\mathbb{E}[X] = \frac{1}{p^2 + (1-p)^2}
$$

The number of games is $2X$, so expected number of games is
$$
\mathbb{E}[2X] = \frac{2}{p^2 + (1-p)^2}
$$

### Q26

Nick and Penny are independently performing independent Bernoulli trials. For concreteness, assume that Nick is flipping a nickel with probability $p_1$ of Heads and Penny is flipping a penny with probability $p_2$ of Heads. Let $X_1,X_2,\ldots$ be Nick’s results and $Y_1,Y_2,\ldots$ be Penny’s results, with $X_i \sim \operatorname{Bern}(p_1)$ and $Y_j \sim \operatorname{Bern}(p_2)$.

(a) Find the distribution and expected value of the first time at which they are simultaneously successful, i.e., the smallest $n$ such that $X_n = Y_n = 1$.

Hint: Define a new sequence of Bernoulli trials and use the story of the Geometric.

(b) Find the expected time until at least one has a success (including the success).

Hint: Define a new sequence of Bernoulli trials and use the story of the Geometric.

(c) For $p_1 = p_2$, find the probability that their first successes are simultaneous, and use this to find the probability that Nick’s first success precedes Penny’s.

Answer:

(a)

They both success with probability $p_1 p_2$. Let $B$ be the turns that they both success, this turn to a First Success distribution:
$$
B \sim \operatorname{FS}(p_1 p_2)
$$

The PMF is:
$$
P(B=k) = (1-p_2 p_2)^{k-1}(p_1 p_2) \qquad \text{for $k=1,2,\ldots,\infty$.}
$$

The expectation is:
$$
\mathbb{E}[X] = \frac{1}{p_1 p_2}
$$

(b)

Let $q_1 = 1-p_1$ and $q_2 = 1 - p_2$, and let $B$ be the number of trials until at least one has a success. Same as First Success distribution but with different probability:
$$
B \sim \operatorname{FS}(1-q_1 q_2)
$$

$$
\mathbb{E}[B] = \frac{1}{1 - q_1 q_2}
$$

(c)

Let $p = p_1 = p_2$, and $q = (1-p_1) = (1-p_2)$

Their first successes can occur simultaneously at trial $1,2,\ldots$. Summing these probabilities is the the probability is the probability that their first successes are simultaneous.

Let $B_i$ be the event that their first successes occurs simultaneously at trial $i$.
$$
P(B_i) = (q^{i-1} p)^2 \qquad \text{for $i=1,2,\ldots$.}
$$

Summing $B_i$, we have
$$
\begin{aligned}
\sum_{i=1}^\infty (q^{i-1} p)^2
&= p^2 \sum_{i=1}^\infty q^{2i-2} \\
&= \frac{p^2}{q^2} \sum_{i=1}^\infty (q^2)^i \\
&= \frac{p^2}{q^2} (\frac{1}{1-q^2} -1) \\
&= \frac{p^2}{q^2} \frac{q^2}{1-q^2} \\
&= \frac{p^2}{1-q^2} \\
&= \frac{p}{2-p}
\end{aligned}
$$

So, the probability that their first success do not appear simultaneously is
$$
1- \frac{p}{2-p} = \frac{2-2p}{2-p}
$$

Because they have the same probability of success, by symmetry, the Nick’s first success precedes Penny’s is
$$
\frac{1-p}{2-p}
$$

### Q27

Let $X$ and $Y$ be $\operatorname{Pois}(\lambda)$ r.v.s, and $T = X + Y$. Suppose that $X$ and $Y$ are not independent, and in fact $X = Y$. Prove or disprove the claim that $T \sim \operatorname{Pois}(2 \lambda)$ in this
scenario.

Answer:

The support of $T$ is $0, 2, 4, \ldots$, which is not the support of Poisson.

### Q28

William is on a treasure hunt. There are $t$ pieces of treasure, each of which is hidden in one of $n$ locations. William searches these locations one by one, without replacement, until he has found all the treasure. (Assume that no location contains more than one piece of treasure, and that William will find the treasure piece when he searches a location that does have treasure.) Let $X$ be the number of locations that William searches during his treasure hunt. Find the distribution of $X$, and find $\mathbb{E}(X)$.

Answer:

In the $X$-th location there must be a treasure, and in the previous $X-1$ locations there must be $t-1$ treasures. Because the hunter searches the location without replacement, the probability of treasure in a location is dependent. Instead, we can think of assigning the treasure to the locations randomly and each assignment is equally likely. So there are
$$
\binom{n}{t}
$$
possible assignments.
Let $L_k$ be the event that the location $k$ contains a treasure and all the other treasures are located on the, say left. By the naive definition of probability we have
$$
P(L_k) = \frac{\binom{k-1}{t-1}}{\binom{n}{t}} \qquad \text{for $t \le k \le n$.}
$$

By the definition expectation we have
$$
\begin{aligned}
\mathbb{E}[X]
&= \sum_{k=t}^n k P(X=k) \\
&= \sum_{k=t}^n k P(L_k) \\
&= \sum_{k=t}^n k \frac{\binom{k-1}{t-1}}{\binom{n}{t}} \\
&= t \sum_{k=t}^n \frac{\binom{k}{t}}{\binom{n}{t}} \\
&= \frac{t} {\binom{n}{t}} \sum_{k=t}^n \binom{k}{t} \\
&= \frac{t \binom{n+1}{t+1}}{\binom{n}{t}} \\
&= t \frac{(n+1)!}{(n-t)! (t+1)!} \frac{(n-t)! t!}{n!} \\
&= t \frac{(n+1)!}{(t+1)!} \frac{t!}{n!} \\
&= t \frac{n+1}{t+1}
\end{aligned}
$$

### Q29

Let $X \sim \operatorname{Geom}(p)$, and define the function $f$ by $f(x) = P(X=x)$, for all real x. Find $\mathbb{E}[f(X)]$. (The notation $f(X)$ means first evaluate $f(x)$ in terms of $p$ and $x$, and then plug in $X$ for $x$; it is not correct to say "$f(X) = P(X= X) = 1$".)

Answer:

Because X is a r.v. so does $f(X)$.
Because the notation $f(X)$ means first evaluate $f(x)$ in terms of $p$ and $x$, and then plug in $X$ for $x$, we have:
$$
f(X) = pq^X
$$

By LOTUS, suppose $k$ is a value in the support of $X$, that means the transformation in LOTUS is $pq^k$, so we have
$$
\begin{aligned}
\mathbb{E}[f(X)]
&= \sum_{k=0}^{\infty} pq^k P(X=k) \\
&= p^2 \sum_{k=0}^{\infty} (q^2)^k \\
&= \frac{p^2}{1-q^2}
\end{aligned}
$$

### Q30

(a) Use LOTUS to show that for $X \sim \operatorname{Pois}(\lambda)$ and any function $g$,
$$
\mathbb{E}[X g(X)] = \lambda \mathbb{E}[g(X+ 1)],
$$
assuming that both sides exist. This is called the Stein-Chen identity for the Poisson.

(b) Find the third moment $\mathbb{E}[X^3]$ for $X \sim \operatorname{Pois}(\lambda)$ by using the identity from (a) and a bit of algebra to reduce the calculation to the fact that $X$ has mean $\lambda$ and variance $\lambda$.

Answer:

(a)

By LOTUS we have
$$
\begin{aligned}
\mathbb{E}[X g(X)]
&= \sum_{k=0}^\infty k g(k) P(X=k) = \sum_{k=1}^\infty k g(k) P(X=k)\\
&= \sum_{k=1}^\infty k g(k) e^{-\lambda} \frac{\lambda^k}{k!} \\
&= e^{-\lambda} \sum_{k=1}^\infty g(k) \frac{\lambda^k}{(k-1)!} \\
&= e^{-\lambda} \sum_{j=0}^\infty g(j+1) \frac{\lambda^{j+1}}{j!} & \text
{reindex $k=j+1$} \\
&= \lambda e^{-\lambda} \sum_{j=0}^\infty g(j+1) \frac{\lambda^j}{j!} & \text{move a $\lambda$ out}

\end{aligned}
$$

By LOTUS we also have
$$
\begin{aligned}
\lambda \mathbb{E}[g(X+ 1)]
&= \lambda \sum_{k=0}^\infty g(k+1) P(X=k) \\
&= \lambda e^{-\lambda} \sum_{k=0}^\infty g(k+1) \frac{\lambda^k}{k!}
\end{aligned}
$$

Therefore
$$
\mathbb{E}[X g(X)] = \lambda \mathbb{E}[g(X+ 1)],
$$

(b)

First, Let $g(X) = X^2$, we have

$$
\begin{aligned}
\mathbb{E}[X^3]
&= \mathbb{E}[X g(X)] \\
&= \lambda \mathbb{E}[g(X+ 1)] \\
&= \lambda \mathbb{E}[(X+1)^2] \\
&= \lambda \mathbb{E}[X^2 + 2X + 1] \\
&= \lambda (\mathbb{E}[X^2] + 2\mathbb{E}[X] + 1) \\
&= \lambda (\mathbb{E}[X^2] + 2\lambda + 1)
\end{aligned}
$$

Because
$$
\operatorname{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2 = \mathbb{E}[X^2] - \lambda^2 = \lambda
$$
We have $\mathbb{E}[X^2] = \lambda + \lambda^2$.

Therefore
$$
\begin{aligned}
\mathbb{E}[X^3]
&= \lambda (\mathbb{E}[X^2] + 2\lambda + 1) \\
&= \lambda (\lambda + \lambda^2 + 2\lambda +1) \\
&= \lambda^3 + 3 \lambda^2 + \lambda
\end{aligned}
$$

### Q31

In many problems about modeling count data, it is found that values of zero in the data are far more common than can be explained well using a Poisson model (we can make
$P(X = 0)$ large for $X \sim \operatorname{Pois}(\lambda)$ by making $\lambda$ small, but that also constrains the mean and variance of $X$ to be small since both are $\lambda$). The _Zero-Inflated Poisson_ distribution is a modification of the Poisson to address this issue, making it easier to handle frequent zero values gracefully.

A Zero-Inflated Poisson r.v. $X$ with parameters $p$ and $\lambda$ can be generated as follows. First flip a coin with probability of $p$ of Heads. Given that the coin lands Heads, $X = 0$. Given that the coin lands Tails, $X$ is distributed $\operatorname{Pois}(\lambda)$. Note that if $X = 0$ occurs, there are two possible explanations: the coin could have landed Heads (in which case the zero is called a structural zero), or the coin could have landed Tails but the Poisson r.v. turned out to be zero anyway. For example, if $X$ is the number of chicken sandwiches consumed by a random person in a week, then $X = 0$ for vegetarians (this is a structural zero), but a chicken-eater could still have $X = 0$ occur by chance (since they might happen not to eat any chicken sandwiches that week).

(a) Find the PMF of a Zero-Inflated Poisson r.v. $X$.

(b) Explain why $X$ has the same distribution as $(1−I)Y$, where $I \sim \operatorname{Bern}(p)$ is independent of $Y \sim \operatorname{Pois}(\lambda)$.

(c) Find the mean of $X$ in two different ways: directly using the PMF of $X$, and using the representation from (b). For the latter, you can use the fact (which we prove in Chapter 7) that if r.v.s $Z$ and $W$ are independent, then $\mathbb{E}[ZW] = \mathbb{E}[Z] \mathbb{E}[W]$.

(d) Find the variance of $X$.

Answer:

Let $q=1-p$, and let $H$ be the event that the coin lands Head. Conditon on $H$ we have

$$
\begin{aligned}
P(X=k)
&= P(X=k \mid H) P(H) + P(X=k \mid H^c) P(H^c) \\
&=
\begin{cases}
q e^{-\lambda} \frac{\lambda^k}{k!} & \text{for $k = 1, 2, \ldots,$} \\
p + qe^{-\lambda} & \text{$k=0$}
\end{cases}
\end{aligned}
$$

(b)

Checking $k=0$:
$$
\begin{aligned}
P((1-I)Y = 0)
&= P(\{Y=0\} \cup \{1-I = 0\}) \\
&= P(Y=0) + P(1-I=0) - P(\{Y=0\} \cap \{1-I = 0\}) \\
&= P(Y=0) + P(1-I=0) - P(Y=0) P(1-I = 0) \\

&= e^{-\lambda} + p - pe^{-\lambda} \\
&= p + q e^{-\lambda}
\end{aligned}
$$

Checking $k=1,2,\ldots$.
$$
\begin{aligned}
P((1-I)Y = k)
&= P(\{Y=k\} \cap \{I = 0\}) \\
&= P(Y=k)P(I=0) \\
&= q e^{-\lambda} \frac{\lambda^k}{k!} \\
\end{aligned}
$$

So they have the same PMF.

(c)

By the PMF of $X$ we have
$$
\begin{aligned}
\mathbb{E}[X]
&= \sum_{k=1}^\infty k q e^{-\lambda} \frac{\lambda^k}{k!} \\
&= q e^{-\lambda} \sum_{k=1}^\infty k \frac{\lambda^k}{k!} \\
&= q e^{-\lambda} \sum_{k=1}^\infty \frac{\lambda^k}{(k-1)!} \\
&= q e^{-\lambda} \sum_{j=0}^\infty \frac{\lambda^{j+1}}{j!} & \text{reindex as $j=k-1$.} \\
&= q e^{-\lambda} \lambda e^{\lambda} & \text{by Taylor series.} \\
&= q \lambda
\end{aligned}
$$

By linearity and independent of r.v. we have:
$$
\begin{aligned}
\mathbb{E}[(1−I)Y]
&= \mathbb{E}[Y] - \mathbb{E}[I] \mathbb{E}[Y] \\
&= \lambda - p \lambda \\
&= q \lambda
\end{aligned}
$$

(d)

By linearity, we have
$$
\begin{aligned}
\mathbb{E}[X^2] 
&= \mathbb{E}[(1-I)^2 Y^2] \\
&= \mathbb{E}[1-2I+I^2] \mathbb{E}[Y^2] \\
&= \mathbb{E}[1-I] \mathbb{E}[Y^2] \\
&= q \lambda(1+\lambda)
\end{aligned}
$$

$$
\begin{aligned}
\operatorname{Var}[X] 
&= \mathbb{E}[X^2] - (\mathbb{E}[X])^2 \\
&= q \lambda(1+\lambda) - (q \lambda)^2 \\
&= q \lambda (1 + \lambda - q \lambda) \\
&= q \lambda (1+p \lambda) \\
&= q \lambda + pq \lambda^2
\end{aligned}
$$

### Q32

A discrete distribution has the _memoryless property_ if for $X$ a random variable with that distribution, $P(X \ge j+ k \mid X \ge j) = P(X \ge k)$ for all nonnegative integers $j$, $k$.

(a) If $X$ has a memoryless distribution with CDF $F$ and PMF $p_i = P(X = i)$, find an expression for $P(X \ge j+ k)$ in terms of $F(j)$, $F(k)$, $p_j$, $p_k$.

(b) Name a discrete distribution which has the memoryless property. Justify your answer with a clear interpretation in words or with a computation.

Answer:

$$
\begin{aligned}
P(X \ge j+k)
&= P(X \ge j+k \mid X \ge j) P(X \ge j) + P(X \ge j+k \mid X \lt j) P(X \lt j) \\
&= P(X \ge k) P(X \ge j)\\\
&= (1 - F(k) + p_k) (1 - F(j) + p_j)
\end{aligned} 
$$

(b)

Geometric distribution is memoryless. The each trial is independent, whenever you get a Tail, the game just reset to it's initial state.

### Q33

Find values of $w$,$b$,$r$ such that the Negative Hypergeometric distribution with parameters $w$,$b$,$r$ reduces to a Discrete Uniform on $\{0,1,\ldots,n\}$. Justify your answer both in terms of the story of the Negative Hypergeometric and in terms of its PMF.

Answer:

Suppose there are $n$ black balls and $1$ white ball in urn. Drawing the balls from the urn randomly and without replacement. Let $X$ be the number of black balls before the drawing the white ball. In this case, we have $w=1$, $b=n$ and $r=1$.

Alternatively, we can think that we keep drawing the balls untill the urn is empty, it doesn't change $X$. Think of the balls lined up in the random order, the order in which they will be drawn. The single white ball can be at any location, assume the location start from $1$ to $n+1$, the number of black balls on the left of white balls is $0,\ldots,n$, they are equally likely, so it's also a Discrete Uniform on $\{0,1,\ldots,n\}$.

$$
X \sim \operatorname{NHGeom}(1, n, 1)
$$

$$
\begin{aligned}
P(X=k)
&= \frac{\binom{1+k-1}{1-1} \binom{1+n-1-k}{1-1}}{\binom{1+n}{1}} \\
&= \frac{\binom{k}{0} \binom{n-k}{0}}{\binom{n+1}{n}} \\
&= \frac{1}{n+1}
\end{aligned}
$$
for $k=0,\ldots,n$, otherwise $P(X=k) = 0$.

Also
$$
X \sim \operatorname{DUnif}(C) \qquad \text{where $C = \{0,1,2,\ldots,n\}$}
$$

In this case
$$
P(X=k) = \frac{1}{|C|} = \frac{1}{n+1}
$$
for $k=0,\ldots,n$, otherwise $P(X=k) = 0$.

## Indicator r.v.s

### Q34

Randomly, $k$ distinguishable balls are placed into $n$ distinguishable boxes, with all possibilities equally likely. Find the expected number of empty boxes.

Answer:

Let $X$ be number of the empty boxes. Let $E_i$ be the indicator that the $i$-th box is empty. So we have
$$
X=\sum_{i=1}^n E_i
$$

For each of the balls, a box only have $1/n$ chance to get it. The probability that the box keeps empty is
$$
(\frac{n-1}{n})^k
$$

By the fundamental bridge and linearity of expectation we have
$$
\begin{aligned}
\mathbb{E}[X]
&= \sum_{i=1}^n (\frac{n-1}{n})^k \\
&= n (\frac{n-1}{n})^k
\end{aligned}
$$

### Q35

A group of $50$ people are comparing their birthdays (as usual, assume their birthdays
are independent, are not February 29, etc.). Find the expected number of pairs of people with the same birthday, and the expected number of days in the year on which at least two of these people were born.

Answer:

Let $X$ be the number of pairs of people with the same birthday. There are 
$$
\binom{50}{2}
$$
different pairs. Let $S_i$ be the indicator that the $i$-th pair has the same birthday, we have
$$
X= S_1 + S_2 + \ldots + S_k \qquad \text{for $k=\binom{50}{2}$.}
$$

In a particular pair, fixing the birthday of one person, the other person only has $1/356$ chance to have the same birthday.
$$
P(S_i) = \frac{1}{365} \qquad \text{for all $i$.}
$$

By the foundamential bridge and linearity of expectation, we have
$$
\mathbb{E}[X] = \binom{50}{2} \frac{1}{365}
$$

Let $Y$ be the number of days in the year on which at least two of these people were born. Let $E_i$ be indicator that the $i$-th day be the birthday to at least two people. We have
$$
Y = \sum_{i=1}^{365} E_i
$$

Randomly assign the people to the 365 days, for a particular day the probability that nobody been assigned to it is
$$
(\frac{364}{365})^{50}
$$

The probability that a person, say Bob, is assigned to it and the other 49 people are not been assigned to it is
$$
\frac{1}{365}(\frac{364}{365})^{49}
$$
And we to consider all the 50 person, so the probability that exactly one person was born on this day is
$$
\frac{50}{365}(\frac{364}{365})^{49}
$$

These two cases are disjoint, so we have
$$
\begin{aligned}
P(E_i)
&= 1 - (\frac{364}{365})^{50} - \frac{50}{365}(\frac{364}{365})^{49} \\
&= \frac{365^{50} - 364^{50} - 50 \cdot 364^{49}}{365^{50}} & \text{for all $i$.}
\end{aligned}
$$

By the fundamental bridge and linearity of expectation, we have
$$
\begin{aligned}
\mathbb{E}[Y]
&= 365 \frac{365^{50} - 364^{50} - 50 \cdot 364^{49}}{365^{50}} \\
&= \frac{365^{50} - 364^{50} - 50 \cdot 364^{49}}{365^{49}}
\end{aligned}
$$

### Q36

A group of $n \ge 4$ people are comparing their birthdays (as usual, assume their
birthdays are independent, are not February 29, etc.). Let $I_{ij}$ be the indicator r.v. of $i$ and $j$ having the same birthday (for $i \lt j$). Is $I_{12}$ independent of $I_{34}$? Is $I_{12}$ independent of $I_{13}$? Are the $I_{ij}$ independent?

Answer:

First checking if $I_{12}$ is independent of $I_{34}$.
$$
P(I_{12} = 1 \mid I_{34} = 1) = \frac{P(\{I_{12} = 1\} \cap \{I_{34} = 1\})}{P(I_{34} =1)}
$$

$I_{12}$ depends only on the birthdays of persons 1 and 2, while $I_{34}$ depends only on the birthdays of persons 3 and 4, and those two groups of birthdays are independent by the model. Therefore the two events are independent.
$$
P(\{I_{12} = 1\} \cap \{I_{34} = 1\}) = P(I_{12} = 1) P(I_{34} = 1)
$$

Therefore
$$
\begin{aligned}
P(I_{12} = 1 \mid I_{34} = 1)
&= \frac{P(I_{12} = 1) P(I_{34} = 1)}{P(I_{34} =1)} \\
&= P(I_{12} = 1)
\end{aligned}
$$

Therefore $I_{12}$ and $I_{34}$ are independent.

Next checking if $I_{12}$ is independent of $I_{13}$.
$$
P(I_{12} = 1 \mid I_{13} = 1) = \frac{P(\{I_{12} = 1\} \cap \{I_{13} = 1\})}{P(I_{13} =1)}
$$

The event $\{I_{12} = 1\} \cap \{I_{13} = 1\}$ means that the three people have the same birthday. The probability of this event is
$$
(\frac{1}{365})^2
$$

We also have
$$
P(I_{12} = 1) = P(I_{13} = 1) = \frac{1}{365}
$$

Therefore
$$
\begin{aligned}
P(I_{12} = 1 \mid I_{13} = 1)
&= \frac{(\frac{1}{365})^2}{\frac{1}{365}} \\
&= \frac{1}{365} \\
&= P(I_{12} = 1)
\end{aligned}
$$

So $I_{12}$ and $I_{13}$ are independent.

But $I_{ij}$ are not independent. Because if we know $I_{12}=1$ and $I_{13}=1$, we must have $I_{23} = 1$.

### Q37

A total of $20$ bags of Haribo gummi bears are randomly distributed to $20$ students.
Each bag is obtained by a random student, and the outcomes of who gets which bag
are independent. Find the average number of bags of gummi bears that the first three
students get in total, and find the average number of students who get at least one bag.

Answer:

Let $O_i$ be the indicator that the $i$-th bag of Haribo gummi bear is obtained by the first three students. By symmetry we have
$$
P(O_i = 1) = \frac{3}{20} \qquad \text{for $i=1,2,\ldots,20$.} 
$$

Let $X$ be the number of bags of gummi bears that the first three students get in total. By linearity of expectation and fundamental bridge we have
$$
\begin{aligned}
\mathbb{E}[X] = \sum_{i=1}^{20} \mathbb{E}[O_i] = 20 \cdot \frac{3}{20} = 3
\end{aligned}
$$

To find the average number of students who get at least one bag, we can find the complement that the number of students that do obtain any bags. Let $E_i$ be the indicator that student $i$ doesn't obtain any bags.
$$
P(E_i = 1) = (\frac{19}{20})^{20}
$$

By the linearity of expectation and fundamental bridge, the average number of students who get at least one bag is
$$
20- 20 \mathbb{E}[E_i] = 20 - 20 (\frac{19}{20})^{20}
$$

### Q38

Each of $n \ge 2$ people puts their name on a slip of paper (no two have the same name).
The slips of paper are shuffled in a hat, and then each person draws one (uniformly at
random at each stage, without replacement). Find the average number of people who
draw their own names.

Answer:

Each person has $1/n$ to draw his name. By linearity and fundamental bridge, the average number of people who draw their own names is
$$
n \cdot \frac{1}{n} = 1
$$

### Q39

Two researchers independently select simple random samples from a population of size
$N$, with sample sizes $m$ and $n$ (for each researcher, the sampling is done without replacement, with all samples of the prescribed size equally likely). Find the expected size of the overlap of the two samples.

Answer:

Let $I_i$ be the indicator that the population member $i$ was sampled by both researchers.
$$
P(I_i = 1) = \frac{m}{N} \frac{n}{N} = \frac{m n}{N^2}
$$

Let $X$ be the number of overlapped samples.
$$
\mathbb{E}[X] = \sum_{i=1}^N\mathbb{E}[I_i] = \sum_{i=1}^N P(I_i = 1) = \frac{mn}{N}
$$

### Q40

In a sequence of n independent fair coin tosses, what is the expected number of occurrences of the pattern "HTH" (consecutively)? Note that overlap is allowed, e.g., $HTHTH$ contains two overlapping occurrences of the pattern.

Answer:

Let $I_i$ be the indicator that the pattern occurs at location $i$. Although $I_i$ are independent but we can still use the linearity of expectation. Let $X$ be the number of the patterns, we have
$$
\mathbb{E}[X] = \sum_{i=1}^{n-2} \mathbb{E}[I_i] = \sum_{i=1}^{n-2} P(I_i = 1) = \frac{n-2}{8}
$$

### Q41

You have a well-shuffled 52-card deck. On average, how many pairs of adjacent cards are there such that both cards are red?

Answer:

Let $I_i$ be the indicator that the $i$-th card and $i+1$-th card are both red. For $1 \le i \le 51$, we have
$$
P(I_i = 1) = \frac{26}{52} \frac{25}{51}
$$

Let $X$ be the number of pairs of adjacent cards that both cards are red.
$$
\mathbb{E}[X] = \sum_{i=1}^{51} \mathbb{E}[I_i] = \sum_{i=1}^{51} P(I_i=1) = 51 \frac{26}{52} \frac{25}{51} = \frac{25}{2}
$$

### Q42

Suppose there are $n$ types of toys, which you are collecting one by one. Each time you
collect a toy, it is equally likely to be any of the $n$ types. What is the expected number
of distinct toy types that you have after you have collected $t$ toys? (Assume that you
will definitely collect $t$ toys, whether or not you obtain a complete set before then.)

Answer:

Let $I_i$ be the indicator that type $i$ is collected. $X$ be the total collected types. For each type we have
$$
P(I_i = 1) = 1 - (\frac{n-1}{n})^t \qquad \text{for $i=1,2,\ldots,n$.}
$$

By the linearity of expecation and fundamental bridge we have
$$
\mathbb{E}[X] = \sum_{i=1}^n \mathbb{E}[I_i] = n (1 - (\frac{n-1}{n})^t) = n - \frac{(n-1)^t}{n^{t-1}}
$$

### Q43

A building has $n$ floors, labeled $1,2,\ldots,n$. At the first floor, $k$ people enter the elevator, which is going up and is empty before they enter. Independently, each decides which of floors $2,3,\ldots,n$ to go to and presses that button (unless someone has already pressed it).

(a) Assume for this part only that the probabilities for floors $2,3,\ldots,n$ are equal. Find the expected number of stops the elevator makes on floors $2,3,\ldots,n$.

(b) Generalize (a) to the case that floors $2,3,\ldots,n$ have probabilities $p_2,\ldots,p_n$ (respectively); you can leave your answer as a finite sum.

Answer:

(a)

Let $I_i$ be the indicator that the elevator will stop at floor $i$. Let $X$ be the total number of stops, so
$$
X=\sum_{i=2}^n I_i
$$

The probability that the elevator stop at floor $i$ is, is complement of the probability that nobody go to the $i$-th floor.
$$
P(I_i = 1) = 1-(\frac{n-2}{n-1})^k
$$

Therefore, we have
$$
\mathbb{E}[X]=\sum_{i=2}^n \mathbb{E}[I_i] = (n-1)(1-(\frac{n-2}{n-1})^k) = n-1-\frac{(n-2)^k}{(n-1)^{k-1}}
$$

(b)

For the $i$-th floor, the probability that nobody choose it is
$$
(1-p_i)^k
$$
So we have
$$
P(I_i = 1) = 1-(1-p_i)^k
$$

Therefore, we have
$$
\begin{aligned}
\mathbb{E}[X]
&=\sum_{i=2}^n \mathbb{E}[I_i] \\
&= \sum_{i=2}^n 1-(1-p_i)^k \\
&= n-1 - \sum_{i=2}^n (1-p_i)^k \\
\end{aligned}
$$

### Q44

There are $100$ shoelaces in a box. At each stage, you pick two random ends and
tie them together. Either this results in a longer shoelace (if the two ends came from
diﬀerent pieces), or it results in a loop (if the two ends came from the same piece).
What are the expected number of steps until everything is in loops, and the expected
number of loops after everything is in loops? (This is a famous interview problem; leave
the latter answer as a sum.)

Hint: For each step, create an indicator r.v. for whether a loop was created then, and
note that the number of free ends goes down by 2 after each step.

Answer:

It's impossible for you to end up with two free ends after all the steps, and each step reduce two free ends, so the number of steps to make everything in loops is
$$
\frac{2 \cdot 100}{2} = 100
$$

Let $I_i$ be the indicator that step $i$ creates the loop ($i$ starts from $1$). And before the step $i$ is performed, there are 
$$
200 - 2(i-1) = 202 - 2i
$$
free ends. That means there are
$$
\frac{202-2i}{2} = 101 - i
$$
lines. There are
$$
\binom{202-2i}{2}
$$
possible choices to choose two free ends, and only $99-i$ of the choices create a loop. Therefore
$$
\begin{aligned}
P(I_i)
&= \frac{101-i}{\binom{202-2i}{2}} \\
&= \frac{2(101-i)}{2(101-i) (201-2i)} \\
&= \frac{1}{201-2i}
\end{aligned}
$$

Let $X$ be the number of loops in the end, we have
$$
\begin{aligned}
\mathbb{E}[X] = \sum_{i=1}^{100} \mathbb{E}[I_i] = \sum_{i=1}^{100} \frac{1}{201-2i}
\end{aligned}
$$

### Q45

Show that for any events $A_1,\ldots,A_n$,
$$
P(A_1 \cap A_2 \ldots \cap A_n) \ge \sum_{j=1}^n P(A_j) - n + 1.
$$

Hint: First prove a similar-looking statement about indicator r.v.s, by interpreting what
the events $I(A_1 \cap A_2 \ldots \cap A_n) = 1$ and $I(A_1 \cap A_2 \ldots \cap A_n) = 0$ mean.

Answer:

Let $I_1, I_2, \ldots I_n$ be the indicators of event $A_1,\ldots,A_n$. 

Consider the statement
$$
I(A_1 \cap A_2 \ldots \cap A_n) \ge \sum_{j=1}^n I(A_j) - n + 1.
$$

For the outcome that $A_1,\ldots,A_n$ all happened, we have
$$
1 \ge n-n+1
$$

Suppose only $k$ of them happened, for $0 \le k \lt n$, we have
$$
0 \ge k - n + 1
$$

That means 
$$
I(A_1 \cap A_2 \ldots \cap A_n) \ge \sum_{j=1}^n I(A_j) - n + 1
$$
holds for all the possible outcomes. Then if we take expectation we have
$$
\mathbb{E}[I(A_1 \cap A_2 \ldots \cap A_n)] \ge \sum_{j=1}^n \mathbb{E}[I(A_j)] - n + 1
$$

So we have
$$
P(A_1 \cap A_2 \ldots \cap A_n) \ge \sum_{j=1}^n P(A_j) - n + 1
$$

### Q46

You have a well-shuffled 52-card deck. You turn the cards face up one by one, without
replacement. What is the expected number of non-aces that appear before the first ace?
What is the expected number between the first ace and the second ace?

Answer:

Let $X$ be the number of non-aces appear before the first ace. We have
$$
X \sim \operatorname{NHGeom}(4, 48, 1)
$$

And we have
$$
\mathbb{E}[X] = \frac{rb}{w+1} = \frac{48}{5}
$$

Let $Y$ be the number of non-aces appear between the first and second ace. Let $Z$ be the number of non-aces appear before the second ace. We have $Y = Z - X$.
$$
\mathbb{E}[Y] = \mathbb{E}[Z] - \mathbb{E}[X]
$$

Because $Z \sim \operatorname{NHGeom}(4,48,2)$, we have
$$
\mathbb{E}[Z] = \frac{rb}{w+1} = \frac{96}{5}
$$

Therefore
$$
\mathbb{E}[Y] = \mathbb{E}[Z] - \mathbb{E}[X] = \frac{96}{5} - \frac{48}{5} = \frac{48}{5}
$$

Sanity check, the aces separates the line into 5 regions, by symmetry each region should have the same expected length.

### Q47

You are being tested for psychic powers. Suppose that you do not have psychic powers.
A standard deck of cards is shuffled, and the cards are dealt face down one by one. Just
after each card is dealt, you name any card (as your prediction). Let $X$ be the number
of cards you predict correctly. (See Diaconis [5] for much more about the statistics of
testing for psychic powers.)

(a) Suppose that you get no feedback about your predictions. Show that no matter what
strategy you follow, the expected value of $X$ stays the same; find this value. (On the
other hand, the variance may be very diﬀerent for diﬀerent strategies. For example, saying “Ace of Spades” every time gives variance $0$.)

Hint: Indicator r.v.s.

(b) Now suppose that you get partial feedback: after each prediction, you are told
immediately whether or not it is right (but without the card being revealed). Suppose
you use the following strategy: keep saying a specific card’s name (e.g., “Ace of Spades”)
until you hear that you are correct. Then keep saying a diﬀerent card’s name (e.g., “Two
of Spades”) until you hear that you are correct (if ever). Continue in this way, naming
the same card over and over again until you are correct and then switching to a new
card, until the deck runs out. Find the expected value of $X$, and show that it is very
close to $e−1$.

Hint: Indicator r.v.s.

(c) Now suppose that you get complete feedback: just after each prediction, the card is
revealed. Call a strategy “stupid” if it allows, e.g., saying “Ace of Spades” as a guess
after the Ace of Spades has already been revealed. Show that any non-stupid strategy
gives the same expected value for $X$; find this value.

Hint: Indicator r.v.s.

Answer:

(a)

Let $I_i$ be the indicator that the guess to the $i$-th card is correct. No matter which card you guess this time $P(I_i = 1) = 1/52$.

Therefore the total number of success guesses is
$$
\sum_{i=1}^{52} = 52 \frac{1}{52} = 1
$$

(b)

Suppose your strategy is first guess card 1 till success, then guess card 2 till success, keep like this, and card 52 till success (if possible).

Let $C_i$ be the indicator that you guess correctly to the card $i$. Then we have
$$
X=\sum_{j=1}^{52} C_j
$$

Because you will always be able to guess correctly for card 1, so 
$$
P(C_1 = 1) = 1
$$

For the card 2 to be guessed correctly, we need card 1 be guessed correctly and card 2 must be on the right of the card 1, Card 1 divides the sequence into two region, by symmetry card 2 is equally likely to be in any of the regions,
$$
P(C_2 = 1) = P(C_1 = 1) \frac{1}{2} = 1 \cdot \frac{1}{2} = \frac{1}{2!}
$$

Similarly, we have
$$
P(C_3 = 1) = P(C_2=1) = 1 \cdot \frac{1}{2} \cdot \frac{1}{3} = \frac{1}{3!}
$$

Generally, we have
$$
P(C_n = 1) = \frac{1}{n!} \qquad \text{for $1 \le n \le 52$.}
$$

Therefore
$$
\begin{aligned}
\mathbb{E}[X]
&= \sum_{i=1}^{52} \mathbb{E}[C_i] \\
&= \sum_{i=1}^{52} P(C_i = 1) \\
&= \sum_{i=1}^{52} \frac{1}{i!}
\end{aligned}
$$

The Taylor series for $e^x$ is
$$
e^x = \sum_{n=0}^\infty \frac{x^n}{n!} \qquad \text{for all $x$.}
$$

When $x = 1$ we have
$$
e = \sum_{n=0}^\infty \frac{1}{n!} = 1 + \sum_{n=1}^\infty \frac{1}{n!}
$$

Therefore
$$
e - 1 \approx \mathbb{E}[X] = \sum_{i=1}^{52} \frac{1}{i!}
$$

(c)

Let $I_i$ be the indicator that your guess to the $i$-th card is correct. At step $i$, there are $52-i+1$ cards left unrevealed, so we have
$$
P(I_i = 1) = \frac{1}{53-i}
$$

$$
\mathbb{E}[X] = \sum_{i=1}^{52} \mathbb{E}[I_i] = \sum_{i=1}^{52} \frac{1}{53-i}
$$

### Q48

Let $X$ be Hypergeometric with parameters $w$, $b$, $n$.

(a) Find $\mathbb{E}[\binom{X}{2}]$ by thinking, without any complicated calculations.

(b) Use (a) to find the variance of $X$. You should get
$$
\operatorname{Var}(X) = \frac{N-n}{N-1} npq,
$$
where $N=w+b$, $p=w/N$, $q=1-p$.

Answer:

(a)

$\binom{X}{2}$ means we sample $n$ balls, among the white balls in the sample, count the number of pairs. Let $I_i$ be the pair $i$ been in the sample. we have
$$
\binom{X}{2} = \sum_{i=1}^{Z} I_i \qquad \text{$Z=\binom{w}{2}$.}
$$

Now consider the probability that a pair is in the sample. The first one can be in any place of the sample, so
$$
P(\text{first ball of the pair in the sample}) = \frac{w}{w+b}
$$
When the first ball is in the sample, there are only $n-1$ places in the sample for the second ball, so
$$
P(\text{second ball in the sample} \mid \text{first ball in the sample}) = \frac{w-1}{w+b-1}
$$

Therefore
$$
P(I_i) = \frac{w}{w+b} \frac{w-1}{w+b-1}
$$

Therefore
$$
\begin{aligned}
\mathbb{E}[\binom{X}{2}]
&= \sum_{i=1}^{\binom{n}{2}} \frac{w}{w+b} \frac{w-1}{w+b-1} \\
&= \binom{n}{2} \frac{w}{w+b} \frac{w-1}{w+b-1}
\end{aligned}
$$

(b)

$$
\begin{aligned}
\mathbb{E}[\binom{X}{2}]
&= \mathbb{E}[\frac{X^2-X}{2}] \\
&= \frac{1}{2} (\mathbb{E}[X^2] - \mathbb{E}[X]) \\
&= \binom{n}{2} \frac{n}{N} \frac{n-1}{N-1}
\end{aligned}
$$

Because
$$
\mathbb{E}[X] = np
$$

we have
$$
\begin{aligned}
\mathbb{E}[X^2] 
&= 2 \binom{n}{2} p \frac{w-1}{N-1} + np \\
&= \frac{n(n-1)p(w-1)}{N-1} + np
\end{aligned}
$$

$$
\begin{aligned}
\operatorname{Var}[X] 
&= \mathbb{E}[X^2] - (\mathbb{E}[X])^2 \\
&= \frac{n(n-1)p(w-1)}{N-1} + np - n^2p^2 \\
&= np (\frac{(n-1)(w-1)}{N-1} + 1 - np) \\
&= \ldots \\
&= \frac{N-n}{N-1} npq
\end{aligned}
$$

### Q49

There are $n$ prizes, with values $\$1,\$2,\ldots,\$n$. You get to choose $k$ random prizes,
without replacement. What is the expected total value of the prizes you get?

Hint: Express the total value in the form $a_1 I_1+\ldots+a_n I_n$, where the $a_j$ are constants and the $I_j$ are indicator r.v.s. Or find the expected value of the $j$-th prize received directly.

Answer:

Let $I_i$ be the indicator that prize $i$ been chosen. Let $X$ be the total values of the prizes you get, we have
$$
X = \sum_{i=1}^n i I_i
$$

For each prize we have
$$
P(I_i = 1) = \frac{k}{n}
$$

Therefore
$$
\begin{aligned}
\mathbb{E}[X]
&= \sum_{i=1}^n i \mathbb{E}[I_i] \\
&= \sum_{i=1}^n i \frac{k}{n} \\
&= \frac{k}{n} \frac{n(n+1)}{2} \\
&= \frac{k(n+1)}{2}
\end{aligned}
$$

### Q50

Ten random chords of a circle are chosen, independently. To generate each of these
chords, two independent uniformly random points are chosen on the circle (intuitively,
“uniformly” means that the choice is completely random, with no favoritism toward
certain angles; formally, it means that the probability of any arc is proportional to the
length of that arc). On average, how many pairs of chords intersect?

Hint: Consider two random chords. An equivalent way to generate them is to pick four
independent uniformly random points on the circle, and then pair them up randomly.

Answer:

There are 
$$
\binom{10}{2}
$$
different 2 pairs chords. Let $I_i$ be the indicator that the chords intersect. Let $X$ be the number of pairs of chords intersect, we have
$$
X= \sum_{i=1}^{\binom{10}{2}} I_i
$$
For a pair of chords, there are 4 points. Consider the possible ways to generate the two chords. Fixing a point among the 4 points, choosing it's end among the other 3 points, only when the end is the middle points among the 3 points that makes the two chords intersect. Therefore
$$
P(I_i = 1) = \frac{1}{3}
$$

Therefore
$$
\mathbb{E}[X] = \sum_{i=1}^{\binom{10}{2}} \mathbb{E}[I_i] = \sum_{i=1}^{\binom{10}{2}} P(I_i = 1) = \binom{10}{2} \frac{1}{3} = 15
$$

### Q51

A hash table is being used to store the phone numbers of $k$ people, storing each
person’s phone number in a uniformly random location, represented by an integer between 1 and $n$ (see Exercise 27 from Chapter 1 for a description of hash tables). Find the expected number of locations with no phone numbers stored, the expected number with exactly one phone number, and the expected number with more than one phone number (should these quantities add up to $n$?).

Answer:

Let $A_i$ be the indicator that the location $i$ is empty. Let $X$ be number of empty locations, we have
$$
X=\sum_{i=1}^n A_i
$$

$$
P(A_i = 1) = (\frac{n-1}{n})^k
$$

Therefore
$$
\mathbb{E}[X] = \sum_{i=1}^n (\frac{n-1}{n})^k = \frac{(n-1)^k}{n^{k-1}}
$$

Let $B_i$ be the indicator that the location $i$ contains exactly $1$ phone number. Let $Y$ be the number of locations that contains exactly 1 phone numbers. So we have
$$
Y=\sum_{i=1}^n B_i
$$

The number of possible assignments for $k$ numbers to $n$ locations is
$$
n^k
$$

For exactly one phone number been assigned to a particular location, other phone numbers must be assigned to the rest of the locations, so we have:
$$
\begin{aligned}
P(B_i = 1)
&= k \frac{(n-1)^{k-1}}{n^k} \\
\end{aligned}
$$

Therefore
$$
\begin{aligned}
\mathbb{E}[Y]
&= \sum_{i=1}^n P(B_i = 1) \\
&= k \frac{(n-1)^{k-1}}{n^{k-1}} \\
\end{aligned}
$$

Let $Z$ be number of locations that contain more than one phone number, we have
$$
Z = n-X-Y
$$

$$
\begin{aligned}
\mathbb{E}[Z] 
&= n - \mathbb{E}[X] - \mathbb{E}[Y] \\
&= n - \frac{(n-1)^k}{n^{k-1}} - k \frac{(n-1)^{k-1}}{n^{k-1}} \\
&= \frac{n^k - (n-1)^k - k(n-1)^{k-1}}{n^{k-1}}
\end{aligned}
$$

### Q52

A coin with probability $p$ of Heads is flipped $n$ times. The sequence of outcomes can be divided into runs (blocks of H’s or blocks of T’s), e.g.,
$\text{HHHTTHTTTH}$ becomes $\text{HHH}$, $\text{TT}$, $\text{H}$, $\text{TTT}$, and $\text{H}$, which has 5 runs. Find the expected number of runs.

Hint: Start by finding the expected number of tosses (other than the first) where the outcome is diﬀerent from the previous one.

Answer:

Let $H_i$ be the event that location $i$ is Head. Let $I_i$ be the indicator that location $i$ is different from location $i-1$. For $2 \le i \le n$, we have
$$
\begin{aligned}
P(I_i = 1) 
&= P(H_i^c \mid H_{i-1}) P(H_{i-1}) + P(H_i \mid H_{i-1}^c) P(H_{i-1}^c) \\
&= (1-p)p + p(1-p) \\
&= 2p (1- p)
\end{aligned}
$$

Let $X$ be the number of runs, we have
$$
\mathbb{E}[X] = 1 + \sum_2^n \mathbb{E}[I_i] = \sum_2^n P(I_i = 1) = 1 + 2(n-1) p (1-p)
$$

### Q53

A coin with probability $p$ of Heads is flipped $4$ times. Let $X$ be the number of occurrences of $\text{HH}$ (for example, $\text{THHT}$ has $1$ occurrence and $\text{HHHH}$ has 3 occurrences). Find $\mathbb{E}[X]$ and $\operatorname{Var}(X)$.

Answer:

Let $q=1-p$. Let $I_i$ be the indicator that location $i$ and $i-1$ forms a $\text{HH}$, for $2 \le i \le 4$. Let $H_i$ be the event that location $i$ is Head. Conditioned on previous location we have
$$
\begin{aligned}
P(I_i = 1) 
&= P(I_i = 1 \mid H_{i-1}) P(H_{i-1}) + P(I_i = 1 \mid H_{i-1}) P(H_{i-1}) \\
&= pp + o \\
&= p^2
\end{aligned}
$$

Let $X$ be the number of $\text{HH}$, we have
$$
X=\sum_{2}^4 I_i
$$

So we have
$$
\mathbb{E}[X] =\sum_{2}^4 \mathbb{E}[I_i] =\sum_{2}^4 P(I_i = 1) = 3p^2
$$

Let $Y=\binom{X}{2}$. For $Y \ne 0$, the result must be $THHH$, $HHHT$, or $HHHH$.
$$
P(Y=1) = P(\text{THHH}) + P(\text{HHHT}) = 2qp^3
$$
$$
P(Y=3) = P(\text{HHHH}) = p^4
$$

Therefore
$$
\mathbb{E}[\binom{X}{2}] = 1P(Y=1) + 3P(Y=3) = 2qp^3 + 3 p^4
$$

We also have
$$
\mathbb{E}[\binom{X}{2}] = \frac{\mathbb{E}[X^2 - X]}{2}
$$

So we have
$$
\begin{aligned}
\mathbb{E}[X^2]
&= 2(2qp^3 + 3 p^4) + \mathbb{E}[X] \\
&= 4qp^3 + 6p^4 + 3p^2
\end{aligned}
$$

Therefore
$$
\begin{aligned}
\operatorname{Var}(X)
&= \mathbb{E}[X^2] - (\mathbb{E}[X])^2 \\
&= 4qp^3 + 6p^4 + 3p^2 - 9p^4 \\
&= 4qp^3 + 3p^2 - 3p^4
\end{aligned}
$$