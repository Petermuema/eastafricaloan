---
title: "eastafricaloandeficit"
output: html_document
date: "2025-01-20"
---

```{r}
data<-data.frame(name=c("Kenya","Uganda","Tanzania","Rwanda","DRC"),
           GPD=c(10000,500,700,1000,300),
           IMF=c(50000,5000,3000,50000,4500),
           Interest=c(0.3)
)
data
```
```{r}
library(tibble)
new_data<-as_tibble(data)
new_data
```



```{r cars}
library(tibble)
new_data<-as_tibble(data)
new_data
```



```{r}
library(dplyr)
library(magrittr)
east_africa<-new_data%>%
  mutate(Total_loan=IMF*Interest)%>%
  mutate(Deficit=GPD-Total_loan)%>%
  select(name,Total_loan,Deficit)%>%
  arrange(Deficit)
east_africa
```

```{r}
library(ggplot2)
graph<-ggplot(data=east_africa,mapping=aes(x=name,Deficit))+
  geom_point()
graph
```


```{r pressure, echo=FALSE}
plot(pressure)
```

Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.
