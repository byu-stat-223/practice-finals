
## General Conference (80 points)

The file `general-conference.csv` contains word counts for [General
Conference Talks](https://www.lds.org/general-conference?lang=eng) from
the past 20 years. The data contains the following columns:

  - `year`: the year of the conference
  - `month`: the month of the conference
  - `session`: the session of conference
  - `talk_title`: title of the talk
  - `speaker`: name of the talk speaker
  - `words`: number of words in the talk

Given this data, you must formulate some hypothesis around word counts.
For example, you may hypothesize that conference talks contained more
words before 2000 compared to after. Or you may hypothesize that Elder
Holland’s talks have more words than Elder Eyring’s talks. Or you may
hypothesize that Priesthood Session talks have more words than General
Relief Society Session talks. These are simply suggestions to get you
thinking. *It is up to you to decide on the hypothesis you want to
investigate*. Once you have decided on your hypothsis, you will conduct
both a bootstrap procedure and a permutation test to test your
hypothesis. The following outlines the steps you should follow and the
points available at each step.

1.  Clearly state your null and alternative hypothesis (in comments if
    using an R Script, or in plain text if using RMarkdown) (10 points)
2.  Read the data into R (5 points)
3.  Subset your data into the groups necessary for your hypothesis test
    (10 points)
4.  Conduct a bootstrap procedure to test your hypothesis (25 points):
      - Calculate the observed difference in median word count between
        your two groups (5 points)
      - Calculate 10,000 bootstrapped differences (10 points)
      - Based on your results from the above 10,000 samples, calculate a
        95% confidence interval on your observed difference (10 points)
5.  Conduct a permutation test to test your hypothesis (25 points):
      - Calculate the observed difference in median word count between
        your two groups (5 points)
      - Perform a permutation test with 10,000 samples (10 points)
      - Calculate the p value for your observed difference along with
        its 95% confidence interval (10 points)
6.  Interpret your conclusions from both procedures (5 points)

## Sickness (40 points)

In R, there is a built-in dataset called `ldeaths` that gives monthly
deaths from lung diseases in the UK. We are interested in knowing if
there are significantly more deaths on average in the first three years
compared to the last three years.

Use the following code to load and format the data in R:

``` r
sick <- as.vector(datasets::ldeaths)
sick_df <- data.frame(matrix(sick, ncol = 12, byrow = TRUE, dimnames = list(1974:1979, month.abb)))
```

`sick_df` is now a `data.frame` that contains 6 rows and 12 columns.
Each row corresponds with a year and each column corresponds with a
month.

We want to know if there are significantly more deaths on average in the
first three years (1974 - 1976) compared to the next three years (1977 -
1979). \[
\text{H}_0:\mu^{1974 - 1976}_{deaths} = \mu^{1977 - 1979}_{deaths} \\
\text{H}_0:\mu^{1974 - 1976}_{deaths} \gt \mu^{1977 - 1979}_{deaths}
\]

Perform a permutation test to determine if there is a significant
difference.

1.  Using `sick_df`, calculate the observed difference in means between
    the first three years and the next three years. (10 points)
2.  Perform a permutation test on the difference in means with 10,000
    repetitions and store the results in a vector (10 points)
3.  Plot a histogram or density curve of your results from step 2 with a
    red vertical line that represents the observed difference calculated
    in step 1 (10 points)
4.  Calculate the P value for the observed difference in means and its
    95% confidence interval (10 points)
