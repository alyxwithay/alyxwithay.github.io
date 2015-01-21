---
layout: post
title:  "Results Section: Tables and Figures"
date:   2014-11-21 10:54:00
comments: true
---

List of things working on for current paper tables and figures.

## Github respository + R markdown file + Paper draft
Github repository for this paper is found [here](https://github.com/SchlossLab/abxD01). In particular, the R markdown file named "abxD01_analysis.Rmd" (or the pdf version) contains info on all figures and how they were generated.

## Figures

# Figure 1: Barchart, Differences in community structures following array of antibiotic treatments

[figure PDF here](https://github.com/SchlossLab/abxD01/tree/master/Figure%201)

- change the "0" to be min of 0.001 instead of 0.0001 relabund
    - **completed 11/20/14, just make sure future files are changed for other graphs using the "abxD01.barcharts.xOTU.test.r"**
- add the 1/2 dashed lines
    - **completed 11/20/14**
- log trans anova to compare the CFUs across abx treatments to see if there are signif. differences
- individual anova to double check which abx treatments differ


# Figure 2: Stripchart, Correlation analysis of bacterial species present on Day 0 with *C. difficile* levels on Day 1

[figure PDF here](https://github.com/SchlossLab/abxD01/tree/master/Figure%202)

- Do I want to change the broad taxonomic groupings? 
    - These groups need to be the same across Figure 2, 4, 5
    
# Figure 3: Barchart, Differences in community structures between abx-titration treated mice

[figure PDF here](https://github.com/SchlossLab/abxD01/tree/master/Figure%203)

- eliminate the untreated groups...
- use OTUs we picked out earlier in figure 1
- do the stats to compare the mid/low to the highest dose
- I want to change the graph so that the OTUs are their own graphs and the titrations are side by side
	- **11/20/14, completed most of the graphical parameters.**
- once code is working then put up the other titration data files
	- **1/17/15, added to github**
- change min relabund from 0.0001 to 0.001 for cef and strep
    - **11/20/14, changed the vanc titrations min**
    - **1/17/15, changed the cef and strep titrations min**
    
- *Possibly work on merging singles*
- *Possibly work on getting plots on top of grid lines*

# Figure 4: Heatmap, Correlation analysis results compared across abx experiments

[figure PDF here](https://github.com/SchlossLab/abxD01/tree/master/Figure%204)

- for all the significant values for each pair of original + abx rows that are both significant, quantify that significance for each column (abx treatment)... see personal notes for more
- same tax groups as figures 2 and 5
- Add "ns" to the graph where not significant
	- **12/8/14**
- Is this the order of drugs I want? -keep consistent
	- **12/8/14**
- change xlabel names
	- **12/8/14**
- change code to get the key back
	- **12/8/14**

# Figure 5: Barchart, Differences in the community with extra microbiome recovery time following abx treatment

[figure PDF here](https://github.com/SchlossLab/abxD01/tree/master/Figure%205)

- Do for ampicillin too
- Pick the same groups shown in Figure 2. AND as side heatmap figure 4
- calculate differences in thetayc between individual days w/recovery
- lactos decrease with recovery... are these the streptococcus?

# Figure 6: 

- Make figure! for modelling results
	- Possibly show as supplemental table the ranked table of models by BIC or adjR^2
- correlation calculations for the delay data	
- Consider rerunning model using higher level taxonomy!!!

- The criteria for picking the otus, these results can be listed in supplementary tables possibly. 
	- **12/1/14, made file with info for table, now make pretty**
- Consider rerunning the model building code using a bigger candidate list
	- **12/1/14 with the BIC included in new calcs**
- Calculate the BIC for each--change code for this
	- **12/1/14**
	- **12/2/14, found a faster easier way to determine variable selection using the "leaps" package in r for multiple linear regression analysis**
- using the best models from the leaps analysis predict the outcome for the newtitration data and the predicted r^2
	- make file with newtitration data that contains the OTUs in the candidate list and run, got 0.67 for the 5 parameter model
		- **12/4/14**
	- now try the best model from both methods of selection...**12/4/14, think im just going to go with the exhaustive method for paper**
	- then model with just the top 3 otus... seems the best trade off point between BIC and adjR2... **12/4/14, gives 0.67 too, but the anova between the 5parameter model and 3 parameter model is significantly different, meaning that the 5 parameter model does improve prediction overall**
-use random forest for delay data alone to see what features stand out
	- how do these OTUs differ from the model built based on the original data set? 
		- **12/17/14 OTU11 has most influence, followed by 1, 5, 23, 21, 3, 6, 39 before dropping off in %IncMSE.  I'm curious to see what inclusion of OTU11 (Ecoli) will have on the effect of the model.**



#Supplemental Figure 1

- make graph showing the inverse Simpson correlation plotted against *C. difficile* CFU

## Tables

Tables are saved within the paper word document uploaded to github (see link at top).

# Table 1: Description of antibiotics in first set of experiments. 

There are probably other targets to include for a few abx. 

- change the order of the abx
	- **11/21/14**
- make class/mechanism uniform throughout table
	- **11/21/14**
- add an administration route column
	- **11/21/14**

# Supplemental Table 1: Titration amounts for each antibiotic treatment.

- change the order of the abx
	- **11/21/14**
- add an administration route column
	- **11/21/14**
	
# Supplemental Table 2: Model OTU Selection Criteria

- make pretty


