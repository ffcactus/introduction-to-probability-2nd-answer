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
