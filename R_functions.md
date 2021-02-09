# Useful functions in R


### Ch. 6

- count the number of missing values 
```{r}
sum(is.na(data$columnname))
```

- removes any row that has any missing values
```{r}
data = na.omit(data)
```

- subset selection
```{r}
library(leaps)
fit1 = regsubsets(target~., data = dataset, nvmax = 10)
summary(fit1)
names(summry(fit1))
```
