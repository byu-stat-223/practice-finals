
## Movies (80 points)

The file `movies.csv` contains details about movies release from 1986 to
2016. There are approximately 220 movies for each year. The data was
downloaded from [Kaggle](https://www.kaggle.com/danielgrijalvas/movies).
The data contains the following columns:

  - `budget`: the budget of a movie. Some movies don’t have this, so it
    appears as 0
  - `company`: the production company
  - `country`: country of origin
  - `director`: the director
  - `genre`: main genre of the movie
  - `gross`: revenue of the movie
  - `name`: name of the movie
  - `rating`: rating of the movie (R, PG, etc.)
  - `released`: release date (YYYY-MM-DD)
  - `runtime`: duration of the movie
  - `score`: IMDb user rating
  - `star`: main actor/actress
  - `votes`: number of user votes
  - `writer`: writer of the movie
  - `year`: year of release

Given this data, you must formulate some hypothesis you can test. There
are a variety of features you can use to formulate your hypothesis. For
example, you may hypothesize that family movies (G and PG) gross more
than other movies. Or you may hypothesize that comedies have a shorter
runtime than action movies. Or you may hypothesize that movies made by
Walt Disney Pictures have higher variance in budgets than those made by
Warner Bros. These are simply suggestions to get you thinking. *It is up
to you to decide on the hypothesis you want to investigate*. Once you
have decided on your hypothesis, you will conduct both a bootstrap
procedure and a permutation test to test your hypothesis. The following
outlines the steps you should follow and the points available at each
step.

1.  Clearly state your null and alternative hypothesis (in comments if
    using an R Script, or in plain text if using RMarkdown) (10 points)
2.  Read the data into R (5 points)
3.  Subset your data into the groups necessary for your hypothesis test
    (10 points)
4.  Conduct a bootstrap procedure to test your hypothesis (25 points):
      - Calculate the observed difference between your two groups. This
        may be a difference in means, variance, median, etc. (5 points)
      - Calculate 10,000 bootstrapped differences (10 points)
      - Based on your results from the above 10,000 samples, calculate a
        95% confidence interval on your observed difference (10 points)
5.  Conduct a permutation test to test your hypothesis (25 points):
      - Calculate the observed difference between your two groups. This
        may be a difference in means, variance, median, etc. (5 points)
      - Perform a permutation test with 10,000 samples (10 points)
      - Calculate the p value for your observed difference along with
        its 95% confidence interval (10 points)
6.  Interpret your conclusions from both procedures (5 points)

## TV Ratings (40 points)

You work in the entertainment industry and you are tasked with
understanding and predicting television ratings for a popular show. The
following data contains TV ratings for the past 5 seasons of the show
(each season is 10 episodes):

``` r
ratings <- c(7.76,6.48,7.61,7.95,8.45,8.70,6.05,8.97,8.97,9.68,7.55,6.90,7.56,
             7.73,7.50,8.62,7.24,8.67,8.17,9.58,6.62,6.54,7.11,7.32,7.23,7.47,
             7.56,7.88,7.71,8.40,5.48,5.56,6.61,6.38,6.36,6.82,5.94,6.27,6.57,
             7.94,5.13,5.64,5.95,6.43,6.23,6.23,6.54,6.74,7.28,8.12)
```

You want to know if the rating from one episode is correlated with the
rating of the next episode. You will conduct a permutation test to
determine if there is significant autocorrelation in the ratings.

1.  Calculate the autocorrelation of the `ratings` data (the correlation
    between each episode and the next episode) (10 points)
2.  Perform a permutation test with 10,000 samples and store the results
    (10 points)
3.  Plot the density of the results from step 2 along with a vertical
    red line for the observed value calculated in step 1 (10 points)
4.  Using the results from 1 and 2, calculate an estimated P value for
    the observed autocorrelation (5 points)
5.  Calculate a 95% confidence interval on the P value you estimated in
    step 3 (5 points)

-----

#### **Please make sure that you save all changes made in RStudio Cloud prior to the deadline. If changes aren’t saved, they cannot be graded.**
