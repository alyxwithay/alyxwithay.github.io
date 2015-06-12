---
layout: post
title:  "Overview of the Humanized GF C. difficile Project"
date:   2015-06-10 12:15:00
comments: true
---
 
Main question: How does the microbiota affect not only colonization of _C. difficile_ but also the course of infection?

Original post: 1/24/15

##Background
The human gut microbiota is known to play a significant role in colonization resistance against the pathogen _C. difficile_. Previous studies have characterized the gut microbiotas of individuals with and without _C. difficile_ infection (CDI) and found marked differences in their community structures, i.e. what bacteria are present and at what abundance [myself and others]. Several studies have also investigated the relative importance of members of the microbiota in their potential contribution to colonization resistance against _C. difficile_ [myself and others]. Across both human and mouse hosts, there are many similarities in potentially protective and harmful bacteria, but there also appears to be host specific bacteria involved. Furthermore, it's not well understood if and how the microbiota affects the course of infection following colonization by _C. difficile_.

##Purpose & Hypothesis
The purpose of this investigation was to assess colonization and infection resistance of human-derived microbiotas in gnotobiotic (originally germ-free) mice against _C. difficile_. Groups of Germ-free animals were inoculated with the fecal microbiotas of 22 human subjects. These subjects included both hospital patients with diarrhea and "healthy" non-hospitalized individuals from the greater surrounding community. Mice harboring human-derived microbiotas were challenged with a clinical isolate of _C. difficile_ and monitored over ten days for signs of CDI and to observe the dynamics of their fecal microbiotas. The same isolate of _C. difficile_ inoculated across the human-derived gnotobiotic mouse groups caused a range of colonization levels and infection severity. We hypothesize that specific patterns in the microbiota structure explain the diverse infection outcomes observed. Furthermore we hypothesize that these patterns in the microbiota will corroborate previous work in our lab looking at microbial candidates for colonization resistance or increased susceptibility in mouse models of CDI. 

##To Do/Questions
1) Phylum level composition at Day 0 and perhaps some other plot to justify why these samples were selected
	* Compare inoculum to Day 0 composition
	* Possibly look at 454 data on those communities at phylum level
2) Phylum level changes over time by line plots for the 3 phenotypes, showing individual mice as dashed lines and the mean as a solid line, likely individual graphs for each phylum
	* also plot the OTU-based distances back to Day 0
3) At OTU level what differences are observed between the 3 phenotypes
4) Can data from day x in a model predict cdiff on day x+1, so a continuous outcome
	* do Day 0 -> Day 1
5) Can data from day 0 in a model predict 1 of the 3 possible phenotypes: little/no colonization, persistent colonization, colonization + death, so a categorical outcome; using random forest’s feature selection to pick important OTUs in each outcome
6) How good is the random forest model from the mouse modeling work on this data?
	* Can make a RF model using phylotypes at tx2 from the mouse modeling and use it for the same classified phylotypes in the GF data set OR alternatively run the data together and test
7) Try Picrust

##Other Interesting Questions
1) How similar/diff are the same communities in diff mice?
1) CFU/weight comparison of same communities w/different cdiff strains
	* How similar/diff are the communities in diff mice at D0?
2) Within the AMS samples:
	* Comparison of with and without cdiff - CDI dies 2dpi, how similar were their communities on Day 0?
	* Comparison of PBS vs Carey Blair storage media
