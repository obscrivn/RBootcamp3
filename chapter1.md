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
* You can convert a table to a data frame using ` as.data.frame() ` function.

* You can change colnames and rownames

* You can use ` relevel() ` to change the order of levels 

* Ex. ` relevel(x, ref="male" )` - you changed the reference into *male** factor

*** =instructions

- Change the line 1 : instead of byrow=TRUE, use byrow=FALSE
- Change ncol to 2 insteda of 3
- Change colnames to only High and Low
- Convert a table into  a data frame using ` as.data.frame() `
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

smoke <- as.data.frame(smoke)

# change column names


# prop.table for columns



# prop.table for rows

```

*** =solution
```{r}

smoke <- matrix(c(51,43,22,92,28,21,68,22,9),ncol=2,byrow=FALSE)

colnames(smoke) <- c("High","Low")

rownames(smoke) <- c("current","former","never")

smoke <- as.data.frame(smoke)


```
*** =sct
```{r}
test_object("smoke",incorrect_msg = "try again")
test_object("colnames(smoke)")
test_object("rownames(smoke)")
test_object("smoke")
success_msg("Good work!")

```
