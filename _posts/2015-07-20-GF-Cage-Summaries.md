---
layout: post
title:  "Germfree Cage Summaries"
date:   2015-07-20
comments: true
---

Summaries, showing the overview of each cage, have been generated using the "build_CageSummaries.R" and "build_microbiotaSummaries.R" files. These include mouse weight change, *C. difficile* CFU, and microbiota changes over time. 

### Objective

I wanted to get an overview of the communities by cage.  Cages differ by *C. difficile* strain (mostly 431) and human stool donor (only a few cages overlap).  There are several questions that can be assessed based on different subsets of the data. 

We are first looking to see how infection with one *C. difficile* strain, strain "431", against different human-derived microbiota mouse backgrounds varies. Does the initial microbiota influence the course of infection and outcome of disease? Our lab has shown this for colorectal cancer in germfree mice as well. Specifically, our lab has shown that cancer-associated microbiotas have increased size and numbers of tumors in a chemically-induced murine model of CRC compared with healthy-associated microbiotas. Given the microbiotas pivotal role in colonization resistance against *C. difficile*, I hypothesize that the microbiota can also affect outcome of infection. 


### Results

In many of the cages, Firmicutes tends to dominate. In those cages where overall Bacteroidetes dominate, these mice all received stool from a donor in the AA surrounding community. 

Comparing the 3 AMS donor cages (N=no carey-blair storage media, NC=no carey-blair storage media or *C. difficile* challenge, Y=yes carey-blair storage media): 

1. Both N and NC have similar starting communities at OTU level.
2. Compared to N/NC, Y has less of OTU17: Clostridium XIVa. 
3. Don't see an increase in the Y group of OTU 14: Flavonifractor
4. Comparing N to NC, delay in increase of OTU59: butyricimonas and increase in OTU14: Flavonifractor

Comparison of same donor into different cages. Are these starting communities the same? How do the microbiota dynamics differ in cages with same donor but different infecting strains?

1. Cages 369 (431 spores) and CON2 (458 spores)
2. Cages 430 (431 spores) and CON3 (299 spores)
3. Cages 578 (431 spores) and CON (395 spores)

Comparing infection dynamics in 3 equivalent cages: donor DA00581 and 431 spores. Are the infection dynamics reproducible? 

* Cages A, C, and D


### Discussion

There are a lot of questions and comparisons still to be answered from these graphs alone. There are some steps I want to take to clarify or pinpoint differences, validate observations, and answer remaining questions. However I still need to do the  random forest analysis. I should incorporate the toxin data before attempting the random forest analysis. 


### What's next

*  <s> I want to breakdown the Firmicutes phylum because many of those OTU graphs are busy. </s>
* <s> I also want to add the toxin graph to build_CageSummaries.R </s>
* include toxin data in random forest analysis. 
* <s> make sure not showing cecum </s>
* <s> change pch to vary </s>
* Should the weight, toxin, and cdiff graphs in summary be build form the end_metadata, which is the overlap between what survived in the sequencing pipeline, or should it just be from the all_metadata? If change, then also make sure that the all_metadata used are just stool samples
* change other scripts to look right away with the stool parameter for only positive days
* <s>Remove cdiff from RF analysis</s>
* Double check when CONA day 0 samples were taken--was it stool the time of community inoculation or a few hours after, or was it the inoculum? This will affect whether include in RF and other analyses.
	* I believe these samples were taken prior to inoculation. All the Day0's thetayc values from this cage are very similar to one another and very different from the subsequent days. Furthermore, in my emails to Sara Poe I told her to collect stool beforehand. 
	* Still--maybe do a barchart to see the global changes over time
* correlation analysis to find similar patterns across time between OTUs
* akkermansia seems to typically be indirectly related to firmicutes (eg. NP1)--which ones specifically? Some lachno
* generalized lotka-volterra equation
