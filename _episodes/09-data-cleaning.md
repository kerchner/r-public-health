---
title: "Data Cleaning"
teaching: 45
exercises: 10
questions:
- "How can I focus on just the variables I'm interested in?"
- "What are some ways of viewing the raw frequencies of variables?"
- "How to count the number of cases vs. controls?"
- "How to assess nulls/missing values in my data"
objectives:
- "Learn how to create a subset with just certain variables"
- "Techniques for dealing with null values in R -- ex. null might be represented in the data as `999`"
keypoints:
- "Use `table()` to look at frequencies"
- "Get a count ..."
---
library(tidyverse)

In cleaning the data, we need to decide the varibles that we are going to assess.  For that we can just look at the data frame that we created from merging.
Next, we want to make sure that the variables of interest have data for all the observations.  If let's say, in our case, we wanted to assess Total Chol, we will have to make sure that all the observations included in the analysis have a value associated with it. At this point, we would then delete all observations that don't have a value for that variable.  Make sure to inspect the data after each step of cleaning/restriction.
~~~
hdlanalysis_df <- merge_df %>% drop_na(LBXTC)
~~~
{: .language-r}

Next, we will restrict to 30=<Age=<65:
~~~
hdlanalysis_df <- hdlanalysis_df %>% filter(RIDAGEYR<=65 & RIDAGEYR>=30)
~~~
{: .language-r}
Next, let's count "NA" for our IV.  WHAT I NEED TO LOOK UP: can we do the analysis with NAs included 
summary(hdlanalysis_df$LBDLDL)
