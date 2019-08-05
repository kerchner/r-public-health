---
title: "Analyzing relationships within data"
teaching: 45
exercises: 10
questions:
- "How can I run a regression (linear, logistic)"
- "How can I compute odds ratios?"
- "How can I run statistical significance tests?"
objectives:
- "`cor()`"
- "Learn how to run regressions with `lm()` and `glm()`"
- "Learn how to isolate parts of the matrix that `lm()` returns"
- "Learn how to run `t.test()` - get p-value, CI, etc."
- "Assess interactions between variables"
keypoints:
- "Use `table()` to look at frequencies"
- "Get a count ..."
---
~~~
health_lm <- lm(LBXTC ~  BMXBMI + as.factor(RIAGENDR)+ RIDAGEYR + LBXTR, merge_df)
~~~
{: .language-r}

~~~
summary(health_lm)
~~~
{: .language-r}

~~~
Coefficients:
                       Estimate Std. Error t value Pr(>|t|)    
(Intercept)          147.821815   3.222024  45.879  < 2e-16 ***
BMXBMI                -0.135958   0.104734  -1.298    0.194    
as.factor(RIAGENDR)2   9.004540   1.467989   6.134 9.83e-10 ***
RIDAGEYR               0.388294   0.036397  10.668  < 2e-16 ***
LBXTR                  0.171620   0.008221  20.875  < 2e-16 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 37.8 on 2698 degrees of freedom
  (488 observations deleted due to missingness)
Multiple R-squared:  0.1981,	Adjusted R-squared:  0.1969 
F-statistic: 166.7 on 4 and 2698 DF,  p-value: < 2.2e-16
~~~
{: .output}