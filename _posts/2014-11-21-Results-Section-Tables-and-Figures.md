---
layout: post
title:  "Results Section: Tables and Figures"
date:   2014-11-21 10:54:00
comments: true
---

List of things working on for current paper tables and figures.

# Github respository + R markdown file
Github repository for this paper is found [here](https://github.com/SchlossLab/abxD01). In particular, the R markdown file named "abxD01_analysis.Rmd" (or the pdf version) contains info on all figures and how they were generated.

# Figures

## Figure 1: Barchart, Differences in community structures following array of antibiotic treatments

<img src="../img/topdose2_tx1_sorted_10x20.pdf" style="width: 400px;"/>


- change the "0" to be min of 0.001 instead of 0.0001 relabund
    - **completed 11/20/14, just make sure future files are changed for other graphs using the "abxD01.barcharts.xOTU.test.r"**
- add the 1/2 dashed lines
    - **completed 11/20/14**
- also wanted to try to make this table in the other direction: Phyla/OTUs as each graph with different shadings or colors for each treatment... see Figure 3
- log trans anova to compare the CFUs across abx treatments to see if there are signif. differences


## Figure 2: Stripchart, Correlation analysis of bacterial species present on Day 0 with *C. difficile* levels on Day 1

<img src="../img/corr_allSig_topdose2_10x8.pdf" style="width: 400px;"/>


- Do I want to change the broad taxonomic groupings? 
    - These groups need to be the same across Figure 2, 4, 5
    
## Figure 3: Barchart, Differences in community structures between abx-titration treated mice

<img src="../img/vanctitr_tx2_barchart_byphyl_8x10_v2.pdf" style="width: 400px;"/>


- I want to change the graph so that the OTUs are their own graphs and the titrations are side by side
    -**11/20/14, completed most of the graphical parameters.**
- once code is working then put up the other titration data files
- change min relabund from 0.0001 to 0.001 for cef and strep
    - **11/20/14, changed the vanc titrations min**
- eliminate the untreated groups...
- use OTUs we picked out earlier in figure 1
- one vs 3 figures for abx?
- do the stats to compare the mid/low to the highest dose
    
- *Possibly work on merging singles*
- *Possibly work on getting plots on top of grid lines*

## Figure 4: Heatmap, Correlation analysis results compared across abx experiments

<img src="../img/corr_heatmap_0.01rel_topdose2_newtitr.pdf" style="width: 400px;"/>


- Add "ns" to the graph where not significant
- Is this the order of drugs I want? -keep consistent
- for all the significant values for each pair of original + abx rows that are both significant, quantify that significance for each column (abx treatment)... see personal notes for more
- change xlabel names
- change code to get the key back
- same tax groups as figures 2 and 5

## Figure 5: Barchart, Differences in the community with extra microbiome recovery time following abx treatment

<img src="../img/metro_d0s_tx2.pdf" style="width: 400px;"/>


- Do for ampicillin too
- Pick the same groups shown in Figure 2. AND as side heatmap figure 4

## Figure 6: 

- Make figure! for modelling results. Or a table??
- The criteria for picking the otus, these results can be listed in supplementary tables possibly. 
- Consider rerunning the model building code using a bigger candidate list, and/or using higher level taxonomy!!!
- Calculate the BIC for each--change code for this

# Tables

# Table 1: Description of antibiotics in first set of experiments. 

- change the order of the abx
- make class/mechanism uniform throughout table
- add an administration route column

