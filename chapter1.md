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

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:cfb29eccfc
## A really bad movie

Have a look at the plot that showed up in the viewer to the right. Which type of movie has the worst rating assigned to it?

*** =instructions
- Adventure
- Action
- Animation
- Comedy

*** =hint
Have a look at the plot. Which color does the point with the lowest rating have?

*** =pre_exercise_code
```{r}
# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer

movies <- read.csv("http://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/movies.csv")

library(ggplot2)

ggplot(movies, aes(x = runtime, y = rating, col = genre)) + geom_point()
```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

msg_bad <- "That is not correct!"
msg_success <- "Exactly! There seems to be a very bad action movie in the dataset."
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:f43b1771ce
## More movies

In the previous exercise, you saw a dataset about movies. In this exercise, we'll have a look at yet another dataset about movies!

A dataset with a selection of movies, `movie_selection`, is available in the workspace.

*** =instructions
- Check out the structure of `movie_selection`.
- Select movies with a rating of 5 or higher. Assign the result to `good_movies`.
- Use `plot()` to  plot `good_movies$Run` on the x-axis, `good_movies$Rating` on the y-axis and set `col` to `good_movies$Genre`.

*** =hint
- Use `str()` for the first instruction.
- For the second instruction, you should use `...[movie_selection$Rating >= 5, ]`.
- For the plot, use `plot(x = ..., y = ..., col = ...)`.

*** =pre_exercise_code
```{r}
# You can also prepare your dataset in a specific way in the pre exercise code
load(url("https://s3.amazonaws.com/assets.datacamp.com/course/teach/movies.RData"))
movie_selection <- Movies[Movies$Genre %in% c("action", "animated", "comedy"), c("Genre", "Rating", "Run")]

# Clean up the environment
rm(Movies)
```

*** =sample_code
```{r}
# movie_selection is available in your workspace

# Check out the structure of movie_selection


# Select movies that have a rating of 5 or higher: good_movies


# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre

```

*** =solution
```{r}
# movie_selection is available in your workspace

# Check out the structure of movie_selection
str(movie_selection)

# Select movies that have a rating of 5 or higher: good_movies
good_movies <- movie_selection[movie_selection$Rating >= 5, ]

# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre
plot(good_movies$Run, good_movies$Rating, col = good_movies$Genre)
```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_function("str", args = "object",
              not_called_msg = "You didn't call `str()`!",
              incorrect_msg = "You didn't call `str(object = ...)` with the correct argument, `object`.")

test_object("good_movies")

test_function("plot", args = "x")
test_function("plot", args = "y")
test_function("plot", args = "col")

test_error()

success_msg("Good work!")
```
