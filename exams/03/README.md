
## Fishing (50 points)

My Grandpa Jasperson (Grandpa J as I’ve always known him) is an avid
fisherman, and he’s passed that love along to me. We both agree that
[Mirror
Lake](http://www.utahfishinginfo.com/utahlakes/uintas/mirrorlake.php)
and [Strawberry
Reservoir](http://www.utahfishinginfo.com/utahlakes/strawberry.php) are
two of the best places in Utah to go fishing. However, we weren’t
certain which place was the best. This past year, we decided to perform
a little experiment. We went fishing 20 times over the summer, and each
time we went, one of us went to Mirror Like while the other went to
Strawberry. We counted the number of fish we caught each trip, and now
we’d like to know which is the better fishing spot.

![](grandpa-j.jpeg)

1.  Using the data provided in `fishing.csv`, calculate the observed
    difference in medians between the two fishing locations (5 points).
2.  Using bootstrap sampling with 10,000 samples, calculate a 95%
    confidence interval on the observed difference in medians (15
    points).
3.  Based on your results, which fishing spot is the best (5 points)?
4.  Based on bootstrap sampling, who is the better fisherman (25
    points)?

## Tommy John (30 points)

You work in the front office of a professional baseball team. You are
faced with the task of deciding whether to sign a pitcher who recently
underwent [Tommy
John](https://en.wikipedia.org/wiki/Ulnar_collateral_ligament_reconstruction)
surgery. Because your team values strikeouts, you wish to perform a
study on the impact of Tommy John surgery on the Strikeout per 9 inning
(k/9) statistic of a pitcher. You have the k/9 statistic both 2 years
before surgery and 2 years after surgery for 15 pitchers.

Perform a a permutation test under the null hypothesis that Tommy John
surgery has no effect on a pitcher’s strikeout statistics and the
alternative hypothesis that having the surgery makes pitchers worse.

\[
H_0 = \text{k9}_{pre} = \text{k9}_{post}\\
H_a = \text{k9}_{pre} > \text{k9}_{post}
\]

Use the mean difference in k/9 as your test statistic.

1.  Using the data provided in `tj.csv`, calculate the observed test
    statistic (5 points).
2.  Perform a permutation test with 10,000 repetitions and store the
    results in a vector (10 points).
3.  Plot a histogram of your results from step 2 with a vertical red
    line that represents the result from part 1 (5 points).
4.  Calculate the P value for the observed test statistic and its 95%
    confidence interval (5 points).
5.  Based on your results, is it worth it to sign a pitcher coming off
    of Tommy John surgery (5 points)?

## Bootstrapped Coverage (40 points)

The `USArrests` data built into R contains arrest statistics for each of
the 50 US states in 1973. In this problem, we’re interested in looking
at the `Assault` column, which can be extracted with the following code:

``` r
assault <- USArrests$Assault
```

We’re going to treat these 50 observations as the population. The
population mean can be calculated with `mean(assault)` and is 170.76. We
want to determine the coverage of a 90% bootstrapped confidence interval
built on a random sample of 10 observations from the `assault` data.

1.  Create a function that takes in a vector (`p`) and returns a 90%
    bootstrapped confidence interval on the mean using a random sample
    of size 10 taken from the vector `p`. Use 1,000 bootstrap samples
    (10 points). This function should do two things:
    1.  Sample 10 random values from `p`.
    2.  Using those 10 random values, calculate and return a 90%
        bootstrapped confidence interval on the mean of `p`.
2.  Using the function defined above, calculate 5,000 bootstrapped
    confidence intervals and store the results (10 points).
3.  Using the results from step 2, calculate the coverage of the
    bootstrapped confidence interval (5 points).
4.  Calculate a 95% confidence interval on your estimate of coverage (5
    points).
5.  Interpret your results. If coverage is not what you would expect,
    what could be done differently to improve the results (10 points)?
