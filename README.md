# METHODOLOGY: A new approach to analyzing the value of tanking: Markov chains

[Link to blog post.](https://dribbleanalytics.blog/2019/05/tanking-markov-chains)

## Data collection

Using Basketball-Reference, I created a database of every team's seed and playoff victories since 1985, when the NBA introduced the draft lottery. I then cleaned the data to make it a consecutive list for each team so that we can see each team's transition from each seed.

## Markov chains

With this data, I created three different Markov chains.

First, I created a 3-state Markov chain. The 3 states were:

1. Bottom five
2. Lottery
3. Playoffs

I analyzed how the first two states transition to the playoffs by running 100,000 simulations of the Markov chain over five- and ten- year periods.

Then, I created a 4-state Markov chain. The 4 states were:

1. Bottom five
2. 6-10
3. 11-14
4. Playoffs

Because the league had 23 teams in 1985 - the first year in the data set - there were only 7 teams not in the playoffs. This meant that a team not in the bottom five was at most two spots out of a playoff berth. Therefore, the data set for this chain consists of all data from 2005, when the NBA had 30 teams.

I analyzed the playoff probability in the same way as the 3-state chain.

Finally, I created a 7-state Markov chain. The 7 states were:

1. Bottom five
2. Lottery
3. Playoffs
4. 1 series won
5. 2 series won (made conference finals)
6. 3 series won (lost finals)
7. 4 series won (won finals)

Instead of analyzing playoff probability, I analyzed a team's chance to make the conference finals. Furthermore, the third state (made playoffs) was included to see if being a first-round exit helps a team.

The conference finals were used instead of the sixth or seventh states because one team won the finals after being a bottom five team (2007-2008 Celtics), but no team lost in the finals after being a bottom five team. Meanwhile, no teams won the finals after being a lottery team, meaning that if we predicted losing/winning the finals, one of the states would have a probability of 0.
