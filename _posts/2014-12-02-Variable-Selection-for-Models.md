---
layout: post
title:  "Variable Selection for Models"
date:   2014-12-02 10:45:00
comments: true
---
Web resources for variable selection in linear models.


# Resources

general steps for variable selection including stepwise AIC

[resources](http://www.statmethods.net/stats/regression.html)

info on Leaps package, which should be used for linear models

some [notes](http://web.as.uky.edu/statistics/users/pbreheny/760/S11/notes/2-22.pdf) for r
also [here](http://www2.hawaii.edu/~taylor/z632/Rbestsubsets.pdf)
and [here](http://www.stat.columbia.edu/~martin/W2024/R10.pdf)
also [here](http://rstudio-pubs-static.s3.amazonaws.com/2897_9220b21cfc0c43a396ff9abf122bb351.html), which has some other methods for picking the "best" model


# Updates:

## 12/05/14
So I've picked a model based on the original data set. It works pretty well for the titration data set for prediction. I used it with the delay data though and I got some bogus numbers for the adjusted and non-adjusted R^2 values (e.g. -9.23098), which range from -1 to 1 supposedly! lol...

