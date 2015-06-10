---
layout: post
title:  "DANG Meeting R"
date:   2015-05-26 12:15:00
comments: true
---


-phyloseq R package to load microbiome data into R from mothur output
	-import.mothur, wrapper for a bunch of other functions in R... what's the vegan package
	
-code sharing: github--public vs. private repositories
	-R.md file with the output visible (graphs, results, etc)... the code can be hidden or visible for the PI
	
-make.sra--to submit sequences to NCBI and make publicly available in the sequence read archive
	-have to fill out the mimarks table for it
	
-dplyr package updated from the plyr package--for wide/long format changes of the data, transforming the data in that way, reshape function
	-tidydata--made by the same people as plyr
	-stringr--supposed to be good for working with strings
	-sometimes excel/text wrangler manipulations are just easier to work with metadata to clean it up and organize it
		-but always save the raw data file
	-broom package
	-90% of the work sometimes is getting the data into one organized consistent form
	
-?files tells you what files are there... look at the files help page
-in Rmd can have a chunk of code that is python/r/terminal code

-ggplot2 vs base commands in R--visuals are cleaner perhaps, but difficult to learn how to use, although some people say the opposite
	-base commands--might be a lot more parameters to tweak but can totally control everything in the graph and save it for the next time you need to make that graph
	-measles infographic to compare the two--look it up, how people made the same graph in different ways
	
-R style guide recommendations, be consistent 
	-sometimes its nice to have examples of input files to show what that is supposed to look like, also nice to have an example of the output to refer to
	
-disadvantage to using rstudio is if need to use the cluster then should use the terminal 

