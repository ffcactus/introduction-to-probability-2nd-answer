**Q1**

How many ways are there to permute the letters in the word MISSISSIPPI?

Answer:

The word "MISSISSIPPI" has 11 characters, if we temporary label all repeated letters so that they are distinguishable, there are $11!$ possible permutations. However permuting the four I's among themselves does not change the resulting word, so each distinct permutation counted $4!$ times. Similarly, we also need to divide $4!$ for letter S, and $2!$ for letter P. We end up with:

$$
\frac{11!}{4! 4! 2!} = 54650
$$

**Q2**

(a) How many 7-digit phone numbers are possible, assuming that the first digit can’t be a 0 or a 1?

(b) Re-solve (a), except now assume also that the phone number is not allowed to start with 911 (since this is reserved for emergency use, and it would not be desirable for the system to wait to see whether more digits were going to be dialed after someone has dialed 911).

Answer:

(a) The first digit have 8 choices, the remaining 6-digit number have $10^6$ choice, the total is $8 * 10^6$.

(b) Among the $8*10^6$ possibility, there are $10^4$ numbers beginning with 911, so the possible number is $8*10^6 - 10^4$.

**Q3**

Fred is planning to go out to dinner each night of a certain week, Monday through Friday, with each dinner being at one of his ten favorite restaurants.

(a) How many possibilities are there for Fred’s schedule of dinners for that Monday through Friday, if Fred is not willing to eat at the same restaurant more than once?

(b) How many possibilities are there for Fred’s schedule of dinners for that Monday through Friday, if Fred is willing to eat at the same restaurant more than once, but is not willing to eat at the same place twice in a row (or more)?

Answer:

(a) This is sampling without replacement. We have 10 choices, sampling 5 times, the result is $10 * 9 * 8 * 7 * 6 = 30240$.

(b) To not eat at the same place in a row, we have 10 choices at the Monday, but only have 9 choices after that, so the choice is $10 * 9 * 9 * 9 * 9 = 65610$.

**Q4**

A round-robin tournament is being held with $n$ tennis players; this means that every player will play against every other player exactly once.

(a) How many possible outcomes are there for the tournament (the outcome lists out who won and who lost for each game)?

(b) How many games are played in total?

Answer

(a) Each game is determined by choosing 2 players from $n$ players:
$$
\binom{n}{2}
$$
Each game has 2 possible outcomes, so the totally possible outcomes are:
$$
2 \binom{n}{2} = n(n-1)
$$

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

**Q7**

Two chess players, A and B, are going to play 7 games. Each game has three possible outcomes: a win for A (which is a loss for B), a draw (tie), and a loss for A (which is a win for B). A win is worth 1 point, a draw is worth 0.5 points, and a loss is worth 0
points.

(a) How many possible outcomes for the individual games are there, such that overall player A ends up with 3 wins, 2 draws, and 2 losses?

(b) How many possible outcomes for the individual games are there, such that A ends up with 4 points and B ends up with 3 points?

(c) Now assume that they are playing a best-of-7 match, where the match will end when either player has 4 points or when 7 games have been played, whichever is first. For example, if after 6 games the score is 4 to 2 in favor of A, then A wins the match and they don’t play a 7th game. How many possible outcomes for the individual games are there, such that the match lasts for 7 games and A wins by a score of 4 to 3?

Answer:

(a) First assign the 3 wins to the 7 games, there are $\binom{7}{3}$ possibilities. Then assign the 2 draws to the remaining 5 games, there are $\binom{5}{2}$ possibilities. Then assign the 2 losses to the remaining 2 games, there are 1 possibilities. By the multiplication rule, the number of the possible games are:
$$
\binom{7}{3} \binom{4}{2} = \frac{7!}{4!3!} \frac{4!}{2!2!} = 210
$$

(b) Each game awards a total of 1 point, gives it to the winner or gives 0.5 to the two players when it a draw. This means that the games that ends up with A having 4 points must ends up with B having 3 points, we only need to consider one player in the games.

The possibility of having 4 points can be:
1. 4 wins, 3 loses.
2. 3 wins, 2 draws, 2 lose.
3. 2 wins, 4 draws, 1 lose.
4. 1 win, 6 draws.

So the number of possible outcomes is:
$$
\binom{7}{4} + \binom{7}{3}\binom{4}{2} + \binom{7}{2}\binom{5}{4} + \binom{7}{1} 
= 35 + 35*6 + 21*5 + 7 = 357
$$

(c) If the seventh game is required, the only possibilities are that after the sixth game:
* Case 1, both A and B got 3 points. In this case, A must win to have exact 4 points after seventh game.
* Case 2, A has 3.5 points and B has 2.5 points. In this case, A must draw with B to have exact 4 points after the seventh game.

So the seventh game doesn't increase the possibilities. The number of the possibilities are determined in the first 6 games.

In the case 1, the possible outcomes of the first 6 games are:
1. A has 3 wins
2. A has 2 wins and 2 draws
3. A has 1 wins and 4 draws
4. A has 6 draws

The number of possibilities of this case is:
$$
\binom{6}{3} + \binom{6}{2}\binom{4}{2} + \binom{6}{1}\binom{5}{4} + \binom{6}{6}
= 20 + 15*6 + 6*5 + 1 = 141 
$$

In the case 2, the possible outcomes of the first 6 games are:
1. A has 3 wins and 1 draws
2. A has 2 wins and 3 draws
3. A has 1 wins and 5 draws

The number of possibilities of this case is:
$$
\binom{6}{3}\binom{3}{1} + \binom{6}{2}\binom{4}{3} + \binom{6}{1}\binom{5}{5}
= 20*3 + 15*4 + 6 = 126
$$

Combine the case 1 and case 2, we have $141 + 126 = 267$ possibilities.

**Q8**

(a) How many ways are there to split a dozen people into 3 teams, where one team has 2 people, and the other two teams have 5 people each?

(b) How many ways are there to split a dozen people into 3 teams, where each team has 4 people?

Answer:

(a) First select 2 people from 12 people to form the first team, the number of possibilities is $\binom{12}{2}$. Then select the 5 people from the 10 people to form the second team, the number of possibilities is $\binom{10}{5}$. The third team is determined after we form the first two teams. By multiplication rule, the number of ways is:
$$
\binom{12}{2} \binom{10}{5} = 66 * 252 = 16632
$$
However the second and third team are undistinguishable, each possible result is been counted $2!$ times. So the number of ways is $16632 / 2 = 8316$

(b) First select the 4 people from the 12 people to form the first team, the number of possibilities is $\binom{12}{4}$, Similarly, the number of possibilities for the second team is $\binom{8}{4}$, and the third team is determined. However, due to the same size, the three teams are undistinguishable. Each possible result is been counted $3!$ times in the process described above. So the number of ways is:
$$
\frac{\binom{12}{4}\binom{8}{4}}{3!} = \frac{495 * 70}{6} = 5775
$$

**Q9**

(a) How many paths are there from the point (0,0) to the point (110,111) in the plane such that each step either consists of going one unit up or one unit to the right?

(b) How many paths are there from (0,0) to (210,211), where each step consists of going one unit up or one unit to the right, and the path has to go through (110,111)?

Answer:

(a) Because the possible directions are up and right, the total steps must be $110 + 111 = 221$. From 221 steps we choose the 110 steps toward right, this determines the steps towards up. So the number of paths are:
$$
\binom{221}{110}
$$

(b) Suppose the number of paths from origin to middle point is $x$, and the number of paths from middle point to destination is $y$, the number of ways from origin to the destination is $x y$:
$$
xy=\binom{221}{110} \binom{200}{100}
$$

**Q10**

To fulfill the requirements for a certain degree, a student can choose to take any 7 out of a list of 20 courses, with the constraint that at least 1 of the 7 courses must be a statistics course. Suppose that 5 of the 20 courses are statistics courses.

(a) How many choices are there for which 7 courses to take?

(b) Explain intuitively why the answer to (a) is not $\binom{5}{1}\binom{19}{6}$.

Answer:

(a) Separate cases by the number of statistics course been chosen:
* Suppose only 1 statistics course has been chosen, the number of possibilities is $\binom{5}{1}\binom{15}{6}$
* Suppose 2 statistics courses have been chosen, the number of possibilities is $\binom{5}{2}\binom{15}{5}$
* Suppose 3 statistics courses have been chosen, the number of possibilities is $\binom{5}{3}\binom{15}{4}$
* Suppose 4 statistics courses have been chosen, the number of possibilities is $\binom{5}{4}\binom{15}{3}$
* Suppose 5 statistics courses have been chosen, the number of possibilities is $\binom{5}{5}\binom{15}{2}$

Sum them up to get all the possibilities:
$$
\binom{5}{1}\binom{15}{6}
+ \binom{5}{2}\binom{15}{5}
+ \binom{5}{3}\binom{15}{4}
+ \binom{5}{4}\binom{15}{3}
+ \binom{5}{5}\binom{15}{2}
$$

(b) $\binom{5}{1}\binom{19}{6}$ is counting on the number of the routings that taking 1 statistics course from the 5 statistics courses first, then taking 6 courses from the remaining 19 courses. But multiple routings can end up with a single distinct possibility. Suppose a final result contains both S1 and S2. The same result can arise by:
* Choosing S1 first, then choosing S2 among the remaining six
* Choosing S2 first, then choosing S1 among the remaining six.

Thus, the same final set is counted twice. More generally, a final set containing $k$ statistics courses is counted $k$ times, so the overcounting is not uniform.

**Q11**

Let $A$ and $B$ be sets with $|A|= n$, $|B|= m$.

(a) How many functions are there from A to B (i.e., functions with domain A, assigning an element of B to each element of A)?

(b) How many one-to-one functions are there from A to B? (See Section A.2.1 of the math appendix for information about one-to-one functions.)

Answer:

(a) For each element of A, there are m possible images in $B$. Since $A$ contains n elements, the multiplication rule gives $m^n$ functions from $A$ to $B$.

(b) We need to consider two cases:
* $n > m$
* $n \le m$ 

For the case of $n > m$, there aren't enough elements in $B$ for each element of $A$. So no one-to-one functions exist.

For the case of $n \le m$, choose an element from $A$, it has $m$ images in $B$. The pick up another element from $A$, it has $m-1$ images in $B$. So the number of possible one-to-one functions is:
$$
\prod_{i=1}^n (m-i+1) = \frac{m!}{(m-n)!}
$$

**Q12**

Four players, named A, B, C and D, are playing a card game. A standard, well-shuﬄed deck of cards is dealt to the players (so each player receives a 13-card hand).

(a) How many possibilities are there for the hand that player A will get? (Within a hand, the order in which cards were received doesn’t matter.)

(b) How many possibilities are there overall for what hands everyone will get, assuming
that it matters which player gets which hand, but not the order of cards within a hand?

(c) Explain intuitively why the answer to Part (b) is not the fourth power of the answer
to Part (a).

Answer:

(a) Choose 13 of the 52 cards to form player A's hand. Therefore, the number of the possibilities is $\binom{52}{13}$.

(b) Choose 13 cards from the deck to player A, similarly 13 cards to player B, C and D.
By multiplication rule, the number of the possibilities is:
$$
\binom{52}{13} \binom{39}{13} \binom{26}{13} \binom{13}{13} 
$$

(c) The fourth power incorrectly assumes that each player’s hand can be chosen independently from all 52 cards. After A receives 13 cards, however, only 39 cards remain available for B. Therefore, the number of choices for each player depends on the hands already dealt.