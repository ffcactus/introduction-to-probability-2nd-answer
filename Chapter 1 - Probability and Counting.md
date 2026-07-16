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
