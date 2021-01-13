Rython - R Code
================
Andrew Patton

## 0\) Load iris as dataframe

``` r
data(iris)
```

## 1\) Split data into train/test sets

Via: [Kyle Ligon](https://twitter.com/redickio)

``` r
library(tidyverse)
library(tidymodels)

iris_split <- iris %>% 
  initial_split(prop = 0.75)

train_iris <- training(iris_split)
test_iris <- testing(iris_split)

print(nrow(train_iris))
```

    ## [1] 113

``` r
print(nrow(test_iris))
```

    ## [1] 37

## 2\) Split a dataframe into parts based on levels of a categorical variable

``` r
split_list <- split(iris, iris$Species)

setosa <- split_list[['setosa']]
versicolor <- split_list[['versicolor']]
virginica <- split_list[['virginica']]
```
