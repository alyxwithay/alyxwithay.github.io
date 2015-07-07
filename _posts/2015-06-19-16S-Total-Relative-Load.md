---
layout: post
title:  "16S Total Relative Load"
date:   2015-07-06 3:15:00
comments: true
---

Progress updates on the qPCRs for assessing total 16S relative load for the antibiotic treatments I've administered.  _Original Post 6/19/15_

## Background
In our recently accepted mBio paper looking at antibiotic induced susceptibility to CDI, we tested the resistance of microbiotas treated with a total of 15 different treatments using 7 different antibiotics. We hypothesized that the structure (and subsequently function) of the microbiota was important in determining susceptibility to disease. We identified several bacterial populations implicated in either resistance or susceptibility to _C. difficile_ infections. In order to determine if loss of overall bacterial load may have contributed to any increased susceptibility in these microbiotas, I am measuring the relative changes in total 16S load by qPCR. 

## Methods
Using 4-5 mice from each treatment group, I'm looking for the differences in total 16S from their respective pre-treatment samples to the sample collected on the day of _C. difficile_ challenge. For each treatment group, I incorporated individual mice from each cage in an attempt to catch any cage to cage differences within treatment groups as well. I used SYBR green for my qPCR reactions and the eubacterium (universal 16S) primers. Each sample is being tested in triplicate, and if their standard deviation from each other is too high (maybe set to ~0.3+) then I'll redo that sample in a final plate. I tried to keep the same antibiotic and its respective treatments on the same plate for ease of comparison. However I also included a positive control (D4 Lachnospiraceae isolate from pure culture). This positive control has been diluted and qPCR'd previously (by me) to ensure correct ct's across dilutions. I included this positive control and its dilutions on each qPCR plate. In order to accurately compare across plates, I am setting the crossing threshold according to this positive control and its dilutions so that its results are consistent across plates. 

## Results
I've uploaded the results from 5 plates of qPCR in the data folder of my repository. Taking a glance at the data, there appear to be minimal effects on total load for a few antibiotic treatments, including low dose cefoperazone, ciprofloxacin, clindamycin, either metronidazole treatment, any streptomycin treatment, vancomycin. Higher doses of cefoperazone used seems to have decreased the level of 16S rRNA genes. The ampicillin results varied by cage more. This treatment also had variable effects on levels of _C. difficile_. 

Currently I've just looked at the difference in CT between individual mice before and after antibiotic treatment. I'm considering doing (pre-sample CT minus control CT) minus (post-sample CT minus control CT). This would account for differences across plates. 