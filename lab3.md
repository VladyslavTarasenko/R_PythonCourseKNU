# Lab3
## Task1
```r
addT <- function(x, y){
  x+y
}
addT(3,4)  
[1] 7
```

## Task2
```r
above <- function(x, n=10){
  x[x>n]
}
above(c(9:13))
[1] 11 12 13

above(c(9:13), 11)
[1] 12 13
```

## Task3
```r
my_ifelse <- function(x, exp, n){
  if (exp == "<") {
    x[x<n]
  } else if(exp == "<="){
    x[x<=n]
  } else if (exp == ">"){
    x[x>n]
  } else if (exp == ">="){
    x[x>=n]
  } else if (exp == "=="){
    x[x==n]
  } else {
    x
  }
}
x <- c(3,4,5,9,10,20,40,15)
my_ifelse(x, ">=", 10)
[1] 10 20 40 15

my_ifelse(x, "==", 5)
[1] 5

my_ifelse(x, "<", 20)
[1]  3  4  5  9 10 15

my_ifelse(x, "<=", 2)
[1] 3 4 5

my_ifelse(x, "+", 0)
[1]  3  4  5  9 10 20 40 15
```

## Task4
```r
columnmean <- function(x, removeNA=TRUE){ 
  colMeans(x, na.rm=removeNA)
  }
x <- matrix(c(1, 2, 3, NA, 5, 6, NA, NA, 9, 10), nrow=2, ncol=5)
columnmean(x)
[1] 1.5 3.0 5.5 NaN 9.5

columnmean (x, FALSE)
[1] 1.5  NA 5.5  NA 9.5
```
