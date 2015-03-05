# Reproducible Research: Peer Assessment 1
Felix P. Muga II  


## Loading and preprocessing the data

The dataset were downloaded from the **COURSE WEBSITE** and named as `activity.csv` which is a comma-separated value file.

The dataset has 17,568 observations with 3 variables. These variables are:

* **steps** : Number of steps taken in a 5-minute interval.  *Missing values* are coded as `NA`.

* **date** :  The `date` on which the measurement was taken in `YYYY-MM-DD` format.  
There are 61 unique `dates` in the dataset which starts in `2012-10-01` and ends in `2012-11-30`.

* **interval** : `Identifier` for the 5-minute interval in which measurement was taken.  
Each `identifier` shall be expressed in `HHMM` format where `HH` is one of  $0,1,\ldots,23$ and `MM` is one of $0, 5,\ldots, 55$.   
The dataset has 288 unique 5-minute interval `identifiers` in a day.  
The interval identifier `0000` is the 1st 5-minute interval of the first hour,   
The interval identifier `0005` is the 2nd 5-minute interval of the first hour,  
$\vdots$   
The interval identifier `0075` is the 12th or the last 5-minute interval of the first hour,   
$\vdots$   
The interval identifier `2300` is the 1st 5-minute interval of the 24th hour,  
The interval identifier `2305` is the 2nd 5-minute interval of the 24th hour,  
$\vdots$   
The interval identifier `2375` is the 12th or the last 5-minute interval of the 24th hour.  

Thus, the total number of observations in the dataset is $288 \times 61 = 17,568$.



```r
#       Loading the CSV file as a data.format
rawdf <- read.csv("activity.csv")
#       Transforming the interval column in HHMM format
rawdf <- transform(rawdf, interval = sprintf("%0004d", interval))
#       The dataset is processed where observations with missing values are removed.
df <- rawdf[complete.cases(rawdf),]
```

We shall be using the following libraries: **dplyr**, **ggplot2**, **lattice** and **stringr** in this report.
        

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
library(ggplot2)
library(lattice)
library(stringr)
```

## What is mean total number of steps taken per day?



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?