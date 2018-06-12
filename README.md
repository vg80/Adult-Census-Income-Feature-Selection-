# Adult-Census-Income-Feature-Selection
Deleting the columns capital gain, capital loss and hours per week
```{r}
Adult= adult
Adult$capitalgain = NULL
Adult$capitalloss = NULL
Adult$fnlwgt = NULL
Adult$hoursperweek = NULL

```
Convering the variables to dummy variables
```{r}
library(dummy)
Adult_dummy = dummy(Adult, int = TRUE)

Adult_dummy = cbind(Adult_dummy, Adult$age)
Adult_dummy_del = Adult_dummy[which(complete.cases(Adult_dummy)==TRUE),]
```
