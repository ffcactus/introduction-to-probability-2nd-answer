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
