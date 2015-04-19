# Reproducible Research: Peer Assessment 1
by slashmatti


## Loading and preprocessing the data
Download the dataset [from this link](https://d396qusza40orc.cloudfront.net/repdata%2Fdata%2Factivity.zip) and unzip it into the working directory of R. The dataset is simply read into R with `read.csv("activity.csv")`. No further preprocessing is necessary at this point.


## What is mean total number of steps taken per day?
Using the dplyr package, the number of steps taken each day over dataset's period of 61 days is found and then plotted in a histogram with the following code.

```r
library(dplyr)
```

```
## 
## Attaching package: 'dplyr'
## 
## The following object is masked from 'package:stats':
## 
##     filter
## 
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

```r
data <- read.csv("activity.csv")
daily <- data %>% group_by(date) %>% summarize(steps =sum(steps))
hist(daily$steps)
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-1-1.png) 

The mean is 1.0766189 &times; 10<sup>4</sup> and the median is 10765 of the total number of steps taken per day.


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
