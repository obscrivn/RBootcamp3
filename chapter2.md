---
title       : T-Test
description : 

--- type:NormalExercise lang:r xp:100 skills:1 key:4c038f7bad

Let's look again at the speeds in the dataframe cars. 
*** =instructions

- Run a two-sided t-test the 90% confidence level on the null hypothesis that the mean is 20
-Fill out blanks in the formula


*** =hint


*** =pre_exercise_code
```{r}

```


*** =sample_code
```{r}
# change X by the correct values
t.test(cars$speed, mu=X, conf.level = .X) 

```

*** =solution
```{r}
t.test(cars$speed, mu=, conf.level = .90) 

```
