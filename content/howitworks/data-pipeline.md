+++
title = "Data Pipeline"
date = "2018-07-31"
author = "iCareer Climber Team"
+++

</br>

## [1] Data Collection

Using Python Selenium and Beautiful Soup libraries to build web scraping tools, our team collected from the web <span style="font-size:22px;">__over 600k__</span> unique resumes and <span style="font-size:22px;">__1.1 million__</span> salary records representing <span style="font-size:22px;">__over 5500__</span> cities across <span style="font-size:22px;">__20__</span> years.

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/tree/master/scrape)

</br>

## [2] Data Transformation

Data ingestion pipelines were created to standardize the data inputs from various sources.

</br>

#### Jobs Title

Job titles vary widely from resume to resume, so we created a heuristic to process each job title into a standard format. In order to group different levels of the same job, we created a list of "job qualifiers" for each job and removed those words from the job title. Job qualifiers were manually determined and include words like *Lead*, *Senior*, *Junior*, *I*, and *Level 2*.

Transformation: ```Senior Software Engineer II``` &rarr; ```['software engineer',['senior','2']]```

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/01_process_job_titles_all_datasets.ipynb)

</br>

#### Job Description

Job descriptions were preprocessed to use for classification modeling. Preprocessing included lemmanization, stopword removal, special character removal, altering contraction, and tokenization. 

Transformation: ```.• Balance daily workflow of prospecting, responding to leads, scheduling and conducting appointments and maintain phone-based client relationships .• Conduct dynamic sales presentations for potential customers .• Use product knowledge and sales skills to recommend suggested products or services to fulfill customers' needs.``` &rarr; ```[' balance daily workflow prospecting responding lead scheduling conducting appointment maintain phonebased client relationship conduct dynamic sale presentation potential customer use product knowledge sale skill recommend suggest product service fulfill customer need ']```

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/functions/word_preprocessing.py)

</br>

#### Education Title

We created a rules-based logic to separate degree type from subject and processed all education information.

Transformation: ```B.S. in Business Administration and Management``` &rarr; ```[['business administration and management'],['bachelors']]```

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/04_process_edu_for_bar_chart.ipynb)

</br>

#### Salary

Salary information was cleaned and standarized.

Transformation: ```50000/YR``` &rarr; ```50000```

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/02_process_other_fields_all_datasets.ipynb)

</br>

#### Location

Locations were parsed into city and state.

Transformation: ```AKRON, OH``` &rarr; ```[['akron'],['Ohio']]```

[Link to Code](https://github.com/kbelsvik/career-skills-capstone/blob/master/model_pipeline/02_process_other_fields_all_datasets.ipynb)

</br>

## [3] Next Steps

1. Collect more data.

2. Identify new ways to group job titles.

3. Identify new ways to parse degree from subject.

4. Group degree types into STEM or non-STEM.
