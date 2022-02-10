---
title: Data Science Interview Prep Questions
tree_state: 🌱
---

1. Say we are doing a train, validation, test split on a dataset with 9 rows and we have a feature that is all 0 except 2 datapoints have the value of 1. What is the probability that these 2 datapoints are all in the same split (either train, val, test)?
2. Say you have a cube, where the vertices of the cube can either be blue or green and they have a probability of $1/2$ for being each color. What is the probability of randomly generated a cube that has no 2 adjacent vertices with the same color?
5. Let's say you have a very large number of features and you want to limit the number using L1 regression. What is L1 penalty? How does it differ from ridge regression?
   1. Say we have features for house price and income, as well as features for number of hospital visits and binary features for diseases that the individual has, which features will be penalized more using L1 regression?
   2. How can we compensate for this so that we don't penalize features that are smaller in scale?
4. Dice Expected Value:
   1. Expected value problem: You roll a 12 sided dice and you get the value from that roll or you get to roll a six sided dice and get 2 times the value of that (or you get to roll 2 6 sided dice)
5. Let's say you Interview at a few small companies, where salary is unknown. Salary is random variable which has equal 1/5 chance of 100,200,300,400,500K salaries. But after time passes from each successive interview, due to inflation the value of each salary becomes new_value = 0.5^interview_number * old_value. So the more interviews you do the less potential salary you can earn. What's the strategy to earn the optimal strategy and the expected amount of time it would take to accept a job.
6. Estimate the amount of time a football is in the air during a football game (or another sport if they are more comfortable with a different sport).
7. Design an algorithm that takes in a list of jobs, salaries, distances, interview difficulties, and whatever else you need, and ranks job opportunities.
8. Given a list of transactions between a group of friends (can be one person paying multiple people, multiple people paying one person and vice versa), calculate and print out how much money individuals owe one another.
9. We have a database with a bunch of tables and some of the columns in different tables represent the same things: (i.e. patient ID is called patient_id, id, individual_id in different tables but there's also claim_id, which is sometimes called id as well among other things). How would you be able to figure out for each column which columns represent the same things?
   1. We can't iterate over every row because the datasets are huge, so how could you reduce computation necessary to find the related columns?
   2. Let's say we sort the ids and then check for overlap using just the last $n$ rows. There could be an issue for finding related columns because the distribution of patient_ids between different columns may not be uniform. For example, what if patient_ids are generated sequentially so that the first registered patient is 1, then 2, etc. If we have a table A that contains mostly patients who joined early then it will be hard to map these patient_ids to the other tables if we check the last $n$ rows. How can we compensate for this to get a more accurate idea of overlap?
10. Expected value of 1 roll where you get the amount shown on a dice. If you don't like it you can roll again. What's the expected value? What if you get to reroll twice?
11. Expected number of rolls to get 3 consecutive heads?
12. https://mindyourdecisions.com/blog/2019/06/10/how-to-solve-facebooks-raining-in-seattle-interview-question/


### Answers

1. Let's fix all the datapoints to be in the same set, so now we have $ {9-2 \choose 3-2}$ different ways to choose the datapoints for one set and then $ {6 \choose 3}$ ways to select the points for the other sets giving us ${7 \choose 1}{6 \choose 3}$ ways in which the 2 datapoints are in the same set (for one of the sets). We multiply this number by 3 to get the number of ways they can be in any of the sets together. Then, there are ${9 \choose 3}{6 \choose 3}$ different ways of selecting  points for each of the 3 train, val, test splits. So, the final answer is:

$$
3(\frac{{7 \choose 1}{6 \choose 3}}{{9 \choose 3}{6 \choose 3}}) = 3\frac{{7 \choose 1}}{{9 \choose 3}} = \frac{7}{84} = 0.08333333333
$$

2. There are 8 vertices in a cube. If you fix one of the vertices to be a specific color, then you will notice that there is only 1 configuration for the rest of the vertices such that the same colors are not adjacent. Now, if you fix it to be the other color then there is again only 1 configuration of vertices such that the same colors are not adjacent. So, there are actually only 2 configurations for the entire cube such that the rule with nonadjacent vertices is true. Therefore, we have a $(1/2)^8$ chance that the vertices will follow the first configuration and a $(1/2)^8$ chance that they follow the second configuration, giving us a total probability of generating a rule satisfying cube of $(1/2)^7$

5. Answer:

   1. Larger features are penalized less compared to smaller scaled features, because they must have a larger slope coefficient
   2. We should standardize features when doing L1 and L2 regression for this reason
   
4. Answer:

   1. $E(\text{12 sided dice}) = 6.5$
   2. $E(\text{2 six sided die}) = 7$
   3. $2*E(\text{1 six sided dice}) = 7$
   4. So we would only not roll twice if we get >= 7. So $E({game}) = ((7+8+9+10+11+12)/6)*(6/12) + (6/12)*7 = 8.25$

5. Optimal strategy is just to stop once you get a company offering the top 4 salaries. Time it takes is $1/(4/5) = 5/4 = 1.25$ rounds.

   1. Checking:

      300K: 100,200,300,400,500 (do top 4)

      150K: 50,100,150,200,250 (do top 4)

      75K: 25,50,75,100,125 (do top 4)

      37.5K: 12.5,25,37.5,50,62.5

6. Not sure just interested in their reasoning

7. Not sure just interested in their reasoning

8. To check that they know how to code. Right answer is any solution that works (the more efficient the better), like storing info in a 2D array of balances and then printing.

9. Can just check every row of columns and compare how much overlap there is compared to other columns

   1. Sort columns and compare overlap of last $n$
   2. Hashing the values make sure they're normally distributed, then sort and compare last $n$

10. $E(1roll) = (1/6)(6+1)6/2 = 3.5$
Only want to reroll if we get lower than 3.5, so 3 or lower.
$E(game with 1 reroll) = 1/2(5) + 1/2(3.5) = 4.25$
So now since the expected value of game with reroll is 4.25, we would only stop playing after the first roll if we get a 5 or a 6
$E(game with 2 rerolls) = 1/3(5.5) + 2/3(1/2(5)+1/2(3.5))= 2.75+2.125=4.667$

11. $E(X) = 1/2(1+E(X)) + 1/2(1/2(2+E(X)) + 1/2(1/2(3 + E(X)) + 1/2(3)) = 14$
- 1/2 chance of rolling tails immediately which increasing flips by 1
- 1/2 times 1/2 chance you roll a heads then tails which gives you 2 rolls
- 1/2 times 1/2 times 1/2 chance you flip for 3 heads

12. P(Rain|yes,yes,yes) = P(yes,yes,yes|Rain)P(Rain)/(P(yes,yes,yes))
$$P(yes,yes,yes|Rain)P(Rain)/(P(yes,yes,yes)) =
P(yes,yes,yes|Rain)P(rain)/(P(rain)P(yes,yes,yes|rain) + (P(no rain)P(yes,yes,yes|no rain))
= (2/3)^3 p / ((2/3)^3 p + (1/3)^3 (1-p))
$$ where p is prob of rain