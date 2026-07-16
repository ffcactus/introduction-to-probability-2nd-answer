# Chapter 1 Probability and Counting

**Q4**

A round-robin tournament is being held with n tennis players; this means that every player will play against every other player exactly once.

(a) How many possible outcomes are there for the tournament (the outcome lists out who won and who lost for each game)?

(b) How many games are played in total?

Answer:

(a) Choose an unordered pair of players, the number of the subset is:
$$
\binom{n}{2}
$$
Each subset has 2 possible outcomes, so the possible coutcomes are:
$$
2^{\binom{n}{2}}
$$

(b) Each subset plays a game, so there are $\binom{n}{2}$ games are played in total.

**Q5**

A knock-out tournament is being held with $2^n$ tennis players. This means that for each round, the winners move on to the next round and the losers are eliminated, until only one person remains. For example, if initially there are $2^4 = 16$ players, then there are 8 games in the first round, then the 8 winners move on to round 2, then the 4 winners move on to round 3, then the 2 winners move on to round 4, the winner of which is declared the winner of the tournament. (There are various systems for determining who plays whom within a round, but these do not matter for this problem.)

(a) How many rounds are there?

(b) Count how many games in total are played, by adding up the numbers of games played in each round.

(c) Count how many games in total are played, this time by directly thinking about it without doing almost any calculation.
Hint: How many players need to be eliminated?

Answer:

(a) Each round eliminates half of the players. For $2^n$ players, we need $n$ rounds.

(b) The first round needs $\frac{2^n}{2} = 2^{n-1}$ games. Each game produces a winner so $2^{n-1}$ players advance to the next round. Consequently, the second round has $2^{n-2}$ games. Continuing in this way, the total number of games is:
$$
\sum_{i=1}^n \frac{2^n}{2^i}
$$

(c) Each game eliminate 1 player, and we need to eliminate $2^n-1$ players, so the number of games in total is $2^n-1$.

**Q6**

There are 20 people at a chess club on a certain day. They each find opponents and start playing. How many possibilities are there for how they are matched up, assuming that in each game it does matter who has the white pieces (in a chess game, one player has the white pieces and the other player has the black pieces)?

Answer:

Arrange the 20 players in a line. Pair the first two players, the next two players, and so on. Within each pair assign the white pieces to the players who appears first in the line. 
There are $20!$ possible lines. However this method overcounts because the ten games can appear in any order without changing the final matching. For each matching, the ten pairs can be arranged in $10!$ different orders. Therefore, the possibilities of how they are matched up are:
$$
\frac{20!}{10!}
$$