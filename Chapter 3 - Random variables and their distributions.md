# Chapter 3 - Random variables and their distributions

## PMFs and CDFs

### Q1

People are arriving at a party one at a time. While waiting for more people to arrive they entertain themselves by comparing their birthdays. Let $X$ be the number of people needed to obtain a birthday match, i.e., before person $X$ arrives no two people have the same birthday, but when person $X$ arrives there is a match. Find the PMF of $X$.

Answer:

The event $\{X=k\}$ can taken as before $k-$ person there is no birthday match, and at exactly $k$ person there is a match, 

Therefore
$$
\begin{aligned}
p_X(k) = P(X=k) 
&= P(\text{no match among first $k-1$ person}) P(\text{person $k$ matches} \mid \text{no match before $k$}) \\

&=\frac{\prod_{i=1}^{k-1} (365-i+1)}{365^{k-1}} \frac{k-1}{365} \\

&= \frac{(k-1)\prod_{i=1}^{k-1} (365-i+1)}{365^k}
\end{aligned}
$$

### Q2

(a) Independent Bernoulli trials are performed, with probability 1/2 of success, until there has been at least one success. Find the PMF of the number of trials performed.

(b) Independent Bernoulli trials are performed, with probability 1/2 of success, until there has been at least one success and at least one failure. Find the PMF of the number
of trials performed.

Answer:

(a)

Let $X$ be the number of trials until there has been at least one success. This can be taken as before $X = k$ there is no success tails, and the $k$'th trial is success.
$$
\begin{aligned}
P(X=k) &= P(\text{first $k-1$ trial are failures}) P(\text{$k$'th trial is success}) \\
&= (\frac{1}{2})^{k-1} \frac{1}{2} \\
&= (\frac{1}{2})^k
\end{aligned}
$$

(b)

Conditioning on the state of the $k$-th trial, we have
$$
\begin{aligned}
P(X=k) &= P(\text{first $k-1$ trial are failures} \mid \text{$k$'th trial is success}) P(\text{$k$'th trial is success}) + P(\text{first $k-1$ trial are successes} \mid \text{$k$'th trial is failure}) P(\text{$k$'th trial is failure}) \\
&= (\frac{1}{2})^k + (\frac{1}{2})^k \\
&= (\frac{1}{2})^{k-1}
\end{aligned}
$$
for $k > 1$, and $P(X = k) = 0$ otherwise.

### Q3

Let $X$ be an r.v. with CDF $F$, and $Y= u + \sigma X$, where $u$ and $\sigma$ are real numbers with $\sigma \gt 0$. (Then $Y$ is called a location-scale transformation of $X$; we will encounter this concept many times in Chapter 5 and beyond.) Find the CDF of $Y$, in terms of $F$.

Answer:

Because
$$
Y = u + \sigma X, \qquad \text{and $\sigma \gt 0$} 
$$
The event $\{Y \le y\}$ is exactly the same set of outcomes as
$$
\{X \le \frac{y - u}{\sigma}\}
$$

So they have the same probability:
$$
P(Y \le y) = P(X \le \frac{y - u}{\sigma}) = F(\frac{y - u}{\sigma})
$$

Therefore
$$
F_Y(y) = F(\frac{y - u}{\sigma})
$$

### Q4

Let $n$ be a positive integer and
$$
F(x) = \frac{\lfloor x \rfloor}{n}
$$
for $0 \le x \le n$, $F(x) = 0$ for $x \lt 0$, and $F(x) = 1$ for $x \gt n$, where $\lfloor x \rfloor$ is the greatest
integer less than or equal to $x$. Show that $F$ is a CDF, and find the PMF that it corresponds to.

Answer:

Check the following properties of $F(x)$.

1. Nondecreasing, If $x_1 \le x_2$, then $F(x_1) \le F(x_2)$.

For $x \lt 0$, we have $F(x) = 0$, fulfill the requirement.

For $x \gt n$, we have $F(x) = 1$, fulfill the requirement.

For $0 \le x \le n$, if $x_1 \le x_2$ we have $\lfloor x_1 \rfloor \le \lfloor x_2 \rfloor$, so we have $F(x_1) \le F(x_2)$.

And because
$$
0 \le \frac{\lfloor x \rfloor}{n} \le 1
$$
If $x_1 \le x_2$, we also have $F(x_1) \le F(x_2)$.

Therefore property 1 fulfilled.

2. Convergence to $0$ and $1$ in the limits:
$$
\lim_{x \to -\infty} F(x) = 0, \quad \text{and} \quad \lim_{x \to +\infty} F(x) = 1
$$

Because $F(x) = 0$ for $x \lt 0$, and $F(x) = 1$ for $x \gt n$, so property 2 fulfilled.

3. Right-continuous:
$$
F(a) = \lim_{x \to a^+} F(x)
$$

Let
$$
m = \lfloor a \rfloor
$$

For $x \gt a$ and sufficiently close to $a$,
$$
\lfloor a \rfloor = \lfloor x \rfloor = m
$$

Therefore
$$
\lim_{x \to a^+} F(x)= \frac{m}{n} = \frac{\lfloor a \rfloor}{n} = F(a).
$$

At the boundary $a = n$
$$
F(a) = \frac{n}{n} = 1,
$$

And immediately to its right we have 
$$
F(x) = 1,
$$

So
$$
\lim_{x \to n^+} F(x) = 1 = F(n)
$$

Therefore property 3 fulfilled.

Hence $F$ is the CDF.

For $k = 1,2,\ldots,n.$
$$
p_X(k) = F(k) - F(k - 1) = \frac{k}{n} - \frac{k-1}{n} = \frac{1}{n}
$$

Otherwise $p_X(k) = 0$.

### Q5

(a) Show that $(\frac{1}{2})^{n+1}$ for $n= 0,1,2,\ldots$ is a valid PMF for a discrete r.v.

(b) Find the CDF of a random variable with the PMF from (a).

Answer:

(a)

First for $n= 0,1,2,\ldots$, we have $(\frac{1}{2})^{n+1} > 0$.

Second
$$
\frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \ldots + \frac{1}{2^n} = 1 - \frac{1}{2^n}
$$
For $n$ is positive integer. When $n \to +\infty$, it approaching to $1$.

Therefore $(\frac{1}{2})^{n+1}$ for $n= 0,1,2,\ldots$ is a valid PMF for a discrete r.v.

(b)

Suppose the r.v. is $X$, for $k \ge 0$
$$
F_X(k) = P(X \le k) = \sum_{i=0}^{\lfloor k \rfloor} (\frac{1}{2})^{i+1} = 1 - \frac{1}{2^{\lfloor k \rfloor+1}} 
$$

And for $k \lt 0$, $F_X(k) = 0$.

### Q6

Benford’s law states that in a very large variety of real-life data sets, the first digit approximately follows a particular distribution with about a $30\%$ chance of a $1$, an $18\%$
chance of a $2$, and in general
$$
P(D=j) = \log_{10}(\frac{j+1}{j}), \quad \text{for $j \in \{1,2,3,\ldots,9\}$},
$$
where $D$ is the first digit of a randomly chosen element. Check that this is a valid PMF (using properties of logs, not with a calculator).

Answer:

For $j \in \{1,2,3,\ldots,9\}$, we have
$$
\frac{j+1}{j} \gt 1
$$
So, we have $P(D = j) > 0$.

Also, we have
$$
\sum_{j=1}^9\log_{10}\frac{j+1}{j} = \log_{10}(\prod_{j=1}^9\frac{j+1}{j}) = \log_{10} 10 = 1
$$

Therefore, it's a valid PMF.

### Q7

Bob is playing a video game that has $7$ levels. He starts at level $1$, and has probability
$p_1$ of reaching level $2$. In general, given that he reaches level $j$, he has probability $p_j$ of
reaching level $j+1$, for $1 \le j \le 6$. Let $X$ be the highest level that he reaches. Find the
PMF of $X$ (in terms of $p_1,\ldots,p_6$).

Answer:

For $k \lt 7$, we have
$$
\begin{aligned}
P(X=k) 
&= P(\text{success on level $1$ to $k-1$})P(\text{failed on level $k$} \mid \text{reached $k-1$}) \\
&=(1-p_k)\prod_{i=1}^{k-1}p_i
\end{aligned}
$$

For $k = 7$, we have
$$
P(X=7) = \prod_{i=1}^{7}p_i
$$

Therefore
$$
p_X(k) =
\begin{cases}
(1-p_k)\prod_{i=1}^{k-1}p_i&\text{for $1 \le k \le 6$}\\
\prod_{i=1}^{6}p_i&\text{for $k = 7$} \\
0&\text{otherwise}
\end{cases}
$$

### Q8

There are $100$ prizes, with one worth $\$1$, one worth $\$2,\ldots,$ and one worth $\$100$. There
are $100$ boxes, each of which contains one of the prizes. You get $5$ prizes by picking
random boxes one at a time, without replacement. Find the PMF of how much your
most valuable prize is worth (as a simple expression in terms of binomial coefficients).

Answer:

Suppose the boxes are order in a line, from left to right the prizes inside them are increasing, and I picking the randomly.

Since I pick up 5 boxes, the most valuable prize start from $\$5$ to $\$100$. The rest 4 boxes should be on the left side. Let $X$ be the r.v. of the most valuable prize, we have
$$
\begin{aligned}
P(X=k) = \frac{\binom{k-1}{4}}{\binom{100}{5}} \qquad \text{for $5 \le k \le 100$}
\end{aligned}
$$
Otherwise $P(X=k)=0$.

### Q9

Let $F_1$ and $F_2$ be CDFs, $0 \lt p \lt 1$, and $F(x) = p F_1(x) + (1−p)F_2(x)$ for all $x$.

(a) Show directly that $F$ has the properties of a valid CDF (see Theorem 3.6.3). The distribution defined by $F$ is called a mixture of the distributions defined by $F_1$ and $F_2$.

(b) Consider creating an r.v. in the following way. Flip a coin with probability $p$ of Heads. If the coin lands Heads, generate an r.v. according to $F_1$; if the coin lands Tails, generate an r.v. according to $F_2$. Show that the r.v. obtained in this way has CDF $F$.

Answer:

(a)

Checking the properties of CDF. 

1. Because both $F_1(x)$ and $F_2(x)$ are nondecreasing, so do $F(x) = pF_1(x) + (1-p)F_2(x)$.

2. Checking the limit at $-\infty$ and $+\infty$.
$$
\begin{aligned}
\lim_{x \to -\infty} F(x)
&= p \lim_{x \to -\infty} F_1(x) + (1-p) \lim_{x \to -\infty} F_2(x) \\
&= p \cdot 0 + (1-p) \cdot 0 \\
&= 0
\end{aligned}
$$

$$
\begin{aligned}
\lim_{x \to +\infty} F(x)
&= p \lim_{x \to +\infty} F_1(x) + (1-p) \lim_{x \to +\infty} F_2(x) \\
&= p \cdot 1 + (1-p) \cdot 1 \\
&= 1
\end{aligned}
$$

3. Checking right-continuous.

For a particular value $a$,
$$
\begin{aligned}
\lim_{x \to a^+} F(x)
&= p \lim_{x \to a^+} F_1(x) + (1-p)\lim_{x \to a^+} F_2(x) \\
&= p F_1(a) + (1-p) F_2(a) \\
&= F(a)
\end{aligned}
$$

Therefore $F(x)$ is a valid CDF.

(b)

Suppose the random variable is $X$. Let $H$ be the event that the coin is head.
$$
\begin{aligned}
F_X(x)
&= P(X \le x) = P(X \le x \mid H)P(H) + P(X \le x \mid H^c)P(H^c) \\
&= p F_1(x) + (1-p) F_2(x)
\end{aligned}
$$

### Q10

(a) Is there a discrete distribution with support $1,2,3,\ldots,$ such that the value of the PMF at $n$ is proportional to $\frac{1}{n}$?

Hint: See the math appendix for a review of some facts about series.

(b) Is there a discrete distribution with support $1,2,3,\ldots,$ such that the value of the PMF at n is proportional to $\frac{1}{n^2}$?

Answer:

(a)

Because every one of the support must have positive probability, so $k \gt 0$.

On the other hand.
$$
k \sum_{n=1}^{+\infty} \frac{1}{n} = k \cdot +\infty
$$
Therefore, such a discrete distribution is impossible.

(b)

Because every one of the support must have positive probability, so $k \gt 0$.

The sum of the probabilities is
$$
k \sum_{n=1}^{+\infty} \frac{1}{n^2} = k \frac{\pi^2}{6} 
$$

So if $k = \frac{6}{\pi^2}$, it can be a valid PMF.

### Q11

Let $X$ be an r.v. whose possible values are $0,1,2,\ldots,$ with CDF $F$. In some countries, rather than using a CDF, the convention is to use the function $G$ defined by $G(x) = P(X \lt x)$ to specify a distribution. Find a way to convert from $F$ to $G$, i.e., if $F$ is a known function, show how to obtain $G(x)$ for all real $x$.

Answer:
 
$$
\begin{aligned}
G(x)
&= F(x) - p_X(x) \\
&=
\begin{cases}
F(x)&\text{when x is not the support of $X$} \\
F(x - 1)&\text{when x is the support of $X$} 
\end{cases}
\end{aligned}
$$

### Q12

(a) Give an example of r.v.s $X$ and $Y$ such that $F_X(x)  \le F_Y(x)$ for all x, where the inequality is strict for some $x$. Here $F_X$ is the CDF of $X$ and $F_Y$ is the CDF of $Y$. For the example you gave, sketch the CDFs of both $X$ and $Y$ on the same axes. Then sketch their PMFs on a second set of axes.

(b) In Part (a), you found an example of two different CDFs where the first is less than or equal to the second everywhere. Is it possible to find two different PMFs where the first is less than or equal to the second everywhere? In other words, find discrete r.v.s $X$ and $Y$ such that $P(X= x) \le P(Y= x)$ for all $x$, where the inequality is strict for some $x$, or show that it is impossible to find such r.v.s.

Answer:

(a)

Consider the example in which the r.v.s having the support and probability in the table below
$$
\begin{array}{c|c|c}
\hline
x&X&Y \\
1&0.25&0.25 \\
2&0&0.25 \\
3&0.75&0.5\\
\end{array}
$$

Therefore, we have
$$
F_X(x) = F_Y(x)=0 \qquad \text{for $x \lt 1$}
$$

$$
F_X(x) = F_Y(x)=0.25 \qquad \text{for $1 \le x \lt 2$}
$$

$$
F_X(x) = 0.25 \lt F_Y(x) = 0.5 \qquad \text{for $2 \le x \lt 3$}
$$

$$
F_X(x) = F_Y(x) = 1 \qquad \text{for $x \ge 3$}
$$

So this example fulfill the requirements.

(b)

If $P(X=x) \le P(Y=x)$ for all x, where the inequality is strict for some $x$, we have
$$
\sum_x P(X=x) \lt \sum_x P(Y=x)
$$

But sum should both equal to $1$, therefore it's impossible to find such r.v.s.

### Q13

Let $X$, $Y$, $Z$ be discrete r.v.s such that $X$ and $Y$ have the same conditional distribution given $Z$, i.e., for all $a$ and $z$ we have
$$
P(X = a \mid Z = z) = P(Y = a \mid Z = z)
$$

Show that $X$ and $Y$ have the same distribution (unconditionally, not just when given $Z$).

Answer:

By LOTP, we have
$$
\begin{aligned}
P(X = a)
&= \sum_z P(X=a \mid Z = z)P(Z = z) \\
&= \sum_z P(Y=a \mid Z = z)P(Z = z) \\
&= P(Y = a)
\end{aligned}
$$

### Q14

Let $X$ be the number of purchases that Fred will make on the online site for a certain
company (in some specified time period). Suppose that the PMF of $X$ is
$$P(X= k) =
\frac{e^{-\lambda} \lambda^k}{k!} \qquad \text{for $k = 0,1,2,\ldots$} 
$$
This distribution is called the Poisson distribution with parameter $\lambda$, and it will be studied extensively in later chapters.

(a) Find $P(X \ge 1)$ and $P(X \ge 2)$ without summing infinite series.

(b) Suppose that the company only knows about people who have made at least one purchase on their site (a user sets up an account to make a purchase, but someone who has never made a purchase there doesn’t appear in the customer database). If the company computes the number of purchases for everyone in their database, then these data are draws from the conditional distribution of the number of purchases, given that at least one purchase is made. Find the conditional PMF of $X$ given $X \ge 1$. (This conditional distribution is called a truncated Poisson distribution.)

Answer:

(a)

$$
\begin{aligned}
P(X \ge 1)
&= 1 - P(X = 0) \\
&= 1 - \frac{e^{-\lambda} \lambda^0}{0!} \\
&= 1 - e^{-\lambda}
\end{aligned}
$$

$$
\begin{aligned}
P(X \ge 2)
&= 1 - P(X = 0) - P(X = 1) \\
&= 1 - \frac{e^{-\lambda} \lambda^0}{0!} - \frac{e^{-\lambda} \lambda^1}{1!}\\
&= 1 - e^{-\lambda} (1+ \lambda)
\end{aligned}
$$

(b)

From the definition of conditional probability we have
$$
P(X=k \mid X \ge 1) = \frac{P(X = k, X \ge 1)}{P(X \ge 1)} 
$$

For $k \ge 1$, we have $P(X=k, X \ge 1) = P(X=k)$, therefore
$$
\begin{aligned}
P(X=k \mid X \ge 1) 
&= \frac{P(X = k, X \ge 1)}{P(X \ge 1)} \\
&= \frac{P(X = k)}{P(X \ge 1)} \\
&= \frac{\frac{e^{-\lambda} \lambda^k}{k!}}{1 - e^{-\lambda}} \\
&= \frac{e^{-\lambda} \lambda^k}{k!(1 - e^{-\lambda})}
\end{aligned}
$$
for $k = 1,2,3,\ldots$, and equals $0$ otherwise.

## Named distributions

### Q15

Find the CDF of an r.v. $X \sim \operatorname{DUnif}(1,2,\ldots,n)$.

Answer

Because
$$
p_X(k) = \frac{1}{|C|} \qquad \text{for $k=1,2,\ldots,n$}
$$

Therefore
$$
F_X(x) = 
\begin{cases}
\frac{\lfloor x \rfloor}{|C|},&1 \le x \le n \\
0,&x\lt 1 \\
1,&x \gt n \\
\end{cases}
$$

### Q16

Let $X \sim \operatorname{DUnif}(C)$, and $B$ be a nonempty subset of $C$. Find the conditional distribution of $X$, given that $X$ is in $B$.

Answer:

Given $k \in B$, we have $\{X=k\} \subseteq \{X \in B\}$, so $P(X=k, X \in B) = P(X = k)$, and we have
$$
\begin{aligned}
P(X=k \mid X \in B)
&= \frac{P(X = k, X \in B)}{P(X \in B)} \\
&= \frac{P(X = k)}{P(X \in B)} \\
&= \frac{\frac{1}{|C|}}{\frac{|B|}{|C|}} = \frac{1}{|B|}
\end{aligned}
$$
For $k \notin B$, $P(X=k \mid X \in B) = 0$.

### Q17

An airline overbooks a flight, selling more tickets for the flight than there are seats on
the plane (figuring that it’s likely that some people won’t show up). The plane has $100$
seats, and $110$ people have booked the flight. Each person will show up for the flight
with probability $0.9$, independently. Find the probability that there will be enough seats for everyone who shows up for the flight.

Answer:

Let $X$ be the number of people that will show up.
$$
X \sim \operatorname{Bin}(110, 0.9)
$$

Therefore
$$
P(X \le 100) = F_X(100) = \sum_{k=0}^{100} \binom{110}{k} 0.9^k 0.1^{110-k}
$$

### Q18

(a) In the World Series of baseball, two teams (call them $A$ and $B$) play a sequence
of games against each other, and the first team to win four games wins the series. Let
$p$ be the probability that $A$ wins an individual game, and assume that the games are
independent. What is the probability that team $A$ wins the series?

(b) Give a clear intuitive explanation of whether the answer to (a) depends on whether
the teams always play $7$ games (and whoever wins the majority wins the series), or the
teams stop playing more games as soon as one team has won $4$ games (as is actually the case in practice: once the match is decided, the two teams do not keep playing more
games).

Answer:

(a)

Let $N$ be the number of games played, and let $A$ be the event that team A wins the series.

The series can end after $4$, $5$, $6$, or $7$ games, and the cases are disjoint, therefore
$$
P(A) = \sum_{n=4}^7 P(A \cap \{N=n\})
$$

When the series ends with $A$ wins, $A$ must win the last game. Before the last game $A$ must have won exactly 3 games, so
$$
P(A \cap \{N=n\}) = p \binom{n-1}{3}p^3(1-p)^{n-4} = \binom{n-1}{3}p^4(1-p)^{n-4}
$$

Therefore
$$
P(A) = \sum_{n=4}^7 \binom{n-1}{3}p^4(1-p)^{n-4}
$$

(b)

The answer does not depend on whether the teams play all seven games or stop as soon as one team wins four games. Once team $A$ has won four games, the outcomes of any remaining games cannot change the winner. Conversely, if $A$ wins a majority of seven games, it must obtain its fourth win at some point during those seven games and would therefore also win under the stop-early rule.

### Q19

In a chess tournament, $n$ games are being played, independently. Each game ends in a win for one player with probability $0.4$ and ends in a draw (tie) with probability $0.6$. Find the PMFs of the number of games ending in a draw, and of the number of players whose games end in draws.

Answer:

Let $D$ be the number of games ending in a draw, $D \sim \operatorname{Bin}(n, 0.6)$, so
$$
p_D(k) = \binom{n}{k}0.6^k0.4^{n-k} \qquad \text{for $k = 0,1,2,\ldots$}
$$
And $p_D(k) = 0$ otherwise.

Let $N$ be the number of players whose games end in draws. $N = 2D$.
$$
\begin{aligned}
p_N(k) = P(N=k)
&= P(2D = k) \\
&= P(D= \frac{k}{2}) \\
&= \binom{n}{\frac{k}{2}}0.6^{\frac{k}{2}}0.4^{n - \frac{k}{2}} \qquad \text{for $k = 0,2,4,6,\ldots$}\\
\end{aligned}
$$
And $p_N(k) = 0$ otherwise.

### Q20

Suppose that a lottery ticket has probability $p$ of being a winning ticket, independently of other tickets. A gambler buys $3$ tickets, hoping this will triple the chance of having at least one winning ticket.

(a) What is the distribution of how many of the 3 tickets are winning tickets?

(b) Show that the probability that at least 1 of the 3 tickets is winning is $3p−3p^2 + p^3$, in two different ways: by using inclusion-exclusion, and by taking the complement of the desired event and then using the PMF of a certain named distribution.

(c) Show that the gambler’s chances of having at least one winning ticket do not quite triple (compared with buying only one ticket), but that they do _approximately_ triple if $p$ is small.

Answer:

(a)

Let $N$ be the number of winning tickets, we have $N \sim \operatorname{Bin}(3, p)$.

(b)

Let $W_1$, $W_2$ and $W_3$ be the events that the first, second and third tickets are winning tickets respectively.

By inclusion-exclusion we have
$$
\begin{aligned}
P(W_1 \cup W_2 \cup W_3)
&= P(W_1) + P(W_2) + P(W_3) - P(W1 \cap W_2) - P(W1 \cap W_3) - P(W2 \cap W_3) + P(W_1 \cap W_2 \cap W_3) \\
&= 3p - 3p^2 + p^3
\end{aligned}
$$

By taking the complement, we can check the event that none of the tickets is a winning ticket. Let $X$ be the number of tickets that is not a winning ticket, we have $X \sim \operatorname{Bin}(3, (1-p))$, therefore the probability of having at least one winning ticket is
$$
1 - P(X=3)=1 - \binom{3}{3}(1-p)^3p^0 = 1 - (1-p)^3 = 3p - 3p^2 + p^3 
$$

(c)

What gambler expect is $3p$, but actually it is $3p - 3p^2 + p^3$, and
$$
3p - 3p^2 + p^3 = 3p - p^2(3- p) \lt 3p \qquad \text{when $0 \lt p \le 1$}
$$

But the ratio approaching to $1$ when $p$ approaching to $0$.
$$
\lim_{p \to 0} \frac{3p - 3p^2 + p^3}{3p} = 1
$$

### Q21

Let $X \sim \operatorname{Bin}(n,p)$ and $Y \sim \operatorname{Bin}(m,p)$, independent of $X$. Show that $X−Y$ is not Binomial.

Answer:

The support of a Binomial PMF is $0,1,2,\ldots,n$.

Let's consider the probability of
$$
P(X - Y = -1) \gt 0
$$

This can happen when
$$
P(X = Y - 1) \gt 0
$$

Because
$$
\{X=0, Y=1\} \subseteq \{X = Y - 1\}
$$
We have 
$$
P(X=0, Y=1) \le P(X = Y - 1)
$$

Because $X$ and $Y$ are independent
$$
P(X=0, Y=1) = P(X=0)P(Y=1)
$$

When $0 \lt p \lt 1$ we have $P(X=0)P(Y=1) \gt 0$, therefore
$$
P(X - Y = -1) = P(X = Y - 1) \ge P(X=0)P(Y=1) \gt 0
$$
but every Binomial random variable is nonnegative; therefore $X−Y$ cannot be Binomial.

### Q22

There are two coins, one with probability $p_1$ of Heads and the other with probability $p_2$ of Heads. One of the coins is randomly chosen (with equal probabilities for the two coins). It is then flipped $n \ge 2$ times. Let $X$ be the number of times it lands Heads.

(a) Find the PMF of $X$.

(b) What is the distribution of $X$ if $p_1 = p_2$?

(c) Give an intuitive explanation of why $X$ is not Binomial for $p_1 \ne p_2$ (its distribution is called a mixture of two Binomials). You can assume that $n$ is large for your explanation, so that the frequentist interpretation of probability can be applied.

Answer:

(a)

Let $C_1$ and $C_2$ be the events that the coin 1 and 2 be chosen respectively.

$$
\begin{aligned}
P(X=k)
&= P(X=k \mid C_1) P(C_1) + P(X=k \mid C_2) P(C_2) \\
&= \frac{1}{2} \binom{n}{k}p_1^k(1-p_1)^{n-k} + \frac{1}{2} \binom{n}{k}p_2^k(1-p_2)^{n-k} \\
&= \frac{1}{2} \binom{n}{k}(p_1^k(1-p_1)^{n-k} + p_2^k(1-p_2)^{n-k}) \qquad \text{for $k=0,1,2,\ldots,n$.}
\end{aligned}
$$

(b)

Suppose $p_1 = p_2 = p$

$$
\begin{aligned}
P(X=k)
&= \frac{1}{2} \binom{n}{k}(p_1^k(1-p_1)^{n-k} + p_2^k(1-p_2)^{n-k}) \\
&= \frac{1}{2} \binom{n}{k}(2p^k(1-p)^{n-k}) \\
&= \binom{n}{k}(p^k(1-p)^{n-k})
\end{aligned}
$$

Therefore
$$
X \sim \operatorname{Bin}(n, p)
$$

(c)

Suppose $n$ is huge, if coin 1 is chosen the number of head will be concentrated near $p_1 n$; similarly if coin 2 is chosen the number of head will be concentrated near $p_2 n$. So the PMF of $X$ is expected to have two peak, at $p_1 n$ and $p_2 n$ respectively. However, a typical Binomial distribution has only one peak.

### Q23

There are $n$ people eligible to vote in a certain election. Voting requires registration.
Decisions are made independently. Each of the $n$ people will register with probability
$p_1$. Given that a person registers, they will vote with probability $p_2$. Given that a person votes, they will vote for Kodos (who is one of the candidates) with probability $p_3$. What is the distribution of the number of votes for Kodos (give the PMF, fully simplified, or the name of the distribution, including its parameters)?

Answer:

A people vote for Kodos with probability $p_1 p_2 p_3$. Let $X$ be the number of people vote for Kodos, $X \sim \operatorname{Bin}(n, p_1 p_2 p_3)$

### Q24

Let $X$ be the number of Heads in $10$ fair coin tosses.

(a) Find the conditional PMF of $X$, given that the first two tosses both land Heads.

(b) Find the conditional PMF of $X$, given that at least two tosses land Heads.

Answer:

Suppose the coin lands head with probability $p = \frac{1}{2}$. Let $E$ be the event that the first two tosses land heads.

$$
P(X = k \mid E) = \frac{P(E \mid X = k) P(X=k)}{P(E)}
$$

All the outcomes that having $k$ heads are equally likely. To find the number of the ones that the first two tosses are heads, we can just count the possible outcomes to the rest of the $k-2$ tosses, therefore
$$
P(E \mid X=k) = \frac{\binom{n-2}{k-2}}{\binom{n}{k}}
$$

Therefore
$$
\begin{aligned}
P(X = k \mid E) 
&= \frac{P(E \mid X = k) P(X=k)}{P(E)} \\
&= \frac{\frac{\binom{n-2}{k-2}}{\binom{n}{k}} \binom{n}{k}p^k (1-p)^{n-k}}{p^2} \\
&= \binom{n-2}{k-2} p^{k-2} (1-p)^{n-k} \\
&= \frac{\binom{8}{k-2} }{2^8} \qquad \text{for $k=2,3,\ldots,n$.}
\end{aligned} \\
$$

(b)

Suppose the coin lands head with probability $p = \frac{1}{2}$. Let $E$ be the event that the at least two tosses land heads.

By Bayes' rule, we have
$$
P(X = k \mid E) = \frac{P(E \mid X = k) P(X=k)}{P(E)}
$$

To find $P(E)$, we check the probability that there is $0$ head and the probability that there is $1$ head.

$$
\begin{aligned}
P(E)
&= 1 - P(X=1) - P(X=0) \\
&= 1 - \binom{n}{1}p^1(1-p)^{n-1} -  \binom{n}{0}p^0(1-p)^{n-0} \\
&= 1 - 10 \cdot (\frac{1}{2})^{10} - 1 \cdot 1 \cdot (\frac{1}{2})^{10} \\
&= 1 - 11 \cdot (\frac{1}{2})^{10}
\end{aligned}
$$

Depends on the value of $k$, we have
$$
P(E \mid X=k) = 
\begin{cases}
1&\text{when $k=2,3,\ldots,n$} \\
0&\text{when $k=0,1$}
\end{cases}
$$

When $k=2,3,\ldots,10$, we have
$$
\begin{aligned}
P(X = k \mid E)
&= \frac{P(E \mid X = k) P(X=k)}{P(E)} \\
&= \frac{P(X=k)}{P(E)} \\
&=\frac{\binom{10}{k} (\frac{1}{2})^{10}}{1 - 11 \cdot (\frac{1}{2})^{10}} \\
&= \frac{\binom{10}{k}}{2^{10} - 11}
\end{aligned}
$$

Therefore
$$
P(X =k \mid E) =
\begin{cases}
\frac{\binom{10}{k}}{2^{10} - 11}&\text{when $k=2,3,\ldots,10$} \\
0&\text{when $k=0,1$}
\end{cases}
$$

### Q25

Alice flips a fair coin $n$ times and Bob flips another fair coin $n+1$ times, resulting
in independent $X \sim \operatorname{Bin}(n, \frac{1}{2})$ and $Y \sim \operatorname{Bin}(n + 1, \frac{1}{2})$.

(a) Show that $P(X \lt Y) = P(n − X \lt n + 1 − Y)$.

(b) Compute $P(X \lt Y)$.

Hint: Use (a) and the fact that $X$ and $Y$ are integer-valued.

Answer:

(a)

Because the coins are both fair, the checking on the heads has the same meaning of checking on the tails. So
$$
P(X \lt Y) \quad \text{and} \quad P(n − X \lt n + 1 − Y)
$$
have the same distribution by heads/tails symmetry, so they are equal.

(b)

Because $P(X \lt Y) = P(n − X \lt n + 1 − Y) = P(X+1 \gt Y)$

Because $X$ and $Y$ are both integers. The event $\{X \lt Y\}$ is complement to $\{X \ge Y\}$, and $\{X \ge Y\}$ is the same as $\{X + 1 \gt Y\}$. Therefore
$$
P(X \lt Y) = 1 - P(X \lt Y)
$$
Hence 
$$
P(X \lt Y) = \frac{1}{2}
$$

### Q26

If $X \sim \operatorname{HGeom}(w,b,n)$, what is the distribution of $n−X$? Give a short proof.

Answer:

$$
P(n-X = k) = P(X = n-k) = \frac{\binom{w}{n-k} \binom{b}{k}}{\binom{w+b}{n}}
$$

Compare with
$$
P(X=k) = \frac{\binom{w}{k} \binom{b}{n-k}}{\binom{w+b}{n}}
$$
we can find that $w$ and $b$ swapped, therefore
$$
(n-X) \sim \operatorname{HGeom}(b, w, n)
$$

### Q27

Recall de Montmort’s matching problem from Chapter 1: in a deck of $n$ cards labeled $1$
through $n$, a match occurs when the number on the card matches the card’s position in
the deck. Let $X$ be the number of matching cards. Is $X$ Binomial? Is X Hypergeometric?

Answer:

Suppose the cards are randomly placed to the positions one at a time, this doesn't change anything to the problem.

For the first card, there are $n$ positions to which it to be assigned. The probability to be assigned to the matching position is $\frac{1}{n}$.

For the second card, we can condition on whether its matching position has already been occupied. It's matching position has $\frac{n-1}{n}$ probability of being unoccupied, and in this situation it has $\frac{1}{n-1}$ probability of been assigned to the matching position. Therefore, it has $\frac{1}{n-1} \frac{n-1}{n} = \frac{1}{n}$ probability of been assigned to the matching position.

Similarly, for the third card, its matching position has $\frac{n-2}{n}$ probability of being unoccupied, and in this situation, it has $\frac{1}{n-2}$ probability of been assigned to the matching position. Therefore, it has $\frac{1}{n-2} \frac{n-2}{n} = \frac{1}{n}$ probability of been assigned to the matching position.

So each card has $\frac{1}{n}$ probability of been assigned to the matching position.

However, in the Binomial distribution trials are independent. Here if we know the first card is in the matching position, the probability for second card to be as the matching position is $\frac{1}{n-1}$. Therefore, the matching is not independent, $X$ is not Binomial.

In a Hypergeometric experiment, the objects have fixed types before sampling—for example, every ball is already labeled white or black. Here, a card is not inherently a "matching card" or a "nonmatching card"; its status depends on the position to which it is assigned.

For a more rigorous argument, consider the support of $X$:
$X=n$ is possible: every card is in its correct position.
$X=n-2$ is possible: swap two cards and leave all others fixed.
$X=n-1$ is impossible: if $n-1$ cards are in their correct positions, the only remaining card must also occupy its correct position.

Thus, the support contains $n-2$ and $n$, but not $n-1$. A Hypergeometric distribution always has a consecutive range of possible integer values. It cannot have a gap like this. Therefore, $X$ is not Hypergeometric.

