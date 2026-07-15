# Chapter 1 Probability and Counting

**Q4**

A round-robin tournament is being held with n tennis players; this means that every player will play against every other player exactly once.

(a) How many possible outcomes are there for the tournament (the outcome lists out who won and who lost for each game)?

(b) How many games are played in total?

Answer:

(a) Take two players as a subset, the number of the subset is:
$$
\binom{n}{2}
$$
Each subset has 2 possible outcomes, so the possible coutcomes are:
$$
2^{\binom{n}{2}}
$$

(b) Each subset plays a game, so there are $\binom{n}{2}$ games are played in total.
