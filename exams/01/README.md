## Climate Change (45 points)
Climate change is an ongoing issue that scientists frequently debate about.
Though there are many factors which contribute to rising average temperatures
across the United States, one claim is that crude oil consumption directly
affects the rising temperatures. As statisticians, we understand that both
variables are observational, meaning that there can be correlation between the
two variables, but causation cannot be concluded. Thus, for this study, we are
interested in discovering whether there is significant correlation between crude
oil consumption levels and average temperature readings.
The dataset `oil-temp.csv` has been provided and contains the following
variables:

+ `year`: Measurement year
+ `crude_oil_consumption`[^1]: Total annual US crude oil imports measured in
thousands of barrels
+ `temp_change`[^2]: Average change in US temperatures by degrees Fahrenheit
    
Given this data, our hypotheses are as follows:
$$
H_0: \text{cor} = 0\\
H_a: \text{cor} \ne 0
$$
    
1. Calculate the actual correlation coefficient between `crude_oil_consumption`
and `temp_change` (5 points)
2. Perform a permutation test with 10,000 samples and store the results in a
vector (15 points)
3. Create a histogram of your permutation test results and include a red line
for the actual correlation value (10 points)
4. Calculate the p value for the observed correlation coefficient and its 95%
confidence interval (10 points)
5. What do you conclude? (5 points)

## Tom Brady (35 points)
Tom Brady recently won his 6th Superbowl as the quarterback of the
New England Patriots. Many have speculated that what makes Brady
so good is his performance in the biggest situations, like the playoffs.
We want to check if Brady actually throws for more yards in playoff
games than he does in regular season games.

The `brady.csv`[^3] file contains data from all of Brady's games and includes
the following columns

+ `game_type`: Either "Regular" or "Playoff" indicating which type of game was played
+ `yards`: Number of yards Tom Brady threw for in the game

Given this data, we have the following hypotheses:
$$
H_0: \mu_{\text{playoff}} = \mu_{\text{regular}}\\
H_a: \mu_{\text{playoff}} > \mu_{\text{regular}}
$$
1. Find the difference in the average yards thrown for in playoff vs
regular season games (5 points)
2. Perform a permutation test with 10,000 samples and store the results in a
vector (15 points)
3. Calculate the p value for the observed difference in average yards thrown and
its 95% confidence interval (10 points)
4. Based on your results, does Tom Brady pass for more yards per game in the playoffs when compared to the regular season? (5 points)

## Seatbelts (40 points)
The built-in R dataset `Seatbelts` contains details about driver deaths and
injuries in Great Britain from Jan 1969 to Dec 1984. More information about the
data can be accessed by running `?Seatbelts`. Use the following line of code to
load this data into R as a data.frame:

```r
seatbelts <- as.data.frame(Seatbelts)
```

This data contains 8 columns and 192 rows of data. The `law` column is either a
0 or 1 indicating whether or not a law was in place requiring a seatbelt to be
worn. We want to know if this law had an impact on the proportion of drivers who
were killed out of those who were seriously injured. This proportion is
calculated by dividing `DriversKilled` by `drivers`.

1. Calculate the observed difference in proportion of drivers killed when the
law was in effect and when it was not in effect (10 points)
2. Calculate 10,000 bootstrapped differences in proportions and store the
results in a vector (15 points)
3. Based on the results from step 2, calculate a 95% confidence interval on the
difference in proportion of drivers killed (10 points)
4. Based on your results, did the law improve the proportion of injured drivers who were killed?
(5 points)

[^1]: Data from EIA.gov
[^2]: Data from EPA.gov
[^3]: Data from https://www.pro-football-reference.com/players/B/BradTo00/gamelog/