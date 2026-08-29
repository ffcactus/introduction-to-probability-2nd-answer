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

### Q28

There are $n$ eggs, each of which hatches a chick with probability $p$ (independently).
Each of these chicks survives with probability $r$, independently. What is the distribution
of the number of chicks that hatch? What is the distribution of the number of chicks that
survive? (Give the PMFs; also give the names of the distributions and their parameters,
if applicable.)

Answer:

Because eggs hatch independently, with the same probability $p$, this is Binomial. Let $H$ be the number of eggs hatch, we have
$$
H \sim \operatorname{Bin}(n, p)
$$
$$
p_H(k)=\binom{n}{k}p^k(1-p)^{n-k} \qquad \text{for $k=0,1,2,\ldots,n$.}
$$

From an egg to a chick survive, the probability is
$$
P(\text{survive and hatch}) = P(\text{hatch}) P(\text{survive} \mid \text{hatch}) = pr
$$

The chicks survive independently, so it's Binomial. Let $S$ be the number of chicks that survive, we have
$$
S \sim \operatorname{Bin}(n, pr)
$$
$$
p_S(k)=\binom{n}{k} (pr)^k(1-pr)^{n-k} \text{for $k=0,1,2,\ldots,n$.}
$$

### Q29

A sequence of $n$ independent experiments is performed. Each experiment is a success
with probability $p$ and a failure with probability $q=1−p$. Show that conditional on
the number of successes, all valid possibilities for the list of outcomes of the experiment
are equally likely.

Answer:

* Let $X$ be the number of successes.
* Let $X_i$ be the indicator of the success of the $i$-th experiment.
* Let $X = X_1 + X_2 + \ldots + X_n$ be the number of successes.

Given that the number of successes is $k$, the probability of a sequence
$$
X_1 = a_1, X_2 = a_2, \ldots, X_n=a_n
$$
in which $a_1, a_2, \ldots a_n \in \{0, 1\}$ and $a_1 + a_2 + \ldots + a_n = k$, is 
$$
\begin{aligned}
P(X_1 = a_1, X_2 = a_2, \ldots, X_n=a_n \mid X=k) = \frac{P(X_1 = a_1, X_2 = a_2, \ldots, X_n=a_n, X=k)}{P(X=k)}
\end{aligned}
$$

From 
$$
\{X_1 = a_1, X_2 = a_2, \ldots, X_n=a_n\} \subseteq \{X = k\}
$$
we have
$$
P(X_1 = a_1, X_2 = a_2, \ldots, X_n=a_n, X=k) = P(X_1 = a_1, X_2 = a_2, \ldots, X_n=a_n)
$$

Therefore
$$
\begin{aligned}
P(X_1 = a_1, X_2 = a_2, \ldots, X_n=a_n \mid X=k) 
&= \frac{P(X_1 = a_1, X_2 = a_2, \ldots, X_n=a_n, X=k)}{P(X=k)} \\
&= \frac{p^k q^{n-k}}{\binom{n}{k} p^k q^{n-k}} \\
&= \frac{1}{\binom{n}{k}}
\end{aligned}
$$

That means the sequence with number of successes $k$ are equally likely.

### Q30

A certain company has $n+m$ employees, consisting of $n$ women and $m$ men. The
company is deciding which employees to promote.

(a) Suppose for this part that the company decides to promote $t$ employees, where
$1 \le t \le n+ m$, by choosing $t$ random employees (with equal probabilities for each set
of $t$ employees). What is the distribution of the number of women who get promoted?

(b) Now suppose that instead of having a predetermined number of promotions to
give, the company decides independently for each employee, promoting the employee
with probability $p$. Find the distributions of the number of women who are promoted,
the number of women who are not promoted, and the number of employees who are promoted.

(c) In the set-up from (b), find the conditional distribution of the number of women
who are promoted, given that exactly $t$ employees are promoted.

Answer:

(a)
All the employees are labelled with woman or man before promotion, the promotion is without replacement, so the number of women $N$ in the promotion has a Hypergeometric distribution.
$$
p_N(k) = \frac{\binom{n}{k} \binom{m}{t-k}}{\binom{m+n}{t}}
$$

(b)

* Let $N$ be the number of women who are promoted.
* $M$ be the number of men who are not promoted, then $M=n-N$.
* $X$ be the number of employees who are promoted.

Because the promotion are independent for all employees, and the probability is the same $p$, from Binomial distribution we have
$$
p_N(k) = \binom{n}{k}p^k (1-p)^{n-k} \qquad \text{for $k=0, 1, \ldots, n$.}
$$

$$
\begin{aligned}
p_M(k)
&= P(n-N=k) \\
&= P(N=n-k) \\
&= \binom{n}{n-k}p^{n-k} (1-p)^k
\end{aligned}
$$

$$
p_X(k) = \binom{m+n}{k}p^k (1-p)^{m+n-k}
$$

(c)

* Let $W$ be the number of women who are promoted.
* Let $X$ be the number of employees who are promoted.
$$
P(W=k \mid X=t) = \frac{\binom{n}{k} \binom{m}{t-k}}{\binom{m+n}{t}} \qquad \text{for $k \le n$ and $t-k \le m$.}
$$
Otherwise, $P(W=k, X=t) = 0$.

### Q31

Once upon a time, a famous statistician offered tea to a lady. The lady claimed that
she could tell whether milk had been added to the cup before or after the tea. The
statistician decided to run some experiments to test her claim.

(a) The lady is given $6$ cups of tea, where it is known in advance that $3$ will be milk-
first and $3$ will be tea-first, in a completely random order. The lady gets to taste each
and then guess which $3$ were milk-first. Assume for this part that she has no ability
whatsoever to distinguish milk-first from tea-first cups of tea. Find the probability that
at least $2$ of her $3$ guesses are correct.

(b) Now the lady is given one cup of tea, with probability $1/2$ of it being milk-first.
She needs to say whether she thinks it was milk-first. Let $p_1$ be the lady’s probability
of being correct given that it was milk-first, and $p_2$ be her probability of being correct given that it was tea-first. She claims that the cup was milk-first. Find the _posterior odds_ that the cup is milk-first, given this information.

Answer:

(a)

The teas are labelled as tea-first or milk-first. Because the the lady has no ability whatsoever to distinguish the teas, so the three cup of tea is sampled at random. The number of milk-first teas in the sample is the number of correct guesses. Let $X$ be the number of correct guesses, $X$ follows a Hypergemetric distribution.

$$
\begin{aligned}
P(\{X=2\} \cup \{X=3\}) 
&= P(X=2) + P(X=3) - (\{X=2\} \cap \{X=3\}) \\
&= P(X=2) + P(X=3) \\
&=\frac{\binom{3}{2} \binom{3}{1}}{\binom{6}{3}} + \frac{\binom{3}{3} \binom{3}{0}}{\binom{6}{3}} \\
&= \frac{1}{2}
\end{aligned}
$$

(b)

Let $M$ be the event that the given cup of tea is milk-first.
Let $C$ be the event that the lady claim the tea is milk-first.

From the conditional odds, we have
$$
\frac{P(M \mid C)}{P(M^c \mid C)} = \frac{P(M)}{P(M^c)} \frac{P(C \mid M)}{P(C \mid M^c)}
$$

Let $S$ be the event that the lady's guess is correct, and conditioned on it, we have
$$
\begin{aligned}
P(C \mid M) 
&= P(C \mid S, M) P(S \mid M) + P(C \mid S^c, M) P(S^c \mid M) \\
&= 1 \cdot p_1 + 0 \cdot (1-p_1) \\
&= p_1
\end{aligned}
$$

$$
\begin{aligned}
P(C \mid M^c) 
&= P(C \mid S, M^c) P(S \mid M^c) + P(C \mid S^c, M^c) P(S^c \mid M^c) \\
&= 0 \cdot p_2 + 1 \cdot (1-p_2) \\
&= 1 - p_2
\end{aligned}
$$

Therefore 
$$
\begin{aligned}
\frac{P(M \mid C)}{P(M^c \mid C)} 
&= \frac{P(M)}{P(M^c)} \frac{P(C \mid M)}{P(C \mid M^c)} \\
&=\frac{\frac{1}{2}}{\frac{1}{2}}\frac{p_1}{1-p_2} \\
&= \frac{p_1}{1-p_2}
\end{aligned}
$$

### Q32

In Evan’s history class, $10$ out of $100$ key terms will be randomly selected to appear
on the final exam; Evan must then choose $7$ of those $10$ to define. Since he knows the
format of the exam in advance, Evan is trying to decide how many key terms he should
study.

(a) Suppose that Evan decides to study $s$ key terms, where $s$ is an integer between $0$
and $100$. Let $X$ be the number of key terms appearing on the exam that he has studied.
What is the distribution of $X$? Give the name and parameters, in terms of $s$.

(b) Using R or other software, calculate the probability that Evan knows at least $7$ of
the $10$ key terms that appear on the exam, assuming that he studies $s= 75$ key terms.

Answer:

(a)

Before the exam, the key terms are marked as been studied by Evan or not. A sample of size 10 is collected as the exam and all the sample are equally likely. We need to check probability that $X$ number of key terms in the exam have already been studied by Evan. Therefore
$$
X \sim \operatorname{HGeom}(s, 100-s,10)
$$

(b)

Skip.

### Q33

A book has $n$ typos. Two proofreaders, Prue and Frida, independently read the book. Prue catches each typo with probability $p_1$ and misses it with probability $q_1 = 1−p_1$,
independently, and likewise for Frida, who has probabilities $p_2$ of catching and $q_2 = 1−p_2$ of missing each typo. Let $X_1$ be the number of typos caught by Prue, $X_2$ be the number caught by Frida, and $X$ be the number caught by at least one of the two proofreaders.

(a) Find the distribution of $X$.

(b) For this part only, assume that $p_1 = p_2$. Find the conditional distribution of $X_1$
given that $X_1 + X_2 = t$.

Answer:

(a)

The event that a typo is caught by at least one of the two proofreaders is complement to the event the it is not caught by either of them. Let $X_n$ be the number typos that is not been caught by either of the proofreaders.
$$
X_n \sim \operatorname{Bin}(n, q_1 q_2)
$$

And $X = n - X_n$, therefore
$$
\begin{aligned}
P(X = k) 
&= P(n-X_n = k) \\
&= P(X_n = n-k) \\
&= \binom{n}{n-k} (q_1 q_2)^{n-k} (1-q_1 q_2)^k \qquad \text{for $k=0,1,2,\ldots,n$.}
\end{aligned}
$$

And $P(X=k) = 0$ otherwise.

(b)

for $k = 0,1,\ldots,t$, we have
$$
\begin{aligned}
P(X_1 = k \mid X_1 + X_2 = t)
&= \frac{P(X_1 = k, X_1 + X_2 = t)}{P(X_1 + X_2 = t)} \\
&= \frac{P(X_1 = k, X_2 = t-k)}{P(X_1 + X_2 = t)} \\
&= \frac{P(X_1 = k) P(X_2 = t-k)}{P(X_1 + X_2 = t)} \qquad \text{Independent check}\\
\end{aligned}
$$

Suppose $p = p_1 = p_2$ and $q=q_1=q_2$, because probability is the same for them to find a typos, $X_1 + X_2 = t$ can be taken as one find $t$ typos in among the $2n$ typos.

Therefore
for $k = 0,1,\ldots,t$, we have
$$
\begin{aligned}
P(X_1 = k \mid X_1 + X_2 = t)
&= \frac{P(X_1 = k) P(X_2 = t-k)}{P(X_1 + X_2 = t)} \\
&= \frac{\binom{n}{k} p^k q^{n-k} \binom{n}{t-k} p^{t-k} q^{n-t+k}}{\binom{2n}{t} p^t q^{2n-t}} \\
&= \frac{\binom{n}{k} \binom{n}{t-k}}{\binom{2n}{t}}
\end{aligned}
$$

Otherwise $P(X_1 = k \mid X_1 + X_2 = t) = 0$.

Hence 
$$
X_1 = k \mid (X_1 + X_2 = t) \sim \operatorname{HGeom(n, n, t)}
$$

### Q34

There are $n$ students at a certain school, of whom $X \sim \operatorname{Bin}(n,p)$ are Statistics majors. A simple random sample of size $m$ is drawn (“simple random sample” means sampling without replacement, with all subsets of the given size equally likely).

(a) Find the PMF of the number of Statistics majors in the sample, using the law of total
probability (don’t forget to say what the support is). You can leave your answer as a
sum (though with some algebra it can be simplified, by writing the binomial coefficients
in terms of factorials and using the binomial theorem).

(b) Give a story proof derivation of the distribution of the number of Statistics majors
in the sample; simplify fully.

Hint: Does it matter whether the students declare their majors before or after the
random sample is drawn?

Answer:

(a)

* Let $M$ be Statistic majors in the sample.

By LOTP, we have
$$
\begin{aligned}
P(M=k)
&= \sum_{i=k}^n P(M=k \mid X=i) P(X=i) \\
&= \sum_{i=k}^n \frac{\binom{i}{k} \binom{n-i}{m-k}}{\binom{n}{m}} \binom{n}{i} p^i (1-p)^{n-i}
\quad \text{for $k=0,1,\ldots,m.$}
\end{aligned}
$$

(b)

The experiment can be interpreted as follows, without loss of generality. Make a simple random sample of $m$ from $n$ students. Then let all the student to choose their major. Each student has probability $p$ of choosing Statistic as their major. Find the distribution of the number of student who choose Statistic as major in the sample.

Let $M$ be Statistic majors in the sample.
$$
M \sim \operatorname{Bin}(m, p)
$$

$$
P(M=k) = \binom{m}{k} p^k (1-p)^{m-k} \quad \text{for $k=0,1,\ldots,m$.}
$$

And $P(M=k) = 0$ otherwise.

### Q35

Players A and B take turns in answering trivia questions, starting with player A
answering the first question. Each time A answers a question, she has probability $p_1$ of getting it right. Each time B plays, he has probability $p_2$ of getting it right.

(a) If A answers $m$ questions, what is the PMF of the number of questions she gets
right?

(b) If A answers $m$ times and B answers $n$ times, what is the PMF of the total number of questions they get right (you can leave your answer as a sum)? Describe exactly when/whether this is a Binomial distribution.

(c) Suppose that the first player to answer correctly wins the game (with no predetermined maximum number of questions that can be asked). Find the probability that A wins the game.

Answer:

(a)

Let $A$ be the number of questions she gets rights.

$$
p_A(k) = \binom{m}{k} p_1^k (1-p_1)^{m-k} \qquad \text{for $k=0,1,\ldots,m$.}
$$

Otherwise $p_A(k) = 0$.

(b)

* Let $A$ be the number of questions she gets rights.
* Let $B$ be the number of questions she gets rights.
* Let $X=A+B$.


$$
\begin{aligned}
P(X = k)
&= \sum_{i=0}^{k} P(A=i) P(B=k-i) \\
&= \sum_{i=0}^{k} \binom{m}{i} p_1^i (1-p_1)^{m-i} \binom{n}{k-i} p_2^{k-i} (1-p_2)^{n-k+i}
\end{aligned}
$$

This is not Binomial A and B have different probability of answering correct.

Suppose $p_1=p_2=p$ and $(1-p_1) = (1-p_2) = q$, we have
$$
\begin{aligned}
P(X = k)
&= \sum_{i=0}^{k} \binom{m}{i} p^i q^{m-i} \binom{n}{k-i} p^{k-i} q^{n-k+i} \\
&= \sum_{i=0}^{k} \binom{m}{i} \binom{n}{k-i} p^k q^{m+n-k} \qquad \text{for $k=0,1,\ldots,m+n$.}
\end{aligned}
$$
Otherwise $P(X = k) = 0$.

Because A and B have the same probability of answering correct, this can be taken as A answering $m+n$ questions. And we group the possible outcomes by the number of correct answers in the first $m$ questions. We can also have
$$
P(X=k) = \sum_{i=0}^{k} \binom{m}{i} \binom{n}{k-i} p^k q^{m+n-k}
$$

So
$$
P(X=k) = \binom{m+n}{k} p^k (1-p)^{m+n-k} \qquad \text{for $k=0,1,\ldots,m+n$.}
$$
Otherwise $P(X=k) = 0$

(c)

* Let $q_1 = (1-p_1)$, $q_2 = (1-p_2)$.
* Let $S_A$ be the event the this time A answers correct.
* Let $F_A$ and $F_B$ be the events that this time A answers incorrect and B answers incorrect respectively.
* Let $A$ be the event that A wins.

For A to win, the possible event are
$$
S_A \\
F_A F_B S_A \\
F_A F_B F_A F_B S_A \\
\ldots 
$$

Sum up the probabilities of all the possible events, we have
$$
P(A) = p_1 \sum_{i=0}^{+\infty}(q_1 q_2)^i = \frac{p_1}{1 - q_1 q_2}
$$

### Q36

There are $n$ voters in an upcoming election in a certain country, where $n$ is a large, even number. There are two candidates: Candidate A (from the Unite Party) and Candidate B (from the Untie Party). Let $X$ be the number of people who vote for Candidate A. Suppose that each voter chooses randomly whom to vote for, independently and with equal probabilities.

(a) Find an exact expression for the probability of a tie in the election (so the candidates end up with the same number of votes).

(b) Use Stirling’s approximation, which approximates the factorial function as
$$
n! \approx \sqrt{2 \pi n} (\frac{n}{e})^n
$$
to find a simple approximation to the probability of a tie. Your answer should be of the form $1/\sqrt{cn}$, with $c$ a constant (which you should specify).

Answer:

(a)

$$
P(X=\frac{n}{2}) = \binom{n}{\frac{n}{2}} (\frac{1}{2})^n
$$

(b)

$$
\begin{aligned}
P(X=\frac{n}{2}) 
&= \binom{n}{\frac{n}{2}} (\frac{1}{2})^n \\
&=\frac{n!}{(\frac{n}{2})! (\frac{n}{2})!} (\frac{1}{2})^n \\
&\approx \frac{\sqrt{2 \pi n} (\frac{n}{e})^n}{\sqrt{\pi n} (\frac{n}{2e})^{\frac{n}{2}} \sqrt{\pi n} (\frac{n}{2e})^{\frac{n}{2}}} (\frac{1}{2})^n \\
&= \frac{\sqrt{2 \pi n} (\frac{n}{e})^n}{\pi n (\frac{n}{2 e})^n} (\frac{1}{2})^n \\
&= \frac{\sqrt{2 \pi n} 2^n}{\pi n} (\frac{1}{2})^n \\
&= \frac{1}{\sqrt{c n}} \qquad \text{where $c = \frac{\pi}{2}$}
\end{aligned}
$$

### Q37

A message is sent over a noisy channel. The message is a sequence $x_1,x_2,\ldots,x_n$ of $n$ bits ($x_i \in \{0,1\}$). Since the channel is noisy, there is a chance that any bit might be corrupted, resulting in an error (a 0 becomes a 1 or vice versa). Assume that the error events are independent. Let $p$ be the probability that an individual bit has an error
$(0 \lt p \lt 1/2)$. Let $y_1,y_2,\ldots,y_n$ be the received message (so $y_i = x_i$ if there is no error in that bit, but $y_i = 1−x_i$ if there is an error there).

To help detect errors, the $n$-th bit is reserved for a parity check: $x_n$ is defined to be $0$ if $x_1 + x_2 + \ldots + x_{n−1}$ is even, and $1$ if $x_1 + x_2 + \ldots + x_{n−1}$ is odd. When the message is received, the recipient checks whether $y_n$ has the same parity as $y_1 + y_2 + \ldots + y_{n−1}$. If the parity is wrong, the recipient knows that at least one error occurred; otherwise, the
recipient assumes that there were no errors.

(a) For $n = 5$, $p = 0.1$, what is the probability that the received message has errors which go undetected?

(b) For general $n$ and $p$, write down an expression (as a sum) for the probability that the received message has errors which go undetected.

(c) Give a simplified expression, not involving a sum of a large number of terms, for the probability that the received message has errors which go undetected.

Hint for (c): Letting
$$
a = \sum_{\text{$k$ even, $k \ge 0$}} \binom{n}{k} p^k (1-p)^{n-k} \\

b = \sum_{\text{$k$ odd, $k \ge 1$}} \binom{n}{k} p^k (1-p)^{n-k}
$$

the binomial theorem makes it possible to find simple expressions for $a+b$ and $a−b$, which then makes it possible to obtain $a$ and $b$.

Answer:

(a)

For the received message has errors which go undetected, it must meet only one of the following cases:

1. The no error happen on the parity bit. Other bits have even number of errors.
2. The error happen on the parity bit. Other bits have odd number of errors.

* Let $U$ be the event that the errors go undetected.
* Let $G$ be the event that the parity bit has no error.
* Let $X$ be the number of errors in non parity bit.

For $n=5$, $p=0.1$, and conditioned on whether there is an error on the parity bit, we have

$$
\begin{aligned}
P(X = 2 \mid G) P(G)
&= (1-p) \binom{4}{2} p^2 (1-p)^{2}
&= 0.9 \cdot 6 \cdot 0.1^2 \cdot 0.9^2
&= 0.04374
\end{aligned}
$$

$$
\begin{aligned}
P(X = 4 \mid G) P(G)
&= (1-p) \binom{4}{4} p^4 (1-p)^{0}
&= 0.9 \cdot 1 \cdot 0.1^4 \cdot 0.9^0
&= 0.00009
\end{aligned}
$$

$$
\begin{aligned}
P(X = 1 \mid G^c) P(G^c)
&= p \binom{4}{1} p^1 (1-p)^{3}
&= 0.1 \cdot 4 \cdot 0.1^1 * 0.9^3
&= 0.02916
\end{aligned}
$$

$$
\begin{aligned}
P(X = 1 \mid G^c) P(G^c)
&= p \binom{4}{3} p^3 (1-p)^{1}
&= 0.1 \cdot 4 \cdot 0.1^3 * 0.9^1
&= 0.00036
\end{aligned}
$$

Therefore
$$
P(U) = 0.04374 + 0.00009 + 0.02916 + 0.00036 = 0.07335
$$

(b)
$$
P(U) = \sum_{\text{$k$ even, $k \ge 2$}} \binom{n}{k} p^k (1-p)^{n-k}
$$

(c)
Let $q = 1-p$

And let
$$
a = \sum_{\text{$k$ even, $k \ge 0$}} \binom{n}{k} p^k q^{n-k} \\

b = \sum_{\text{$k$ odd, $k \ge 1$}} \binom{n}{k} p^k q^{n-k}
$$

We know that
$$
a + b = \sum_{k \ge 0}^n \binom{n}{k} p^k q^{n-k} = 1
$$

Because
$$
\begin{aligned}
(p - q)^n 
&= \sum_{k=0}^n \binom{n}{k} (-p)^k q^{n-k} \\
&= \sum_{\text{$k$ is even, $k \ge 0$}}^n \binom{n}{k} p^k q^{n-k} - \sum_{\text{$k$ is odd, $k \ge 1$}}^n \binom{n}{k} p^k q^{n-k} \\
&= a - b
\end{aligned}
$$

So we have
$$
\begin{cases}
a + b = 1 \\
a - b = (p - q)^n
\end{cases}
$$
So
$$
a = \frac{1 + (p-q)^n}{2}
$$

So
$$
\begin{aligned}
P(U)
&= a - \binom{n}{0}p^0 q^n \\
&= a - q^n \\
&= \frac{1 + (p - q)^n - 2q^n}{2}
\end{aligned}
$$

## Independence of r.v.s

### Q38

(a) Give an example of dependent r.v.s $X$ and $Y$ such that $P(X \lt Y) = 1$.

(b) Give an example of independent r.v.s $X$ and $Y$ such that $P(X \lt Y) = 1$.

Answer:

Skip.

### Q39

Give an example of two discrete random variables $X$ and $Y$ on the same sample space such that $X$ and $Y$ have the same distribution, with support $\{1,2,\ldots,10\}$, but the event $X=Y$ never occurs. If $X$ and $Y$ are independent, is it still possible to construct such an example?

Answer:

Arrange $1,2,\ldots,10$ in a circle, randomly pick up value and take the one on immediately to its right. Let $X$ be the randomly picked up value, $Y$ be the one on it's right. $X$ and $Y$ have the same distribution, but the event $X=Y$ never occurs.

If they are independent
$$
P(X = k, Y=k) = P(X=k)P(Y=k) \gt 0
$$
So if they are independent it's impossible.

### Q40

Suppose $X$ and $Y$ are discrete r.v.s such that $P(X=Y) = 1$. This means that X and Y always take on the same value.

(a) Do X and Y have the same PMF?

(b) Is it possible for X and Y to be independent?

Answer:

(a)

From $P(X = Y) = 1$ we have $P(X \ne Y) = 0$.

$$
\begin{aligned}
P(X = k)
&= P(\{X = k\} \cap \{X=Y\}) + P(\{X = k\} \cap \{X \ne Y\}) \\
&= P(\{X = k\} \cap \{X=Y\}) \qquad \text{because $ P(X \ne Y) = 0$} \\
&= P(\{Y = k\} \cap \{X=Y\}) \qquad \text{bacause $X = Y$}\\
&= P(Y=k)
\end{aligned}
$$

Thus,
$$
P(X = k) = P(Y = k) \qquad \text{for every $k$.}
$$

Therefore $X$ and $Y$ have the same PMF.

(b)

From (a) we have
$$
P(X=k) = P(Y=k) = P(X=k, Y=k) = p_k
$$

If $X$ and $Y$ are independent, we have
$$
P(X=k, Y=k) = P(X=k)P(Y=k) = p_k^2 = p_k
$$

So we have $p_k = 0$ or $p_k = 1$. But because we must also have 
$$
\sum_k P(X=k) = \sum_k p_k = 1
$$

That means $p_k = 1$ and there is exact one possible $k$. That means $X$ and $Y$ both equals to the same constant value. Only this case fulfill the requirement. 

### Q41

If $X$,$Y$,$Z$ are r.v.s such that $X$ and $Y$ are independent and $Y$ and $Z$ are independent, does it follow that X and Z are independent?

Hint: Think about simple and extreme examples.

Answer:

Let $X=Z$ and $Y$ has exactly one constant value $c_0$.

In this case $X$ and $Y$ are independent. $Z$ and $Y$ are independent. But $X$ and $Z$ are not independent.

### Q42

Let $X$ be a random day of the week, coded so that Monday is $1$, Tuesday is $2$, etc. (so $X$ takes values $1,2,\ldots,7$, with equal probabilities). Let $Y$ be the next day after $X$ (again represented as an integer between $1$ and $7$). Do $X$ and $Y$ have the same distribution? What is $P(X \lt Y)$?

Answer:

Yes they have the same distribution $\operatorname{DUnif}(7)$.

$$
P(X \lt Y) = \frac{6}{7}
$$

### Q43

(a) Is it possible to have two r.v.s $X$ and $Y$ such that $X$ and $Y$ have the same distribution
but $P(X \lt Y) \ge p$, where:

* $p= 0.9$?
* $p= 0.99$?
* $p= 0.9999999999999$?
* $p= 1$?

For each, give an example showing it is possible, or prove it is impossible.
Hint: Do the previous question first.

(b) Consider the same question as in Part (a), but now assume that $X$ and $Y$ are
independent. Do your answers change?

Answer:

(a)

Arrange $1,2,\ldots,n$ in to a cycle. Let $X$ be the number of a randomly picked up value in the cycle. Let $Y$ be the number immediately to the right of $X$.

In this example, $X$ and $Y$ have the same distribution $\operatorname{DUnif}(n)$. And
$$
P(X \lt Y) = \frac{n-1}{n} \ge p
$$

so $p$ can be any value in the range of $(0,1)$.

But if $p = 1$, $X \lt Y$ in any cases, that means there exists a support of $Y$ that is not the support of $X$. So $X$ and $Y$ can't have the same distribution.

(b)

If $X$ and $Y$ are independent and have the same distribution, we can swap the their name and does not change their joint distribution. Therefore we have
$$
P(X \lt Y) + P(Y \lt X) + P(X=Y) = 1 \\
P(X \lt Y) = P(Y \lt X)
$$

Therefore the maximum value of $P(X \lt Y)$ is $0.5$.

### Q44

For $x$ and $y$ binary digits ($0$ or $1$), let $x \oplus y$ be $0$ if $x = y$ and $1$ if $x \ne y$ (this operation is called exclusive or (often abbreviated to XOR), or _addition mod 2_).

(a) Let $X \sim \operatorname{Bern}(p)$ and $Y \sim \operatorname{Bern}(1/2)$, independently. What is the distribution of $X \oplus Y$?

(b) With notation as in (a), is $X \oplus Y$ independent of $X$? Is $X \oplus Y$ independent of $Y$? Be sure to consider both the case $p = 1/2$ and the case $p \ne 1/2$.

(c) Let $X_1,\ldots,X_n$ be i.i.d. $\operatorname{Bern}(1/2)$. For each nonempty subset $J$ of $\{1,2,\ldots,n\}$, let
$$
Y_J = \bigoplus_{j \in J} X_j
$$

where the notation means to “add” in the $\oplus$ sense all the elements of $J$; the order in which this is done doesn’t matter since $x \oplus y= y \oplus x$ and $(x \oplus y) \oplus z = x \oplus (y \oplus z)$. Show that $Y_J \sim \operatorname{Bern}(1/2)$ and that these $2^n−1$ r.v.s are pairwise independent, but not independent. For example, we can use this to simulate $1023$ pairwise independent
fair coin tosses using only $10$ independent fair coin tosses.

Hint: Apply the previous parts with $p = 1/2$. Show that if $J$ and $K$ are two different nonempty subsets of $\{1,2,\ldots,n\}$, then we can write $Y_J = A \oplus B, Y_K = A \oplus C$, where $A$ consists of the $X_i$ with $i \in J \cap K$, $B$ consists of the $X_i$ with $i \in J \cap K^c$, and $C$ consists of
the $X_i$ with $i \in J^c \cap K$. Then $A$, $B$, $C$ are independent since they are based on disjoint sets of $X_i$. Also, at most one of these sets of $X_i$ can be empty. If $J \cap K= \empty$, then $Y_J = B$, $Y_K = C$. Otherwise, compute $P(Y_J = y,Y_K = z)$ by conditioning on whether $A=1$.

(a)
For the support of $X \oplus Y$ we have
$$
\begin{aligned}
P(X \oplus Y = 1)
&= P(X=1, Y=0) + P(X=0, Y=1) \\
&= P(X=1)P(Y=0) + P(X=0)P(Y=1) \\
&= p \cdot \frac{1}{2} + (1-p) \cdot \frac{1}{2} \\
&= \frac{1}{2}
\end{aligned}
$$

$$
\begin{aligned}
P(X \oplus Y = 0)
&= P(X=0, Y=0) + P(X=1, Y=1) \\
&= P(X=0)P(Y=0) + P(X=1)P(Y=1) \\
&= (1-p) \cdot \frac{1}{2} + p \cdot \frac{1}{2} \\
&= \frac{1}{2}
\end{aligned}
$$

(b)

Because
$$
P(X \oplus Y = 0, X=0) = P(X \oplus Y = 0 \mid X=0) P(X=0) = \frac{1}{2} (1-p) \\
P(X \oplus Y = 0) P(X=0) = \frac{1}{2} (1-p)
$$
So we have $P(X \oplus Y = 0, X=0) = P(X \oplus Y = 0) P(X=0)$

Because
$$
P(X \oplus Y = 0, X=1) = P(X \oplus Y = 0 \mid X=1) P(X=1) = \frac{1}{2} p \\
P(X \oplus Y = 0) P(X=1) = \frac{1}{2} p
$$
So we have $P(X \oplus Y = 0, X=1) = P(X \oplus Y = 0) P(X=1)$

Because
$$
P(X \oplus Y = 1, X=0) = P(X \oplus Y = 1 \mid X=0) P(X=0) = \frac{1}{2} (1-p) \\
P(X \oplus Y = 1) P(X=0) = \frac{1}{2} (1-p)
$$
So we have $P(X \oplus Y = 1, X=0) = P(X \oplus Y = 1) P(X=0)$

Because
$$
P(X \oplus Y = 1, X=1) = P(X \oplus Y = 1 \mid X=1) P(X=1) = \frac{1}{2} p \\
P(X \oplus Y = 1) P(X=1) = \frac{1}{2} p
$$
So we have $P(X \oplus Y = 1, X=1) = P(X \oplus Y = 1) P(X=1)$

Therefore $X \oplus Y$ and $X$ are independent.

Because
$$
P(X \oplus Y = 0, Y=0) = P(X \oplus Y = 0 \mid Y=0) P(Y=0) = (1-p) \frac{1}{2} \\
P(X \oplus Y = 0) P(Y=0) = \frac{1}{2} \frac{1}{2}
$$
So we have $P(X \oplus Y = 0, Y=0) = P(X \oplus Y = 0) P(Y=0)$ only when $p=1/2$.

Because
$$
P(X \oplus Y = 0, Y=1) = P(X \oplus Y = 0 \mid Y=1) P(Y=1) = p \frac{1}{2} \\
P(X \oplus Y = 0) P(Y=1) = \frac{1}{2} \frac{1}{2}
$$
So we have $P(X \oplus Y = 0, Y=1) = P(X \oplus Y = 0) P(Y=1)$ only when $p=1/2$.

Because
$$
P(X \oplus Y = 1, Y=0) = P(X \oplus Y = 1 \mid Y=0) P(Y=0) = p \frac{1}{2} \\
P(X \oplus Y = 1) P(Y=0) = \frac{1}{2} \frac{1}{2}
$$
So we have $P(X \oplus Y = 1, Y=0) = P(X \oplus Y = 1) P(Y=0)$ only when $p=1/2$.

Because
$$
P(X \oplus Y = 1, Y=1) = P(X \oplus Y = 1 \mid Y=1) P(Y=1) = (1-p) \frac{1}{2} \\
P(X \oplus Y = 1) P(Y=1) = \frac{1}{2} \frac{1}{2}
$$
So we have $P(X \oplus Y = 1, Y=1) = P(X \oplus Y = 1) P(Y=1)$ only when $p=1/2$.

Therefore $X \oplus Y$ and $Y$ are independent only when $p=\frac{1}{2}$.

(c)

Suppose $X = \sum_j X_j$
$$
Y_J = \bigoplus_{j \in J} X_j = 
\begin{cases}
1 & \text{when $X$ is odd,} \\
0 & \text{when $X$ is even.}
\end{cases}
$$

Because each possible $X$ are equally likely, we have $Y_J \sim \operatorname{Bern}(1/2)$.

Consider $X_1$, $X_2$ and $X_3$. From (b) we know that $\{X_1 \oplus X_2\}$ and $\{X_1 \oplus X_3\}$ are independent. But knowing the value of $X_1 \oplus X_2$ and $X_1 \oplus X_3$ determines the value of $X_2 \oplus X_3$.

Note: The answer to part (c) is not good.
