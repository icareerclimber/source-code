+++
title = "The Models"
date = "2018-07-29"
author = "iCareer Climber Team"
+++

</br>

## [1] Document Similarity Model

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/03_process_salary_and_create_ngram_model.ipynb)

We provide career recommendations in a ranked order based on the similarity of a job seeker's current job experiences. Our model is powered by resume information all across the US. This product is a proof of concept and contains a small subset of possible jobs (114 unique job titles). The list of jobs is derived from the availability of salary and resume data. We selected all jobs that contained at least 100 salary records in the past 5 years and 500 resume job summaries in the past 10 years.

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/doc_similarity_image1.png" width="1000">


</br>

### Model Parameters

```
Number of Classes:
    114

Train-Test Split:
    222,978 / 11,736 (95% / 5%)

TD-IDF Vectorizer:
    Min_df: 5
    Ngram_range: [1,3]

Undersampling:
    More common jobs were undersampled to 2500 records based on job recency.

Oversampling:
    Less common jobs were oversampled to 2500 records using the regular Synthetic Minority Over-sampling Technique (SMOTE).

Multinomial Naive Bayes Classifier:
    Alpha: 0.02
```

</br>

### Model Performance

</br>

__Performance__

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

### PCA Analysis

We performed a PCA analysis to test the clustering results from the TD-IDF vectorization of job summaries. The vectors were reduced to a 3-dimensional space and put into the [Embedding Projector](https://projector.tensorflow.org/) website. The below results show that different job summaries for the same job share a lot of the same skills and language.

</br>

1. Below are the 500 closest job summaries to a randomly selected ___Android Engineer___ job summary. A majority of these job summaries have the job title Android Engineer indicating that Android Engineers view and discribe their roles similarly.

&emsp;&emsp;<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/pca_viz_android_engineer.png" width="1000">

2. Below are the 500 closest job summaries to a randomly selected ___Consultant___ job summary. Many different job titles are represented in this group. It appears the role of a Consultant is much more variable than that of an Android Engineer.

&emsp;&emsp;<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/pca_viz_consultant.png" width="1000">

</br>

3. Just for fun, we selected a random ___Data Scientist___ job summary. The Data Scientist role appears to be at the intersection of data analysis, engineering, product management, and research. ;)

&emsp;&emsp;<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/pca_viz_data_scientist.png" width="1000">

To play with the data yourself, you can input our [vector file](https://drive.google.com/open?id=1y9wjQhVtUC7Z3APXqlJ8D-04CP5N4mWN) and [metadata file](https://drive.google.com/open?id=1w4LXTvw0G-g6Wg1_lZL5DHFl646J6cf4) to this website: [https://projector.tensorflow.org/](https://projector.tensorflow.org/) 

</br>

### Example Output

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/doc_similarity_image2.png" width="1000">

</br>


## [2] Job Skills Model

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/03_process_salary_and_create_ngram_model.ipynb)

In order to produce useful skills information, we created a model similar to the Document Similarity Model with a few differences.

</br>

### Model Parameter Differences

```
Train-Test Split:
    325,787 / 17,147

TD-IDF Vectorizer:
    Ngram_range: [3,3]

Undersampling:
    Common job undersampling to 5000 records

Oversampling:
    SMOTE oversampling to 5000 records
```

</br>

### Model Performance

| &emsp;Metric&emsp; | &emsp;Result&emsp; |
|---|---|
| &emsp;Accuracy&emsp; | &emsp;39.30%&emsp; |
| &emsp;F1 Score&emsp; | &emsp;35.57%&emsp; |
| &emsp;Precision Score&emsp; | &emsp;36.70%&emsp; |
| &emsp;Recall Score&emsp; | &emsp;36.12%&emsp; |

</br>

### Example Outputs

</br>

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/skills_technical_writer.png" height="300">&emsp;&emsp;&emsp;<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/skills_front_end_engineer.png" height="300">&emsp;&emsp;&emsp;<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/skills_data_scientist.png" height="300">

</br>

## [3] Time-Based Model (Not Productionized)

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/07_process_model_software_engineer_over_time.ipynb)

The resumes we collected contained a large number of ___software engineering___ roles, so we thought it would be interesting to create a classification model to derive the most important skills for different periods of time for software engineers. Below are the highest weighted skills for each timeframe. __This model is not included in the app.__

</br>

### Model Parameters

```
Number of Classes:
    5

TD-IDF Vectorizer:
    Min_df: 0
    Ngram_range: [2,4]

Oversampling:
    Less common jobs were oversampled to 2500 records using the regular Synthetic Minority Over-sampling Technique (SMOTE).

Multinomial Naive Bayes Classifier:
    Alpha: 0.1
```

</br>

### Model Performance

| &emsp;Metric&emsp; | &emsp;Result&emsp; |
|---|---|
| &emsp;Accuracy&emsp; | &emsp;54.52%%&emsp; |

</br>

### Results

Technology is one of the fastest changing industries. From this model, we can see the rise to prominence and the fall of different tools throughout time.

|   &emsp;  Earlier-1998    &emsp;  |   &emsp;  1998-2003   &emsp;  |   &emsp;  2003-2008   &emsp;  |   &emsp;  2008-2013   &emsp;  |   &emsp;  2013-2018   &emsp;  |
|       ---     |       ---     |       ---     |       ---     |       ---     |
|   &emsp;  development team    &emsp;  |   &emsp;  database design &emsp;  |   &emsp;  unit testing    &emsp;  |   &emsp;  management system   &emsp;  |   &emsp;  version control &emsp;  |
|   &emsp;  test plan   &emsp;  |   &emsp;  rational rose   &emsp;  |   &emsp;  <span style="color:blue">___crystal report___</span>  &emsp;  |   &emsp;  html cs javascript  &emsp;  |   &emsp;  unit testing    &emsp;  |
|   &emsp;  window nt   &emsp;  |   &emsp;  client server   &emsp;  |   &emsp;  java j2ee   &emsp;  |   &emsp;  test plan   &emsp;  |   &emsp;  web application using   &emsp;  |
|   &emsp;  software design &emsp;  |   &emsp;  vb net  &emsp;  |   &emsp;  net asp net &emsp;  |   &emsp;  data access &emsp;  |   &emsp;  <span style="color:green">___visual studio___</span>   &emsp;  |
|   &emsp;  customer support    &emsp;  |   &emsp;  <span style="color:blue">___crystal report___</span>  &emsp;  |   &emsp;  web base    &emsp;  |   &emsp;  front end   &emsp;  |   &emsp;  full stack  &emsp;  |
|   &emsp;  tcp ip  &emsp;  |   &emsp;  <span style="color:purple">___using visual basic___</span>  &emsp;  |   &emsp;  software development    &emsp;  |   &emsp;  sql query   &emsp;  |   &emsp;  develop maintain    &emsp;  |
|   &emsp;  programmer analyst  &emsp;  |   &emsp;  store procedure &emsp;  |   &emsp;  oracle 9i   &emsp;  |   &emsp;  design implement    &emsp;  |   &emsp;  store procedure &emsp;  |
|   &emsp;  cobol ii    &emsp;  |   &emsp;  software application    &emsp;  |   &emsp;  html cs &emsp;  |   &emsp;  java j2ee   &emsp;  |   &emsp;  technology use  &emsp;  |
|   &emsp;  ibm mainframe   &emsp;  |   &emsp;  tcp ip  &emsp;  |   &emsp;  develop test    &emsp;  |   &emsp;  <span style="color:green">___visual studio___</span>   &emsp;  |   &emsp;  new feature &emsp;  |
|   &emsp;  client server   &emsp;  |   &emsp;  pl sql  &emsp;  |   &emsp;  store procedure &emsp;  |   &emsp;  new feature &emsp;  |   &emsp;  code review &emsp;  |
|   &emsp;  system use  &emsp;  |   &emsp;  technology use  &emsp;  |   &emsp;  role responsibility &emsp;  |   &emsp;  using asp net   &emsp;  |   &emsp;  agile scrum &emsp;  |
|   &emsp;  assembly language   &emsp;  |   &emsp;  user interface  &emsp;  |   &emsp;  window xp   &emsp;  |   &emsp;  unit testing    &emsp;  |   &emsp;  rest api    &emsp;  |
|   &emsp;  user interface  &emsp;  |   &emsp;  data warehouse  &emsp;  |   &emsp;  team member &emsp;  |   &emsp;  application use &emsp;  |   &emsp;  design implement    &emsp;  |
|   &emsp;  device driver   &emsp;  |   &emsp;  development team    &emsp;  |   &emsp;  design implementation   &emsp;  |   &emsp;  user interface  &emsp;  |   &emsp;  using asp net   &emsp;  |
|   &emsp;  develop implement   &emsp;  |   &emsp;  html javascript &emsp;  |   &emsp;  business logic  &emsp;  |   &emsp;  web base    &emsp;  |   &emsp;  entity framework    &emsp;  |
|   &emsp;  <span style="color:purple">___using visual basic___</span>  &emsp;  |   &emsp;  responsibility include  &emsp;  |   &emsp;  <span style="color:purple">___visual basic___</span>    &emsp;  |   &emsp;  software engineer   &emsp;  |   &emsp;  management system   &emsp;  |
|   &emsp;  vax vms &emsp;  |   &emsp;  operating system    &emsp;  |   &emsp;  management system   &emsp;  |   &emsp;  business logic  &emsp;  |   &emsp;  development team    &emsp;  |
|   &emsp;  pl sql  &emsp;  |   &emsp;  technical support   &emsp;  |   &emsp;  user interface  &emsp;  |   &emsp;  code review &emsp;  |   &emsp;  software engineer   &emsp;  |
|   &emsp;  responsibility include  &emsp;  |   &emsp;  web service &emsp;  |   &emsp;  net sql server  &emsp;  |   &emsp;  responsibility involve  &emsp;  |   &emsp;  sql server  &emsp;  |

</br>

## [4] Next Steps

1. Currently, the model considers similar ngrams like `accounts payable balance` and `organize accounts payable` to be completely different phrases. We would like to test training a vectorization model, like Doc2Vec, to place similar ngrams closer to each other in the vector space.

2. We would also like to test vect creation using the OpenAI Transformer model.

3. We would like to expand the number of classes used in the model.

4. We would like to incorporate a time component to the app. Can we see changes in the skills needed for each job?
