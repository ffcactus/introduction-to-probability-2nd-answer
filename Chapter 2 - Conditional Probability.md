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

**Q12**

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

**Q13**

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

**Q14**

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

**Q15**

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

**Q16**

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

**Q17**

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

**Q18**

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

**Q19**

Explain the following Sherlock Holmes saying in terms of conditional probability, carefully distinguishing between prior and posterior probabilities: "It is an old maxim of mine that when you have excluded the impossible, whatever remains, however improbable, must be the truth."

Solution: Skip

**Q20**

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

**Q21**

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

**Q22**

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

**Q23**

Let $G$ be the event that a certain individual is guilty of a certain robbery. In gathering
evidence, it is learned that an event $E_1$ occurred, and a little later it is also learned that
another event $E_2$ also occurred. Is it possible that individually, these pieces of evidence increase the chance of guilt (so $P(G \mid E_1) \gt P(G)$ and $P(G \mid E_2) \gt P(G)$), but together
they decrease the chance of guilt (so $P(G \mid E_1,E_2) \lt P(G)$)?

Solution: Skip.

**Q24**

Is it possible to have events $A_1$, $A_2$, $B$, $C$ with $P(A_1 \mid B) \gt P(A_1 \mid C)$ and $P(A_2 \mid B) \gt P(A_2 \mid C)$, yet $P(A_1 \cup A_2 \mid B) \lt P(A_1 \cup A_2 \mid C)$? If so, find an example (with a “story”
interpreting the events, as well as giving specific numbers); otherwise, show that it is
impossible for this phenomenon to happen.





