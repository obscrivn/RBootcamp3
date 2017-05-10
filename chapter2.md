---
title       : T-Test
description : 

--- type:NormalExercise lang:r xp:100 skills:1 key:4c038f7bad
## t-test
Let's look again at the speeds in the dataframe cars. 
*** =instructions

- Run a two-sided t-test the 90% confidence level on the null hypothesis that the mean is 20
- Fill out blanks in the formula
- Run a t-test with null hypothesis that the mean speed of the cars with stopping distance
 under 40 feet is 12 (mean). Use the default confidence level of .95.


*** =hint


*** =pre_exercise_code
```{r}

```


*** =sample_code
```{r}
# change X by the correct values
t.test(cars$speed, mu=X, conf.level = .X) 

# add condition and mean, uncomment the line
#t.test(cars$speed[], mu = X)

```

*** =solution
```{r}
# change X by the correct values
t.test(cars$speed, mu=, conf.level = .90) 

# add condition and mean
t.test(cars$speed[cars$dist < 40], mu = 12)
```

*** =sct
```{r}

test_output_contains("t.test(cars$speed, mu=, conf.level = .90)")
test_output_contains("t.test(cars$speed[cars$dist < 40], mu = 12)")
success_msg("Good work!")

```

--- type:NormalExercise lang:r xp:100 skills:1 key:a6b607960f
## Correlation
Let's again look at the dataset
http://cl.indiana.edu/~obscrivn/docs/movie_metadata.csv

*** =instructions
- Import csv file
- Type in the console help function for ` cor `
- attach dataset
- Compute the correlation between a movie's budget and the number of Facebook likes
- Use ` cor() ` function
- Get all the movies with genre "Action"
- Attach new set

*** =hint


*** =pre_exercise_code
```{r}

```


*** =sample_code
```{r}
# import data from 
#url http://cl.indiana.edu/~obscrivn/docs/movie_metadata.csv
movie.data <- 

# attach


# correlation


# subset - fill the info inside the square brackets
action.movie.data <- movie.data[]

# attach

# another correlation
```

*** =solution
```{r}
movie.data <- read.csv("http://cl.indiana.edu/~obscrivn/docs/movie_metadata.csv")

attach(movie.data)
#Compute the correlation between a movie's budget and the number of Facebook likes.
 
cor(budget, movie_facebook_likes)
 
#Let's look at a subset. Get all the movies with genre "Action" and assign it to a variable action.movie.data
 
action.movie.data <- movie.data[genres=="Action",]
# attach
attach(action.movie.data)

# another cor
cor(budget, movie_facebook_likes)
#Compute the correlation between a movie's budget and the number of Facebook likes for just the action movies.
 ```
 
*** =sct
```{r}
test_object("movie.data")
test_object("action.movie.data")
test_output_contains("cor(budget, movie_facebook_likes)")
success_msg("Good work!")

```
