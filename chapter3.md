---
title       : Regression
description : 

--- type:MultipleChoiceExercise xp:50 skills:1 key:a211c8722d

## Regression
If you have two categorical variable, your regression is:


*** =instructions
- linear
- multinomial
- binomial


*** =sct
```{r}
msg1 = "Try again"
msg2 = "Try again"
msg3 = "Well done"
test_mc(correct = 3, feedback_msgs = c(msg1,msg2,msg3))
```

--- type:MultipleChoiceExercise xp:50 skills:1 key:8abfaf0f2b


## Regression Packages
You can use help functions to read about the following functions ` lm ` and ` glm `

Which one allows to perform regression with continuous and categorical dependent/response variable?

*** =instructions
- lm
- glm


*** =sct
```{r}
msg1 = "Try again"
msg2 = "Well done"
test_mc(correct = 2, feedback_msgs = c(msg1,msg2))
```