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

I ran a full random forest model over all 10 days predicting level of cdiff colonization. This model was built on OTUs not including cdiff OTU 8, OTUs were greater than 1% for at least 1 day by cage. This ultimately was based on 141 OTUs. The model explained 62.4% of the variation:
![Full Random Forest](https://github.com/SchlossLab/Schubert_humanCdGF_2015/blob/master/results/figures/rf_full.png?raw=true)

OTU 110 Coriobacteriaceae is by far the most important OTU. Interestingly this OTU is only present at above 1% in the "NP1" group over time and a couple "NP2" days. This "NP1" group is one of the few groups with little to no cdiff colonization, which only happens late in the time course. 

**Blast results of top 5: **

OTU_Name | Blast Name | Max Score | Total Score | Query Coverage | E value | Identity | Accession
--- | --- | --- | --- | --- | --- | --- | ---
OTU110_Coriobacteriaceae | Eggerthella lenta strain DSM 2243 | 383 | 383 | 100% | 2e-106 | 94% | NR_074377.1
OTU42_Lachnospiraceae | Blautia obeum strain ATCC 29174 | 429 | 429 | 100% | 3e-120 | 97% | NR_118692.1
OTU44_Clostridium | Clostridium subterminale strain JCM 1417, Clostridium thiosulfatireducens strain DSM 13105, Clostridium subterminale strain DSM 6970, Clostridium sulfidigenes strain SGB2, Clostridium thiosulfatireducens strain LUP 21, Clostridium subterminale strain DSM 6970 | 468 | 468 | 100% | 6e-132 | 100% | NR_113027.1, NR_112656.1, NR_112653.1, NR_044161.1, NR_042718.1, NR_041795.1
OTU17_Clostridium_XlVa | [Clostridium] clostridioforme strain ATCC 25537, [Clostridium] bolteae strain JCM 12243, [Clostridium] bolteae strain 16351 | 468 | 468 | 100% | 6e-132 | 100% | NR_118128.1, NR_113410.1, NR_025567.1
OTU5_Akkermansia | Akkermansia muciniphila strain ATCC BAA-835, Akkermansia muciniphila strain Muc | 468 | 468 | 100% | 6e-132 | 100% | NR_074436.1, NR_042817.1

<br>

The partial plot including the top 12 OTUs only from the previous full model explained 59.2% of the variation. The relative importance among the top 12 also shifts a bit, placing greater importance on Enterococcus OTU2 levels:
![Full Random Forest](https://github.com/SchlossLab/Schubert_humanCdGF_2015/blob/master/results/figures/rf_partial.png?raw=true)


### Links to GitHub issues/commit messages

* [Random forest R script on github](https://github.com/SchlossLab/Schubert_humanCdGF_2015/blob/master/code/build_randomForest.R)
* [Results file](https://github.com/SchlossLab/Schubert_humanCdGF_2015/blob/master/data/process/random_forest.data)

### What's next

* <s>Remove cdiff OTU 8</s>
* incorporate other variables into the model, such as toxin activity for cdiff levels
* <s>only look at cdiff 431!!</s>
* Make function to pick days included
* <s>Blast the top 4 OTUs in full RF model</s>