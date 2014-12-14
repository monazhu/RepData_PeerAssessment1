Assignment 1
===========================

### Loading and preprocessing the data
Load the data. I am reading the file through my local drive.

```r
DF<-read.table(file="C:/Users/Evil Plushie/Dropbox/Coursera/Module 5 Reproducible Research/activity.csv", sep=",", header=T)
```

```
## Warning in file(file, "rt"): cannot open file 'C:/Users/Evil
## Plushie/Dropbox/Coursera/Module 5 Reproducible Research/activity.csv': No
## such file or directory
```

```
## Error in file(file, "rt"): cannot open the connection
```

### What is mean total number of steps taken per day?
Create a histogram of the total number of steps taken each day

```r
library(reshape2)
library(plyr)

mdf.sub<-melt(DF, id=c(2,3)) 
dcast.sub<-dcast(mdf.sub, date~variable, sum)
```

```
## Error in .fun(.value[0], ...): invalid 'type' (character) of argument
```

```r
hist(dcast.sub$steps, xlab="Total Number of Steps per Day", main=NULL)
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2-1.png) 

Calculate and report the mean and median total number of steps taken per day

```r
mean(dcast.sub$steps, na.rm=T)
```

```
## [1] 10766.19
```

```r
median(dcast.sub$steps, na.rm=T)
```

```
## [1] 10765
```

### What is the average daily activity pattern?
A time series plot of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all days (y-axis)

```r
dcast.int<-dcast(mdf.sub, interval~variable, mean, na.rm=T)
```

```
## Warning in mean.default(.value[0], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```
## Warning in mean.default(.value[i], ...): argument is not numeric or
## logical: returning NA
```

```r
plot(dcast.int$steps~dcast.int$interval, type="l")
```

```
## Warning in min(x): no non-missing arguments to min; returning Inf
```

```
## Warning in max(x): no non-missing arguments to max; returning -Inf
```

```
## Error in plot.window(...): need finite 'ylim' values
```

![plot of chunk unnamed-chunk-4](figure/unnamed-chunk-4-1.png) 

The 5-minute interval containing the maximum number of steps

```r
dcast.int$interval[which.max(dcast.int[,2])]
```

```
## integer(0)
```

### Imputing missing values
Total number of missing values in the dataset

```r
sum(is.na(DF$steps))
```

```
## [1] 2304
```

Create a new dataset that is equal to the original dataset but with the missing data filled in

```r
DF.new=DF
# imputed means were based on the average of the number of steps taken per interval
for(i in which(sapply(DF.new, is.numeric))){
  DF.new[is.na(DF.new[, i]), i] <- mean(DF.new[, i],  na.rm = TRUE)
}
```

New Histogram

```r
mdf.sub2<-melt(DF.new, id=c(2,3)) 
dcast.sub2<-dcast(mdf.sub2, date~variable, sum)
```

```
## Error in .fun(.value[0], ...): invalid 'type' (character) of argument
```

```r
hist(dcast.sub2$steps, xlab="Total Number of Steps per Day", main=NULL)
```

![plot of chunk unnamed-chunk-8](figure/unnamed-chunk-8-1.png) 
As a result of this imputation, the overall frequencies were raised


### Are there differences in activity patterns between weekdays and weekends
Create a new factor variable in the dataset with two levels - "weekday" and "weekend" 

```r
DF$weekday<-weekdays(as.Date(DF$date))
DF$day.type<-ifelse(DF$weekday=="Sunday"|DF$weekday=="Saturday", "Weekend", "Weekday")
```

Plotting steps vs. interval for weekend and weekday separately

```r
melt.int<-melt(DF, id=(2:5), na.rm=T)
dcast.int2<-dcast(melt.int, interval~day.type+variable, mean)
par(mfrow=c(2,1), mar=c(2.2,2.2,1,1))

plot(dcast.int2$Weekend_steps~dcast.int2$interval, type="l", main="Weekend") #top plot
plot(dcast.int2$Weekday_steps~dcast.int2$interval, type="l", main="Weekday") #bottom plot
```

![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-10-1.png) 


knit("PA1_template.Rmd")


