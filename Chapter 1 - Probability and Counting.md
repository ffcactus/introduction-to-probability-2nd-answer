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

**Q13**

A certain casino uses 10 standard decks of cards mixed together into one big deck, which we will call a superdeck. Thus, the superdeck has $52*10 = 520$ cards, with 10 copies of each card. How many different 10-card hands can be dealt from the superdeck? The order of the cards does not matter, nor does it matter which of the original 10 decks the cards came from. Express your answer as a binomial coefficient.

Hint: Bose-Einstein.

Answer:

Binomial coefficient requires the set to be chosen has distinct elements, here the big deck has duplicated cards. Instead, rearrange the 10 standard decks so that the same kind of cards form a deck, so there are 52 decks each has 10 cards.
So this problem can be translated into choose 10 cards from these 52 decks where a type can be chosen repeatedly, By using Bose-Einstein, the possibility is:
$$
\binom{52 + 10 - 1}{10}
$$

**Q14**

You are ordering two pizzas. A pizza can be small, medium, large, or extra large, with any combination of 8 possible toppings (getting no toppings is allowed, as is getting all 8). How many possibilities are there for your two pizzas?

Answer:

First, multiplication rule to these steps:
1. Choose the size, 4 possibilities.
2. Choose the the toppings. Each topping can be selected or not, so there are $2^8$ possibilities.

Therefore, the number of possibilities of a pizza is:
$$
N = 4 * 2^8
$$

Now consider the possibilities of two pizzas. The number of possibilities for the two pizzas are the same is $N$, The number of possibilities for the two pizzas are different is $\binom{N}{2}$. Therefore the number of the possibilities is:
$$
N + \binom{N}{2}
$$

**Q15**

Give a story proof that:
$$
\sum_{k=0}^n \binom{n}{k} = 2^n
$$

Answer:

A pizza can have any combination of 8 possible toppings (getting no toppings is allowed, as is getting all 8). The number of possibility of the pizza can be calculated in these two ways:

1. Each topping can be selected or not, so there are $2^8$ possibilities.
2. Select 0 toppings $\binom{8}{0}$, select 1 toppings $\binom{8}{1}$, and so on, therefore there are $\sum_{k=0}^n \binom{n}{k}$ possibilities.

**Q16**

Show that for all positive integers $n$ and $k$ with $n \ge k$,
$$
\binom{n}{k} + \binom{n}{k-1} = \binom{n+1}{k}
$$

Suppose there are $n$ student and 1 teacher in a class, we need to choose $k$ people from the class. Obviously, we can choose $k$ from $n+1$, the number of possibilities is $\binom{n+1}{k}$. Or we can separate the result in two groups, with or without the teacher:
* For the groups with the teacher, it can be taken as select $k-1$ students from $n$ student, the number of possibilities is $\binom{n}{k-1}$.
* For the groups without the teacher, it can be taken as select $k$ students from $n$ students, the number of possibilities is $\binom{n}{k}$.

Therefore
$$
\binom{n}{k} + \binom{n}{k-1} = \binom{n+1}{k}
$$

**Q17**

Give a story proof that
$$
\sum_{k=0}^n \binom{n}{k}^2 = \binom{2n}{n}
$$
for all positive integers $n$.

Answer:

Here is the story: 
Count the possibilities of selecting $n$ people from $n$ men and $n$ women, the order of the $n$ people doesn't matter. 

Obviously, the possiblities is $\binom{2n}{n}$. However the number of possibilities can also be calculated by summing over all the possibilites of different number of men have been selected. The number of selected men varies from 0 to n. In the cases of 0 man be selected, the possiblitis can be expressed as choosing 0 man from $n$ men, and then choosing $n$ women from $n$ women, which is $\binom{n}{0}\binom{n}{n}$. In the cases of 1 man be selected, the possiblitis can be expressed as choosing 1 man from $n$ men, and then choosing $n-1$ women from $n$ women, which is $\binom{n}{1}\binom{n}{n-1}$. Continue in this way and sum over these possibilities, it must match $\binom{2n}{n}$
$$
\sum_{k=0}^n \binom{n}{k} \binom{n}{n-k} = \sum_{k=0}^n \binom{n}{k}^2 = \binom{2n}{n}
$$

**Q18**

Give a story proof that
$$
\sum_{k=1}^n k \binom{n}{k}^2 = n \binom{2n-1}{n-1}
$$
, for all possible integers $n$.

Hint: Consider choosing a committee of size $n$ from two groups of size $n$ each, where
only one of the two groups has people eligible to become the chair of the committee.

Answer:

Story: Choosing a committee of size $n$ from two groups of size $n$ each, where
only one of the two groups has people eligible to become the chair of the committee. Find out the number of possibilities of the committee in which who is the chair matters.

Suppose the chair of committee must be chosen from group A and the other group is B. The following two methods count the same possibilities.

Method 1: Choose the chair first

Use multiplication rule to the following step:
1. Choose the chair of the committee from the group A. 
2. Choose $n-1$ people from the remaining $2n-1$ people.

The number of possibilities is:
$$
n \binom{2n-1}{n-1}
$$

Method 2: Classify by the number chosen from group A.

Suppose $N_k$ is the number of the possiblities that there are $k$ people in the comittee were chosen from group A. It can be expressed by the following steps:
1. Choose $k$ people from group A.
2. Choose 1 people as the chair.
3. Choose $n-k$ people from group B. 

By multiplication rule, the number of possibilities is:
$$
N_k = k \binom{n}{k} \binom{n}{n-k}
$$
Because $\binom{n}{k} = \binom{n}{n-k}$, it becomes:
$$
N_k = k \binom{n}{k}^2
$$
Because $k$ varies from 1 to $n$, Summing over all possible value of $k$:
$$
\sum_{k=1}^n k \binom{n}{k}^2
$$

Because solution 1 and 2 should have the same result, so
$$
\sum_{k=1}^n k \binom{n}{k}^2 = n \binom{2n-1}{n-1}
$$

**Q19**

Give a story proof that
$$
\sum_{k=2}^n \binom{k}{2} \binom{n-k+2}{2}  = \binom{n+3}{5}
$$
for all integers $n \ge 2$.

Hint: Consider the middle number in a subset of {1,2,...,n+3} of size 5.

Answer:

Story:
Find the number of possibilities of choosing a subset of size 5 from {1,2,...,n+3}, order doesn't matter.

Obviously, by binomial coefficient the result is:
$$
\binom{n+3}{5}
$$

However, the following method should end up with the same result. Suppose $k+1$ is the middle number of the a valid outcome. And it separates the sampling space into 2 subspaces, (both subspaces do not include the middle number), the left sub space is {1,2,..,k} of size k, the right sub space is {k+2,k+3,...,n+3} of size $n+3-(k+1)=n-k+2$. Choose 2 number from both the left and right subspace. Summing over $k+1$ from 3 to $n+1$, that is summing over $k$ from 2 to $n$, we can get all the outcomes:
$$
\sum_{k=2}^n \binom{k}{2} \binom{n-k+2}{2}
$$

**Q20**

(a) Show using a story proof that
$$
\binom{k}{k} + \binom{k+1}{k} + \binom{k+2}{k} + ... + \binom{n}{k} = \binom{n+1}{k+1}
$$
where $n$ and $k$ are positive integers with $n \ge k$. This is called the *hockey stick identity*.
Hint: Imagine arranging a group of people by age, and then think about the oldest
person in a chosen subgroup.

(b) Suppose that a large pack of Haribo gummi bears can have anywhere between 30 and 50 gummi bears. There are 5 delicious flavors: pineapple (clear), raspberry (red), orange (orange), strawberry (green, mysteriously), and lemon (yellow). There are 0 non-delicious flavors. How many possibilities are there for the composition of such a pack of gummi bears? You can leave your answer in terms of a couple binomial coefficients, but not a sum of lots of binomial coefficients.

Answer:

(a)
Suppose there are groups of $n+1$ people ordered by age from youngest to oldest. Consider the number of possibilities of choosing a subgroup of $k+1$ people.

Obviously, by binomial coefficient the result is:
$$
\binom{n+1}{k+1}
$$

Now consider the alternative method, by classifying the original position of the oldest person in the subset. For a fixed oldest people in the subgroup, suppose his original position is $i$, we choose $k$ people from his left side with ${i-1} people, the number of possible choose is:
$$
\binom{i-1}{k}
$$
The range of $i$ is from $k+1$ to $n+1$, sum over the cases:
$$
\sum_{i=k+1}^{n+1} \binom{i-1}{k} = \sum_{i=k}^{n} \binom{i}{k}
$$

The alternative method should end up with the same result, so we have:
$$
\sum_{i=k}^{n} \binom{i}{k} = \binom{n+1}{k+1}
$$
where $n$ and $k$ are positive integers with $n \ge k$.

(b) For a fixed total of $x$ gummi bears in a large pack, different color ones add up to $x$, by Bose-Einstein formula, the number of possibilities of this pack is:
$$
\binom{x + 5 - 1}{5 - 1}
$$
Sum over all possible pack sizes, we have:
$$
\sum_{x=30}^{50} \binom{x+4}{4}
$$
Reindex the sum by let $i=x+4$. Then
$$
\sum_{i=34}^{54} \binom{i}{4}
$$
To apply hockey stick identity, write:
$$
\sum_{i=34}^{54} \binom{i}{4} = \sum_{i=4}^{54} \binom{i}{4} - \sum_{i=4}^{33} \binom{i}{4}
$$
With hockey stick identity, we have
$$
\sum_{i=4}^{54} \binom{i}{4} = \binom{55}{5}, \qquad
\sum_{i=4}^{33} \binom{i}{4} = \binom{34}{5}
$$
So the simplified result is:
$$
\sum_{i=34}^{54} \binom{i}{4} = \binom{55}{5} - \binom{34}{5}
$$

**Q21**

Define $\begin{Bmatrix} n \\ k \end{Bmatrix}$ as the number of ways to partition {1,2,...,n} into k nonempty subsets, or
the number of ways to have $n$ students split up into k groups such that each group has at least one student. For example, $\begin{Bmatrix} 4 \\ 2 \end{Bmatrix} = 7$ because we have the following possibilities.
* {1}, {2,3,4}
* {2}, {1,3,4}
* {3}, {1,2,4}
* {4}, {1,2,3}
* {1,2}, {3,4}
* {1,3}, {2,4}
* {1,4}, {2,3}

Prove the following identities:

(a)
$$
\begin{Bmatrix}n+1 \\ k \end{Bmatrix} = 
\begin{Bmatrix}n \\ k-1 \end{Bmatrix} +
k \begin{Bmatrix}n \\ k \end{Bmatrix}
$$
Hint: I’m either in a group by myself or I’m not.

(b)
$$
\sum_{j=k}^n \binom{n}{j} \begin{Bmatrix}j \\ k \end{Bmatrix} =
\begin{Bmatrix}n+1 \\ k+1    \end{Bmatrix}
$$
Hint: First decide how many people are not going to be in my group.

Answer:

(a)

Suppose the
$$
N=\begin{Bmatrix} n \\ k \end{Bmatrix}
$$
When adding a new element to the sampling space, classify the changes into two cases:
1. The new element joins one of the partitions.
2. The new element forms the a new block by itself.

In case 1, for each outcome of $N$, there are $k$ partitions the new element can merge into, so the number of possibilities is $kN$.

In case 2, we need to reduce the original $k$ partitions to $k-1$ so that the new element can form partition by itself, so the number of possibilities is $\begin{Bmatrix} n \\ k - 1 \end{Bmatrix}$.

Summing over the two cases, we have:
$$
\begin{align}
\begin{Bmatrix}n+1 \\ k \end{Bmatrix} &= 
\begin{Bmatrix}n \\ k-1 \end{Bmatrix} +
kN \\
&= \begin{Bmatrix}n \\ k-1 \end{Bmatrix} +
k \begin{Bmatrix}n \\ k \end{Bmatrix}
\end{align}
$$

(b)
Consider $n+1$ students, one of whom is a distinguished new student. We want to partition them into $k+1$ nonempty blocks. The number of such partitions is
$$
N = \begin{Bmatrix} n + 1\\ k + 1\end{Bmatrix}
$$

We can let the new student to form a block by himself, or let others to join his block. That means the number of students that join the block vary from 0 to $n-k$.

For a fixed $i$ students join the new block with the new student. We first choose the $i$ students from $n$, the number of possibilities is:
$$
\binom{n}{i}
$$
The remaining $n - i$ students are partitioned into $k$ blocks, and the number of possibilities is:
$$
\begin{Bmatrix} n - i \\ k \end{Bmatrix}
$$
By multiplication rule, we have:
$$
\binom{n}{i} \begin{Bmatrix} n - i \\ k \end{Bmatrix}
$$
Summing over the number of students join the new block:
$$
N=
\sum_{i=0}^{n-k} \binom{n}{i} \begin{Bmatrix} n - i \\ k \end{Bmatrix} =
\sum_{i=0}^{n-k} \binom{n}{n-i} \begin{Bmatrix} n - i \\ k \end{Bmatrix}
$$
Reindex by $j=n-i$, because $i$ varies from 0 to $n-k$, $j$ varies from $n$ to $k$, so we have:
$$
N = \sum_{j=k}^{n} \binom{n}{j} \begin{Bmatrix} j \\ k \end{Bmatrix} = \begin{Bmatrix} n + 1\\ k + 1\end{Bmatrix}
$$

**Q22**

The Dutch mathematician R.J. Stroeker remarked:

*Every beginning student of number theory surely must have marveled at the miraculous
fact that for each natural number $n$ the sum of the first $n$ positive consecutive cubes is
a perfect square.*

Every beginning student of number theory surely must have marveled at the miraculous
fact that for each natural number n the sum of the first n positive consecutive cubes is
a perfect square.

Furthermore, it is the square of the sum of the first $n$ positive integers! That is,
$$
1^3 + 2^3 + 3^3 + ... + n^3 = (1+2+3+...+n)^2
$$

Usually this identity is proven by induction, but that does not give much insight into why the result is true, nor does it help much if we wanted to compute the left-hand side but didn’t already know this result. In this problem, you will give a story proof of the identity.

(a) Give a story proof of the identity
$$
1 + 2 + 3 + ... + n = \binom{n+1}{2}
$$

Hint: Consider a round-robin tournament (see Exercise 4).

(b) Give a story proof of the identity
$$
1^3 + 2^3 + 3^3 + ... + n^3 = 6 \binom{n+1}{4} + 6 \binom{n+1}{3} + \binom{n+1}{2}
$$
It is then just basic algebra (not required for this problem) to check that the square of the right-hand side in (a) is the right-hand side in (b).

Hint: Imagine choosing a number between 1 and $n$ and then choosing 3 numbers between 0 and $n$ smaller than the original number, with replacement. Then consider cases based on how many distinct numbers were chosen.

Answer:

(a) Consider a round-robin tournament in which every player will play against every other player exactly once. Suppose the number of games is $N$ for $n$ player. Now consider the games when here comes a new player. The player must play with every other player, so it increases $n$ new games. Therefore, we have:
$$
1 + 2 + 3 + ... + n = \binom{n+1}{2}
$$

(b)
Consider choosing 4 numbers in {0,1,...,n} with $n \ge 3$ like this:
1. The first number must be chosen from {1,2,...,n}.
2. The remaining 3 numbers are chosen from {0,1,...,n} with replacement.

Counting the number of distinct 4 numbers, order matters.

Method 1: classify on the first chosen number.

For a fixed first chosen number $k$, we then choose 1 number from {0,1,...,k-1}, repeat 3 times. With multiplication rule, the number of possibilities is $k^3$.

Summing over $k$ from 1 to $n$, the number of distinct 4 numbers is:
$$
\sum_{i=1}^n i^3
$$

Method 2: classify on the number of distinct numbers in a outcome.

Because the first number is always different than the rest 3 numbers, the possible distinct number in a outcome are 2, 3 and 4.

When there are 2 distinct numbers in the outcome, the number of possibilities is $\binom{n+1}{2}$.

When there are 3 distinct numbers in the outcome, the number of possibilities can be calculated like this. First choose 3 from $n+1$. Suppose the numbers are A, B, C. Fix A as the first number, it can be expanded into: ABBC, ABCB, ABCC, ACBB, ACBC, ACCB. So there are $6\binom{n+1}{3}$ possibilities.

When there are 4 distinct numbers in the outcome, the number of possibilities can be calculated like this. First choose 4 from $n+1$. Suppose the numbers are A, B, C, D. Fix A as the first number, it can be expanded into ABCD, ABDC, ACBD, ACDB, ADBC, ADCB. So there are $6\binom{n+1}{4}$ possibilities.

Summing over on the three cases, we have:
$$
6 \binom{n+1}{4} + 6 \binom{n+1}{3} + \binom{n+1}{2}
$$

The two methods should end up with the same result, so we have:
$$
1^3 + 2^3 + 3^3 + ... + n^3 = 6 \binom{n+1}{4} + 6 \binom{n+1}{3} + \binom{n+1}{2}
$$