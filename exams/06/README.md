
## The Office (75 points)

The [`schrute`](https://github.com/bradlindblad/schrute) R package
contains the script from every episode of the popular television series
[“The
Office”](https://en.wikipedia.org/wiki/The_Office_\(American_TV_series\)).
The raw data (stored in a data frame called `theoffice`) contains the
following columns:

  - `index`: Row indicator (values from 1 to number of rows)
  - `season`: Season of The Office
  - `episode`: Episode number for the given season
  - `episode_name`: Name of the episode
  - `director`: Episode director
  - `writer`: Episode writer (sometimes delimited by `;`)
  - `character`: Name of the character from the show
  - `text`: The line that was spoken
  - `text_w_direction`: Same as `text`, but includes directions (ie \[On
    the phone\])

Given this data, it’s possible to formulate and test various hypotheses.
For example, you could hypothesize that male characters have more lines
than female characters. Or you could hypothesize that episodes written
by B.J. Novak contain more lines than episodes written by Mindy Kaling.
Or you could hypothesize that the number of lines spoken by Dwight and
Jim are correlated. Since each “line” of the show is an observation,
it’s possible to expand the data so that each *word* of the show is an
observation:

``` r
# install.packages("tidytext")
library(tidytext)
library(schrute)

office_tokens <- theoffice %>% 
  unnest_tokenoutput = word, input = text)
```

In this case, `office_tokens` is a data frame of 570566 observations
where each observation represents a single word spoken by a character in
the show. With this alternative format, you can investigate questions
like who has the most words or which words are most common across
seasons and episodes.

Regardless of how you choose to represent the data, you must come up
with your own null and alternative hypotheses (you can use the examples
provided for inspiration). Once you have decided on your hypotheses, you
will conduct both a bootstrap procedure and a permutation test to test
your hypotheses.

1.  Clearly state your null and alternative hypothesis (in comments if
    using an R Script, or in plain text if using RMarkdown) (10 points)
2.  Calculate the observed test statistic upon which your hypothesis is
    based. This might be a difference in means or a correlation or any
    other summary statistic. It should be a single value (10 points)
3.  Conduct a bootstrap procedure to test your hypothesis (20 points):
      - Calculate 5,000 bootstrapped test statistics (10 points)
      - Based on your results from the above 5,000 samples, calculate a
        95% confidence interval on your observed test statistic (10
        points)
4.  Conduct a permutation test to test your hypothesis (20 points):
      - Perform a permutation test with 5,000 samples (10 points)
      - Calculate the p value for your original test statistic along
        with its 95% confidence interval (10 points)
5.  Interpret your conclusions from both procedures (5 points)
6.  Plot the resulting distribution from both procedures in the same
    plot along with a vertical line indicating the observed test
    statistic. (10 points)

## Cars (45 points)

The built in `cars` dataset in R contains 2 columns:

  - speed: The speed of the car
  - dist: The stopping distance of the car

Given this data, we have the following hypotheses:

**Null:** There is no correlation between `speed` and `dist`  
**Alternative:** The correlation between `speed` and `dist` is greater
than zero

1.  Calculate the correlation between `speed` and `dist` (10 points)
2.  Perform a permutation test with 10,000 samples and store the results
    (10 points)
3.  Plot the density of the results from step 3 along with a vertical
    red line for the observed correlation calculated in step 2 (10
    points)
4.  Using the results from 2 and 3, calculate an estimated P value for
    the observed correlation (5 points)
5.  Calculate a 95% confidence interval on the P value you estimated in
    step 5 (5 points)
6.  Interpret your results (5 points)

-----

#### **Please make sure that you save all changes made in RStudio Cloud prior to the deadline. If changes are not saved, they cannot be graded.**
