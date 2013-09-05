
# Learning the apply family of functions

One of the greatest joys of vectorized operations is being able to use the entire family of `apply` functions that are available in base `R`.

These include:

```coffee
apply
by
lapply
tapply
sapply
```

## apply

m <- matrix(c(1:10, 11:20), nrow = 10, ncol = 2)

apply(m, 1, sum)
apply(m, 2, sum)
apply(m, 1, mean)
apply(m, 2, mean)

## by

```coffee
head(iris)
by(iris, [, 1:4], Species, mean)
```


## tapply
Two examples

```coffee
df <- data.frame(names = sample(c("A","B","C"), 10, rep = T), length = rnorm(10))
tapply(df$length, df$names, mean)

# Now with a more familiar dataset
tapply(iris$Petal.Length, iris$Species, mean)
```

## lapply (and llply)

What it does: Retruns a list of same length as the input. 
Each element of the output is a result of applying a function to the corresponding element.

```coffee
my_list <- list(a = 1:10, b = 2:20)
lapply(my_list, mean)
```



## sapply

sapply is a more user friendly version of lapply and will return a list of matrix where appropriate.


Let's work with the same list we just created.

```coffee
my_list
x <- sapply(my_list, mean)
class(x)


## replicate

An extremely useful function to generate datasets for simulation purposes. 

```coffee
replicate(10, rnorm(10))
replicate(10, rnorm(10), simplify = TRUE)
```

## mapply

