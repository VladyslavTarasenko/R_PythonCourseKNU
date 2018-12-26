# lab1
## task1

```{r}
chr <- "textual";
class(chr)

num <- 1.0
class(num)

int <- 1L;
class(int)

com <- as.complex(2+2i)
class(com)

lgc <- TRUE;
class(lgc)
```
## task2 
```{r}
v1 <- 5:75
v2 <- c(3.14, 2.71, 0, 13)
v3 <- as.logical(c(1:100))
```
## task3
```{r}
m <- rbind(c(0.5, 1.3, 3.5), c(3.9, 131, 2.8), c(0, 2.2, 4.6), c(2, 7, 5.1))
```
## task4
```{r}
vlist <- list(chr, num, int, com, lgc)
```
## task5
```{r}
f <- factor(c("baby", "child", "adult"))
```
## task6
```{r}
vNA <-list( 1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11)
counterNA <- function(x){
  c <- 0
  p <- -1
  index <- 0
  for(item in x){
    index <- index + 1
    if(is.na(item)){
      c <- c + 1
      if(p == -1)
        p <- index
    }
  }
  c(c,p)
}
counterNA(vNA)
```
## task7
```{r}
df <- data.frame(c_1 = 1:4, c_2 = c(T, T, F, F))
```
## task8
```{r}
names(df)[1] <- 'New names'
```
