---
title       : Contingency Tables
description : Insert the chapter description here

--- type:NormalExercise lang:r xp:100 skills:1 key:21e5dc8285

## Creating 2x2 table

* You can create a table using ` as.table() ` function.

* You can use ` prop.table() ` to change raw frequencies to percentages

* ` prop.table(mydata, 1) ` for row and ` prop.table(mydata, 2) ` for column percentages

*** =instructions

- Convert a matrix into  a table using ` as.table() `
- Add margins to your table with ` addmargins() `
- Create a probability table (with percentage instead of raw numbers). First calculate percentages over columns, then over rows

*** =hint


*** =pre_exercise_code
```{r}

```


*** =sample_code
```{r}

smoke <- matrix(c(51,43,22,92,28,21,68,22,9),ncol=3,byrow=TRUE)

colnames(smoke) <- c("High","Low","Middle")

rownames(smoke) <- c("current","former","never")

# convert smoke into a table
smoke <-

# margins


# prop.table for columns



# prop.table for rows

```

*** =solution
```{r}

smoke <- matrix(c(51,43,22,92,28,21,68,22,9),ncol=3,byrow=TRUE)

colnames(smoke) <- c("High","Low","Middle")

rownames(smoke) <- c("current","former","never")

# table
smoke <- as.table(smoke)

# margins
addmargins(smoke)

# prop.table for columns
prop.table(smoke, 2)


# prop.table for rows
prop.table(smoke, 1)

```
*** =sct
```{r}
test_object("smoke",incorrect_msg = "try again")
test_output_contains("addmargins(smoke)")
test_output_contains("prop.table(smoke, 2)")
test_output_contains("prop.table(smoke, 1)")
success_msg("Good work!")

```
--- type:NormalExercise lang:r xp:100 skills:1 key:ada56e2f25

## Modify your data frame

You can convert you data into data frame by using ` as.data.frame() `

*** =instructions

- Change the line 1 : instead of byrow=TRUE, use ` byrow=FALSE `
- Change colnames to only **h**,**l**,**m**
- Convert you data into  a data frame using ` as.data.frame() `
- Type ` str() ` function



*** =hint


*** =pre_exercise_code
```{r}

```


*** =sample_code
```{r}

smoke <- matrix(c(51,43,22,92,28,21,68,22,9),ncol=3,byrow=TRUE)

colnames(smoke) <- c("High","Low","Middle")

rownames(smoke) <- c("current","former","never")

# data frame
mydata <-
# str


```

*** =solution
```{r}

smoke <- matrix(c(51,43,22,92,28,21,68,22,9),ncol=3,byrow=FALSE)

colnames(smoke) <- c("h","l","m")

rownames(smoke) <- c("current","former","never")

#data frame
mydata <- as.data.frame(smoke)
#str
str(mydata)

```
*** =sct
```{r}
#test_object("colnames(smoke)")
test_object("mydata")
test_output_contains("str(mydata)")
success_msg("Good work!")

```
