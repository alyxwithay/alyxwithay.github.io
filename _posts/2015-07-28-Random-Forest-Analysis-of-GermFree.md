---
layout: post
title:  "Random Forest Analysis of Germfree Experiments"
date:   2015-07-28
comments: true
---

I'm using random forest models to make predictions on the "humanized" germfree mouse experiments. 


### Problem definition

Want to predict: 

* Day 1 cdifficile levels based on day 0 community
* Level of toxin based on community
* Community to predict death or not--try using just last day of each or include each day with its outcome of death or not
	* Categorical random forest to predict low colonization, high/sustained 
       colonization, or death

### Plan

Maybe a function to generally take the previous day and subsequent day's cdiff predictions

* Inputs: 
	* day of interest
	* Predicted variable (cdiff, toxin levels, death)

### Results

I ran a full random forest model over all 10 days predicting level of cdiff colonization.  I need to rerun to eliminate the Cdiff OTU(s). This model explained 66% of the variation. 
![Full Random Forest](https://github.com/SchlossLab/Schubert_humanCdGF_2015/blob/master/results/figures/rf_full_wCD.png?raw=true)

Without cdiff OTU 8, OTUs greater than 1%, over all 10 days, with 64.8% of the variation explained:
![Full Random Forest](https://github.com/SchlossLab/Schubert_humanCdGF_2015/blob/master/results/figures/rf_full.png?raw=true)

### Links to GitHub issues/commit messages

* [Random forest R script on github](https://github.com/SchlossLab/Schubert_humanCdGF_2015/blob/master/code/build_randomForest.R)
* [Results file](https://github.com/SchlossLab/Schubert_humanCdGF_2015/blob/master/data/process/random_forest.data)

### What's next

* <s>Remove cdiff OTU 8</s>
* incorporate other variables into the model, such as toxin activity for cdiff levels
* only look at cdiff 431!!
* Make function to pick days included