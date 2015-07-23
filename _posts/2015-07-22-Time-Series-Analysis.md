---
layout: post
title:  "Time Series Analysis"
date:   2015-07-22
comments: true
---

In this post I outline some methods for analyzing time-series multivariate data or "compositional time-series data". This will be important for both the germfree study and the *C. difficile* dynamics paper. 

## References
[Compositional Time Series Analysis, 2007](http://ima.udg.edu/~barcelo/index_archivos/ISI2007_Aguilar.pdf)

* "Historically, the main approach to analyzing CTS data has been based on the application of an initial transform to break the unit sum constraint, followed by the use of standard time series techniques. Finally, the inverse transformation is used on the derived results so as to obtain results pertinent to the original sample space."

[Time Series Analysis of Computational Data Using a Dynamic Linear Model Approach, 2002](http://www.amstat.org/sections/srms/proceedings/y2002/files/jsm2002-000806.pdf)

* "In this article, we analyze compositional time series data after a BoxCox transformation. Inference is carried out in the Bayesian framework using a very rich class of scale mixture of multivariate normals (SMMVN) for modeling the errors."

[Time Series Models for Compositional Data](http://polmeth.wustl.edu/media/Paper/brand99b.pdf)

* Outlines their development of a time series model for compositional data (political science related) 
* Discusses modeling based on a Dirichlet distribution, but cautions that this distribution is limited in its correlation structure and can't allow wide array of patterns
* They choose to map the components to log-ratios, then model the log-ratios using multivariate normal or multivariate additive-logistic Student-t distributions

[Compositional VARIMA time series](http://onlinelibrary.wiley.com/store/10.1002/9781119976462.ch7/asset/ch7.pdf?v=1&t=icf4irac&s=76e2d3498fd65a79d1d8ae0212fefa17152ab5dd)
* Compositional time series: An application

Aitchison J 1986 The Statistical Analysis of Compositional Data. Monographs on Statistics and Applied Probability. Chapman and Hall Ltd (reprinted 2003 with additional material by The Blackburn Press), London (UK). 416 p.

* Aitchison basically was the "father" of compositional time series data analysis

## Transformations

* Additive log-ratio transformation
* Box-Cox transformation
* Centered (or symmetric) log-ratio transformation 
* Isometric log-ratio transformation (see Bergman, 2008, Compositional time series: An application)
* OR Direct modeling in the simplex, which assumes Dirichlet distribution and allows for dependence between components

## Models following transformation:
 
* Regression with vector autoregressive moving average (VARMA) errors
* Kalman filtering? 

# Generalized Lotka-Volterra Model

This was used in the [Stein et al. paper](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003388). You apparently need a lot of time points, and we only have 11 days. 

# Boolean Dynamic Model

This was used in the [Steinway et al. paper](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1004338). They used metagenomic data for this model and combined it with genome-scale metabolic network reconstructions. 

These models require less parameterization compared with ordinary differential equation models. 

## Model performance assessment

* conditional predictive ordinate (CPO)

## R features and packages

The ["compositions"](https://cran.r-project.org/web/packages/compositions/compositions.pdf) package in r seems to be the most obvious package for this type of analysis. It includes various methods of transforming the data. It references "amounts", meaning typically positive values that sum up to 100% or 1, which in our data refers to OTUs. This sum constraint affects covariance structure. 

This package includes 4 approaches based on 2 questions: "whether the total sum of the amounts is a relevant information, and which is the meaningful measure of difference of the data." In our case, the sum is irrelevant, leaving 2 options: 

1. acomp (Aitchison  
