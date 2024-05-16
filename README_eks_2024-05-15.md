# **It Takes a Village**
### *An exploration of county-level predictors of high school dropout rates in California*
###### Eli Winton, Emily K. Sanders, and Radha Mohanty
###### DSB-318, Project 4, Group 4, May 17, 2024
---
###### *A [table of contents](#Table-of-Contents) for the repository is available at the bottom of this README.*

## Problem Statement
Not obtaining a high school diploma carries serious detrimental consequences for a child's whole life.  We will investigate how various social conditions predict high school dropout rates at the county level in California using regression algorithms and data retrieved from government sources.

## Target Audience
We have been hired by the *Coalition for Unprecedented Transformative Education for California Teachers and Students*, an umbrella organization for non-governmental organizations (NGOs) in California, to assess factors that may contribute to unequal opportunity for educational attainment across regions of the state. These NGOs will use our findings and recommendations to shape their own policy goals and political advocacy.

## Background and Purpose
There are many social determinants of educational success, beyond just any child’s merit or self-discipline, but that children who do not obtain high school diplomas often face social and economic hardships for the rest of their lives. Therefore, at the request of our commissioners, we will use publicly available data about a variety of social conditions across California counties to predict the dropout rate within a [4 year adjusted graduation cohort](https://www.cde.ca.gov/ds/ad/acgrinfo.asp).  This will allow our commissioners to become more informed about the disparities in educational outcomes across the state and better advocate for increasing students' opportunities for success by decreasing the dropout rate.  

If a suitable predictive model can be created, it will allow advocates to anticipate the county-level dropout rate if current trends continue, and plan their community efforts and political advocacy accordingly.  For example, if Modoc County were predicted to have a high dropout rate whereas Lassen County were predicted to have a low one, the *North-Eastern Alliance for Transforming the Californian  Technology Sector*, a group of innovators who seek to inspire underpriviliged young people to pursue careers in the technology industry, may choose to focus their efforts on Modoc County, where they are more needed.  Furthermore, if a model suitable for interpretation can be created, it will allow us and our commissioners to evaluate which social determinants may be the most influential on the rate of degree acquisition, and make decisions accordingly.  In this case, for example, the *Glenn Open Opportunity Society for Education*, a civic organization in Glenn County dedicated to mentoring high school students, may choose to prioritize students with certain characteristics to to matched with members for 1-on-1 mentoring.  In either case, political advocacy groups in the coalition, such as *Educators Dare to Dream of Immigration Equity*, can use our findings to advance their goals at the statehouse.

## Metric of Success
We will assess our models using R-squared, a measurement of how much variance in the dropout rate across counties can be explained by our model, and Root Mean Squared Error (RMSE), a measurement of how far off our model's estimates, based on the predictor variables, are from the actual dropout rate that was observed in the population.  Although we will present on the best model(s) we find, whatever they may be, we aspire to find model(s) with R-squared scores upward of 80%, and/or RMSEs equal to or less than 2 standard deviations of dropout rates - that is, that the value of true dropout rate minus the RMSE would not exceed 18.1326.

## Deliverables
- A written report of our procedure, findings, and recommendations for action and future work.  A full table of contents is available at the bottom of this README.
- Slides from the presentation of this report to the Spring 2024 Meeting of the *Coalition for Unprecedented Transformative Education for California Teachers and Students*.

## Apparatus
This analysis was primarily conducted in `python`, and partially in Excel.  The developers of `python` have graciously made it open source; Excel is a Microsoft product.  Each collaborator used their `python` development environment of choice; we expect that anyone reproducing our work would be able to do the same.  Within `python`, we used several relevant modules, most notably `pandas`, `sklearn`, `numpy`, `matplotlib.pyplot`, and `seaborn`.  At least one collaborator also used `os`, `datetime`, and `string`.  All of these `python` modules are open source.

## Method
We collected multiple publicly available datasets about county-level social conditions in California for use in our analysis.  We retrieved the majority of these datasets from [data.world](https://data.world/), where they had been [compiled](https://data.world/chhs) after originating with the [California Health and Human Services Agency](https://www.chhs.ca.gov/).  We also retrieved a few datasets from the [California Employment Development Department](https://edd.ca.gov/), the [California Department of Education](https://www.cde.ca.gov/), and [KidsData.org](https://www.kidsdata.org), where we found neatly packaged [US Census](https://data.census.gov/) data.  For each dataset, we downloaded the file to one of our local computers, then used `python` and/or Excel to reshape it for our needs, reduce dimensionality (rows and columns) wherever necessary, and perform any necessary data cleaning (i.e., attending to missing values).  In some cases, we engineered new features out of existing ones; for example, we combined two datasets about the GINI coefficient, each with several missing values, into one GINI feature with no missing values.  Whenever necessary, we imputed missing values; more details are provided on this in the notebooks.  At the end of this process, we had assembled a dataset with one row for each of 57 out of California's 58 counties.  (Because [Alpine County has very few residents](https://www.census.gov/quickfacts/fact/table/alpinecountycalifornia#), too much of its data were suppressed for it to be usable in the analysis.)  In the interest of creating reproducible code, we used a random seed of [31](https://www.history.com/this-day-in-history/california-becomes-the-31st-state-in-record-time) throughout.

## Modeling


## Conclusions and Recommendations


## Table of Contents
|Folder|Contents|Description|
|--------|-----------|---------------|
|(none)|readme|This is the current file.|
|(none)|ca_dropout_rate_presentation.pdf|The presentation slides that accompany this report.|
|/01_notebooks| |This folder contains a collection of Jupyter notebooks, in which reader can find examples of the `python` code we used to run our analyses, as well as brief written explanations.  These notebooks are named in the order we recommend reading them.|
|/02_data||This folder contains data files.  The overall data file that we based our analysis on is loose in the folder.  The subfolders contain the original datasets and data dictionaries as retrieved from the sources, as well as our cleaned versions of those datasets.
||ca_dropout_and_predictors.csv|This is the dataset we based our analyses on.  It was constructed from the multiple datasets retrieved from the sources.|
||/01_original_datasets|This folder contains the individual CSV files corresponding to different variables as retrieved from the sources.  Note that we have only included the files we used; most of them were originally part of a larger package of files available at the source.|
||/02_cleaned_datasets|This folder contains the individual CSV files corresponding to different variables as they appeared after we cleaned and streamlined them.  Note that we made a few further edits as needed between these versions and the final analysis dataset.  These edits should be readily visibly apparent.|
||/03_output|This folder contains any data files produced within the notebooks.|
||/04_original_data_dictionaries|This folder contains the original data dictionaries that came with the datasets, whenever available.  Note that not all datasets came with a data dictionary, and that not all of the variables in these data dictionaries remained in our final dataset.|
|/03_images| |This folder contains images, mostly graphs, that support the report.|





