+++
title = "The Models"
date = "2018-07-29"
tags = ["theme"]
categories = ["starting"]
author = "iCareer Climber Team"
+++

</br>

## [1] Document Similarity

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/03_process_salary_and_create_ngram_model.ipynb)

We provide career recommendations in a ranked order based on the similarity of a job seeker's current/past job experiences. Our model is powered by resume information all across the US.

This product is a proof of concept and contains a small subset of possible jobs. Our model contains 114 unique job titles. The list of job titles is derived from the availability of salary information. We selected all jobs that contained at least 100 salary records in the past 5 years and 500 resume job summaries in the past 10 years. We had used 230k job summaries to train and test our model. 

</br>

### Model Parameters

```
Number of Classes - 114

Train-Test Split - 222,978 / 11,736 (95% / 5%)

TD-IDF Vectorizer - min_df: 5, ngram_range: [1,3]

Undersampling - More common jobs were undersampled to 2500 records based on job recency.

Oversampling - Less common jobs were oversampled to 2500 records using the regular Synthetic Minority Over-sampling Technique (SMOTE).

Multinomial Naive Bayes Classifier - alpha: 0.02
```

</br>

### Model Performance

</br>

| &emsp;Metric&emsp; | &emsp;Result&emsp; |
|---|---|
| &emsp;Accuracy&emsp; | &emsp;48.86%&emsp; |
| &emsp;F1 Score&emsp; | &emsp;46.14%&emsp; |
| &emsp;Precision Score&emsp; | &emsp;47.60%&emsp; |
| &emsp;Recall Score&emsp; | &emsp;47.55%&emsp; |

</br>

__Lowest/Highest Precision__

| &emsp;  Class &emsp;  | &emsp;  Precision &emsp;  | &emsp;  Support &emsp;  |
|   ---   |   ---:   |   ---:   |
| &emsp;  consultant  &emsp;  | &emsp;  9.09% &emsp;  | &emsp;  131 &emsp;  |
| &emsp;  business consultant &emsp;  | &emsp;  11.76%  &emsp;  | &emsp;  48  &emsp;  |
| &emsp;  director  &emsp;  | &emsp;  16.67%  &emsp;  | &emsp;  119 &emsp;  |
| &emsp;  manager &emsp;  | &emsp;  21.21%  &emsp;  | &emsp;  127 &emsp;  |
| &emsp;  it specialist &emsp;  | &emsp;  22.22%  &emsp;  | &emsp;  64  &emsp;  |
| &emsp;  build and release engineer  &emsp;  | &emsp;  82.22%  &emsp;  | &emsp;  131 &emsp;  |
| &emsp;  database administrator  &emsp;  | &emsp;  83.47%  &emsp;  | &emsp;  123 &emsp;  |
| &emsp;  caregiver &emsp;  | &emsp;  86.67%  &emsp;  | &emsp;  66  &emsp;  |
| &emsp;  android engineer  &emsp;  | &emsp;  88.89%  &emsp;  | &emsp;  61  &emsp;  |
| &emsp;  ios engineer  &emsp;  | &emsp;  89.58%  &emsp;  | &emsp;  52  &emsp;  |


</br>

__Lowest/Highest Recall__

| &emsp;  Class &emsp;  | &emsp;  Recall  &emsp;  | &emsp;  Support &emsp;  |
|   ---   |   ---:   |   ---:   |
| &emsp;  consultant  &emsp;  | &emsp;  1.53% &emsp;  | &emsp;  131 &emsp;  |
| &emsp;  business consultant &emsp;  | &emsp;  4.17% &emsp;  | &emsp;  48  &emsp;  |
| &emsp;  manager &emsp;  | &emsp;  5.51% &emsp;  | &emsp;  127 &emsp;  |
| &emsp;  engineer  &emsp;  | &emsp;  7.63% &emsp;  | &emsp;  118 &emsp;  |
| &emsp;  director  &emsp;  | &emsp;  10.92%  &emsp;  | &emsp;  119 &emsp;  |
| &emsp;  build and release engineer  &emsp;  | &emsp;  84.73%  &emsp;  | &emsp;  131 &emsp;  |
| &emsp;  salesforce engineer &emsp;  | &emsp;  85.09%  &emsp;  | &emsp;  114 &emsp;  |
| &emsp;  android engineer  &emsp;  | &emsp;  91.80%  &emsp;  | &emsp;  61  &emsp;  |
| &emsp;  net engineer  &emsp;  | &emsp;  91.82%  &emsp;  | &emsp;  110 &emsp;  |
| &emsp;  technical recruiter &emsp;  | &emsp;  94.95%  &emsp;  | &emsp;  99  &emsp;  |

</br>

__Lowest/Highest F-Score__

| &emsp;  Class &emsp;  | &emsp;  F-Score &emsp;  | &emsp;  Support &emsp;  |
|   ---   |   ---:   |   ---:   |
| &emsp;  consultant  &emsp;  | &emsp;  2.61% &emsp;  | &emsp;  131 &emsp;  |
| &emsp;  business consultant &emsp;  | &emsp;  6.15% &emsp;  | &emsp;  48  &emsp;  |
| &emsp;  manager &emsp;  | &emsp;  8.75% &emsp;  | &emsp;  127 &emsp;  |
| &emsp;  engineer  &emsp;  | &emsp;  12.77%  &emsp;  | &emsp;  118 &emsp;  |
| &emsp;  director  &emsp;  | &emsp;  13.20%  &emsp;  | &emsp;  119 &emsp;  |
| &emsp;  database administrator  &emsp;  | &emsp;  82.79%  &emsp;  | &emsp;  123 &emsp;  |
| &emsp;  build and release engineer  &emsp;  | &emsp;  83.46%  &emsp;  | &emsp;  131 &emsp;  |
| &emsp;  technical recruiter &emsp;  | &emsp;  85.45%  &emsp;  | &emsp;  99  &emsp;  |
| &emsp;  ios engineer  &emsp;  | &emsp;  86.00%  &emsp;  | &emsp;  52  &emsp;  |
| &emsp;  android engineer  &emsp;  | &emsp;  90.32%  &emsp;  | &emsp;  61  &emsp;  |

</br>

__Most Confused__

| &emsp;  Actual Class  &emsp;  | &emsp;  Predicted Class &emsp;  | &emsp;  Cases &emsp;  |
|   ---   |   ---   |   ---:   |
| &emsp;  accountant  &emsp;  | &emsp;  staff accountant  &emsp;  | &emsp;  38  &emsp;  |
| &emsp;  marketing director  &emsp;  | &emsp;  marketing manager &emsp;  | &emsp;  35  &emsp;  |
| &emsp;  java software engineer  &emsp;  | &emsp;  j2ee engineer &emsp;  | &emsp;  32  &emsp;  |
| &emsp;  associate &emsp;  | &emsp;  cashier &emsp;  | &emsp;  31  &emsp;  |
| &emsp;  network administrator &emsp;  | &emsp;  network engineer  &emsp;  | &emsp;  30  &emsp;  |
| &emsp;  manager &emsp;  | &emsp;  general manager &emsp;  | &emsp;  28  &emsp;  |
| &emsp;  assistant &emsp;  | &emsp;  administrative assistant  &emsp;  | &emsp;  26  &emsp;  |
| &emsp;  design engineer &emsp;  | &emsp;  mechanical design engineer  &emsp;  | &emsp;  26  &emsp;  |
| &emsp;  process engineer  &emsp;  | &emsp;  manufacturing engineer  &emsp;  | &emsp;  25  &emsp;  |
| &emsp;  project manager &emsp;  | &emsp;  it project manager  &emsp;  | &emsp;  25  &emsp;  |

</br>

### Example Result

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/doc_similarity_image.png" width="1000">

### PCA Analysis


To play with the data yourself, you can input our vector and metadata file to this website: [https://projector.tensorflow.org/](https://projector.tensorflow.org/)


[Link to Generate Vectors](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/03_process_salary_and_create_ngram_model.ipynb)

[Link to Vectors File](https://drive.google.com/open?id=1y9wjQhVtUC7Z3APXqlJ8D-04CP5N4mWN)

[Link to Metadata File](https://drive.google.com/open?id=1w4LXTvw0G-g6Wg1_lZL5DHFl646J6cf4)

## [2] Job Skills

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/03_process_salary_and_create_ngram_model.ipynb)

</br>

## [3] Next Steps


