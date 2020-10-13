## Probability (19 questions)


#### 1. Bobo the amoeba has a 25%, 25%, and 50% chance of producing 0, 1, or 2 offspring, respectively. Each of Bobo’s descendants also have the same probabilities. What is the probability that Bobo’s lineage dies out?
P=1/4+1/4^2+1/2*1/4^2
#### 2. In any 15-minute interval, there is a 20% probability that you will see at least one shooting star. What is the proba- bility that you see at least one shooting star in the period of an hour?
  P=1-0.8^4
#### 3. How can you generate a random number between 1 - 7 with only a die?
Toss a die twice, if (6,6) appears, toss it twice. By doing so, we got pairs of numbers from (1,1) to (6,5), divide them into 7 sets of 5 each. This way all seven sets outcome are equally likely.
#### 4. How can you get a fair coin toss if someone hands you a coin that is weighted to come up heads more often than tails?
  If the probability of getting a head is p, (p!=1/2). In order to get a fair coin toss, we can toss the coin twice, if HT p(1-p), then “head”. If TH (1-p)p, then “tail”. If HH p^2 or TT (1-p)^2, repeat
#### 5. You have an 50-50 mixture of two normal distributions with the same standard deviation. How far apart do the means need to be in order for this distribution to be bimodal?
  - more than two standard deviations [Quora Answer](https://www.quora.com/You-have-an-50-50-mixture-of-two-normal-distributions-with-the-same-standard-deviation-How-far-apart-do-the-means-need-to-be-in-order-for-this-distribution-to-be-bimodal-Why)
#### 6. Given draws from a normal distribution with known parameters, how can you simulate draws from a uniform distribution?
  - plug the draws to the CDF of normal distribution with known parameters, the reason for that is because CDF can be thought of as a percentile function, which is distributed uniformly. No matter how weird shape the original distribution is, plugging random draws into its CDF function always guarantee the transformed draw is uniformed distributed. On the contrary, if we plug the uniform distribution into the inverse quantile function, we can always get the original distribution back. 
#### 7. A certain couple tells you that they have two children, at least one of which is a girl. What is the probability that they have two girls?
  - GG, GB, BG, BB.  Given at least of which is a girl, we eliminate BB from the pool of choice. Therefore, the probability that they have two girls is 1/3. 
#### 8. You have a group of couples that decide to have children until they have their first girl, after which they stop having children. What is the expected gender ratio of the children that are born? What is the expected number of children each couple will have?
  -  gender ratio 1:1. Let X be the number of children until a couple have a girl. X~geom(p), with p=1/2.
The expected number of children each couple will have is 2. 
#### 9. How many ways can you split 12 people into 3 teams of 4?
  -  1 2 3 4 |5 6 7 8 | 9 10 11 12| There are 12! Different ways to arrange 12 people in a line, for each group with 4, it has 4! Different permutations, also have 3! Way for group permutation. Therefore, we have 12!/(3!*4!^3) number of ways. 
#### 10. Your hash function assigns each object to a number between 1:10, each with equal probability. With 10 objects, what is the probability of a hash collision? What is the expected number of hash collisions? What is the expected number of hashes that are unused.
  - the probability of a hash collision: 1-(10!/10^10)
  - the expected number of hash collisions: 1-10*(9/10)^10
  - the expected number of hashes that are unused: 10*(9/10)^10
#### 11. You call 2 UberX’s and 3 Lyfts. If the time that each takes to reach you is IID, what is the probability that all the Lyfts arrive first? What is the probability that all the UberX’s arrive first?
Lyft comes first, (3/5)*(2/4)*(1/3)=1/10, UberX’s arrive first, (2/5)*(1/4)=1/10.

#### 12. I write a program should print out all the numbers from 1 to 300, but prints out Fizz instead if the number is divisible by 3, Buzz instead if the number is divisible by 5, and FizzBuzz if the number is divisible by 3 and 5. What is the total number of numbers that is either Fizzed, Buzzed, or FizzBuzzed?
- #(Fizz or Buzz)=#(Fizz)+#(Buzz)-#(Fizz and Buzz)=140

#### 13. On a dating site, users can select 5 out of 24 adjectives to describe themselves. A match is declared between two users if they match on at least 4 adjectives. If Alice and Bob randomly pick adjectives, what is the probability that they form a match?
  - (C (5,4) * C (19,1) + C(5,5)* C(19,0))/ C(24,5)
#### 14. A lazy high school senior types up application and envelopes to n different colleges, but puts the applications randomly into the envelopes. What is the expected number of applications that went to the right college?
  - Let X be the number of applications that went to the right college. $X=\sum_{i=1}^nI_i$ I_i is the indicator function that ith application goes to the ith college.
-  $$E(X)=\sum_{i=1}^nE(I_i)=\sum_{i=1}^nP(X_i=i)= \sum_{i=1}^n*1/n=1$$
#### 15. Let’s say you have a very tall father. On average, what would you expect the height of his son to be? Taller, equal, or shorter? What if you had a very short father?
  -  Regress to the mean. 
#### 16. What’s the expected number of coin flips until you get two heads in a row? What’s the expected number of coin flips until you get two tails in a row?
  - 6. [Quora Answer] (https://www.quora.com/What-is-the-expected-number-of-coin-flips-until-you-get-two-heads-in-a-row)
#### 17. Let’s say we play a game where I keep flipping a coin until I get heads. If the first time I get heads is on the nth coin, then I pay you 2n-1 dollars. How much would you pay me to play this game?
  - less than $3 [Quora Answer] (https://math.stackexchange.com/questions/1448973/fair-value-of-game-involving-obtaining-heads)
#### 18. You have two coins, one of which is fair and comes up heads with a probability 1/2, and the other which is biased and comes up heads with probability 3/4. You randomly pick coin and flip it twice, and get heads both times. What is the probability that you picked the fair coin?
  - 4/13 Bayes Theorem
#### 19. You have a 0.1% chance of picking up a coin with both heads, and a 99.9% chance that you pick up a fair coin. You flip your coin and it comes up heads 10 times. What’s the chance that you picked up the fair coin, given the information that you observed?
  * Events: F = "picked a fair coin", T = "10 heads in a row"
  * (1) P(F|T) = P(T|F)P(F)/P(T) (Bayes formula)
  * (2) P(T) = P(T|F)P(F) + P(T|¬F)P(¬F) (total probabilities formula)
  * Injecting (2) in (1): P(F|T) = P(T|F)P(F)/(P(T|F)P(F) + P(T|¬F)P(¬F)) = 1 / (1 + P(T|¬F)P(¬F)/(P(T|F)P(F)))
  * Numerically: 1/(1 + 0.001 * 2^10 /0.999).
  * With 2^10 ≈ 1000 and 0.999 ≈ 1 this simplifies to 1/2
#### 20. What is a P-Value ?
  * The probability of obtaining a test statistic which is as extreme as or more extreme than observed given the null hypothesis is true. 
  * ⇒ If the p-value is small, the null hypothesis is unlikely
