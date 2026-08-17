# Conditional Probability

## Conditioning on evidence

### Q1

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

### Q2

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

### Q3

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

### Q4

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

### Q5

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

### Q6

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

### Q7

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

### Q8

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

### Q9

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

### Q10

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

### Q11

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

### Q12

Alice is trying to communicate with Bob, by sending a message (encoded in binary) across a channel.

(a) Suppose for this part that she sends only one bit (a 0 or 1), with equal probabilities. If she sends a 0, there is a 5% chance of an error occurring, resulting in Bob receiving a 1; if she sends a 1, there is a 10% chance of an error occurring, resulting in Bob receiving a 0. Given that Bob receives a 1, what is the probability that Alice actually sent a 1?

(b) To reduce the chance of miscommunication, Alice and Bob decide to use a repetition code. Again Alice wants to convey a 0 or a 1, but this time she repeats it two more times, so that she sends 000 to convey 0 and 111 to convey 1. Bob will decode the message by going with what the majority of the bits were. Assume that the error probabilities are as in (a), with error events for different bits independent of each other. Given that Bob receives 110, what is the probability that Alice intended to convey a 1?

Solution:

(a)

* Let $R_1$ be the event that Bob receives a 1.
* Let $S_1$ be the event that Alice sends a 1.

$$
\begin{aligned}
P(S_1 | R_1) &= \frac{P(R_1 \mid S_1) P(S_1)}{P(R_1)} \\
&= \frac{P(R_1 \mid S_1) P(S_1)}{P(R_1 \mid S_1) P(S_1) + P(R_1 \mid S_1^c) P(S_1^c)} \\
&= \frac{0.9 \cdot 0.5}{0.9 \cdot 0.5 + 0.05 \cdot 0.5} \\
&\approx 0.947
\end{aligned}
$$

(b)

* Let $A_1$, $B_1$ and $C_1$ be the event that Bob receives a 1 for the first bit, second bit and third bit, respectively.
* Let $S_1$ be the event that Alice convey a 1.

$$
\begin{aligned}
P(S_1 \mid A_1, B_1, C_1^c) &= \frac{P(A_1, B_1, C_1^c \mid S_1) P(S_1)}{P(A_1, B_1, C_1^c)} \\
&= \frac{P(A_1, B_1, C_1^c \mid S_1) P(S_1)}{P(A_1, B_1, C_1^c \mid S_1) P(S_1) + P(A_1, B_1, C_1^c \mid S_1^c) P(S_1^c)} \\
&= \frac{(0.9 \cdot 0.9 \cdot 0.1) \cdot 0.5}{(0.9 \cdot 0.9 \cdot 0.1) \cdot 0.5 + (0.05 \cdot 0.05 \cdot 0.95) \cdot 0.5} \\
&\approx 0.972
\end{aligned}
$$

### Q13

Company A has just developed a diagnostic test for a certain disease. The disease afflict 1% of the population. As defined in Example 2.3.9, the sensitivity of the test is the probability of someone testing positive, given that they have the disease, and the specificity of the test is the probability that of someone testing negative, given that they don’t have the disease. Assume that, as in Example 2.3.9, the sensitivity and specificity are both 0.95.

Company B, which is a rival of Company A, offers a competing test for the disease. Company B claims that their test is faster and less expensive to perform than Company A’s test, is less painful (Company A’s test requires an incision), and yet has a higher overall success rate, where overall success rate is defined as the probability that a random
person gets diagnosed correctly.

(a) It turns out that Company B’s test can be described and performed very simply: no matter who the patient is, diagnose that they do not have the disease. Check whether Company B’s claim about overall success rates is true.

(b) Explain why Company A’s test may still be useful.

(c) Company A wants to develop a new test such that the overall success rate is higher than that of Company B’s test. If the sensitivity and specificity are equal, how high does the sensitivity have to be to achieve their goal? If (amazingly) they can get the sensitivity equal to 1, how high does the specificity have to be to achieve their goal? If (amazingly) they can get the specificity equal to 1, how high does the sensitivity have to be to achieve their goal?

Solution:

(a)

Let $B$ be the event that the test done by company B is successful. Let $A$ be the event that the test done by company A is successful. Let $D$ be the event that a random person has the disease.

Because Company B's test always diagnose the patient has no disease, we have
$$
\begin{aligned}
P(B) &= P(D) P(B \mid D) + P(D^c)P(B \mid D^c) \\
&= 0.01 \cdot 0 + 0.99 \cdot 1 \\
&= 0.99
\end{aligned}
$$

On the other hand, we have
$$
\begin{aligned}
P(A) &= P(D) P(A \mid D) + P(D^c)P(A \mid D^c) \\
&= 0.01 \cdot 0.95 + 0.99 \cdot 0.95 \\
&= 0.95
\end{aligned}
$$

So Company B's claim is true.

(b)

Company B's test can't identify any disease. To find out if a patient has the disease we need Company A's test, although it's not 100$ sensitive.

(c)

If Company A's new test has the same sensitivity and specificity. Suppose both value are $x$, we have
$$
\begin{aligned}
P(A) &= P(D) P(A \mid D) + P(D^c)P(A \mid D^c) \\
&= 0.01 \cdot x + 0.99 \cdot x \\
&= x
\end{aligned}
$$
So it needs to be higher than 99% so that the overall success rate is higher than Company B' test.

If Company A's new test has 100% sensitivity and $x$ specificity, we have
$$
\begin{aligned}
P(A) &= P(D) P(A \mid D) + P(D^c)P(A \mid D^c) \\
&= 0.01 \cdot 1 + 0.99 \cdot x \\
&\gt 0.99
\end{aligned}
$$
$x \approx 0.989899$ The specificity needs to be higher than approximately 98.99%.

If Company A's new test has x sensitivity and 100% specificity, we have
$$
\begin{aligned}
P(A) &= P(D) P(A \mid D) + P(D^c)P(A \mid D^c) \\
&= 0.01 \cdot x + 0.99 \cdot 1 \\
&\gt 0.99
\end{aligned}
$$
The sensitivity only needs to be higher than 0.

### Q14

Consider the following scenario, from Tversky and Kahneman [27]:

_Let $A$ be the event that before the end of next year, Peter will have installed a burglar alarm system in his home. Let $B$ denote the event that Peter’s home will be burglarized before the end of next year._

(a) Intuitively, which do you think is bigger, $P(A \mid B)$ or $P(A \mid B^c)$? Explain your intuition.

(b) Intuitively, which do you think is bigger, $P(B \mid A)$ or $P(B \mid A^c)$? Explain your intuition.

(c) Show that for any events $A$ and $B$ (with probabilities not equal to 0 or 1), the inequality $P(A \mid B) >P(A \mid B^c)$ is equivalent to $P(B \mid A) >P(B \mid A^c)$.

(d) Tversky and Kahneman report that 131 out of 162 people whom they posed (a) and (b) to said that $P(A \mid B) \gt P(A \mid B^c)$ and $P(B \mid A) \lt P(B \mid A^c)$. What is a plausible
explanation for why this was such a popular opinion despite (c) showing that it is
impossible for these inequalities both to hold?

Solution:

(a)

I think $P(A \mid B) \gt (A \mid B^c)$, because if given Peter's home burglarized it's more likely he will carry out his plan.

(b)

I think $P(B \mid A) \lt P(B \mid A^c)$, because after Peter installed the system, it's less likely his home will be burglarized after that.

(c) Out of my capability.

(d) See (a) and (b).

### Q15

Let $A$ and $B$ be events with $0 \lt P(A \cap B) \lt P(A) \lt P(B) \lt P(A \cup B) \lt 1$. You are
hoping that both $A$ and $B$ occurred. Which of the following pieces of information would you be happiest to observe: that $A$ occurred, that $B$ occurred, or that $A \cup B$ occurred?

Solution:

$$
P(A \cap B \mid A) = \frac{P(A \cap B \cap A)}{P(A)} = \frac{P(A \cap B)}{P(A)}
$$

$$
P(A \cap B \mid B) = \frac{P(A \cap B \cap B)}{P(B)} = \frac{P(A \cap B)}{P(B)}
$$

$$
P(A \cap B \mid A \cup B) = \frac{P(A \cap B \cap (A \cup B))}{P(A \cup B)} = \frac{P(A \cap B)}{P(A \cup B)}
$$

So we have $P(A \cap B \mid A) \gt P(A \cap B \mid B) \gt P(A \cap B \mid A \cup B)$. I would be happiest to observe that A occurred.

### Q16

Show that $P(A \mid B) \le P(A)$ implies $P(A \mid B^c) \ge P(A)$, and give an intuitive explanation of why this makes sense.

Solution:

Let $a = P(A)$, $b = P(B)$, $r = P(A \cap B)$. Then
$$
P(A | B) = \frac{r}{b}
$$

Also,
$$
P(A \cap B^c) = P(A) - P(A \cap B) = a - r
$$

$$
P(A \mid B^c) = \frac{P(A \cap B^c)}{P(B^c)} = \frac{a-r}{1-b}
$$

Therefore
$$
P(A \mid B) \le P(A) \iff \frac{r}{b} \le a \iff r \le ab
$$

$$
P(A \mid B^c) \ge P(A) \iff \frac{a-r}{1-b} \ge a \iff a - r \ge a - ab \iff r \le ab
$$

Therefore $P(A \mid B) \le P(A)$ implies $P(A \mid B^c) \ge P(A)$.

Note that
$$
P(A)= P(A\mid B)P(B) + P(A\mid B^c)P(B^c).
$$

$P(A)$ is a weighted average of
$$
P(A\mid B) \quad \text{and} \quad P(A\mid B^c).
$$

If knowing $B$'s occurrence makes $A$ less likely than usual, knowing $B$ did not occur must make $A$ more likely than usual so that a weighted average of $A$ won't change.

### Q17

In deterministic logic, the statement "A implies B" is equivalent to its contrapositive,
"not B implies not A". In this problem we will consider analogous statements in probability, the logic of uncertainty. Let $A$ and $B$ be events with probabilities not equal to
0 or 1.

(a) Show that if $P(B \mid A) = 1$, then $P(A^c \mid B^c) = 1$.

Hint: Apply Bayes’ rule and LOTP.

(b) Show however that the result in (a) does not hold in general if $=$ is replaced by $\approx$. In particular, find an example where $P(B \mid A)$ is very close to 1 but $P(A^c \mid B^c)$ is very close to 0.

Hint: What happens if A and B are independent?

Solution:

(a)

$$
\begin{aligned}
P(B \mid A) = 1 &\iff \frac{P(A \mid B) P(B)}{P(A)} = 1 \\
&\iff \frac{P(A \mid B) P(B)}{P(A \mid B) P(B) + P(A \mid B^c) P(B^c)} = 1 \\
&\iff P(A \mid B^c)P(B^c) = 0 \\
&\iff P(A \mid B^c) = 0 \\
&\iff P(A^c \mid B^c) = 1
\end{aligned}
$$

(b)

Now suppose we randomly choose a cell from an $n$ by $n$ grid, each cell is equally likely to be chosen. Let $A$ be the event that the chosen cell is NOT in the top row. Let $B$ be the event that the chosen cell is NOT in the first column. We have $P(A) = \frac{n-1}{n}$, $P(B) = \frac{n-1}{n}$, $P(A \cap B) = \frac{(n-1)^2}{n^2}$.

Therefore $A$ and $B$ are independent, and consequently $A^c$ and $B^c$ are also independent.

So we have
$$
P(B \mid A) = P(B) = \frac{n-1}{n} \qquad P(A^c \mid B^c) = P(A^c) = \frac{1}{n}
$$

When $n$ is large, we have $P(B \mid A) \approx 1$ and $P(A^c \mid B^c) \approx 0$.

### Q18

Show that if $P(A) = 1$, then $P(A \mid B) = 1$ for any $B$ with $P(B) \gt 0$. Intuitively, this says
that if someone dogmatically believes something with absolute certainty, then no amount
of evidence will change their mind. The principle of avoiding assigning probabilities of
0 or 1 to any event (except for mathematical certainties) was named Cromwell’s rule
by the statistician Dennis Lindley, due to Cromwell saying to the Church of Scotland,
"Think it possible you may be mistaken."

Hint: Write $P(B) = P(B \cap A) + P(B \cap A^c)$, and then show that $P(B \cap A^c) = 0$.

Solution:

We have
$$
\begin{aligned}
P(B) &= P(B \cap A) + P(B \cap A^c)
\end{aligned}
$$

Because $A^c \cap B \subseteq A^c$, We have $P(A^c \cap B) \le P(A^c) = 0$, so $P(A^c \cap B) = 0$. Therefore
$$
P(B) = P(B \cap A) + 0,
$$

and hence
$$
P(B) = P(B \cap A)
$$

and hence
$$
\begin{aligned}
P(A \mid B) = \frac{P(A \cap B)}{P(B)} = \frac{P(B)}{P(B)} = 1
\end{aligned}
$$

### Q19

Explain the following Sherlock Holmes saying in terms of conditional probability, carefully distinguishing between prior and posterior probabilities: "It is an old maxim of mine that when you have excluded the impossible, whatever remains, however improbable, must be the truth."

Solution: Skip

### Q20

The Jack of Spades (with cider), Jack of Hearts (with tarts), Queen of Spades (with a wink), and Queen of Hearts (without tarts) are taken from a deck of cards. These four cards are shuffled, and then two are dealt. Note: Literary references to cider, tarts, and winks do not need to be considered when solving this problem.

(a) Find the probability that both of these two cards are queens, given that the first card dealt is a queen.

(b) Find the probability that both are queens, given that at least one is a queen.

(c) Find the probability that both are queens, given that one is the Queen of Hearts.

Solution:

(a)

Let $Q_1$ and $Q_2$ be the event that the first card is queen and the second card is queen, respectively. So we need to figure out $P(Q_1 \cap Q_2 \mid Q_1)$.

$$
\begin{aligned}
P(Q_1 \cap Q_2 \mid Q_1) &= \frac{P(Q_1 \mid Q_1 \cap Q_2) P(Q_1 \cap Q_2)}{Q_1} \\

&= \frac{1 \cdot \frac{2}{4} \cdot \frac{1}{3}}{\frac{1}{2}} \\

&= \frac{1}{3}
\end{aligned}
$$

(b)

Let $Q_1$ and $Q_2$ be the event that the first card is queen and the second card is queen, respectively. So we need to figure out $P(Q_1 \cap Q_2 \mid Q_1 \cup Q_2)$.

Consider $P(Q_1 \cap Q_2)$ separately, we have
$$
P(Q_1 \cap Q_2) = \frac{2! \cdot 2!}{4!} = \frac{1}{6}
$$

Now, consider $P(Q_1 \cap Q_2 \mid Q_1 \cup Q_2)$, we have
$$
\begin{aligned}
P(Q_1 \cap Q_2 \mid Q_1 \cup Q_2) &= \frac{P(Q_1 \cup Q_2 | Q_1 \cap Q_2) P(Q_1 \cap Q_2)}{P(Q_1 \cup Q_2)} \\
&= \frac{P(Q_1 \cup Q_2 | Q_1 \cap Q_2) P(Q_1 \cap Q_2)}{P(Q_1) + P(Q_2) - P(Q_1 \cap Q_2)} \\
&= \frac{1 \cdot \frac{1}{6}}{\frac{1}{2} + \frac{1}{2} - \frac{1}{6}} \\
&= \frac{1}{5}
\end{aligned}
$$

(c)

Let $Q_1$ and $Q_2$ be the event that the first card is queen and the second card is queen, respectively. Let $H$ be the event that one of first two card is Queen of Hearts.

First consider the probability that one of the first two card is Queen of Hearts. Classifying on the position of the Queen of Hearts, we have
$$
P(H) = \frac{3! + 3!}{4!} = \frac{1}{2}
$$

Now, consider $P(Q_1 \cap Q_2 \mid H)$, we have
$$
\begin{aligned}
P(Q_1 \cap Q_2 \mid H) &= \frac{P(H \mid Q_1 \cap Q_2) P(Q_1 \cap Q_2)}{P(H)} \\
&= \frac{1 \cdot \frac{1}{6}}{\frac{1}{2}} \\
&= \frac{1}{3}
\end{aligned}
$$

### Q21

A fair coin is flipped 3 times. The toss results are recorded on separate slips of paper (writing "H" if Heads and "T" if Tails), and the 3 slips of paper are thrown into a hat.

(a) Find the probability that all 3 tosses landed Heads, given that at least 2 were Heads.

(b) Two of the slips of paper are randomly drawn from the hat, and both show the letter H. Given this information, what is the probability that all 3 tosses landed Heads?

Solution

(a)

Let $H_1$, $H_2$ and $H_3$ be the event that the first, second and third toss is head, respectively. Let $E$ be the event that there are at least 2 heads. At least 2 heads is a complement of at most 1 heads. But the probability of at most 1 heads should equals to the probability of at most 1 tails, which should equals to the probability of at least 2 heads. So $P(E) = \frac{1}{2}$.

$$
\begin{aligned}
P(H_1 \cap H_2 \cap H_3 \mid E) &= \frac{P(E \mid H_1 \cap H_2 \cap H_3) P(H_1 \cap H_2 \cap H_3)}{P(E)} \\
&= \frac{1 \cdot \frac{1}{8}}{\frac{1}{2}} \\
&= \frac{1}{4}
\end{aligned}
$$

(b)

* Let $H_1$, $H_2$ and $H_3$ be the event that the first, second and third toss is head, respectively.
* Let $E$ be the event that two of the slips of paper are randomly drawn from the hat and both show letter H.
* Let $C_0$, $C_1$, $C_2$ and $C_3$ be the event that there are 0, 1, 2 and 3 heads, respectively.

Let's first find out $P(E)$. Classifying on number of heads, we have
$$
P(E) = P(E \mid C_0)P(C_0) + P(E \mid C_1)P(C_1) + P(E \mid C_2) P(C_2) + P(E \mid C_3) P(C_3)
$$
In which $P(E | C_0) = 0$, $P(E \mid C_1) = 0$, $P(E \mid C_3) = 1$. So we obtain
$$
P(E) = P(E \mid C_2)P(C_2) + P(C_3) = P(E \mid C_2) \cdot \frac{3}{8} + \frac{1}{8}
$$

There are 3 undistinguishable slips, 2 heads and 1 tails, the possibility of choosing 2 slips and they are two heads is
$$
P(E \mid C_2) = \frac{\binom{2}{2}}{\binom{3}{2}} = \frac{1}{3}
$$

Therefore
$$
P(E) = \frac{1}{3} \cdot \frac{3}{8} + \frac{1}{8} = \frac{1}{4}
$$

Then
$$
\begin{aligned}
P(H_1 \cap H_2 \cap H_3 \mid E) &= \frac{P(E \mid H_1 \cap H_2 \cap H_3) P(H_1 \cap H_2 \cap H_3)}{P(E)} \\
&= \frac{1 \cdot \frac{1}{8}}{\frac{1}{4}} \\
&= \frac{1}{2}
\end{aligned}
$$

### Q22

A bag contains one marble which is either green or blue, with equal probabilities. A green marble is put in the bag (so there are 2 marbles now), and then a random marble is taken out. The marble taken out is green. What is the probability that the remaining marble is also green?

Solution

* Let $G_1$ be the event that the first marble in the bag is green.
* Let $T_G$ be the event that the taken out marble is green.
* Let $R_G$ be the event that the remaining marble is green.

Given $G_1$, we have
$$
\begin{aligned}
P(R_G \mid T_G, G_1) &= \frac{P(T_G \mid R_G, G_1) P(R_G \mid G_1)}{P(T_G \mid G_1)}
&= 1
\end{aligned}
$$

Given $G_1^c$, we have
$$
\begin{aligned}
P(R_G \mid T_G, G_1^c) &= \frac{P(T_G \mid R_G, G_1^c) P(R_G \mid G_1^c)}{P(T_G \mid G_1^c)}
&= \frac{0 \cdot \frac{1}{2}}{\frac{1}{2}} \\
&= 0
\end{aligned}
$$

By the conditional LOTP, partitioning on $G_1$ and $G_1^c$, we have
$$
\begin{aligned}
P(R_G | T_G) &= P(R_G \mid G_1, T_G)P(G_1 \mid T_G) + P(R_G \mid G_1^c, T_G)P(G_1^c \mid T_G) \\
&= 1 \cdot P(G_1 | T_G) + 0 \cdot P(G_1^c \mid T_G) \\
&= \frac{P(T_G \mid G_1) P(G_1)}{P(T_G)} \\
&= \frac{P(T_G \mid G_1) P(G_1)}{P(T_G \mid G_1)P(G_1) + P(T_G \mid G_1^c) P(G_1^c)} \\
&= \frac{1 \cdot \frac{1}{2}}{1 \cdot \frac{1}{2} + \frac{1}{2} \cdot \frac{1}{2}} \\
&= \frac{2}{3}
\end{aligned}
$$

### Q23

Let $G$ be the event that a certain individual is guilty of a certain robbery. In gathering
evidence, it is learned that an event $E_1$ occurred, and a little later it is also learned that
another event $E_2$ also occurred. Is it possible that individually, these pieces of evidence increase the chance of guilt (so $P(G \mid E_1) \gt P(G)$ and $P(G \mid E_2) \gt P(G)$), but together
they decrease the chance of guilt (so $P(G \mid E_1,E_2) \lt P(G)$)?

Solution: Skip.

### Q24

Is it possible to have events $A_1$, $A_2$, $B$, $C$ with $P(A_1 \mid B) \gt P(A_1 \mid C)$ and $P(A_2 \mid B) \gt P(A_2 \mid C)$, yet $P(A_1 \cup A_2 \mid B) \lt P(A_1 \cup A_2 \mid C)$? If so, find an example (with a “story”
interpreting the events, as well as giving specific numbers); otherwise, show that it is
impossible for this phenomenon to happen.

Solution:

Group B has 51 boy and 49 girls, and all of boys are taller than 180cm, and all the girls are lower than 180cm. Group C has 50 boys and 50 girls, all girls are taller than 180cm, all the boys are lower than 180cm. We need to select person from them, all the boys and girls are equally likely be selected.

* Let $B$ and $C$ be the event that the selected person belongs to group B and C, respectively.
* Let $A_1$ be the event that the selected person is a boy.
* Let $A_2$ br the event that the selected person is taller than 180cm.

We have
$$
P(A_1 \mid B) = \frac{51}{100} \gt P(A_1 \mid C) = \frac{50}{100}
$$
$$
P(A_2 \mid B) = \frac{51}{100} \gt P(A_2 \mid C) = \frac{50}{100}
$$

$$
\begin{aligned}
P(A_1 \cup A_2 \mid B) &= P(A_1 \mid B) + P(A_2 \mid B) - P(A_1 \cap A_2 \mid B) \\
&= \frac{51}{100} + \frac{51}{100} - \frac{51}{100} \\
&= \frac{51}{100}
\end{aligned}
$$

$$
\begin{aligned}
P(A_1 \cup A_2 \mid C) &= P(A_1 \mid C) + P(A_2 \mid C) - P(A_1 \cap A_2 \mid C) \\
&= \frac{50}{100} + \frac{50}{100} - 0 \\
&= \frac{100}{100}
\end{aligned}
$$

### Q25

A crime is committed by one of two suspects, A and B. Initially, there is equal evidence against both of them. In further investigation at the crime scene, it is found that the guilty party had a blood type found in 10% of the population. Suspect A does match this blood type, whereas the blood type of Suspect B is unknown.

(a) Given this new information, what is the probability that A is the guilty party?

(b) Given this new information, what is the probability that B’s blood type matches that found at the crime scene?

Solution

(a)

* Let $G_A$ be the event that suspect A is guilty.
* Let $E_A$ be the event that suspect A's blood type matches the guilty party.

$$
\begin{aligned}
P(G_A \mid E_A) &= \frac{P(E_A \mid G_A) P(G_A)}{P(E_A | G_A)P(G_A) + P(E_A \mid G_A^c)P(G_A^c)} \\
&= \frac{0.5}{0.5 + 0.1 \cdot 0.5} \\
&\approx 0.9091
\end{aligned}
$$

(b)

* Let $G_A$ be the event that suspect A is guilty.
* Let $E_A$ be the event that suspect A's blood type matches the guilty party.

$$
\begin{aligned}
P(E_B \mid E_A) &= P(E_B \mid G_A, E_A) P(G_A \mid E_A) + P(E_B \mid G_A^c, E_A) P(G_A^c \mid E_A) \\
&\approx 0.1 \cdot 0.9091 + 1 \cdot (1-0.9091) \\
&\approx 0.1818
\end{aligned}
$$

### Q26

To battle against spam, Bob installs two anti-spam programs. An email arrives, which is either legitimate (event $L$) or spam (event $L^c$), and which program $j$ marks as legitimate (event $M_j$) or marks as spam (event $M_j^c$) for $j \in \{1,2\}$. Assume that 10% of Bob’s email is legitimate and that the two programs are each "90% accurate" in the sense that $P(M_j \mid L) = P(M_j^c \mid L^c) = 9/10$. Also assume that given whether an email is spam, the two programs' outputs are conditionally independent.

(a) Find the probability that the email is legitimate, given that the 1st program marks
it as legitimate (simplify).

(b) Find the probability that the email is legitimate, given that both programs mark it
as legitimate (simplify).

(c) Bob runs the 1st program and $M_1$ occurs. He updates his probabilities and then runs the 2nd program. Let $P(A) = P(A \mid M_1)$ be the updated probability function after running the 1st program. Explain briefly in words whether or not $P(L \mid M_2) = P(L \mid M_1 \cap M_2)$: is conditioning on $M_1 \cap M_2$ in one step equivalent to first conditioning on $M_1$, then updating probabilities, and then conditioning on $M_2$?

Solution:

(a)
$$
\begin{aligned}
P(L \mid M_1) &= \frac{P(M_1 \mid L)P(L)}{P(M_1)} \\
&= \frac{P(M_1 \mid L)P(L)}{P(M_1 \mid L)P(L) + P(M_1 \mid L^c)P(L^c)} \\
&= \frac{0.9 \cdot 0.1}{0.9 \cdot 0.1  + 0.1 \cdot 0.9} \\
&= 0.5
\end{aligned}
$$

(b)
$$
\begin{aligned}
P(L \mid M_1 \cap M_2) &= \frac{P(M_1 \cap M_2 \mid L) P(L)}{P(M_1 \cap M_2)} \\
&= \frac{P(M_1 \cap M_2 \mid L) P(L)}{P(M_1 \cap M_2 \mid L)P(L) + P(M_1 \cap M_2 \mid L^c)P(L^c)} \\
&= \frac{0.9^2 \cdot 0.1}{0.9^2 \cdot 0.1 + 0.1^2 \cdot 0.9} \\
&= 0.9
\end{aligned}
$$

(c)
Yes, they are the same.

### Q27

Suppose that there are 5 blood types in the population, named type 1 through type 5,
with probabilities $p_1,p_2,\ldots,p_5$. A crime was committed by two individuals. A suspect,
who has blood type 1, has prior probability $p$ of being guilty. At the crime scene, blood
evidence is collected, which shows that one of the criminals has type 1 and the other
has type 2.
Find the posterior probability that the suspect is guilty, given the evidence. Does the
evidence make it more likely or less likely that the suspect is guilty, or does this depend
on the values of the parameters $p$, $p_1,\ldots,p_5$? If it depends on these values, give a simple criterion for when the evidence makes it more likely that the suspect is guilty.

Solution:

* Let $A$ be the event that the suspect is guilty.
* Let $B_1$ and $B_2$ be the event that blood type 1 and type 2 is collected at the crime scene, respectively.

$$
\begin{aligned}
P(A \mid B_1, B_2) &= \frac{P(B_1, B_2 \mid A) P(A)}{P(B_1, B_2 \mid A) P(A) + P(B_1, B_2 \mid A^c) P(A^c)} \\
&= \frac{p_2 p}{p_2 p + 2p_1p_2(1-p)}
\end{aligned}
$$

Whether the value is great or less than $p$ depends on $p_1$, $p_2$ and $p$.
$$
\operatorname{odds}(A \mid E) = \frac{P(A \mid E)}{P(A^c \mid E)} = \frac{P(E \mid A)}{P(E \mid A^c)} \frac{P(A)}{P(A^c)}
$$

### Q28

Fred has just tested positive for a certain disease.

(a) Given this information, find the posterior odds that he has the disease, in terms of
the prior odds, the sensitivity of the test, and the specificity of the test.

(b) Not surprisingly, Fred is much more interested in P(have disease|test positive),
known as the positive predictive value, than in the sensitivity P(test positive|have disease).
A handy rule of thumb in biostatistics and epidemiology is as follows:

_For a rare disease and a reasonably good test, specificity matters much more than sensitivity in determining the positive predictive value._

Explain intuitively why this rule of thumb works. For this part you can make up some
specific numbers and interpret probabilities in a frequentist way as proportions in a
large population, e.g., assume the disease afflicts 1% of a population of 10000 people
and then consider various possibilities for the sensitivity and specificity.

Solution:

(a)

* Let $s$ and $p$ be the sensitivity and specificity of the test, respectively.
* Let $D$ be the event that Fred has disease.
* Let $T^{+}$ and $T^{-}$ be the event that the test is positive and negative, respectively.

We have
$$
\begin{aligned}
\frac{P(D \mid T^{+})}{P(D^c \mid T^{+})} &= \frac{P(T^{+} \mid D)}{P(T^{+} \mid D^c)} \frac{P(D)}{P(D^c)} \\
&= \frac{s}{1-p} \frac{P(D)}{P(D^c)}
\end{aligned}
$$

(b)

* Let $s$ and $p$ be the sensitivity and specificity of the test, respectively.
* Let $D$ be the event that Fred has disease.
* Let $T_p$ be the event that the test is positive.

Suppose the disease afflicts $d=0.0001$ of the population. We have
$$
\begin{aligned}
P(D \mid T_p) &= \frac{P(T_p \mid D)P(D)}{P(T_p \mid D)P(D) + P(T_p \mid D^c) P(D^c)} \\
&= \frac{sd}{sd + (1-p)(1-d)}
\end{aligned}
$$

Suppose $p = s = 0.99$, we have $P(D \mid S) = 0.00980392$

Suppose $s = 0.999$, $p = 0.99$, we have $P(D \mid S) = 0.00989217$

Suppose $p = 0.999$, $s = 0.99$, we have $P(D \mid S) = 0.09009009$

Suppose $p = 0.9999$, $s = 0.99$, we have $P(D \mid S) = 0.49751244$

The increase performance on the specificity has a higher impact on the positive predictive value. This is because $1-d$ is much larger than $d$, and $1-p$ has a higher impact.

### Q29

A family has two children. Let $C$ be a characteristic that a child can have, and assume that each child has characteristic $C$ with probability $p$, independently of each other and of gender. For example, $C$ could be the characteristic "born in winter" as in Example 2.2.7. Under the assumptions of Example 2.2.5, show that the probability that both children are girls given that at least one is a girl with characteristic $C$ is $\frac{2−p}{4-p}$. Note that this is $\frac{1}{3}$ if $p=1$ (agreeing with the first part of Example 2.2.5) and approaches $\frac{1}{2}$ from below as p→0 (agreeing with Example 2.2.7).

Solution:

* Let $G_1$ and $G_2$ be the event that the first and the second child is girl, respectively.
* Let $E$ be the event that at least one is a girl with characteristic $C$.

First, we have
$$
P(E) = \frac{1}{2} p + \frac{1}{2} p - (\frac{1}{2} p)^2 = \frac{4p - p^2}{4}
$$

Therefore
$$
\begin{aligned}
P(G_1 \cap G_2 \mid E) &= \frac{P(E \mid G_1 \cap G_2) P(G_1 \cap G_2)}{P(E)} \\
&= \frac{(p + p - p^2) \cdot \frac{1}{4}}{\frac{4p - p^2}{4}} \\
&= \frac{2-p}{4-p}
\end{aligned}
$$

## Independence and conditional independence

### Q30

A family has 3 children, creatively named A, B, and C.

(a) Discuss intuitively (but clearly) whether the event "A is older than B" is independent of the event "A is older than C".

(b) Find the probability that A is older than B, given that A is older than C.

Solution:

(a) Knowing that "A is older than B" gives us the information that A is older than usual which makes "A is older than C" more likely to happen, so this two event should be dependent.

(b)

Think of A, B, C are equally likely ordered sequence, there are 3! possibilities.

For "A is older than C", the number of possible outcomes is (A is oldest, or A is the second oldest)
$$
2! + 1
$$

For "A is older than B and C", the number of possible outcomes is (A must be oldest)
$$
2!
$$

Therefore
$$
\begin{aligned}
P(\text{A is older than B} | \text{A is older than C}) &= \frac{P(\text{A is older than B, A is older than C})}{P(\text{A is older than C})} \\
&= \frac{2!}{2!+1} = \frac{2}{3}
\end{aligned}
$$

### Q31

Is it possible that an event is independent of itself? If so, when is this the case?

Solution:

Let $A$ be an event. If $A$ is independent of itself, then $P(A) = P(A \cap A) = P(A)^2$, so $P(A)$ is $0$ or $1$. So this is only possible in the extreme cases that the event has probability $0$ or $1$.

### Q32

Consider four nonstandard dice (the Efron dice), whose sides are labeled as follows
(the 6 sides on each die are equally likely).

* A: 4,4,4,4,0,0
* B: 3,3,3,3,3,3
* C: 6,6,2,2,2,2
* D: 5,5,5,1,1,1

These four dice are each rolled once. Let $A$ be the result for die A, $B$ be the result for die B, etc.

(a) Find $P(A > B)$, $P(B > C)$, $P(C > D)$, and $P(D > A)$.

(b) Is the event $A>B$ independent of the event $B>C$? Is the event $B>C$ independent of the event $C>D$? Explain.

Solution:

(a)
$$
\begin{aligned}
P(A > B) &= P(A > B \mid A = 4)P(A=4) + P(A > B \mid A=0)P(A=0) \\
&=1 \cdot \frac{4}{6} + 0 \cdot \frac{2}{6} = \frac{4}{6}
\end{aligned}
$$

Similarly, we have
$$
P(B > C) = \frac{4}{6}
$$

$$
P(C > D) = \frac{2}{3}
$$

$$
P(D > A) = \frac{2}{3}
$$

(b)

Consider all the possibility of A,B,C. In order to fulfill A > B, A must be 4, so 4/6 possible outcome remains, In the remaining outcomes, C must be 2, so only 4/6 of C remains. Therefore
$$
P(A > B, B > C) = (\frac{4}{6})^2
$$

On the other hand
$$
P(A > B) P(B > C) = \frac{4}{6} \frac{4}{6}
$$

Therefore A > B and B > C are independent. A > B only tells us the possible value of A, but it doesn't help on knowing B > C.

Similarly
$$
P(B > C, C > D) = \frac{4}{6} \cdot \frac{1}{2} = \frac{1}{3}
$$

$$
P(B > C) P(C > D) = \frac{4}{9}
$$

So B > C and C > D are dependent. Knowing B > C determined the possible values of C, and hence determined the possible values of D.

### Q33

Alice, Bob, and 100 other people live in a small town. Let $C$ be the set consisting of the
100 other people, let $A$ be the set of people in $C$ who are friends with Alice, and let $B$ be the set of people in C who are friends with Bob. Suppose that for each person in C, Alice is friends with that person with probability 1/2, and likewise for Bob, with all of
these friendship statuses independent.

(a) Let $D \subseteq C$. Find $P(A=D)$.

(b) Find $P(A \subseteq B)$.

(c) Find $P(A \cup B= C)$.

Solution:

(a)

Suppose $k= | D |$
$$
P(A = D) = (\frac{1}{2})^k (\frac{1}{2})^{100-k} = (\frac{1}{2})^{100}
$$

(b)

Suppose $F_1, \ldots F_n$ are the event that person $i$ is Alice's friend, then is also Bob's friend.
$$
P(A \subseteq B) = \prod_{i=1}^{100} P(F_i) = (\frac{3}{4})^{100}
$$

(c)

Suppose $F_1, \ldots F_n$ are the event that the people $i$ is a friend of Alice or Bob.
$$
P(A \cup B = C) = \prod_{i=i}^{100} P(F_i) = \prod_{i=i}^{100} (\frac{1}{2} + \frac{1}{2} - (\frac{1}{2})^2) = (\frac{3}{4})^{100}
$$

### Q34

Suppose that there are two types of drivers: good drivers and bad drivers. Let $G$ be the event that a certain man is a good driver, $A$ be the event that he gets into a car accident next year, and $B$ be the event that he gets into a car accident the following year. Let $P(G) = g$ and $P(A \mid G) = P(B \mid G) = p_1$, $P(A \mid G^c) = P(B \mid G^c) = p_2$, with $p1 \lt p2$. Suppose that given the information of whether or not the man is a good driver, A and B are independent (for simplicity and to avoid being morbid, assume that the accidents being considered are minor and wouldn’t make the man unable to drive).

(a) Explain intuitively whether or not A and B are independent.

(b) Find $P(G \mid A^c)$.

(c) Find $P(B \mid A^c)$.

Solution:

(a)

Without knowing if the driver is a good driver, if he has accident in the next year, generally, he's more likely to have an accident in the next year because he's driving skill keeps the same. Or you can say he's less likely to have an accident in the next year because he will be more careful. Anyway, knowing if he has an accident next year will impact our believe about he will have an accident in the following year.

(b)

$$
\begin{aligned}
P(G \mid A^c) &= \frac{P(A^c \mid G)P(G)}{P(A^c \mid G)P(G) + P(A^c \mid G^c)P(G^c)} \\
&= \frac{(1-p_1)g}{(1-p_1)g + (1-p_2)(1-g)}
\end{aligned}
$$

(c)

Suppose
$$
v = P(G \mid A^c) = \frac{(1-p_1)g}{(1-p_1)g + (1-p_2)(1-g)}
$$

We have
$$
\begin{aligned}
P(B \mid A^c) &= P(B \mid A^c, G) P(G \mid A^c) + P(B \mid A^c, G^c)P(G^c \mid A^c) \\
&= P(B \mid G) P(G \mid A^c) + P(B \mid G^c) P(G^c \mid A^c) \\
&= p_1 v + p_2 (1-v)
\end{aligned}
$$

### Q35

You are going to play 2 games of chess with an opponent whom you have never played against before (for the sake of this problem). Your opponent is equally likely to be a beginner, intermediate, or a master. Depending on which, your chances of winning an individual game are 90%, 50%, or 30%, respectively.

(a) What is your probability of winning the first game?

(b) Congratulations: you won the first game! Given this information, what is the probability that you will also win the second game (assume that, given the skill level of your opponent, the outcomes of the games are independent)?

(c) Explain the distinction between assuming that the outcomes of the games are independent and assuming that they are conditionally independent given the opponent’s skill level. Which of these assumptions seems more reasonable, and why?

Solution:

(a)

$$
P(\text{win the first game}) = 0.9 \frac{1}{3} + 0.5 \frac{1}{3} + 0.3 \frac{1}{3} \approx 0.5667
$$

(b)

* Let $W_1$ and $W_2$ be the events that you win the first and second games, respectively.
* Let $O_1, O_2, O_3$ be the events that your opponent is a beginner, an intermediate and master player, respectively.

First, we should have
$$
P(O_1 \mid W_1) = \frac{P(W_1 \mid O_1) P(O_1)}{P(W_1)} \approx \frac{0.9 \cdot 0.3333}{0.5667} \approx 0.5293 \\

P(O_2 \mid W_1) = \frac{P(W_1 \mid O_2) P(O_2)}{P(W_1)} \approx \frac{0.5 \cdot 0.3333}{0.5667} \approx 0.2941 \\

P(O_3 \mid W_1) = \frac{P(W_1 \mid O_3) P(O_3)}{P(W_1)} \approx \frac{0.3 \cdot 0.3333}{0.5667} \approx 0.1764 \\
$$

Using the conditional form of LOTP, we have
$$
\begin{aligned}
P(W_2 \mid W_1) &= P(W_2 \mid O_1, W_1)P(O_1 \mid W_1) + P(W_2 \mid O_2, W_1)P(O_2 \mid W_1) + P(W_2 \mid O_3, W_1)P(O_3 \mid W_1) \\
&= P(W_2 \mid O_1)P(O_1 \mid W_1) + P(W_2 \mid O_2)P(O_2 \mid W_1) + P(W_2 \mid O_3)P(O_3 \mid W_1) \\
&\approx 0.9 \cdot 0.5293 + 0.5 \cdot 0.2941 + 0.3 \cdot 0.1764 \\
&\approx 0.6763
\end{aligned}
$$

### Q36

(a) Suppose that in the population of college applicants, being good at baseball is independent of having a good math score on a certain standardized test (with respect
to some measure of "good"). A certain college has a simple admissions procedure: admit
an applicant if and only if the applicant is good at baseball or has a good math score
on the test.

Give an intuitive explanation of why it makes sense that among students that the college admits, having a good math score is negatively associated with being good at baseball, i.e., conditioning on having a good math score decreases the chance of being good at baseball.

(b) Show that if $A$ and $B$ are independent and $C= A \cup B$, then $A$ and $B$ are conditionally dependent given $C$ (as long as $P(A \cap B) \gt 0$ and $P(A \cup B) \lt 1$), with
$$
P(A \mid B,C) \lt P(A \mid C).
$$
This phenomenon is known as Berkson's paradox, especially in the context of admissions
to a school, hospital, etc.

(a)

* Let $B$ be the event that the applicant is good at baseball.
* Let $M$ be the event that the applicant is good at math.

So an applicant has these possibilities:
$$
BM \qquad BM^c \qquad B^cM \qquad B^c M^c
$$

Knowing the applicant is good a baseball, gives no information about whether the applicant is good at math, and vice versa. However, $B^cM^c$ is excluded from the admitted applicants, so the possibilities of the admitted applicants reduced to:
$$
BM \qquad BM^c \qquad B^cM
$$
As you can see, the applicants maybe good at both baseball and math, but if we know a applicant is only good a baseball, the applicant must be not good at math, and vice versa. That is the negative association.

(b)
First we have
$$
\begin{aligned}
P(A \mid B, C) &= P(A \mid B)
&& \text{$B \subseteq C$} \\

&= P(A)
&& \text{$A$ and $B$ are independent}
\end{aligned}
$$

And we also have
$$
\begin{aligned}
P(A \mid C) &= \frac{P(A \cap C)}{P(C)} \\

&= \frac{P(A)}{P(C)}
&& \text{$A \subseteq C$} \\

&= \frac{P(A)}{P(A \cup B)} \\

&> P(A)&& \text{$P(A \cap B) \gt 0$}
\end{aligned}
$$

Therefore
$$
P(A \mid C) \gt P(A \mid B, C)
$$

### Q37

Two different diseases cause a certain weird symptom; anyone who has either or both
of these diseases will experience the symptom. Let $D_1$ be the event of having the first disease, $D_2$ be the event of having the second disease, and $W$ be the event of having the weird symptom. Suppose that $D_1$ and $D_2$ are independent with $P(D_j) = p_j$, and that a person with neither of these diseases will have the weird symptom with probability $w_0$. Let $q_j = 1−p_j$, and assume that $0 \lt p_j \lt 1$.

(a) Find $P(W)$.

(b) Find $P(D_1 \mid W)$, $P(D_2 \mid W)$, and $P(D_1, D_2 \mid W)$.

(c) Determine algebraically whether or not $D_1$ and $D_2$ are conditionally independent given $W$.

(d) Suppose for this part only that $w_0 = 0$. Give a clear, convincing intuitive explanation in words of whether $D_1$ and $D_2$ are conditionally independent given $W$.

Solution:

(a)

$$
\begin{aligned}
P(W) &= P(W \mid D_1, D_2) P(D_1, D_2) + P(W \mid D_1, D_2^c) P(D_1, D_2^c) + P(W \mid D_1^c, D_2) P(D_1^c, D_2) + P(W \mid D_1^c, D_2^c) P(D_1^c, D_2^c) \\
&= p_1 p_2 + p_1 q_2 + q_1 p_2 + w_0 q_1 q_2
\end{aligned}
$$

(b)

$$
\begin{aligned}
P(D_1 \mid W) &= \frac{P(W \mid D_1) P(D_1)}{P(W)}
&= \frac{p_1}{p_1 p_2 + p_1 q_2 + q_1 p_2 + w_0 q_1 q_2}
\end{aligned}
$$

$$
\begin{aligned}
P(D_2 \mid W) &= \frac{P(W \mid D_2) P(D_2)}{P(W)}
&= \frac{p_2}{p_1 p_2 + p_1 q_2 + q_1 p_2 + w_0 q_1 q_2}
\end{aligned}
$$

$$
\begin{aligned}
P(D_1, D_2 \mid W) &= \frac{P(W \mid D_1, D_2) P(D_1, D_2)}{P(W)}
&= \frac{p_1 p_2}{p_1 p_2 + p_1 q_2 + q_1 p_2 + w_0 q_1 q_2}
\end{aligned}
$$

(c)

Suppose $Z = p_1 p_2 + p_1 q_2 + q_1 p_2 + w_0 q_1 q_2$

If $Z=1$ we have
$$
P(D_1 \mid W) P(D_2 \mid W) = P(D_1, D_2 \mid W) = \frac{p_1 p_2}{Z}
$$

Otherwise
$$
P(D_1 \mid W) P(D_2 \mid W) \ne P(D_1, D_2 \mid W)
$$

(d)

When $w_0 = 0$, a person has the weird symptom if and only if they have at least one disease:
$$
W = D_1 \cup D_2
$$

So among people known to have the symptom:

* If they do not have $D_1$, they must have $D_2$.
* If they do not have $D_2$, they must have $D_1$.

So in this case, $D_1$ and $D_2$ are dependent.

### Q38

We want to design a spam filter for email. As described in Exercise 1, a major strategy is to find phrases that are much more likely to appear in a spam email than in a non-spam email. In that exercise, we only consider one such phrase: "free money". More realistically, suppose that we have created a list of 100 words or phrases that are much more likely to be used in spam than in non-spam.
Let $W_j$ be the event that an email contains the $j$-th word or phrase on the list. Let
$$
p = P(\text{spam}), \qquad p_j = P(W_j \mid \text{spam}), \qquad r_j = P(W_j \mid \text{not spam}),
$$
where "spam" is shorthand for the event that the email is spam.

Assume that $W_1,\ldots,W_{100}$ are conditionally independent given that the email is spam, and conditionally independent given that it is not spam. A method for classifying emails (or other objects) based on this kind of assumption is called a naive Bayes classifier. (Here “naive” refers to the fact that the conditional independence is a strong assumption, not to Bayes being naive. The assumption may or may not be realistic, but naive Bayes classifiers sometimes work well in practice even if the assumption is not realistic.)

Under this assumption we know, for example, that
$$
P(W_1,W_2,W_3^c ,W_4^c ,\ldots,W_{100}^c \mid \text{spam}) = p_1 p_2(1−p_3)(1−p_4)...(1−p_{100}).
$$

Without the naive Bayes assumption, there would be vastly more statistical and computational difficulties since we would need to consider $2^{100} \approx 1.3 \cdot 10^{30}$ events of the
form $A_1 \cap A_2 \ldots \cap A_{100}$ with each $A_j$ equal to either $W_j$ or $W_
j^c$. A new email has just arrived, and it includes the 23rd, 64th, and 65th words or phrases on the list (but not the other 97). So we want to compute
$$
P(spam|W_1^c ,\ldots,W_{22}^c,W_{23},W_{24}^c,\ldots,W_{63}^c,W_{64},W_{65},W_{66}^c,\ldots,W_{100}^c).
$$

Note that we need to condition on all the evidence, not just the fact that $W_{23} \cap W_{64} \cap W_{65}$
occurred. Find the conditional probability that the new email is spam (in terms of p
and the $p_j$ and $r_j$).

Solution

Let $S$ be the event that the email is spam.

Suppose
$$
E = W_1^c \cap \ldots W_{22}^c \cap W_{23} \cap W_{24}^c \cap \ldots \cap W_{63}^c \cap W_{64} \cap W_{65} \cap W_{66}^c \cap \ldots \cap W_{100}^c
$$

We have
$$
\begin{aligned}
P(S \mid E) &= \frac{P(E \mid S) P(S)}{P(E \mid S) P(S) + P(E \mid S^c) P(S^c)} \\
&=\frac{a p}{ap + b(1-p)}
\end{aligned}
$$
In which
$$
a = (1-p_1)(1-p_2) \ldots (1-p_{22}) p_{23} (1-p_{24}) \ldots (1-p_{63}) p_{64} p_{65} (1-p_{66}) \ldots (1-p_{100}) \\
b = (1-r_1)(1-r_2) \ldots (1-r_{22}) r_{23} (1-r_{24}) \ldots (1-r_{63}) r_{64} r_{65} (1-r_{66}) \ldots (1-r_{100})
$$

## Monty Hall

### Q39

(a) Consider the following 7-door version of the Monty Hall problem. There are 7 doors, behind one of which there is a car (which you want), and behind the rest of which there are goats (which you don’t want). Initially, all possibilities are equally likely for where the car is. You choose a door. Monty Hall then opens 3 goat doors, and offers you the option of switching to any of the remaining 3 doors. Assume that Monty Hall knows which door has the car, will always open 3 goat doors and offer the option of switching, and that Monty chooses with equal probabilities from all his choices of which goat doors to open. Should you switch? What is your probability of success if you switch to one of the remaining 3 doors?

(b) Generalize the above to a Monty Hall problem where there are $n \ge 3$ doors, of which
Monty opens $m$ goat doors, with $1 \le m \le n - 2$.

Solution

(a)

* Let $W$ be the event that the contestant switches to one of the three available doors and wins.
* Let $D_1,\ldots,D_7$ be the events that the car is behind the door from 1 to 7, respectively.

Without lose the generality, we can assume the contestant choose door 1 (if he didn’t pick door 1, we could simply relabel the doors, or rewrite this solution with the door numbers permuted).

However
$$
P(W) = \sum_{i=1}^7 P(W \mid D_i) P(D_i)
$$

And we have $P(D_i) = 1/7$ for $i \in \{1,\ldots,7\}$.

Given the car is behind door 1, switch will lose the game, so we have $P(W \mid D_1) = 0$.

For the $D_2$ to $D_7$, Monty won't open the door with that car, because there are 3 doors remains, if the contestant choose the remaining doors randomly, we have
$$
P(W \mid D_i) = \frac{1}{3} \qquad \text{For $i \in \{2,\ldots,7\}$}
$$

Therefore
$$
P(W) = 0 \cdot \frac{1}{7} + 6 \cdot \frac{1}{3} \cdot \frac{1}{7} = \frac{2}{7}
$$

On the other hand, if the contestant doesn't switch the door, the probability of win is $1/7$, So the contestant should switch the door.

(b)

$$
P(W) = \frac{(n-1)}{n (n-m-1)} \gt \frac{1}{n}
$$

### Q40

Consider the Monty Hall problem, except that Monty enjoys opening door 2 more
than he enjoys opening door 3, and if he has a choice between opening these two doors,
he opens door 2 with probability $p$, where $\frac{1}{2} \le p \le 1$.
To recap: there are three doors, behind one of which there is a car (which you want),
and behind the other two of which there are goats (which you don’t want). Initially,
all possibilities are equally likely for where the car is. You choose a door, which for concreteness we assume is door 1. Monty Hall then opens a door to reveal a goat, and offers you the option of switching. Assume that Monty Hall knows which door has the car, will always open a goat door and offer the option of switching, and as above assume that if Monty Hall has a choice between opening door 2 and door 3, he chooses door 2 with probability $p$ (with $\frac{1}{2} \le p \le 1$).

(a) Find the unconditional probability that the strategy of always switching succeeds
(unconditional in the sense that we do not condition on which of doors 2 or 3 Monty
opens).

(b) Find the probability that the strategy of always switching succeeds, given that Monty opens door 2.

(c) Find the probability that the strategy of always switching succeeds, given that Monty opens door 3.

Solution:

(a)

* Let $W$ be the event that the contestant chooses to switch and wins.
* Let $C_1$, $C_2$ and $C_3$ be the events that the car behind the door 1, 2 and 3, respectively.

$$
\begin{aligned}
P(W) &= P(W \mid C_1) P(C_1) + P(W \mid C_2) P(C_2) + P(W \mid C_3) P(C_3) \\
&= 0 \cdot \frac{1}{3} + 1 \cdot \frac{1}{3} + 1 \cdot \frac{1}{3} \\
&= \frac{2}{3}
\end{aligned}
$$

(b)

* Let $W$ be the event that the contestant chooses to switch and wins.
* Let $C_1$, $C_2$ and $C_3$ be the events that the car behind the door 1, 2 and 3, respectively.
* Let $D_2$ be the event that Monty opens door 2.

In case Monty opens door 2, the car can only be at door 1 or 3.

* If the car is at door 1, Monty choose door 2 at $p$ probability.
* If the car is at door 2, Monty choose door 2 at 0 probability.
* If the car is at door 3, Monty choose door 2 at 1 probability.

$$
\begin{aligned}

P(C_3 \mid D_2) &= \frac
{P(D_2 \mid C_3) P(C_3)}
{P(D_2)} \\

&=
\frac
{P(D_2 \mid C_3) P(C_3)}
{P(D_2 \mid C_1) P(C_1) + P(D_2 \mid C_2) P(C_2) + P(D_2 \mid C_3) P(C_3)} \\

&=
\frac
{1 \cdot \frac{1}{3}}
{p \cdot \frac{1}{3} + 0 \cdot \frac{1}{3} + 1 \cdot \frac{1}{3}} \\

&= \frac{1}{p + 1}

\end{aligned}
$$

Therefore
$$
\begin{aligned}
P(W \mid D_2) &= P(W \mid C_1, D_2) P(C_1 \mid D_2) + P(W \mid C_3, D_2) P(C_3 \mid D_2) \\
&= 0 + 1 \cdot \frac{1}{p+1} \\
&= \frac{1}{p+1}
\end{aligned}
$$

(c)

* Let $C_1$, $C_2$ and $C_3$ be the events that the car behind the door 1, 2 and 3, respectively.
* Let $D_3$ be the event that Monty opens door 3.

Equivalently, what we need to find is the probability that the car is at door 2, given Monty open door 3.
$$
\begin{aligned}
P(C_2 \mid D_3) &= \frac{P(D_3 \mid C_2) P(C_2)}{P(D_3)}
\end{aligned}
$$

Consider $P(D_3)$ separately.

* If the car is behind door 1, Monty choose $D_3$ at probability $1-p$.
* If the car is behind door 2, Monty choose $D_3$ at probability 1.
* If the car is behind door 3, Monty can't choose $D_3$ at all.

Hence
$$
\begin{aligned}
P(D_3) &= P(D_3 \mid C_1) P(C_1) + P(D_3 \mid C_2) P(C_2) \\
&= (1 - p) \cdot \frac{1}{3} + 1 \cdot \frac{1}{3} \\
&= \frac{2 - p}{3}
\end{aligned}
$$

Therefore
$$
\begin{aligned}
P(C_2 \mid D_3) &= \frac{P(D_3 \mid C_2) P(C_2)}{P(D_3)} \\
&= \frac{1 \cdot \frac{1}{3}}{\frac{2 - p}{3}} \\
&= \frac{1}{2 - p}
\end{aligned}
$$

### Q41

The ratings of Monty Hall’s show have dropped slightly, and a panicking executive
producer complains to Monty that the part of the show where he opens a door lacks
suspense: Monty always opens a door with a goat. Monty replies that the reason is so
that the game is never spoiled by him revealing the car, but he agrees to update the
game as follows.

Before each show, Monty secretly flips a coin with probability $p$ of Heads. If the coin lands Heads, Monty resolves to open a door with a goat (with equal probabilities if there is a choice). Otherwise, Monty resolves to open a random door, with equal probabilities. Of course, Monty will not open the door that the contestant initially chooses. The contestant knows $p$ but does not know the outcome of the coin flip. When the show starts, the contestant chooses a door. Monty (who knows where the car is) then opens a door. If the car is revealed, the game is over; if a goat is revealed, the contestant is offered the option of switching. Now suppose it turns out that the contestant chooses door 1 and then Monty opens door 2, revealing a goat. What is the contestant’s probability of success if they switch to door 3?

Solution:

* Let $C_1$, $C_2$ and $C_3$ be the events that the car behind the door 1, 2 and 3, respectively.
* Let $D_2$ be the event that Monty opens door 2 and reveals a goat.
* Let $H$ be the event that the coin is head.

Equivalently, what we need to find is the probability that the car is behind door 3 given Monty opens door 2, we have
$$
P(C_3 \mid D_2) = \frac{P(D_2 \mid C_3) P(C_3)}{P(D_2)}
$$

Consider $P(D_2)$ separately. Because the game did not end with Monty opened a door with a car, the car is not behind door 2. So we have
$$
P(D_2) = P(D_2 \mid C_1) P(C_1) + P(D_2 \mid C_3) P(C_3)
$$

Monty opens the door depends on the state of the coin.
$$
\begin{aligned}
P(D_2 \mid C_1) &= P(D_2 \mid C_1, H)P(H) + P(D_2 \mid C_1, H^c)P(H^c) \\
&= \frac{1}{2} \cdot p + \frac{1}{2} \cdot (1 - p) = \frac{1}{2}
\end{aligned}
$$

$$
\begin{aligned}
P(D_2 \mid C_3) &= P(D_2 \mid C_3, H)P(H) + P(D_2 \mid C_3, H^c)P(H^c) \\
&= 1 \cdot p + \frac{1}{2} \cdot (1 - p) = \frac{p + 1}{2}
\end{aligned}
$$

Hence
$$
\begin{aligned}
P(D_2) &= P(D_2 \mid C_1) P(C_1) + P(D_2 \mid C_3) P(C_3) \\
&= \frac{1}{2} \cdot \frac{1}{3} + \frac{p+1}{2} \cdot \frac{1}{3} \\
&= \frac{p+2}{6}
\end{aligned}
$$

Therefore
$$
\begin{aligned}
P(C_3 \mid D_2) &= \frac{P(D_2 \mid C_3) P(C_3)}{P(D_2)} \\
&= \frac{\frac{p + 1}{2} \cdot \frac{1}{3}}{\frac{p+2}{6}} \\
&= \frac{p+1}{p+2}
\end{aligned}
$$

### Q42

Consider the following variation of the Monty Hall problem, where in some situations Monty may not open a door and give the contestant the choice of whether to switch doors. Specifically, there are 3 doors, with 2 containing goats and 1 containing a car. The car is equally likely to be anywhere, and Monty knows where the car is. Let $0 \le p \le 1$. The contestant chooses a door. If this initial choice has the car, Monty will open another door, revealing a goat (choosing with equal probabilities among his two choices of door),
and then offer the contestant the choice of whether to switch to the other unopened door. If the contestant’s initial choice has a goat, then with probability $p$ Monty will open another door, revealing a goat, and then offer the contestant the choice of whether to switch to the other unopened door; but with probability $1−p$, Monty will not open a door, and the contestant must stick with their initial choice.
The contestant decides in advance to use the following strategy: initially choose door 1. Then, if Monty opens a door and offers the choice of whether to switch, do switch.

(a) Find the unconditional probability that the contestant will get the car. Also, check what your answer reduces to in the extreme cases $p=0$ and $p=1$, and briefly explain why your answer makes sense in these two cases.

(b) Monty now opens door 2, revealing a goat. So the contestant switches to door 3. Given this information, find the conditional probability that the contestant will get the car.

Solution:

(a)

* Let $W$ be the event that the contestant follows the switching strategy and wins.
* Let $C_1$, $C_2$ and $C_3$ be the events that the car behind the doors 1, 2 and 3, respectively.
* Let $A$ be the event that Monty allow the contestant to switch.

We have
$$
P(W) = P(W \mid C_1) P(C_1) + P(W \mid C_2) P(C_2) + P(W \mid C_3) P(C_3)
$$

Depends on if Monty allow the contestant to choose, We have
$$
\begin{aligned}
P(W \mid C_1) &= 0
\end{aligned}
$$

$$
\begin{aligned}
P(W \mid C_2) &= P(W \mid C_2, A) P(A \mid C_2) + P(W \mid C_2, A^c) P(A^c \mid C_2) \\
&= 1 \cdot p + 0 \cdot (1 - p)
\end{aligned}
$$

$$
\begin{aligned}
P(W \mid C_3) &= P(W \mid C_3, A) P(A \mid C_3) + P(W \mid C_3, A^c) P(A^c \mid C_3) \\
&= 1 \cdot p + 0 \cdot (1 - p)
\end{aligned}
$$

Hence
$$
\begin{aligned}
P(W) &= P(W \mid C_1) P(C_1) + P(W \mid C_2) P(C_2) + P(W \mid C_3) P(C_3) \\
&= 0 \cdot \frac{1}{3} + p \cdot \frac{1}{3} + p \cdot \frac{1}{3} \\
&= \frac{2p}{3}
\end{aligned}
$$

* If $p=0$, then when the initial choice contains a goat, Monty does not offer a switch, so the contestant remains with the goat. When the initial choice contains the car, Monty offers a switch, and the contestant switches away from the car. Thus, the contestant loses in every case.
* If $p=1$, Monty always allow the contestant to switch, and the result agrees with our previous calculation.

(b)

* Let $C_1$, $C_2$ and $C_3$ be the events that the car behind the doors 1, 2 and 3, respectively.
* Let $O_2$ be the event that Monty opened door 2 and revealed a goat.
* Let $A$ be the event that Monty allow the contestant to switch.

Equivalently, this is to find
$$
\begin{aligned}
P(C_3 \mid O_2) &= \frac{P(O_2 \mid C_3) P(C_3)}{P(O_2)} \\
&= \frac{P(O_2 \mid C_3) P(C_3)}{P(O_2 \mid C_1) P(C_1) + P(O_2 \mid C_3) P(C_3)}
\end{aligned}
$$

We know that
$$
P(O_2 \mid C_1) = \frac{1}{2}
$$

If the contestant did choose the door initially, depends on if Monty allows the switching, we have
$$
\begin{aligned}
P(O_2 \mid C_3) &= P(O_2 \mid C_3, A) P(A \mid C_3) + P(O_2 \mid C_3, A^c) P(A^c \mid C_3) \\
&= 1 \cdot p + 0 \\
&= p
\end{aligned}
$$

Therefore
$$
\begin{aligned}
P(C_3 \mid O_2)
&= \frac{P(O_2 \mid C_3) P(C_3)}{P(O_2 \mid C_1) P(C_1) + P(O_2 \mid C_3) P(C_3)} \\
&= \frac
{p \cdot \frac{1}{3}}
{\frac{1}{2} \cdot \frac{1}{3} + 0 + p \cdot \frac{1}{3}} \\
&= \frac{2p}{1+2p}
\end{aligned}
$$

### Q43

You are the contestant on the Monty Hall show. Monty is trying out a new version of his game, with rules as follows. You get to choose one of three doors. One door has a car behind it, another has a computer, and the other door has a goat (with all permutations equally likely). Monty, who knows which prize is behind each door, will open a door (but not the one you chose) and then let you choose whether to switch from your current choice to the other unopened door.

Assume that you prefer the car to the computer, the computer to the goat, and (by transitivity) the car to the goat.

(a) Suppose for this part only that Monty always opens the door that reveals your less preferred prize out of the two alternatives, e.g., if he is faced with the choice between revealing the goat or the computer, he will reveal the goat. Monty opens a door, revealing a goat (this is again for this part only). Given this information, should you switch? If you do switch, what is your probability of success in getting the car?

(b) Now suppose that Monty reveals your less preferred prize with probability $p$, and your more preferred prize with probability $q = 1−p$. Monty opens a door, revealing a computer. Given this information, should you switch (your answer can depend on $p$)? If you do switch, what is your probability of success in getting the car (in terms of $p$)?

Solution:

(a)

* Let $W$ be the event that the contestant uses the switch strategy and wins.
* Let $C_1$, $C_2$ and $C_3$ be the events that the car behind the doors 1, 2 and 3, respectively.
* Let $G$ be the event that Monty opens a door, revealing a goat.

Without lose the generality, suppose the contestant choose door 1. If Monty reveals a goat, The remaining is a car and a computer. There are 4 equally likely possible arrangement.

* {Car, Computer, Goat}
* {Car, Goat, Computer}
* {Computer, Car, Goat}
* {Computer, Goat, Car}

Therefore
$$
P(C_1 \mid G) = \frac{1}{2}
P(C_2 \mid G) = \frac{1}{4}
P(C_3 \mid G) = \frac{1}{4}
$$

So we have
$$
\begin{aligned}
P(W \mid G) &= P(W \mid C_1, G) P(C_1 \mid G) + P(W \mid C_2, G) P(C_2 \mid G) + P(W \mid C_3, G)(C_3 \mid G) \\
&= 0 \cdot \frac{1}{2} + 1 \cdot \frac{1}{4} + 1 \cdot \frac{1}{4} \\
&= \frac{1}{2}
\end{aligned}
$$

Compare with the do-not-switch strategy, of which $P(W) = P(C_1) = \frac{1}{3}$, the switch strategy increase the probability of winning to $\frac{1}{2}$.

(b)

* Let $W$ be the event that the contestant uses the switch strategy and wins.
* Let $C_1$, $C_2$ and $C_3$ be the events that the car behind the doors 1, 2 and 3, respectively.
* Let $T$ be the event that Monty opens a computer.
* Let $L$ be the event that Monty reveals a less preferred prize.

Here are all equally likely possible outcomes of the arrangement.

$$
\begin{array}{c|c|c|c|c|c}

\text{Case}&\text{Door 1}&\text{Door 2}&\text{Door 3}&\text{Reveal less preferred}&\text{Reveal more preferred}\\

\hline

1&Car&Computer&Goat&Goat&Computer\\

2&Car&Goat&Computer&Goat&Computer\\

3&Goat&Car&Computer&Computer&Car\\

4&Goat&Computer&Car&Computer&Car\\

5&Computer&Car&Goat&Goat&Car\\

6&Computer&Goat&Car&Goat&Car\\

\end{array}
$$

Given Monty reveals a computer, we only need to consider the cases 1, 2, 3 and 4.

By the LOTP, we have
$$
P(W \mid T) = P(W \mid C_1, T)P(C_1 \mid T) + P(W \mid C_2, T)P(C_2 \mid T) + P(W \mid C_3, T)P(C_3 \mid T)
$$

Because the contestant uses the switch strategy, $P(W \mid C_1, T) = 0$.

Conditioning on $L$, we have
$$
\begin{aligned}
P(C_2 \mid T) &= P(C_2 \mid T, L) P(L \mid T) + P(C_2 \mid L^c, T) P(L^c \mid T)
\end{aligned}
$$

Given $T \cap L$, only case 3 and 4 remains. They are equally likely, because

* They have the same prior $\frac{1}{6}$.
* They are generated by the same probability $p$.

So
$$
P(C_2 \mid T, L) = \frac{1}{2}
$$

Given $T \cap L^c$, only case 1 and 2 remains. But no car behind door 2, so
$$
P(C_2 \mid T, L^c) = 0
$$

Now consider $P(L \mid T)$ and $P(L^c \mid T)$.
$$
\begin{aligned}
P(L \mid T) &= \frac{P(T \mid L)P(L)}{P(T \mid L)P(L) + P(T \mid L^c)P(L^c)} \\
&= \frac{\frac{1}{3} \cdot p}{\frac{1}{3} \cdot p + \frac{1}{3} \cdot (1-p)} \\
&= p
\end{aligned}
$$

$$
\begin{aligned}
P(L^c \mid T) &= \frac{P(T \mid L^c)P(L^c)}{P(T \mid L)P(L) + P(T \mid L^c)P(L^c)} \\
&= \frac{\frac{1}{3} \cdot (1-p)}{\frac{1}{3} \cdot p + \frac{1}{3} \cdot (1-p)} \\
&= 1-p
\end{aligned}
$$

Therefore
$$
\begin{aligned}
P(C_2 \mid T) &= P(C_2 \mid T, L) P(L \mid T) + P(C_2 \mid L^c, T) P(L^c \mid T) \\
&= \frac{1}{2} \cdot p + 0 \cdot (1 - p) \\
&= \frac{p}{2}
\end{aligned}
$$

Similarly
$$
\begin{aligned}
P(C_3 \mid T) &= P(C_3 \mid T, L) P(L \mid T) + P(C_3 \mid L^c, T) P(L^c \mid T) \\
&= \frac{1}{2} \cdot p + 0 \cdot (1 - p) \\
&= \frac{p}{2}
\end{aligned}
$$

Therefore
$$
\begin{aligned}
P(W \mid T) &= P(W \mid C_1, T)P(C_1 \mid T) + P(W \mid C_2, T)P(C_2 \mid T) + P(W \mid C_3, T)P(C_3 \mid T) \\
&=0 + P(W \mid C_2, T) \cdot \frac{p}{2} + P(W \mid C_3, T) \cdot \frac{p}{2} \\
&= 1 \cdot \frac{p}{2} + 1 \cdot \frac{p}{2} \\
&= p
\end{aligned}
$$

Let $W_0$ be the event that the contestant choose not to switch.

$$
\begin{aligned}
P(W_0 \mid T) &= P(W_0 \mid C_1, T)P(C_1 \mid T) + P(W_0 \mid C_2, T)P(C_2 \mid T) + P(W_0 \mid C_3, T)P(C_3 \mid T) \\
&=1 \cdot P(C_1 \mid T) + 0 \cdot \frac{p}{2} + 0 \cdot \frac{p}{2} \\
&= P(C_1 \mid T)
\end{aligned}
$$

Similarly
$$
\begin{aligned}
P(C_1 \mid T) &= P(C_1 \mid T, L) P(L \mid T) + P(C_1 \mid L^c, T) P(L^c \mid T) \\
&= 0 \cdot p + 1 \cdot (1 - p) \\
&= 1- p
\end{aligned}
$$

So
$$
P(W_0 \mid T) = 1 - p
$$

When the contestant should switch when
$$
P(W \mid T) = p \gt P(W_0 \mid T) = 1-p \iff p \gt \frac{1}{2}
$$

### Q44

Monty Hall has introduced a new twist in his game, by generalizing the assumption that
the initial probabilities for where the car is are $(\frac{1}{3}, \frac{1}{3}, \frac{1}{3})$. Specifically, there are three doors, behind one of which there is a car (which the contestant wants), and behind the other two of which there are goats (which the contestant doesn’t want). Initially, door $i$ has probability $p_i$ of having the car, where $p_1$, $p_2$, $p_3$ are known constants such that
$0 < p_1 \le p_2 \le p_3 < 1$ and $p_1 + p_2 + p_3 = 1$. The contestant chooses a door. Then Monty opens a door (other than the one the contestant chose) and offers the contestant the option of switching to the other unopened door.

(a) Assume for this part that Monty knows in advance which door has the car. He always opens a door to reveal a goat, and if he has a choice of which door to open he chooses
with equal probabilities. Suppose for this part that the contestant initially chooses door 3, and then Monty opens door 2, revealing a goat. Given the above information, find
the conditional probability that door 3 has the car. Should the contestant switch doors? (If whether to switch depends on the $p_i$’s, give a fully simplified criterion in terms of the $p_i$’s.)

(b) Now assume instead that Monty does not know in advance where the car is. He randomly chooses which door to open (other than the one the contestant chose), with
equal probabilities. (The game is spoiled if he reveals the car.) Suppose again that the contestant initially chooses door 3, and then Monty opens door 2, revealing a goat. Given the above information, find the conditional probability that door 3 has the car. Should the contestant switch doors? (If whether to switch depends on the $p_i$’s, give a fully simplified criterion in terms of the $p_i$’s.)

(c) Repeat (a), except with the contestant initially choosing door 1 rather than door 3.

(d) Repeat (b), except with the contestant initially choosing door 1 rather than door 3.

Solution:

* Let $C_1$, $C_2$, and $C_3$ be the events that the cars are behind door 1, 2 and 3, respectively.

* Let $G_2$ be the event that Monty opens door 2 and reveals a goat.

* Let $W_0$ be the event that the contestant does not switch and wins.

* Let $W_1$ be the event that the contestant switches and wins.

(a)

If the contestant chooses not to switch, from the LOTP, we have
$$
\begin{aligned}
P(W_0 \mid G_2) &=
P(W_0 \mid C_1, G_2) P(C_1 \mid G_2) +
P(W_0 \mid C_2, G_2) P(C_2 \mid G_2) +
P(W_0 \mid C_3, G_2) P(C_3 \mid G_2)
\end{aligned}
$$

First find out the weights.
$$
\begin{aligned}
P(C_1 \mid G_2) &= \frac
{P(G_2 \mid C_1) P(C_1)}
{P(G_2 \mid C_1)P(C_1) + P(G_2 \mid C_2)P(C_2) + P(G_2 \mid C_3)P(C_3)} \\

&= \frac
{1 \cdot p_1}
{1 \cdot p_1 + 0 \cdot p_2 + \frac{1}{2} \cdot p_3} \\

&= \frac{2 p_1}{2 p_1 + p_3} \\

P(C_2 \mid G_2) &= 0 \\

P(C_3 \mid G_2) &= \frac{P(G_2 \mid C_3) P(C_3)}{P(G_2 \mid C_1)P(C_1) + P(G_2 \mid C_2)P(C_2) + P(G_2 \mid C_3)P(C_3)} \\
&= \frac
{\frac{1}{2} \cdot p_3}
{1 \cdot p_1 + 0 \cdot p_2 + \frac{1}{2} \cdot p_3} \\
&= \frac{p_3}{2 p_1 + p_3} \\
\end{aligned}
$$

Hence
$$
\begin{aligned}
P(W_0 \mid G_2) &=
P(W_0 \mid C_1, G_2) P(C_1 \mid G_2) +
P(W_0 \mid C_2, G_2) P(C_2 \mid G_2) +
P(W_0 \mid C_3, G_2) P(C_3 \mid G_2) \\

&= 0 + 0 + 1 \cdot \frac{p_3}{2 p_1 + p_3} \\

&= \frac{p_3}{2 p_1 + p_3}
\end{aligned}
$$

If the contestant chooses to switch, from the LOTP, we have:
$$
\begin{aligned}
P(W_1 \mid G_2) &=
P(W_1 \mid C_1, G_2) P(C_1 \mid G_2) +
P(W_1 \mid C_2, G_2) P(C_2 \mid G_2) +
P(W_1 \mid C_3, G_2) P(C_3 \mid G_2)
\end{aligned}
$$

The weights keep the same as if the contestant doesn't not switch. Hence
$$
\begin{aligned}
P(W_1 \mid G_2) &=
P(W_1 \mid C_1, G_2) P(C_1 \mid G_2) +
P(W_1 \mid C_2, G_2) P(C_2 \mid G_2) +
P(W_1 \mid C_3, G_2) P(C_3 \mid G_2) \\

&= 1 \cdot \frac{2 p_1}{2 p_1 + p_3} + 0 + 0 \\

&= \frac{2 p_1}{2 p_1 + p_3}
\end{aligned}
$$

So the conditional probability of door 3 has the car is:
$$
P(C_3 \mid G_2) = \frac{p_3}{2 p_1 + p_3}
$$

And when $2 p_1 \gt p_3$, the contestant should use the switch strategy.

(b)

If the contestant chooses to not switch, the probability of winning is the same as the probability that the car is behind the door 3.
$$
\begin{aligned}
P(C_3 \mid G_2)
&= \frac{P(G_2 \mid C_3) P(C_3)}{P(G_2 \mid C_1)P(C_1) + P(G_2 \mid C_2)P(C_2) + P(G_2 \mid C_3)P(C_3)} \\
&=\frac{0.5 \cdot p_3}{0.5 \cdot p_1 + 0 \cdot p_2 + 0.5 \cdot p_3} \\
&= \frac{p_3}{p_1 + p_3}
\end{aligned}
$$

If the contestant chooses to switch, the probability of winning is the same as the probability that the car is behind the door 1.
$$
\begin{aligned}
P(C_1 \mid G_2)
&= \frac{P(G_2 \mid C_1) P(C_1)}{P(G_2 \mid C_1)P(C_1) + P(G_2 \mid C_2)P(C_2) + P(G_2 \mid C_3)P(C_3)} \\
&=\frac{0.5 \cdot p_1}{0.5 \cdot p_1 + 0 \cdot p_2 + 0.5 \cdot p_3} \\
&= \frac{p_1}{p_1 + p_3}
\end{aligned}
$$

So, the conditional probability that the car is behind door 3 is
$$
P(C_3 \mid G_2) = \frac{p_3}{p_1 + p_3}
$$
And if $p_1 > p_3$ the contestant should switch the choosing door.

(c)
Now the contestant chooses door 1 initially. The probability that the car is behind door 1 is
$$
\begin{aligned}
P(C_1 \mid G_2)
&= \frac{P(G_2 \mid C_1) P(C_1)}{P(G_2 \mid C_1)P(C_1) + P(G_2 \mid C_2)P(C_2) + P(G_2 \mid C_3)P(C_3)} \\
&=\frac{0.5 \cdot p_1}{0.5 \cdot p_1 + 0 \cdot p_2 + 1 \cdot p_3} \\
&= \frac{p_1}{p_1 + 2 p_3}
\end{aligned}
$$

So the probability of winning if the contestant doesn't switch is
$$
P(C_1 \mid G_2) = \frac{p_1}{p_1 + 2 p_3}
$$

The probability of winning if the contestant chooses to switch is
$$
\begin{aligned}
P(C_3 \mid G_2)
&= \frac{P(G_2 \mid C_3) P(C_3)}{P(G_2 \mid C_1)P(C_1) + P(G_2 \mid C_2)P(C_2) + P(G_2 \mid C_3)P(C_3)} \\
&=\frac{1 \cdot p_3}{0.5 \cdot p_1 + 0 \cdot p_2 + 1 \cdot p_3} \\
&= \frac{2 p_3}{p_1 + 2 p_3}
\end{aligned}
$$

So when $2 p_3 > p1$ the contestant should switch. And because $0 < p_1 \le p_2 \le p_3 < 1$, the contestant should always switch.

(d)

If the contestant chooses to not switch, the probability of winning is the same as the probability that the car is behind the door 1.
$$
\begin{aligned}
P(C_1 \mid G_2)
&= \frac{P(G_2 \mid C_1) P(C_1)}{P(G_2 \mid C_1)P(C_1) + P(G_2 \mid C_2)P(C_2) + P(G_2 \mid C_3)P(C_3)} \\
&=\frac{0.5 \cdot p_1}{0.5 \cdot p_1 + 0 \cdot p_2 + 0.5 \cdot p_3} \\
&= \frac{p_1}{p_1 + p_3}
\end{aligned}
$$

If the contestant chooses to switch, the probability of winning is the same as the probability that the car is behind the door 3.
$$
\begin{aligned}
P(C_3 \mid G_2)
&= \frac{P(G_2 \mid C_3) P(C_3)}{P(G_2 \mid C_1)P(C_1) + P(G_2 \mid C_2)P(C_2) + P(G_2 \mid C_3)P(C_3)} \\
&=\frac{0.5 \cdot p_3}{0.5 \cdot p_1 + 0 \cdot p_2 + 0.5 \cdot p_3} \\
&= \frac{p_3}{p_1 + p_3}
\end{aligned}
$$

So, the conditional probability that the car is behind door 1 is
$$
P(C_1 \mid G_2) = \frac{p_1}{p_1 + p_3}
$$
And if $p_3 > p_1$ the contestant should switch the choosing door.

### Q45

Monty Hall is trying out a new version of his game. In this version, instead of there always being 1 car and 2 goats, the prizes behind the doors are generated independently, with each door having probability $p$ of having a car and $q=1−p$ of having a goat. In detail: There are three doors, behind each of which there is one prize: either a car or a goat. For each door, there is probability $p$ that there is a car behind it and $q=1−p$ that there is a goat, independent of the other doors.

The contestant chooses a door. Monty, who knows the contents of each door, then opens one of the two remaining doors. In choosing which door to open, Monty will always reveal a goat if possible. If both of the remaining doors have the same kind of prize, Monty chooses randomly (with equal probabilities). After opening a door, Monty offers the contestant the option of switching to the other unopened door. The contestant decides in advance to use the following strategy: First choose door 1. Then, after Monty opens a door, switch to the other unopened door.

(a) Find the unconditional probability that the contestant will get a car.

(b) Monty now opens door 2, revealing a goat. Given this information, find the conditional probability that the contestant will get a car.

Answer:

(a)

The table below shows the possible outcomes of door 2 and 3, and the behavior of Monty:
$$
\begin{array}{c|c|c|c|c}

\text{Case}&\text{Door 2}&\text{Door 3}&\text{Monty's behavior}&\text{Result}\\

\hline

1&\text{Car}&\text{Car}&\text{Random}&\text{Win}\\

2&\text{Car}&\text{Goat}&\text{Open door 3}&\text{Win}\\

3&\text{Goat}&\text{Car}&\text{Open door 2}&\text{Win}\\

4&\text{Goat}&\text{Goat}&\text{Random}&\text{Lose}\\

\end{array}
$$

* Let $C_1$, $C_2$ and $C_3$ be the events that a car is behind door 1, 2 and 3, respectively.
* Let $W$ be the event that the contestant win a car.

By LOTP we have:
$$
\begin{aligned}
P(W)
&= P(W \mid C_2, C_3) P(C_3, C_3) + P(W \mid C_2, C_3^c) P(C_2, C_3^c) + P(W \mid C_2^c, C_3) P(C_2^c, C_3) + P(W \mid C_2^c, C_3^c) P(C_2^c, C_3^c) \\
&= 1 \cdot p^2 + 1 \cdot pq + 1 \cdot qp + 0 \cdot q^2 \\
&= p^2 + 2pq
\end{aligned}
$$

(b)

The observed information is that Monty opens door 2 and reveals a goat. Only cases 3 and 4 are compatible with this observation.

* Let $C_1$, $C_2$ and $C_3$ be the events that a car is behind door 1, 2 and 3, respectively.
* Let $O_2$ be the event that Monty opens door 2 and reveals a goat.

By Bayes' rule, we have
$$
\begin{aligned}
P(C_3 \mid O_2) = \frac{P(O_2 \mid C_3)P(C_3)}{P(O_2)}
\end{aligned}
$$

By LOTP we have
$$
\begin{aligned}
P(O_2)
&= P(O_2 \mid C_2^c, C_3) P(C_2^c, C_3) + P(O_2 \mid C_2^c, C_3^c)P(C_2^c, C_3^c) \\
&= 1 \cdot qp + 0.5 \cdot q^2
\end{aligned}
$$

To find the likelihood, we can condition on the contents of door \(2\).
$$
\begin{aligned}
P(O_2 \mid C_3)
&= P(O_2 \mid C_2, C_3) P(C_2 \mid C_3) + P(O_2 \mid C_2^c, C_3) P(C_2^c \mid C_3) \\
&= P(O_2 \mid C_2, C_3) P(C_2) + P(O_2 \mid C_2^c, C_3) P(C_2^c) \\
&= 0 \cdot p + 1 \cdot q \\
&= q
\end{aligned}
$$

Therefore, we have
$$
\begin{aligned}
P(C_3 \mid O_2)
&= \frac{P(O_2 \mid C_3)P(C_3)}{P(O_2)} \\
&=\frac{q \cdot p}{1 \cdot qp + 0.5 \cdot q^2} \\
&=\frac{2pq}{2pq + q^2} \\
\end{aligned}
$$

### Q46

Monty Hall is trying out a new version of his game, with rules as follows. The contestant gets to choose one of four doors. One door has a car behind it, another has an apple, another has a book, and another has a goat. All 24 permutations for which door has which prize are equally likely. In order from least preferred to most preferred, the contestant’s preferences are: goat, apple, book, car.

Monty, who knows which prize is behind each door, will open a door (other than the contestant’s initial choice) and then let the contestant choose whether to switch to another unopened door. Monty will reveal the least preferred prize (among the 3 doors other than the contestant’s initial choice) with probability $p$, the intermediately preferred prize with probability $1−p$, and the most preferred prize never.

The contestant decides in advance to use the following strategy: Initially choose door 1. After Monty opens a door, switch to one of the other two unopened doors, randomly choosing between them (with probability 1/2 each).

(a) Find the unconditional probability that the contestant will get the car.

Hint: Condition on where the car is.

(b) Find the unconditional probability that Monty will reveal the apple.

Hint: Condition on what is behind door 1.

(c) Monty now opens a door, revealing the apple. Given this information, find the conditional probability that the contestant will get the car.

Answer:

(a)

There are $4!$ possible permutations of the prizes. But for the contestant to win the car must initially be behind the door 2, 3 or 4, and by symmetry, there are $\frac{3}{4} 4! = 18$ such kinds of permutations. Monty never reveals the car, and the contestant chooses uniformly the two remaining doors, exactly one of which contains the car. So the probability for the contestant to win is
$$
\frac{9}{4!} = \frac{3}{8}
$$

(b)

* Let $G_1,\ldots,G_4$ be the events that the goat is behind door 1, 2, 3 and 4, respectively.
* Let $A_1,\ldots,A_4$ be the events that the apple is behind door 1, 2, 3 and 4, respectively.
* Let $B_1,\ldots,B_4$ be the events that the book is behind door 1, 2, 3 and 4, respectively.
* Let $C_1,\ldots,C_4$ be the events that the car is behind door 1, 2, 3 and 4, respectively.
* Let $R_A$ be the event that Monty reveals the apple.

Conditioned on the prize behind the door 1, we have
$$
\begin{aligned}
P(R_A)
&= P(R_A \mid G_1)P(G_1) + P(R_A \mid A_1)P(A_1) + P(R_A \mid B_1)P(B_1) + P(R_A \mid C_1)P(C_1) \\
&= p \cdot \frac{1}{4} + 0 \cdot \frac{1}{4} + (1 - p) \cdot \frac{1}{4} + (1 - p) \cdot \frac{1}{4} \\
&= \frac{2 - p}{4}
\end{aligned}
$$

(c)

Based on (b), and

* Let $W$ be the event that the contestant wins a car.

$$
\begin{aligned}
P(W \mid R_A)
&= \frac{P(W \cap R_A)}{P(R_A)}
\end{aligned}
$$

And because
$$
\begin{aligned}
P(W \cap R_A)
&= P(W \cap R_A \mid G_1)P(G_1) + P(W \cap R_A \mid A_1)P(A_1) + P(W \cap R_A \mid B_1)P(B_1) + P(W \cap R_A \mid C_1)P(C_1) \\
&= \frac{1}{2} \cdot p \cdot \frac{1}{4} + 0 + \frac{1}{2} \cdot (1 - p) \cdot \frac{1}{4} + 0 \\
&= \frac{p}{8} + \frac{1 - p}{8} \\
&= \frac{1}{8}
\end{aligned}
$$

Therefore
$$
\begin{aligned}
P(W \mid R_A)
&= \frac{P(W \cap R_A)}{P(R_A)} \\
&= \frac{\frac{1}{8}}{\frac{2-p}{4}} \\
&= \frac{1}{4-2p}
\end{aligned}
$$
