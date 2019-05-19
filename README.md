
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Introduction

  - Chicago’s bike share system Data from Divvy Website

Questions to answer:

What time of day do people ride bikes the most?

### Download the data

``` r
temp <- tempfile()
download.file("https://s3.amazonaws.com/divvy-data/tripdata/Divvy_Trips_2018_Q1.zip", temp)
data <- read.csv(unz(temp, "Divvy_Trips_2018_Q1.csv"))
unlink(temp)
```

R packages needed:

``` r
library(ggplot2)
library(dplyr)
```

``` r
head(data)
##   X01...Rental.Details.Rental.ID X01...Rental.Details.Local.Start.Time
## 1                       17536702                   2018-01-01 00:12:00
## 2                       17536703                   2018-01-01 00:41:35
## 3                       17536704                   2018-01-01 00:44:46
## 4                       17536705                   2018-01-01 00:53:10
## 5                       17536706                   2018-01-01 00:53:37
## 6                       17536707                   2018-01-01 00:56:15
##   X01...Rental.Details.Local.End.Time X01...Rental.Details.Bike.ID
## 1                 2018-01-01 00:17:23                         3304
## 2                 2018-01-01 00:47:52                         5367
## 3                 2018-01-01 01:33:10                         4599
## 4                 2018-01-01 01:05:37                         2302
## 5                 2018-01-01 00:56:40                         3696
## 6                 2018-01-01 01:00:41                         6298
##   X01...Rental.Details.Duration.In.Seconds.Uncapped
## 1                                             323.0
## 2                                             377.0
## 3                                           2,904.0
## 4                                             747.0
## 5                                             183.0
## 6                                             266.0
##   X03...Rental.Start.Station.ID X03...Rental.Start.Station.Name
## 1                            69          Damen Ave & Pierce Ave
## 2                           253     Winthrop Ave & Lawrence Ave
## 3                            98      LaSalle St & Washington St
## 4                           125            Rush St & Hubbard St
## 5                           129       Blue Island Ave & 18th St
## 6                           304         Broadway & Waveland Ave
##   X02...Rental.End.Station.ID  X02...Rental.End.Station.Name  User.Type
## 1                         159      Claremont Ave & Hirsch St Subscriber
## 2                         325 Clark St & Winnemac Ave (Temp) Subscriber
## 3                         509            Troy St & North Ave Subscriber
## 4                         364           Larrabee St & Oak St Subscriber
## 5                         205           Paulina St & 18th St Subscriber
## 6                         299         Halsted St & Roscoe St Subscriber
##   Member.Gender X05...Member.Details.Member.Birthday.Year
## 1          Male                                      1988
## 2          Male                                      1984
## 3          Male                                      1989
## 4          Male                                      1983
## 5          Male                                      1989
## 6        Female                                      1994
```

Each row is a single ride by a person.

<img src="README_figs/README-1st line graph-1.png" width="672" />

..
