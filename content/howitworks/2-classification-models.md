+++
title = "Classification Models"
date = "2018-07-29"
tags = ["theme"]
categories = ["starting"]
author = "iCareer Climber Team"
+++

</br>

## [1] Document Similarity

We provide career recommendations in a ranked order based on the similarity of a job seeker's current/past job experiences. Our model is powered by resume information all across the US.

This product is a proof of concept and contains a small subset of possible jobs. Our model contains 114 unique job titles. The list of job titles is derived from the availability of salary information. We selected all jobs that contained at least 100 salary records in the past 5 years and 500 resume job summaries in the past 10 years. We had used 230k job summaries to train and test our model. 

</br>

__Current Best Performing Model__

```
PARAMETERS

# Labels: 114

Train-Test Split: 95 / 5

TD-IDF Vectorizer

   1. min_df: 5

   2. ngram_range: [1,3]

Undersampling

   More common jobs were undersampled to 2500 records based on job recency.

Oversampling

   Less common jobs were oversampled to 2500 records using the regular Synthetic Minority Over-sampling Technique (SMOTE).

Multinomial Naive Bayes Classifier 

   1. alpha: 0.02

```


| Metric | Result |
|---|---|
| Accuracy | 48.86% |
| F1 Score | 46.14% |
| Precision Score | 47.60% |
| Recall Score | 47.55% |

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/03_process_salary_and_create_ngram_model.ipynb)

</br>

## [2] Job Skills

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/03_process_salary_and_create_ngram_model.ipynb)

</br>

## [3] Next Steps


