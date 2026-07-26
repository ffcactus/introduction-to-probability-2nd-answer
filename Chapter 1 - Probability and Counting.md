# Counting

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

# Story proofs

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

# Naive definition of probability

**Q23**

Three people get into an empty elevator at the first floor of a building that has 10 floors. Each presses the button for their desired floor (unless one of the others has already pressed that button). Assume that they are equally likely to want to go to floors 2 through 10 (independently of each other). What is the probability that the buttons for 3 consecutive floors are pressed?

Answer:

The number of possibility of the three floors chosen by the three people is: $9^3=729$.

From floor (2,3,4) to floor (8,9,10), there are 7 possibilities. We can classify on these 7 possibilities. For a fixed case there are $3*2*1$ possible ways for the three person to press the button. By multiplication rule, the total ways is $7*3*2*1=42$.

Therefore the probability that the buttons for 3 consecutive floors are:
$$
\frac{42}{729}
$$

**Q24**

A certain family has 6 children, consisting of 3 boys and 3 girls. Assuming that all birth orders are equally likely, what is the probability that the 3 eldest children are the 3 girls?

Answer:

There are $6!$ possible way for the 6 children to burn in order.

For the outcomes that the 3 eldest children are the 3 girls, it can be calculated like this. First calculate the possible orders of the three girls, which is $3!$. Then calculate the possible orders of the three boys, which is also $3!$. By multiplication rule, the number of possible ways that 3 eldest children are the 3 girls is $3!3!$.

Therefore, the probability is:
$$
\frac{3!3!}{6!} = \frac{1}{20}
$$

**Q25**

A city with 6 districts has 6 robberies in a particular week. Assume the robberies are located randomly, with all possibilities for which robbery occurred where equally likely. What is the probability that at least one district had more than 1 robbery?

Answer:

To find the probability, first count the total number of equally likely ways to distribute the six robberies among the six districts. For example, suppose the robberies are $r_1,r_2,...,r_6$, in order; and the districts are $d_1,d_2,...,d_6$. A possible outcome is $(d_1, d_2, d_1, d_3, d_4, d_5)$, in which $r_1$ and $r_3$ occurred at $d_1$. Next, count the outcomes in which at least one district has more than one robbery.

Assign these 6 robberies to the 6 districts which is choosing from {$d_1,d_2,...,d_6$} six times with replacement, the result is:
$$
6^6
$$

Now consider the possible outcomes for at least one district has more than one robbery. We can count the complement that every district has exactly one robbery, which is choosing from {$d_1, d_2,...,d_6$} without replacement. The number of possibilities is
$$
6!
$$
Therefore the probability is:
$$
\frac{6^6-6!}{6^6} 
$$

**Q26**

A survey is being conducted in a city with 1 million residents. It would be far too expensive to survey all of the residents, so a random sample of size 1000 is chosen (in practice, there are many challenges with sampling, such as obtaining a complete list of everyone in the city, and dealing with people who refuse to participate). The survey is conducted by choosing people one at a time, with replacement and with equal probabilities.

(a) Explain how sampling with vs. without replacement here relates to the birthday problem.

(b) Find the probability that at least one person will get chosen more than once.

Answer:

(a) The birthday problem is analogous to sampling with replacement because one person’s birthday does not affect the possible birthdays of the others. This comes from the nature of birthdays.

However, when we restrict attention to the event that all birthdays are different, the counting is similar to sampling without replacement, because each new birthday must differ from all the birthdays already observed.

(b)

The number of possibilities that choose 1000 person from 1 million residents with replacement is:
$$
(10^6)^{1000} = 10^{6000}
$$

The number of possibilities that at least one person will get chosen more than once is the complement of the event that all 1000 people are different. The number of ways to choose 1000 different people is the number of ways to choose from 1 million residents without replacement 1000 times:
$$
\prod_{i=1}^{1000} (10^6 - i + 1)
$$

Therefore, the probability is:
$$
1 - \frac{\prod_{i=1}^{1000} (10^6 - i + 1)}{10^{6000}}
$$

**Q27**

A hash table is a commonly used data structure in computer science, allowing for fast
information retrieval. For example, suppose we want to store some people’s phone numbers. Assume that no two of the people have the same name. For each name $x$, a hash function $h$ is used, letting $h(x)$ be the location that will be used to store $x$’s phone number. After such a table has been computed, to look up $x$’s phone number one just recomputes $h(x)$ and then looks up what is stored in that location.
The hash function $h$ is deterministic, since we don’t want to get different results every time we compute $h(x)$. But $h$ is often chosen to be pseudorandom. For this problem, assume that true randomness is used. Let there be $k$ people, with each person’s phone number stored in a random location (with equal probabilities for each location, independently of where the other people’s numbers are stored), represented by an integer between 1 and $n$. Find the probability that at least one location has more than one phone number stored there.

Answer:

The total number of possible assignments of the $k$ phone numbers to the $n$ location is:
$$
n^k
$$

To count the outcomes in which at least one location contains more than one phone number, use the complement: each location is used at most once.
The number of assignments with no collisions is:
$$
\prod_{i=1}^k (n-i+1)
$$

Therefore, the probability is:
$$
1 - \frac{\prod_{i=1}^k (n-i+1)} {n^k}
$$

**Q28**

A college has 10 time slots for its courses, and blithely assigns courses to completely random time slots, independently. The college offers exactly 3 statistics courses. What is the probability that 2 or more of the statistics courses are in the same time slot?

Answer:

Each of the three distinct statistics courses can be independently assigned to any of the ten time slots. Therefore, the total number of equally likely assignments is
$$
10^3
$$

The complementary event is all the three statistic courses are assigned to different time slot. The first course has 10 choices, the second has 9 remaining choices, and the third has 8 remaining choices. Thus, the number of assignments in the complementary event is:
$$
10*9*8
$$

Therefore, the probability is:
$$
1 - \frac{10*9*8} {10^3} = 0.28
$$

**Q29**

For each part, decide whether the blank should be filled in with $=$, $\gt$, or $\lt$, and give
a clear explanation.

(a) (probability that the total after rolling 4 fair dice is 21) __ (probability that the total after rolling 4 fair dice is 22)

(b) (probability that a random 2-letter word is a palindrome) __ (probability that a
random 3-letter word is a palindrome)

Answer:

(a)

Rolling 4 fair dice, there are $6^4$ equally likely outcomes. 

Here are the combinations that sum to 21:
1. 6+6+6+3, there are $\frac{4!}{3!}=4$ possible ordering.
2. 6+6+5+4, there are $\frac{4!}{2!}=12$ possible ordering.
3. 5+5+5+6, there are $\frac{4!}{3!}=4$ possible ordering.

Here are the combinations that sum to 22:
1. 6+6+6+4, there are $\frac{4!}{3!}=4$ possible ordering.
2. 6+6+5+5, there are $\frac{4!}{2!2!}=6$ possible ordering.

So rolling 4 fair dice, the probability that the total is 21 is greater than 22.

(b)

There are 26^2 possible 2-letter word and they are equally likely. Among them, 26 are palindrome.

There are 26^3 possible 3-letter word and they are equally likely. Among them, 26*26 are palindrome. Each possible choice of the first 2 letters determines exactly a 3-letter palindrome.
$$
\frac{26}{26^2} = \frac{26^2}{26^3}
$$

Therefore, the probability for the 2-letter palindrome and the 3-letter palindrome are the same.

**Q30**

With definitions as in the previous problem, find the probability that a random n-letter word is a palindrome for $n=7$ and for $n=8$.

Answer:

There are $26^7$ possible equally likely 7-letter words. There are $26^4$ possibilities for the first 4 letters, and each of them determines a 7-letter palindrome, so the probability of a 7-letter palindrome is $\frac{26^4}{26^7}=\frac{1}{26^3}$.

There are $26^8$ possible equally likely 8-letter words. There are $26^4$ possibilities for the first 4 letters, and each of them determines a 7-letter palindrome, so the probability of an 8-letter palindrome is $\frac{26^4}{26^8}=\frac{1}{26^4}$.

**Q31**

Elk dwell in a certain forest. There are $N$ elk, of which a simple random sample of size $n$ are captured and tagged ("simple random sample" means that all $\binom{N}{n}$ sets of $n$ elk are equally likely). The captured elk are returned to the population, and then a new sample is drawn, this time with size $m$. This is an important method that is widely used in ecology, known as capture-recapture. What is the probability that exactly $k$ of the $m$ elk in the new sample were previously tagged? (Assume that an elk that was captured before doesn’t become more or less likely to be captured again.)

Answer:

After the first capture-and-release, there are $n$ tagged elk and $N-n$ untagged elk, and all of them are equally likely to be chosen next time.

In the second capture, there are $\binom{N}{m}$ equally likely outcomes. 
Next count the outcomes that have exactly $k$ tagged elk. Use the multiplication rule for the following two steps:

1. Choose $k$ elk from $n$ tagged elk, which is $\binom{n}{k}$.
2. Choose $m-k$ elk from $N-n$ untagged elk, which is $\binom{N-n}{m-k}$.

So the number of second samples containing exactly $k$ tagged elk is:
$$
\binom{n}{k} \binom{N-n}{m-k}
$$

Therefore, the probability that exactly $k$ of the $m$ elk in the new sample were previously tagged is:
$$
\frac{\binom{n}{k} \binom{N-n}{m-k}}{\binom{N}{m}}
$$ 

**Q32**

Four cards are face down on a table. You are told that two are red and two are black, and you need to guess which two are red and which two are black. You do this by pointing to the two cards you’re guessing are red (and then implicitly you’re guessing that the other two are black). Assume that all configurations are equally likely, and that you do not have psychic powers. Find the probability that exactly $j$ of your guesses are correct, for $j = 0,1,2,3,4$.

Answer:

The guesses are equally likely, and there are $\binom{4}{2} = 6$ possible guesses.

For a guess to contain exactly $r$ actual red cards, we can use the multiplication rule to create the outcome like this:

1. Choose $r$ of the two actual red cards.
2. Choose the remaining $2-r$ guessed-red cards from the two actual black cards.

Therefore, the number of such guesses is
$$
\binom{2}{r} \binom{2}{2-r}
$$

However, if there are exactly $r$ correct guesses to the red cards, there must be exactly $r$ correct guesses to the black cards. So the correct guesses $j=2r$.

* Because $j=2r$, the number of corrected guesses must be even, so $j=1$ and $j=3$ are impossible.
* When $j=0$, $r=0$, the probability is $\frac{\binom{2}{0} \binom{2}{2}}{6} = \frac{1}{6}$.
* When $j=2$, $r=1$, the probability is $\frac{\binom{2}{1} \binom{2}{1}}{6} = \frac{4}{6}$.
* When $j=4$, $r=2$, the probability is $\frac{\binom{2}{2} \binom{2}{0}}{6} = \frac{1}{6}$.

**Q33**

A jar contains $r$ red balls and $g$ green balls, where $r$ and $g$ are fixed positive integers.
A ball is drawn from the jar randomly (with all possibilities equally likely), and then a
second ball is drawn randomly.

(a) Explain intuitively why the probability of the second ball being green is the same as the probability of the first ball being green.

(b) Define notation for the sample space of the problem, and use this to compute the
probabilities from (a) and show that they are the same.

(c) Suppose that there are 16 balls in total, and that the probability that the two balls
are the same color is the same as the probability that they are different colors. What
are $r$ and $g$ (list all possibilities)?

Answer:

(a) Imagine the balls in a line randomly, so each position is equally likely to be green, and the probability is $\frac{g} {r + g}$. If the balls are drawn one by one, the probability that each position contains a green ball is the same.

(b) Convert the original question to this one:

*Randomly choose $g$ locations from $r+g$ locations, check the probability that the first location been chosen, and the probability that the second location be chosen.*

There are $\binom{r+g}{g}$ possible equally likely assignment.

For the fixed cases that the first location is chosen, the number of possibilities equals to the number of possible assignments that choosing $g-1$ location from the remaining $r+g-1$ locations, which is
$$
\binom{r+g-1}{g-1}
$$.

So the probability of the first location been chosen is
$$
\frac{\binom{r+g-1}{g-1}} {\binom{r+g}{g}} = \frac{g}{g+r}
$$

Similarly, the probability of the second location been chosen is the same.

(c) In (b) we proof that every time when draw a ball from the jar, the probability of red is $\frac{r}{g+r}$, the probability of green is $\frac{g}{r+g}$. If the probability of of same color and different color is the same, we have
$$
\frac{g}{g+r} \frac{g-1}{g+r-1} + \frac{r}{g+r} \frac{r-1}{g+r-1} = \frac{g}{g+r} \frac{r}{g+r-1} + \frac{r}{g+r} \frac{g}{g+r-1}
$$

Simplify it and we have
$$
g^2-2gr+r^2-g-r=0
$$

Solve the equations
$$
\begin{cases}
g^2-2gr+r^2-g-r=0 \\
g+r=16
\end{cases}
$$
We have $g=10, r=6$ or $g=6, r=10$.

**Q34**

A random 5-card poker hand is dealt from a standard deck of cards. Find the probability of each of the following possibilities (in terms of binomial coefficients).

(a) A flush (all 5 cards being of the same suit; do not count a royal flush, which is a flush with an ace, king, queen, jack, and 10).

(b) Two pair (e.g., two 3’s, two 7’s, and an ace).

Answer:

(a) There are $\binom{52}{5}$ equally likely possible outcomes for a random 5-card poker hand. There are 4 possible suits for a flush. For a fixed suit, we can choose 5 cards from 13 possible cards but remove the single royal flush outcome. Summing over all four suits, we have
$$
4 \binom{13}{5} - 4
$$

Therefore, the probability of a flush is
$$
\frac{4 \binom{13}{5} - 4} {\binom{52}{5}}
$$

(b) First, chose the numbers for the two pair, there are
$$
\binom{13}{2}
$$
possible outcomes for the numbers. Each number has
$$
\binom{4}{2}
$$
possible outcomes from different suits. So for the two pair, we have 
$$
\binom{13}{2} \binom{4}{2} \binom{4}{2}
$$
possible outcomes. Second, chose the last card, We can't choose the number used in the two pair, so it is chosen from the remaining $52-8=44$ cards.

Therefore, the probability for two pair is
$$
\frac{\binom{13}{2} \binom{4}{2} \binom{4}{2} \binom{48}{1}} {\binom{52}{5}}
$$

**Q35**

A random 13-card hand is dealt from a standard deck of cards. What is the probability that the hand contains at least 3 cards of every suit?

Answer:

A random 13-card hand has
$$
\binom{52}{13}
$$
possible outcomes. And it at most can only 3 cards of every suit.

If there are at least 3 cards of every suit, there must be exact 4 cards for a suit. Choose a suit that contains 4 cards in the hand. For the other suits, each contains 3 cards. By multiplication rule, the number of valid outcomes is:
$$
4 \binom{13}{4}\binom{13}{3}^4
$$

Therefore the probability of a hand contains at least 3 cards of every suit is
$$
\frac{4 \binom{13}{4}\binom{13}{3}^4}{\binom{52}{13}}
$$

**Q36**

A group of 30 dice are arranged in a line. What is the probability that 5 of each of the values
1,2,3,4,5,6 appear?

Answer:

The total number of ordered possible outcomes of 30 dice is
$$
6^{30}
$$

Suppose the 30 dice in a line randomly. Each valid outcome can be generated like this:
1. Choose 5 positions from 30 available positions for the five dice of value 1.
2. Choose 5 positions from the remaining 25 available positions for the five dice showing value 2.
3. Choose 5 positions from the remaining 20 available positions for the five dice showing value 3.
4. Choose 5 positions from the remaining 15 available positions for the five dice showing value 4.
5. Choose 5 positions from the remaining 10 available positions for the five dice showing value 5.
6. Choose 5 positions from the remaining 5 available positions for the five dice showing value 6.

By using multiplication rule, there are
$$
\binom{30}{5} \binom{25}{5} \binom{20}{5} \binom{15}{5} \binom{10}{5} \binom{5}{5}
$$
possible assignments.

Therefore, the probability that 5 of each of the values 1,2,3,4,5,6 appear is:
$$
\frac{\binom{30}{5} \binom{25}{5} \binom{20}{5} \binom{15}{5} \binom{10}{5} \binom{5}{5}}{6^{30}}
$$

**Q37**

A deck of cards is shuffled well. The cards are dealt one by one, until the first time an
ace appears.

(a) Find the probability that no kings, queens, or jacks appear before the first ace.

(b) Find the probability that exactly one king, exactly one queen, and exactly one jack
appear (in any order) before the first ace.

Answer:

(a) The shuffled deck has $52!$ possible arrangements. Classify the favorable arrangements by the position $1 \le i \le 37$ that appear the first ace. For a fixed position, choose an ace from the 4 suits and put it at position $i$. For the remaining 3 aces, 4 kings, 4 queens and 4 jacks, put them behind the chosen ace. We need to choose 15 positions from the remaining $52-i$ positions to arrange them. So we have 
$$
4 \binom{52-i}{15} 15!
$$
arrangements for aces, kings, queens and jacks. And there are
$$
36!
$$ 
possible arrangements for the rest cards. Summing over the position, we have
$$
\sum_{i=1}^{37} 4 \binom{52-i}{15} 15! 36!
$$
possible favorable outcomes. Therefore the possibility is
$$
\frac{\sum_{i=1}^{37} 4 \binom{52-i}{15} 15! 36!}{52!}
$$

(b) Ignore the 36 cards that are neither aces, kings, queens, nor jacks. Among the 16 special cards there are $16!$ possible arrangements. To generate a favorable outcome, first choose one king, one queen and one jack, put them in the first three positions randomly, there are
$$
4^3 \cdot 3!
$$ 
possible ways. Then choose an ace, the possible ways become
$$
4^4 \cdot 3!
$$
Then arrange the rest 12 cards in any order, the possible ways become
$$
4^4 \cdot 3! \cdot 12!
$$
Therefore, the probability is
$$
\frac{4^4 \cdot 3! \cdot 12!}{16!} = \frac{16}{455}
$$

**Q38**

Tyrion, Cersei, and ten other people are sitting at a round table, with their seating arrangement having been randomly assigned. What is the probability that Tyrion and Cersei are sitting next to each other? Find this in two ways:

(a) using a sample space of size 12!, where an outcome is fully detailed about the seating;

(b) using a much smaller sample space, which focuses on Tyrion and Cersei.

Answer:

(a) There are $12!$ possible equally likely assignments. To find the favorable assignments, we can classify on the Tyrion's position. For a fixed Tyrion's position $1 \le i \le 12$, Cersei's position can be assigned to the left or right next to it, however, so there are $2$ choices for Cersei's position. There are $10!$ possible assignments for the other $10$ people to the rest positions. So the number of the favorable assignments is
$$
\sum_{i=1}^{12} 2 \cdot 10! = 24 \cdot 10!
$$
Therefore, the probability is
$$
\frac{24 \cdot 10!}{12!} = \frac{2}{11}
$$

(b) There are $12 \cdot 11$ equally likely assignments for Tyrion and Cersei combined position. Now, classify on Tyrion's position, for a fixed Tyrion's position, there are 2 possible choices for Cersei's position to be next to Tyrion's. Therefore, the probability is:
$$
\frac{12 \cdot 2}{12 \cdot 11} = \frac{2}{11}
$$

**Q38**

An organization with $2n$ people consists of $n$ married couples. A committee of size $k$ is selected, with all possibilities equally likely. Find the probability that there are exactly $j$ married couples within the committee.

Answer:

To better explain the solution, arrange the couples in two lines, the men in a line and women in another line, the couple's position are the same in the lines. There are $n$ people in each line.

There are $\binom{2n}{k}$ equally likely choices to choose $k$ people from the $2n$ people to form committee.

To count the number of the favorable committee, first choose $j$ married couples from the $n$ married couples, and there are $\binom{n}{j}$ choices.

Then choose the remaining $k-2j$ people for the rest of the committee from the remaining $n-j$ couples, and there are 2 choices from each chosen couple. So the number of ways to choose the uncoupled people in the committee is
$$
\binom{n-j}{k-2j} 2^{k-2j}
$$

By using the multiplication rule, the number of ways to choose the favorable committee is
$$
\binom{n}{j} \binom{n-j}{k-2j} 2^{k-2j}
$$

Therefore, when $k \le n+j$, the probability is
$$
\frac{\binom{n}{j} \binom{n-j}{k-2j} 2^{k-2j}}{\binom{2n}{k}}
$$

**Q40**

There are $n$ balls in a jar, labeled with the numbers 1,2,...,$n$. A total of $k$ balls are drawn, one by one with replacement, to obtain a sequence of numbers.

(a) What is the probability that the sequence obtained is strictly increasing?

(b) What is the probability that the sequence obtained is increasing (but not necessarily strictly increasing, i.e., there can be repetitions)?

Answer:

(a) With replacement, there are $n^k$ equally likely possible sequences. For a strictly increasing sequence, the numbers must be distinct. This is choosing $k$ from $n$ without replacement, each choice maps to a strictly increasing sequence, so the number strictly increasing sequences is
$$
\binom{n}{k}
$$
Therefore, the probability is
$$
\frac{\binom{n}{k}}{n^k}
$$

(b) For a non-decreasing sequence, once we know the number of occurrences of each number, the sequence is completely determined. And those occurrence times sum to $k$, this is a stars-and-bars problem. Therefore, the probability is
$$
\frac{\binom{k+n-1}{k}}{n^k}
$$

**Q41**

Each of $n$ balls is independently placed into one of $n$ boxes, with all boxes equally likely. What is the probability that exactly one box is empty?

Answer:

There are $n^n$ equally likely outcomes if order matters.

Now consider the number of favorable outcomes. If one box is empty, we can take it as there are $n-1$ boxes. If we remove a particular box, and ensure other $n-1$ boxes are not empty, we can first choose n-1 balls from $n$ balls and put them to each of the $n-1$ boxes, we have $(n-1)!$ possible assignment. For the remaining 1 ball it can be put into any of the $n-1$ box. By using multiplication rule, we have
$$
\binom{n}{n-1} \cdot (n-1)! \cdot (n-1) = (n-1) \cdot n!
$$
However, each outcome is counted twice because the box containing two balls has two possible choices for which ball was placed last. Therefore the probability is:
$$
\frac{(n-1) \cdot n!}{2 \cdot n^n}
$$

# Axioms of probability

The following set operation is useful for using the axioms of probability:
1. $A=(A\cap B)\cup(A\cap B^c)$
2. $A\cup B=A\cup(B\cap A^c)$
3. $(A\cup B)^c=A^c\cap B^c$
4. $(A\cap B)^c=A^c\cup B^c$


**Q43**

Show that for any events $A$ and $B$,
$$
P(A) + P(B) - 1 \le P(A \cap B) \le P(A \cup B) \le P(A) + P(B)
$$
For each of these three inequalities, give a simple criterion for when the inequality is actually an equality (e.g., give a simple condition such that $P(A \cap B) = P(A \cup B)$ if and only if the condition holds).

Answer:

1. Proof for $P(A) + P(B) - 1 \le P(A \cap B)$

We can first prove that
$$
P(A) + P(B) - P(A \cap B) = P(A \cup B)
$$
and because $P(A \cup B) \le P(S) = 1$, so
$$
P(A) + P(B) - P(A \cap B) \le 1
$$
Rearranging gives
$$
P(A) + P(B) - 1 \le P(A \cap B)
$$

Now, we prove $P(A) + P(B) - P(A \cap B) = P(A \cup B)$.

Because $A \cup B = A \cup (B \cap A^c)$, and because $A$ and $B \cap A^c$ are disjoint. By the axiom, we have
$$
P(A \cup B) = P(A) + P(B \cap A^c)
$$
Rearranging gives
$$
P(B \cap A^c) = P(A \cup B) - P(A) \qquad (1)
$$

Because $B=(A \cap B) \cup (A^c \cap B)$, and because $A \cap B$ is disjoint with $A^c \cap B$. By the axiom, we have
$$
P(B) = P(B \cap A) + P(B \cap A^c)
$$
Rearranging gives
$$
P(B \cap A^c) = P(B) - P(B \cap A) \qquad (2)
$$

By (1) and (2) we have
$$
P(A \cup B) - P(A) = P(B) - P(B \cap A)
$$
Rearrange, we proof that
$$
P(A) + P(B) - P(A \cup B) = P(A \cap B)
$$

Hence, we proof that
$$
P(A) + P(B) - 1 \le P(A \cap B)
$$
When $P(A \cup B) = P(S) = 1$, the inequality is actually an equality.

2. Proof $P(A \cap B) \le P(A \cup B)$.

Because
$$
P(A) + P(B) - P(A \cap B) = P(A \cup B) \qquad (1)
$$
And
$$
P(A) = P(A \cap B) + P(A \cap B^c) \qquad (2) \\
P(B) = P(B \cap A) + P(B \cap A^c) \qquad (3)
$$
Replace $P(A)$ and $P(B)$ by (2) and (3), (1) can be expressed as
$$
P(A \cap B) + P(A \cap B^c) + P(B \cap A^c) = P(A \cup B)
$$

So
$$
P(A \cap B) \le P(A \cup B)
$$
When $P(A \cap B^c) + P(B \cap A^c) = 0$, the inequality is actually an equality.

3. Proof $P(A \cup B) \le P(A) + P(B)$

Because
$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$
So
$$
P(A \cup B) \le P(A) + P(B)
$$
When $P(A \cap B) = 0$, the inequality is actually an equality.

**Q44**

Let $A$ and $B$ be events. The difference $B-A$ is defined to be the set of all elements of
B that are not in A. Show that if $A \subseteq B$, then $P(B−A) = P(B)−P(A)$, directly using the axioms of probability.

Answer:

Since $A \subseteq B$,
$$
B \setminus A= B \cap A^c \tag{1}
$$
We can decompose B as
$$
B = (B \cap A^c) \cup A
$$

Because $B \cap A^c$ and $A$ are disjoint sets. By the additivity axiom of probability function, we have
$$
P(B) = P(B \cap A^c) + P(A)
$$
Replace with (A) and with rearrange, we have
$$
P(B−A) = P(B)−P(A)
$$

**Q45**

Let $A$ and $B$ be events. The symmetric difference $A \triangle B$ is defined to be the set of all elements that are in A or B but not both. In logic and engineering, this event is also
called the XOR (exclusive or) of A and B. Show that
$$
P(A \triangle B) = P(A) + P(B) − 2 P(A \cap B)
$$
directly using the axioms of probability.

Answer:

Since $A=(A\cap B)\cup(A\cap B^c)$, and (A \cap B) and (A \cap B^c) are disjoint sets. By the additivity of probability, we obtain
$$
P(A) = P(A \cap B) + P(A \cap B^c) \tag{1}
$$

Similarly we have
$$
P(B) = P(B \cap A) + P(B \cap A^c) \tag{2}
$$

Add (1) and (2) we have
$$
P(A) + P(B) = 2 P(A \cap B) + P(A \cap B^c) + P(B \cap A^c)
$$

Rearrange gives
$$
P(A \cap B^c) + P(B \cap A^c) = P(A) + P(B) - 2 P(A \cap B) \tag{3}
$$

By definition
$$
A \triangle B = (A \cap B^c) \cup (B \cap A^c)
$$
And because (A \cap B^c) and (B \cap A^c) are disjoint sets, we have
$$
P(A \triangle B) = P(A \cap B^c) + P(B \cap A^c) \tag{4}
$$

Substituting (3) into (4), we obtain
$$
P(A \triangle B) = P(A) + P(B) - 2 P(A \cap B)
$$

**Q46**

Let $A_1, A_2,\ldots,A_n$ be events. Let $B_k$ be the event exactly $k$ of the $A_i$ occur, and $C_k$ be the event that at least $k$ of the $A_i$ occur, for $0 \le k \le n$. Find a simple expression for $P(B_k)$ in terms of $P(C_k)$ and $P(C_{k+1})$.

Answer:

Because 
$$
A = (A \cap B) \cup (A \cap B^c) \tag{1}
$$

Substituting $A=A_1 \cap A_2$, and $B=A_3$ into (1) we obtain
$$
A_1 \cap A_2 = (A_1 \cap A_2 \cap A_3) \cup (A_1 \cap A_2 \cap A_3^c) \tag{2}
$$

We can define $C_k$ and $B_k$ like this
$$
C_k = \bigcup_{\substack{S \subseteq \{1,\ldots,n\}\\ |S| = k}}(\bigcap_{i \in S} A_i) \tag{3}
$$

$$
B_k = \bigcup_{\substack{S \subseteq \{1,\ldots,n\}\\ |S| = k}} ((\bigcap_{i \in S} A_i) \cap (\bigcap_{j \notin S} A_j^c)) \tag{4}
$$

With (2), (3) and (4) we should have
$$
C_k = C_{k+1} \dot\cup B_k
$$

The events $B_k$ and $C_{k+1}$ are disjoint because exactly \(k\) events cannot occur while at least $k+$ events occur.
$$
P(C_k) = P(C_{k+1}) + P(B_k)
$$
Rearrange obtain
$$
P(B_k) = P(C_k) - P(C_{k+1})
$$

**Q47**

Events $A$ and $B$ are independent if $P(A \cap B) = P(A)P(B)$ (independence is explored
in detail in the next chapter).

(a) Give an example of independent events $A$ and $B$ in a finite sample space $S$ (with
neither equal to $\varnothing$ or $S$), and illustrate it with a Pebble World diagram.

(b) Consider the experiment of picking a random point in the rectangle
$$
R = \{(x,y): 0 \lt x \lt 1, 0 \lt y \lt 1 \}
$$

where the probability of the point being in any particular region contained within $R$ is
the area of that region. Let $A_1$ and $B_1$ be rectangles contained within R, with areas not
equal to 0 or 1. Let $A$ be the event that the random point is in $A_1$, and $B$ be the event
that the random point is in $B_1$. Give a geometric description of when it is true that $A$
and $B$ are independent. Also, give an example where they are independent and another
example where they are not independent.

(c) Show that if $A$ and $B$ are independent, then
$$
P (A \cup B) = P(A) + P(B) - P(A)P(B) = 1 - P(A^c)P(B^c)
$$


Answer:

(a) In the 2 by 2 Pebble World, Suppose $A$ is the event of choosing a pebble in the top row, $B$ is the event of choosing a pebble in the first column. $A \cap B$ is the event of choosing the top left pebble. $P(A) = 0.5$, $P(B) = 0.5$, $P(A \cap B) = 0.25$. So $P(A \cap B) = P(A)P(B)$. It means $A$ is independent of $B$.

(b) Skip

(c) Skip

**Q48**

Arby has a belief system assigning a number $P_{Arby}(A)$ between $0$ and $1$ to every event
$A$ (for some sample space). This represents Arby’s degree of belief about how likely A
is to occur. For any event $A$, Arby is willing to pay a price of $1000·P_{Arby}(A)$ dollars to
buy a certificate such as the one shown below

    Certificate

    The owner of this certificate can redeem it for $1000 if A occurs. No
    value if A does not occur, except as required by federal, state, or local
    law. No expiration date.

Likewise, Arby is willing to sell such a certificate at the same price. Indeed, Arby is
willing to buy or sell any number of certificates at this price, as Arby considers it the
"fair" price.

Arby stubbornly refuses to accept the axioms of probability. In particular, suppose that
there are two disjoint events A and B with
$$
P_{Arby}(A \cup B) \ne P_{Arby}(A) + P_{Arby}(B) \text{.}
$$

Show how to make Arby go bankrupt, by giving a list of transactions Arby is willing
to make that will guarantee that Arby will lose money (you can assume it will be
known whether $A$ occurred and whether $B$ occurred the day after any certificates are
bought/sold).

Answer: Skip

# Inclusion-exclusion

**Q49**

A fair die is rolled $n$ times. What is the probability that at least $1$ of the $6$ values never appears?

Answer:

Suppose $A_i$ is the event that value $i$ never appears. The problem is to find out
$$
P(A_1 \cup \ldots \cup A_6)
$$
We can use inclusion-exclusion rule. First of all, there are $6^n$ equally likely outcomes of rolling a fair die $n$ times. If a particular value $i$ never appears, every roll has only 5 allowed values, therefore
$$
|A_i| = 5^n
$$
There are $\binom{6}{1}$ choices for which value is missing, give the first inclusion-exclusion term
$$
\binom{6}{1} 5^n
$$
Similarly, $|A_i \cap A_j| = 4^n$, the second term is
$$
\binom{6}{2} 5^n
$$

The last term is
$$
\binom{6}{6} 0^n = 0
$$

So the probability that at least one of the 6 values never appears is
$$
\frac{\binom{6}{1} 5^n - \binom{6}{2} 4^n + \binom{6}{3} 3^n - \binom{6}{4} 2^n + \binom{6}{5} 1^n}{6^n}
$$

**Q50**

A card player is dealt a 13-card hand from a well-shuﬄed, standard deck of cards.
What is the probability that the hand is void in at least one suit ("void in a suit" means
having no cards of that suit)?

Answer:

Suppose $A_i$ is the event that suit $i$ is void in the hand. This problem is to figure out
$$
P(A_1 \cup A_2 \cup A_3 \cup A_4)
$$
We can use inclusion-exclusion rule. There are $\binom{52}{13}$ equally likely hands. Among these possible outcomes $|A_i| = \binom{39}{13}$. So the first term is
$$
\binom{4}{1} \binom{39}{13}
$$

Similarly the second term is
$$
\binom{4}{2} \binom{26}{13}
$$

The third term is
$$
\binom{4}{3} \binom{13}{13}
$$

The last term is 4 suits are avoid, and it's impossible.

So the probability that the hand is void in at least one suit is
$$
\frac{\binom{4}{1} \binom{39}{13} - \binom{4}{2} \binom{26}{13} + \binom{4}{3} \binom{13}{13}}{\binom{52}{13}}
$$

**Q51**

For a group of 7 people, find the probability that all 4 seasons (winter, spring, summer, fall) occur at least once each among their birthdays, assuming that all seasons are equally likely.

Answer:

There are $4^7$ equally likely outcomes for the birthdays among the 4 seasons. By using the Stirling number, the number of possible partitions that each block has at least 1 birthday is
$$
\begin{Bmatrix} 7 \\ 4 \end{Bmatrix}
$$
Each partition has $7!$ ordered possibilitis. Therefore the possibility is
$$
\frac{7! \cdot \begin{Bmatrix} 7 \\ 4 \end{Bmatrix}}{4^7}
$$

**Q52**

A certain class has 20 students, and meets on Mondays and Wednesdays in a classroom with exactly 20 seats. In a certain week, everyone in the class attends both days. On both days, the students choose their seats completely randomly (with one student per seat). Find the probability that no one sits in the same seat on both days of that week.

Answer:

Fix any particular Monday seating. There are $20!$ equally likely Wednesday seatings.

Let $A_i$ be the event that student $i$ occupies the same seat on Wednesday as on Monday. We want to count Wednesday seatings in which none of the $A_i$ occur. We can use inclusion-exclusion to calculate the complement probability
$$
P(\bigcup_{i=1}^{20} A_i)
$$
If there are $k$ students take the same seat, we only need to consider $20-k$ students, and there are $\binom{20}{k}$ ways to choose the $k$ students.

By inclusion-exclusion, the number of favorable Wednesday seatings is
$$
\sum_{k=0}^{20} (-1)^k \binom{20}{k} (20-k)! \tag{1}
$$

Note that
$$
\binom{20}{k} (20-k)! = \frac{20!}{(20-k)!k!} (20-k)! = \frac{20!}{k!} \tag{2}
$$

Substituting (2) into (1), we obtain
$$
\sum_{k=0}^{20} (-1)^k \frac{20!}{k!} = 20! \sum_{k=0}^{20} (-1)^k \frac{1}{k!}
$$

Therefore the probability is
$$
\frac{20! \sum_{k=0}^{20} (-1)^k \frac{1}{k!}}{20!} = \sum_{k=0}^{20} (-1)^k \frac{1}{k!}
$$

**Q53**

Fred needs to choose a password for a certain website. Assume that he will choose an 8-character password, and that the legal characters are the lowercase letters a, b, c, ... , z, the uppercase letters A, B, C, ... , Z, and the numbers 0, 1, ... , 9.

(a) How many possibilities are there if he is required to have at least one lowercase letter in his password?

(b) How many possibilities are there if he is required to have at least one lowercase letter and at least one uppercase letter in his password?

(c) How many possibilities are there if he is required to have at least one lowercase letter, at least one uppercase letter, and at least one number in his password?

Answer:

(a)

Assume $A_i$ is the event that the position $i$ contains a lowercase letter. We can consider using inclusion-exclusion to figure out
$$
|A_1 \cup \ldots \cup A_{26}|
$$

For a particular set of $k$ position:
* Those $k$ positions have 26 lowercase choices.
* The other $k-8$ positions have 62 choices.

Thus, a k-fold intersection has
$$
26^k \cdot 62^{8-k}
$$
passwords. Inclusion-exclusion gives
$$
\sum_{k=1}^8 (-1)^{k+1} \binom{8}{k} 26^k \cdot 62^{8-k}
$$

Alternatively, at least one lowercases is complementory to no lowercases so the number of possible favorable password is $62^8 - 36^8$

(b)

Let $A_l$ be the event that there is at least one lowercase letter in the password, $A_u$ is the event that there is at least one uppercase letter in the password. By (a), we have $|A_l| = |A_u| = 62^8 - 36^8$.

Because
$$
|A_l \cup A_u| = |A_l| + |A_u| - |A_l \cap A_u|
$$

And $|A_l \cup A_u|$ is complementory to $|A_n|$, where $A_n$ is the event that the password only contains numbers, which is $10^8$.

So we have
$$
|A_l \cap A_u| = 62^8 - 2 \cdot 36^8 + 10^8
$$

(c)

Let $A_d$ be the event that there is at least one digit in the password. We need to find
$$
|A_l \cap A_u \cap A_d|
$$

From inclusion-exclusion rule, we know that
$$
|A_l \cup A_u \cup A_d| = |A_l| + |A_u| + |A_d| - |A_l \cap A_u| - |A_l \cap A_d| - |A_u \cap A_d| + |A_l \cap A_u \cap A_d|
$$

We know that
$$
|A_l \cup A_u \cup A_d| = 62^8 \\
|A_l| = 62^8 - 36^8 \\
|A_u| = 62^8 - 36^8 \\
|A_d| = 62^8 - 52^8 \\
|A_l \cap A_u| = 62^8 - 2 \cdot 36^8 + 10^8 \\
|A_l \cap A_d| = |A_l| + |A_d| - |A_l \cup A_d| = 62^8 - 36^8 - 52^8 + 26^8\\
|A_u \cap A_d| = 62^8 - 36^8 - 52^8 + 26^8
$$
Substituting these into the inclusion-exclusion formula, we have
$$
62^8 = 52^8 + 2 \cdot 36^8 - 2 \cdot 26^8 - 10^8 + |A_l \cap A_u \cap A_d|
$$
Rearranging gives
$$
|A_l \cap A_u \cap A_d| = 62^8 - 52^8 - 2 \cdot 36^8 + 2 \cdot 26^8 + 10^8
$$

**Q54**

Alice attends a small college in which each class meets only once a week. She is deciding between 30 non-overlapping classes. There are 6 classes to choose from for each day of the week, Monday through Friday. Trusting in the benevolence of randomness, Alice decides to register for 7 randomly selected classes out of the 30, with all choices equally likely. What is the probability that she will have classes every day, Monday
through Friday? (This problem can be done either directly using the naive definition of probability, or using inclusion-exclusion.)

Answer:

Let $M_i$ be the event that Alice chooses no class that meet on day $i$, where $i \in \{1,\ldots,5\}$. We want the the probability that none of the events $M_i$ occur.

There are
$$
\binom{30}{7}
$$
equally likely ways for Alice to choose seven of the thirty classes.

For a fixed $S \subseteq \{1, \ldots, 5\}$ with $|S| = k$, let
$$
B_S = \bigcap_{i \in S} M_i
$$

The event $B_S$ occurs when Alice chooses no classes on any of the $k$ days in $S$. Excluding those days leaves $30-6k$ available classes. Therefore,
$$
|B_S| = \binom{30 - 6k}{7}.
$$

There are $\binom{5}{k}$ ways to choose $k$ excluded days. By inclusion-exclusion,
$$
|\bigcup_{k=1}^5 M_k| = \sum_{k=1}^5 (-1)^{k+1}\binom{5}{k}\binom{30 - 6k}{7}.
$$

Hence, the number of favorable selections in which Alice has at least one class every day is
$$
\binom{30}{7} - |\bigcup_{k=1}^5 M_k| = \sum_{k=0}^5 (-1)^{k}\binom{5}{k}\binom{30 - 6k}{7}
$$

And the desired probability is
$$
\begin{aligned}
\frac{\sum_{k=0}^5 (-1)^{k}\binom{5}{k}\binom{30 - 6k}{7}}{\binom{30}{7}}
\end{aligned}
$$

**Q55**

A club consists of 10 seniors, 12 juniors, and 15 sophomores. An organizing committee of size 5 is chosen randomly (with all subsets of size 5 equally likely).

(a) Find the probability that there are exactly 3 sophomores in the committee.

(b) Find the probability that the committee has at least one representative from each of the senior, junior, and sophomore classes.

Answer:

(a) First select the 3 sophomores, then select the rest from the seniors and juniors. The probability is
$$
\frac{\binom{15}{3} \binom{22}{2}}{\binom{37}{5}}
$$

(b)

Let $M_s$, $M_j$ and $M_p$ be the event that no seniors, no juniors and no sophomores in the committee respectively.

Obviously
$$
|M_s| = \binom{27}{5} \\
|M_j| = \binom{25}{5} \\
|M_p| = \binom{22}{5} \\
|M_s \cap M_j| = \binom{15}{5} \\ 
|M_s \cap M_p| = \binom{12}{5} \\ 
|M_j \cap M_p| = \binom{10}{5} \\ 
|M_s \cap M_j \cap M_p| = 0
$$

By inclusion-exclusion we have
$$
\begin{aligned}
|M_s \cup M_j \cup M_p| &= |M_s| + |M_j| + |M_p| - |M_s \cap M_j| - |M_s \cap M_p| - |M_j \cap M_p| + |M_s \cap M_j \cap M_p| \\
&= \binom{27}{5} + \binom{25}{5} + \binom{22}{5} - \binom{15}{5} - \binom{12}{5} - \binom{10}{5}
\end{aligned} 
$$

Therefore the desired probability is
$$
1 - \frac{\binom{27}{5} + \binom{25}{5} + \binom{22}{5} - \binom{15}{5} - \binom{12}{5} - \binom{10}{5}}{\binom{37}{5}}
$$
