+++
title = "The Models"
date = "2018-07-29"
author = "iCareer Climber Team"
+++

</br>

## [1] Document Similarity Model 

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/doc_similarity_image1.png" width="500">

We provide career recommendations in a ranked order based on the similarity of a job seeker's current job experiences. Our model is powered by resume information across the US. This product is a proof of concept and contains a small subset of possible jobs (114 unique job titles). The list of jobs is derived from the availability of salary and resume data. We selected all jobs that contained at least 100 salary records in the past 5 years and 500 resume job summaries in the past 10 years.

<a href="https://github.com/icareerclimber/career-skills-capstone/blob/master/model_pipeline/03_process_salary_and_create_ngram_model.ipynb" target="_blank">Link to Code</a>

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

| Metric | Result |
|---|---|
| Accuracy | 48.86% |
| F1 Score | 46.14% |
| Precision Score | 47.60% |
| Recall Score | 47.55% |

</br>

__Lowest/Highest Precision__

|   Class   |   Precision   |   Support   |
|   ---   |   ---:   |   ---:   |
|   consultant    |   9.09%   |   131   |
|   business consultant   |   11.76%    |   48    |
|   director    |   16.67%    |   119   |
|   manager   |   21.21%    |   127   |
|   it specialist   |   22.22%    |   64    |
|   build and release engineer    |   82.22%    |   131   |
|   database administrator    |   83.47%    |   123   |
|   caregiver   |   86.67%    |   66    |
|   android engineer    |   88.89%    |   61    |
|   ios engineer    |   89.58%    |   52    |


</br>

__Lowest/Highest Recall__

|   Class   |   Recall    |   Support   |
|   ---   |   ---:   |   ---:   |
|   consultant    |   1.53%   |   131   |
|   business consultant   |   4.17%   |   48    |
|   manager   |   5.51%   |   127   |
|   engineer    |   7.63%   |   118   |
|   director    |   10.92%    |   119   |
|   build and release engineer    |   84.73%    |   131   |
|   salesforce engineer   |   85.09%    |   114   |
|   android engineer    |   91.80%    |   61    |
|   net engineer    |   91.82%    |   110   |
|   technical recruiter   |   94.95%    |   99    |

</br>

__Lowest/Highest F1-Score__

|   Class   |   F1-Score   |   Support   |
|   ---   |   ---:   |   ---:   |
|   consultant    |   2.61%   |   131   |
|   business consultant   |   6.15%   |   48    |
|   manager   |   8.75%   |   127   |
|   engineer    |   12.77%    |   118   |
|   director    |   13.20%    |   119   |
|   database administrator    |   82.79%    |   123   |
|   build and release engineer    |   83.46%    |   131   |
|   technical recruiter   |   85.45%    |   99    |
|   ios engineer    |   86.00%    |   52    |
|   android engineer    |   90.32%    |   61    |

</br>

__Most Confused__

|   Actual Class    |   Predicted Class   |   Cases   |
|   ---   |   ---   |   ---:   |
|   accountant    |   staff accountant    |   38    |
|   marketing director    |   marketing manager   |   35    |
|   java software engineer    |   j2ee engineer   |   32    |
|   associate   |   cashier   |   31    |
|   network administrator   |   network engineer    |   30    |
|   manager   |   general manager   |   28    |
|   assistant   |   administrative assistant    |   26    |
|   design engineer   |   mechanical design engineer    |   26    |
|   process engineer    |   manufacturing engineer    |   25    |
|   project manager   |   it project manager    |   25    |

</br>

### PCA Analysis

We performed a PCA analysis to test the clustering results from the TD-IDF vectorization of job summaries. The vectors were reduced to a 3-dimensional space and put into the <a href="https://projector.tensorflow.org/" target="_blank">Embedding Projector</a> website. The below results show that different job summaries for the same job share a lot of the same skills and language.

</br>

1. Below are the 500 closest job summaries to a randomly selected ___Android Engineer___ job summary. Many of these job summaries have the job title Android Engineer indicating that Android Engineers view and describe their roles similarly.

&emsp;&emsp;&emsp;<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/pca_viz_android_engineer.png" width="1000">

2. Below are the 500 closest job summaries to a randomly selected ___Consultant___ job summary. Many different job titles are represented in this group. It appears the role of a Consultant is much more variable than that of an Android Engineer.

&emsp;&emsp;&emsp;<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/pca_viz_consultant.png" width="1000">

</br>

3. Just for fun, we selected a random ___Data Scientist___ job summary. The Data Scientist role appears to be at the intersection of data analysis, engineering, product management, and research. ;)

&emsp;&emsp;&emsp;<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/pca_viz_data_scientist.png" width="1000">

To play with the data yourself, you can input our <a href="https://drive.google.com/open?id=1y9wjQhVtUC7Z3APXqlJ8D-04CP5N4mWN" target="_blank">vector file</a> and <a href="https://drive.google.com/open?id=1w4LXTvw0G-g6Wg1_lZL5DHFl646J6cf4" target="_blank">metadata file</a> to this website: <a href="https://projector.tensorflow.org/" target="_blank">projector.tensorflow.org</a> 

</br>

### Example Output

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/doc_similarity_image2.png" width="1000">

</br>

---------------------------------------

</br>


## [2] Job Skills Model

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/skills_app.png" width="500">

To produce useful skills information, we created a model like the Document Similarity Model with a few differences.

<a href="https://github.com/icareerclimber/career-skills-capstone/blob/master/model_pipeline/03_process_salary_and_create_ngram_model.ipynb" target="_blank">Link to Code</a> 

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

| Metric | Result |
|---|---|
| Accuracy | 39.30% |
| F1 Score | 35.57% |
| Precision Score | 36.70% |
| Recall Score | 36.12% |

</br>

### Example Outputs

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/skills_technical_writer.png" height="300"><img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/skills_front_end_engineer.png" height="300"><img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/skills_data_scientist.png" height="300">

</br>

---------------------------------------

</br>

## [3] Time-Based Model (Not Productionized)

The resumes we collected contained a large number of ___software engineering___ roles, so we thought it would be interesting to create a classification model to derive the most important software engineering skills throughout time. Below are the highest weighted skills for each time period. __This model is not included in the app.__

<a href="https://github.com/icareerclimber/career-skills-capstone/blob/master/model_pipeline/07_process_model_software_engineer_over_time.ipynb" target="_blank">Link to Code</a> 


</br>

### Model Parameters

```
Number of Classes:
    5

Train-Test Split:
    62,440 / 3287 (95% / 5%)

TD-IDF Vectorizer:
    Min_df: 0
    Ngram_range: [2,4]

Oversampling:
    Classes were balanced using the regular Synthetic Minority Over-sampling Technique (SMOTE).

Multinomial Naive Bayes Classifier:
    Alpha: 0.1
```

</br>

### Model Performance

|    Class |  Precision |  Recall | F1-Score | Support|
|   --- |  ---: | ---: | ---: | ---:|
|   Earlier-1998 |  67.66% | 57.38% | 62.10% | 474|
|   1998-2003 |  46.68% | 42.27% | 44.37% | 466|
|   2003-2008 |  45.39% | 40.85% | 43.00% | 639|
|   2008-2013 |  43.86% | 56.57% | 49.41% | 776|
|   2013-2018 |  70.46% | 67.06% | 68.72% | 932|

</br>

### Results

Technology is one of the fastest changing industries. From this model, we can see the rise to prominence and the fall of different software engineering tools throughout time.

|     Earlier-1998      |     1998-2003     |     2003-2008     |     2008-2013     |     2013-2018     |
|       ---     |       ---     |       ---     |       ---     |       ---     |
|     development team      |     database design   |     unit testing      |     management system     |     version control   |
|     test plan     |     rational rose     |     <span style="color:orange">___crystal report___</span>    |     html cs javascript    |     unit testing      |
|     window nt     |     client server     |     java j2ee     |     test plan     |     web application using     |
|     software design   |     vb net    |     net asp net   |     data access   |     <span style="color:red">___visual studio___</span>     |
|     customer support      |     <span style="color:orange">___crystal report___</span>    |     web base      |     front end     |     full stack    |
|     tcp ip    |     <span style="color:blue">___using visual basic___</span>    |     software development      |     sql query     |     develop maintain      |
|     programmer analyst    |     store procedure   |     oracle 9i     |     design implement      |     store procedure   |
|     cobol ii      |     software application      |     html cs   |     java j2ee     |     technology use    |
|     ibm mainframe     |     tcp ip    |     develop test      |     <span style="color:red">___visual studio___</span>     |     new feature   |
|     client server     |     pl sql    |     store procedure   |     new feature   |     code review   |
|     system use    |     technology use    |     role responsibility   |     using asp net     |     agile scrum   |
|     assembly language     |     user interface    |     window xp     |     unit testing      |     rest api      |
|     user interface    |     data warehouse    |     team member   |     application use   |     design implement      |
|     device driver     |     development team      |     design implementation     |     user interface    |     using asp net     |
|     develop implement     |     html javascript   |     business logic    |     web base      |     entity framework      |
|     <span style="color:blue">___using visual basic___</span>    |     responsibility include    |     <span style="color:blue">___visual basic___</span>      |     software engineer     |     management system     |
|     vax vms   |     operating system      |     management system     |     business logic    |     development team      |
|     pl sql    |     technical support     |     user interface    |     code review   |     software engineer     |
|     responsibility include    |     web service   |     net sql server    |     responsibility involve    |     sql server    |

</br>

---------------------------------------

</br>

## [4] Next Steps

1. Currently, these models consider similar ngrams like `accounts payable balance` and `organize accounts payable` to be completely different phrases. We want to explore different vectorization models, like Doc2Vec and OpenAI Transformer, to place similar ngrams closer to each other in the vector space.

2. We will expand the number of classes used in the model.

3. We are interested in incorporating a time component to the app. Can we model changes in job skills over time?
