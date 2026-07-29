# Conditioning on evidence

**Q1**

A spam filter is designed by looking at commonly occurring phrases in spam. Suppose that 80% of email is spam. In 10% of the spam emails, the phrase "free money" is used, whereas this phrase is only used in 1% of non-spam emails. A new email has just arrived, which does mention "free money". What is the probability that it is spam?

Solution:

* Let $S$ be the event that the email is spam.
* Let $F$ be the event that the email contains the phrase "free money".

By the definition of conditional probability and the law of total probability, we have
$$
\begin{aligned}
P(S | F) 
&= \frac{P(S \cap F)}{P(F)}
&& \text{(definition of conditional probability)} \\
&= \frac{P(S \cap F)}{P(F | S)P(S) + P(F | S^c)P(S^c)}
&& \text{(LOTP)} \\
&= \frac{0.8 \cdot 0.1}{0.1 \cdot 0.8 + 0.01 \cdot (1-0.8)} \\
&\approx  0.976
\end{aligned}
$$

**Q2**

A woman is pregnant with twin boys. Twins may be either identical or fraternal.
Suppose that 1/3 of twins born are identical, that identical twins have a 50% chance of being both boys and a 50% chance of being both girls, and that for fraternal twins each twin independently has a 50% chance of being a boy and a 50% chance of being a girl. Given the above information, what is the probability that the woman’s twins are identical?

Solution:

* Let $I$ be the event that the woman's twins are identical, and we have $P(I) = \frac{1}{3}$ and $P(I^c) = \frac{2}{3}$.
* Let $B_1$ be the event that the first child is a boy.
* Let $B_2$ be the event that the second child is a boy.

We have
$$
\begin{aligned}
P(I | B_1 \cap B_2) &= \frac{P(I \cap B_1 \cap B_2 )}{P(B_1, B_2)} \\
&= \frac{P(I \cap B_1 \cap B_2 )}{P(B_1, B_2 | I) P(I) + P(B_1, B_2 | I^c) P(I^c)}
&& \text{(LOTP)} \\
&= \frac{0.5 \cdot \frac{1}{3}}{0.5 \cdot \frac{1}{3} + 0.5 \cdot 0.5 \cdot \frac{2}{3}} \\
&=0.5
\end{aligned}
$$

**Q3**

According to the CDC (Centers for Disease Control and Prevention), men who smoke are 23 times more likely to develop lung cancer than men who don’t smoke. Also according to the CDC, 21.6% of men in the U.S. smoke. What is the probability that a man in the U.S. is a smoker, given that he develops lung cancer?

Solution:

* Let $S$ be the event that a randomly selected man is a smoker. Then $P(S) = 0.216$.
* Let $C$ be the event that a man develops lung cancer.
* Let $x=P(C \mid S^c)$, we have $P(C \mid S) = 23x$

By the definition of conditional probability we have
$$
\begin{aligned}
P(S \mid C) &= \frac{P(S \cap C)}{P(C)} \\

&= \frac{P(C \mid S) P(S)}{P(C)} 
&& \text{(multiplication rule)} \\

&= \frac{P(C \mid S) P(S)}{P(C \mid S)P(S) + P(C \mid S^c)P(S^c)}
&& \text{(LOTP)} \\

&= \frac{23x \cdot P(S)}{23x \cdot P(S) + x \cdot P(S^c)} \\
&= \frac{23 \cdot P(S)}{23 \cdot P(S) + P(S^c)} \\
&= \frac{23 \cdot 0.216}{23 \cdot 0.216 + 1 - 0.216} \\
&\approx 0.86
\end{aligned}
$$

**Q4**

Fred is answering a multiple-choice problem on an exam, and has to choose one of $n$ options (exactly one of which is correct). Let $K$ be the event that he knows the answer, and $R$ be the event that he gets the problem right (either through knowledge or through luck). Suppose that if he knows the right answer he will definitely get the problem right, but if he does not know then he will guess completely randomly. Let $P(K) = p$.

(a) Find $P(K \mid R)$ (in terms of $p$ and $n$).

(b) Show that $P(K \mid R) \ge p$, and explain why this makes sense intuitively. When (if ever) does $P(K \mid R)$ equal $p$?

Solution:

(a)

Fred randomly choose the option when he doesn't know, so we have $P(R \mid K^c) = \frac{1}{n}$.

By multiplication rule and LOTP, we have
$$
\begin{aligned}
P(K \mid R) &= \frac{P(R \mid K) P(K)}{P(R \mid K) P(K) + P(R \mid K^c) P(K^c)} \\
&= \frac{1 \cdot p}{1 \cdot p + \frac{1}{n}(1 - p)} \\
&= \frac{p}{p + \frac{1}{n}(1-p)} \\
&= \frac{np}{np - p  + 1}
\end{aligned}
$$

(b)

To prove
$$
P(K \mid R) = \frac{np}{np - p  + 1} \ge p
$$
Since $np-p+1 = (n-1)p + 1 > 0$, we can instead to prove that
$$
np \ge p(np - p + 1) \\
$$
If $p \ne 0$, we need to prove
$$
n \ge np - p + 1 \\
np - p + 1 - n \le 0 \\
(n-1) p  - (n-1) \le 0 \\
(n-1)(p - 1) \le 0
$$
If $n = 1, 0 \lt p \lt 1$,  we have $(n-1)(p - 1) = 0$, otherwise, because $p-1$ is negative, we have $(n-1)(p - 1) \lt 0$. 

If $p=0$, $P(K \mid R) = 0 = p$.

If $p=1$, $P(K \mid R) = 1 = p$.

Therefore, we have proved that, for $0 \le p \le 1$, we have
$$
P(K \mid R) = \frac{np}{np - p  + 1} \ge p
$$



In the following cases we have $P(K \mid R) = p$:
1. $n=1$ and $0 \lt p \lt 1$
2. $p=0$ or $p=1$

This makes intuitive sense because learning that Fred answered the question correctly makes it more likely that he knew the answer, compared with our prior belief $p$.

**Q5**

Three cards are dealt from a standard, well-shuffled deck. The first two cards are flipped over, revealing the Ace of Spades as the first card and the 8 of Clubs as the second card. Given this information, find the probability that the third card is an ace in two ways: using the definition of conditional probability, and by symmetry.

Solution:

* Let $A_1$ be the event that the first card is the ace of spades.
* Let $A_2$ be the event that the second card is the 8 of clubs.
* Let $A_3$ be the event that the third card is an ace.

We need to find $P(A_3 \mid A_1 \cap A_2)$, by the definition of conditional probability we have
$$
\begin{aligned}
P(A_3 \mid A_1 \cap A_2) &= \frac{P(A_3 \cap A_1 \cap A_2)}{P(A_1 \cap A_2)}.
\end{aligned}
$$

To calculate $P(A_3 \cap A_1 \cap A_2)$, fix the first 2 cards and classify on the different aces on the third card, by the naive definition of probability we have
$$
P(A_3 \cap A_1 \cap A_2) = 3 \cdot \frac{49!}{52!}.
$$

Similarly we have
$$
P(A_1 \cap A_2) = \frac{50!}{52!}.
$$

Therefore
$$
\begin{aligned}
P(A_3 \mid A_1 \cap A_2) &= \frac{P(A_3 \cap A_1 \cap A_2)}{P(A_1 \cap A_2)} \\
&= \frac{3 \cdot \frac{49!}{52!}}{\frac{50!}{52!}} \\
&= \frac{3}{50}
\end{aligned}
$$

It can also be interpreted like this. There are 50 cards remaining, and each is equally likely to be the third card. Since 3 of those 50 cards are aces, the probability that the third card is an ace is $\frac{3}{50}$.
 
**Q6**

A hat contains 100 coins, where 99 are fair but one is double-headed (always landing Heads). A coin is chosen uniformly at random. The chosen coin is flipped 7 times, and it lands Heads all 7 times. Given this information, what is the probability that the chosen coin is double-headed? (Of course, another approach here would be to look at both sides of the coin -- but this is a metaphorical coin.)

Solution:

* Let $D$ be the event that the chosen coin is double-headed.
* Let $E$ be the event that the chosen coin lands heads all 7 times.

By Bayes' rule and LOTP we have
$$
\begin{aligned}
P(D \mid E) &= \frac{P(E \mid D) P(D)}{P(E)}
&= \frac{P(E \mid D) P(D)}{P(E | D)P(D) + P(E | D^c) P(D^c)} \\
&= \frac{1 \cdot 0.01}{1 \cdot 0.01 + 0.5^7 \cdot 0.99} \\
&\approx 0.564
\end{aligned}
$$

**Q7**

A hat contains 100 coins, where at least 99 are fair, but there may be one that is double-headed (always landing Heads); if there is no such coin, then all 100 are fair. Let $D$ be the event that there is such a coin, and suppose that P(D) = 1/2. A coin is chosen
uniformly at random. The chosen coin is flipped 7 times, and it lands Heads all 7 times.

(a) Given this information, what is the probability that one of the coins is double-headed?

(b) Given this information, what is the probability that the chosen coin is double-headed?

Solution:

(a)

Let $E$ be the event that the chosen coin lands heads all 7 times.
By Bayes' rule, we have
$$
P(D \mid E) = \frac{P(E \mid D)P(D)}{P(E)}
$$

By LOTP, we have
$$
P(E) = P(D)P(E \mid D) + P(D^c)P(E \mid D^c) 
$$

Therefore
$$
\begin{aligned}
P(D \mid E) &= \frac{P(E \mid D)P(D)}{P(D)P(E \mid D) + P(D^c)P(E \mid D^c) } \\
&= \frac{(1 \cdot 0.01 + 0.5^7 \cdot 0.99) \cdot 0.5}{(1 \cdot 0.01 + 0.5^7 \cdot 0.99) \cdot 0.5 + 0.5^7 \cdot 0.5} \\
&\approx 0.694
\end{aligned}
$$

(b) 

* Let $B$ be the event that the chosen coin is double-headed. 
* Let $E$ be the event that the chosen coin lands heads all 7 times.

By Bayes' rule we have
$$
\begin{aligned}
P(B \mid E) = \frac{P(E \mid B) P(B)}{P(E)} 
\end{aligned}
$$

$P(B)$ depends on if the double-headed coin exist, so we have
$$
\begin{aligned}
P(B) &= P(B \mid D) P(D) + P(B \mid D^c) P(D^c) \\
&= 0.01 \cdot 0.5 + 0 \cdot 0.5 \\
&= 0.005
\end{aligned}
$$

$P(E)$ also depends on if the double-head coin exist, so we have
$$
\begin{aligned}
P(E) &= P(D)P(E \mid D) + P(D^c)P(E \mid D^c) \\
&= (1 \cdot 0.01 + 0.5^7 \cdot 0.99) \cdot 0.5 + 0.5^7 \cdot 0.5 \\
&\approx 0.0128
\end{aligned}
$$

Therefore
$$
\begin{aligned}
P(B \mid E) &= \frac{P(E \mid B) P(B)}{P(E)} \\
&= \frac{1 \cdot 0.005}{0.0128} \\
&\approx 0.391
\end{aligned}
$$

**Q8**

The screens used for a certain type of cell phone are manufactured by 3 companies, A, B, and C. The proportions of screens supplied by A, B, and C are 0.5, 0.3, and 0.2, respectively, and their screens are defective with probabilities 0.01, 0.02, and 0.03, respectively. Given that the screen on such a phone is defective, what is the probability that Company A manufactured it?

Solution:

Let $M_A, M_B, M_C$ be the event that the screen of such a phone is manufactured by company A, B and C, respectively.

Let $D$ be the event that the screen on such a phone is defective.

By Bayes' rule we have
$$
P(M_A \mid D) = \frac{P(D \mid M_A) P(M_A)}{P(D)}
$$

By LOTP we have
$$
\begin{aligned}
P(D) &= P(D \mid M_A)P(M_A) + P(D \mid M_B)P(M_B) + P(D \mid M_C)P(M_C) \\
&= 0.5 \cdot 0.01 + 0.3 \cdot 0.02 + 0.2 \cdot 0.03 \\
&= 0.017
\end{aligned}
$$

Therefore we have
$$
\begin{aligned}
P(M_A \mid D) &= \frac{P(D \mid M_A) P(M_A)}{P(D)} \\
&= \frac{0.005}{0.017} \\
&\approx 0.294
\end{aligned}
$$

**Q9**

(a) Show that if events $A_1$ and $A_2$ have the same prior probability $P(A_1) = P(A_2)$, $A_1$ implies $B$, and $A_2$ implies $B$, then $A_1$ and $A_2$ have the same posterior probability
$P(A_1 \mid B) = P(A_2 \mid B)$ if it is observed that $B$ occurred.

(b) Explain why (a) makes sense intuitively, and give a concrete example.

Solution:

(a)
By Bayes' rule, we have
$$
P(A_1 \mid B) = \frac{P(A_1)P(B \mid A_1)}{P(B)} \\
P(A_2 \mid B) = \frac{P(A_2)P(B \mid A_2)}{P(B)}
$$

If $P(A_1) = P(A_2)$ and $P(B \mid A_1) = 1, P(B \mid A_2) = 1$, we can see that $P(A_1 \mid B) = P(A_2 \mid B)$.

(b)

Conditioning on $B$ removes possibilities outside of $B$, on the other hand, but $A_1$ and $A_2$ are inside $B$ and are equally likely. So nothing changed in $A_1$ and $A_2$.

**Q10**

Fred is working on a major project. In planning the project, two milestones are set up,
with dates by which they should be accomplished. This serves as a way to track Fred’s
progress. Let $A_1$ be the event that Fred completes the first milestone on time, $A_2$ be
the event that he completes the second milestone on time, and $A_3$ be the event that he
completes the project on time.

Suppose that $P(A_j+1|A_j) = 0.8$ but $P(A_j+1|A_j^c) = 0.3$ for $j = 1,2$, since if Fred falls
behind on his schedule it will be hard for him to get caught up. Also, assume that the second milestone supersedes the first, in the sense that once we know whether he is on time in completing the second milestone, it no longer matters what happened with the first milestone. We can express this by saying that $A_1$ and $A_3$ are conditionally independent given $A_2$ and they’re also conditionally independent given $A_2^c$.

(a) Find the probability that Fred will finish the project on time, given that he completes
the first milestone on time. Also find the probability that Fred will finish the project on
time, given that he is late for the first milestone.

(b) Suppose that $P(A_1) = 0.75$. Find the probability that Fred will finish the project
on time.

Solution:

(a)

Suppose that Fred completed the first milestone on time. Then we have
$$
P(A_2 \mid A_1) = 0.8, \qquad P(A_2^c \mid A_1) = 0.2 \tag{1}
$$

By the conditional LOTP, we have
$$
P(A_3 \mid A_1) = P(A_3 \mid A_2, A_1) P(A_2 \mid A_1) + P(A_3 \mid A_2^c, A_1) P(A_2^c \mid A_1) \tag{2}
$$

Because the second milestone supersedes the first, we have
$$
P(A_3 \mid A_2, A_1) = P(A_3 \mid A_2) = 0.8, \qquad P(A_3 \mid A_2^c, A_1) = P(A_3 \mid A_2^c) = 0.3 \tag{3}
$$

Substituting (3) and (1) into (2), we obtain
$$
P(A_3 \mid A_1) = 0.8 \cdot 0.8 + 0.3 \cdot 0.2 = 0.7
$$

Suppose that Fred is late for the first milestone. Then we have
$$
P(A_2 \mid A_1^c) = 0.3, \qquad P(A_2^c \mid A_1^c) = 0.7 \tag{4}
$$

By the conditional LOTP, we have
$$
P(A_3 \mid A_1^c) = P(A_3 \mid A_2, A_1^c) P(A_2 \mid A_1^c) + P(A_3 \mid A_2^c, A_1^c) P(A_2^c \mid A_1^c) \tag{5}
$$

Also, because the second milestone supersedes the first, we have
$$
P(A_3 \mid A_2, A_1^c) = P(A_3 \mid A_2) = 0.8, \qquad P(A_3 \mid A_2^c, A_1^c) = P(A_3 \mid A_2^c) = 0.3 \tag{6}
$$

Substituting (6) and (4) into (5), we obtain
$$
P(A_3 \mid A_1^c) = 0.8 \cdot 0.3 + 0.3 \cdot 0.7 = 0.45
$$

(b)

By the law of total probability, we have
$$
\begin{aligned}
P(A_2) &= P(A_2 \mid A_1) P(A_1) + P(A_2 \mid A_1^c) P(A_1^c) \\
&= 0.8 \cdot 0.75 + 0.3 \cdot 0.25 \\
&= 0.675
\end{aligned}
$$

$$
\begin{aligned}
P(A_3) &= P(A_3 \mid A_2) P(A_2) + P(A_3 \mid A_2^c) P(A_2^c) \\
&= 0.8 \cdot 0.675 + 0.3 \cdot 0.325 \\
&= 0.6375
\end{aligned}
$$

**Q11**

An _exit poll_ in an election is a survey taken of voters just after they have voted. One
major use of exit polls has been so that news organizations can try to figure out as
soon as possible who won the election, before the votes are officially counted. This has
been notoriously inaccurate in various elections, sometimes because of selection bias:
the sample of people who are invited to and agree to participate in the survey may not
be similar enough to the overall population of voters.

Consider an election with two candidates, Candidate A and Candidate B. Every voter is invited to participate in an exit poll, where they are asked whom they voted for; some accept and some refuse. For a randomly selected voter, let $A$ be the event that they voted for A, and $W$ be the event that they are willing to participate in the exit poll. Suppose that $P(W \mid A) = 0.7$ but $P(W \mid A^c) = 0.3$. In the exit poll, 60% of the respondents say they voted for $A$ (assume that they are all honest), suggesting a comfortable victory for A. Find $P(A)$, the true proportion of people who voted for A.

Solution:

By the odds form of Bayes' rule, we have
$$
\frac{P(A \mid W)}{P(A^c \mid W)} = \frac{P(W \mid A)}{P(W \mid A^c)} \frac{P(A)}{P(A^c)}
$$
We know that
$$
\frac{P(A \mid W)}{P(A^c \mid W)} = \frac{0.6}{0.4} 
$$
and
$$
\frac{P(W \mid A)}{P(W \mid A^c)} = \frac{0.7}{0.3}
$$

So we have
$$
\operatorname{odds}(A) = \frac{P(A)}{P(A^c)} = \frac{0.6}{0.4} \cdot \frac{0.3}{0.7} \approx 0.643
$$

$$
P(A) = \operatorname{odds}(A) / (1 + \operatorname{odds}(A)) \approx 0.391
$$

