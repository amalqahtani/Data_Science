
---
title: "Covid19 Data"
author: "team A"
date: "`r format(Sys.time(), '%d %B, %Y')`"
output:  
    rmdformats::readthedown:
      toc_float: true
      number_sections: true
      code_folding: hide
      keep_tex: yes
---



```{r setup, echo=FALSE, cache=FALSE}
  library(knitr)
library(rmdformats)
## Global options
options(max.print="75", scipen = 999, digits = 3, big.mark=",", warn = -1)
opts_chunk$set(echo=FALSE,
	             cache=TRUE,
               prompt=FALSE,
               tidy=TRUE,
               comment=NA,
               message=FALSE,
               warning=FALSE)
opts_knit$set(width=75)
```

```{r basicfunct, include=FALSE}
loadPkg = function(x) { if (!require(x,character.only=T, quietly =T)) { install.packages(x,dep=T,repos="http://cran.us.r-project.org"); if(!require(x,character.only=T)) stop("Package not found") } }
```

```{r libraries}
#library(ggplot2)
#require(gridExtra)
#library(kableExtra)
loadPkg("ggplot2")
loadPkg("gridExtra")
loadPkg("kableExtra")
```

![](covid19.jpg)

# Introduction

Team A are the following members: Amal Alqahtani, Peng Jiaxiang, Elahi	Naureen, and Mu Xinya. You may find our work over on [GitHub](https://github.com/amalqahtani/Data_Science).

Coronavirus disease-19 (COVID-19) has spread rapidly around the world, and many risk factors have been hypothesized to affect case and death rates. We felt that a relevant discussion to have would be `What are the most regions with the highest number of deaths`? What can we say about patient demographics? Does race considered a significant risk factor for increased Covid19 incidence in the United States?' Have there been any general trends amongst the health conditions? 
These questions are all suited to EDA, and with these questions in mind, we want to see if we could find data on Covid19 that would be readily available for us to analyze. Eventually, our question morphed into the following: **are there any specific factors (i.e. patient demographics, social determinants of health, environmental variables, underlying health conditions, country of origin) that could be used to describe the factors affecting COVID-19 Case and Death Rate in the U.S. in general?** 

We were able to find a dataset called `120 years of Olympic history: athletes and results` on Github over here: [https://github.com/johndurbin93/Covid-19-Dataset](https://github.com/johndurbin93/Covid-19-Dataset). This dataset includes COVID-19 confirmed case number and death number through April 14, 2020 which were obtained for each U.S. county from the Center for Systems Science and Engineering (CSSE) Coronavirus Resource Center at Johns Hopkins University. Race demographics for counties was obtained from the County Health Rankings and Roadmaps Program database. Daily temperature data for counties was obtained from the National Oceanic and Atmospheric Administration. This data was compiled by a group of reserchers. 

The report is organized as follows:

1. Summary of Dataset
2. Description of Data
3. What are the patient demographics? (demographics Data)
4. Where do ...... come from? or What are the most regions with the highest number of deaths? (country of origin Data)
5. What are the social determinants of health? (social determinants of health Data)
6. Environmental variables Data Goes Here?
7. Are there any common underlying health conditions? (health conditions Data)
8. Have there been any ....... trends among patient over the times? (Trends Over Time)
9. Are patient a certain race? (race Data)
10. Discussion And Conclusion
