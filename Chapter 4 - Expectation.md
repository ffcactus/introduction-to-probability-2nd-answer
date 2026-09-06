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
