## PRACTICAL 1

##  Reading in data

```{r}
#| echo: true

library(datasets)
data(airquality)
data(cars)
```


## 1: Finding missing rows

```{r}
#| echo: true

missing_rows <- subset(airquality, !complete.cases(airquality))
print(missing_rows)
```

## 2: Basic statistics for temp and ozone

```{r}
#| echo: true

summary(airquality$Temp)
sd(airquality$Temp)

summary(airquality$Ozone)
sd(airquality$Ozone)
```

## 3: Finding beta estimates for linear regression

```{r}
#| echo: true

X <- cbind(1, cars$speed)
Y <- cars$dist

beta <- solve(t(X) %*% X) %*% t(X) %*% Y
print(beta)

```

## 4: Compare results with lm()

```{r}
#| echo: true

model <- lm(dist ~ speed, data = cars)
print(coef(model))
```

## PRACTICAL 2

## 1: Generate simulated Data

```{r}
#| echo: true

set.seed(1)
x <- seq(1, 100, by = 1)
noise <- rnorm(length(x), mean = 0, sd = 0.2)
y <- sin(x/10) + noise
```

## 2: Lowess Algorithm

```{r}
#| echo: true

```


## PRACTICAL 3

## Setup

```{r}
#| echo: true

if (!requireNamespace("tidyverse", quietly = TRUE)) {
  install.packages("tidyverse")
}
library(tidyverse)

if (!requireNamespace("nycflights13", quietly = TRUE)) {
  install.packages("nycflights13")
}
library(nycflights13)
```

## 1: Displaying dataset

```{r}
#| echo: true

view(flights)
```
