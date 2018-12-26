# Lab5
## Task1
```r
pmean <- function(pollutant, id = 1:332, directory = "C:/Users/Polzovatel/Desktop/RPython/specdata") {
  data = sapply(id, function(i) read.csv(paste(directory, "/", formatC(i, width = 3, flag = "0"), ".csv", sep=""))[[pollutant]])
  return (mean(data, na.rm = TRUE))
}

pmean("sulfate", 1:10)
[1] 4.064128

pmean("nitrate", 70)
[1] 0.2551667
```

## Task2
```r
complete <- function(id = 1:332, directory = "C:/Users/Polzovatel/Desktop/RPython/specdata"){
  for (i in id) { 
    data2 <- read.csv(paste(directory, "/", formatC(i, width = 3, flag = "0"),  ".csv", sep = ""))
     numrow <- sum(complete.cases(data2))
  }
  return(data.frame(id, numrow))
}
complete (c(2, 4, 8, 10, 12))
  id numrow
1  2   1041
2  4    474
3  8    192
4 10    148
5 12     96

complete (c(11:15))
 id numrow
1  11    443
1  12     96
2  13     46
3  14     96
4  15     83
```

## Task3
```r
corr <- function(threshold = 0, directory="C:/Users/Mary/Documents/specdata") {
    corv <- NULL
    for (i in 1:332) {
    data3 <- read.csv(paste(directory, "/", formatC(i, width = 3, flag = "0"),".csv", sep = ""))
       res <- data3[complete.cases(data3), ]
        if (nrow(res) > threshold)
        corv <- c(corv, cor(res[,"sulfate"], res[, "nitrate"]))
    }
    if(length(corv) > 0)
    return (corv)
    return (as.numeric(c()))
}
head(corr())
[1] -0.22255256 -0.01895754 -0.14051254 -0.04389737 -0.06815956 -0.12350667

head(corr(200))
[1] -0.01895754 -0.14051254 -0.04389737 -0.06815956 -0.12350667 -0.07588814

summary(corr())
    Min.  1st Qu.   Median     Mean  3rd Qu.     Max. 
-1.00000 -0.05282  0.10718  0.13684  0.27831  1.00000 
```
