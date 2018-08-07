+++
title = "Back-End Architecture"
date = "2018-07-27"
author = "iCareer Climber Team"
+++

</br>

## [1] The Backend Application

<a href="https://github.com/kbelsvik/career-skills-capstone/tree/master/careers-api" target="_blank">Link to Code</a>

The backend is a Flask application whose primary purpose is to accept job description inputs and output job similarity scores using the model.  This allows us to serve up model results for consumption by the frontend application.

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/Backend-arch.png" width="500">

The application is built as a docker container which can easily be tested locally and then uploaded to Google Cloud Container Registry and deployed to a Google Cloud cluster with Kubernetes.


The models are stored in a Google Cloud Storage bucket, which is mounted to the application container using <a href="https://cloud.google.com/storage/docs/gcs-fuse" target="_blank">FUSE</a>.  The models are stored as pickled Scikit Learn models which can be loaded into the Flask application.

</br>

## [2] The API Requests

The backend is a basic REST api which accepts and serves JSON data.

```bash
$ curl -XPOST -H 'Content-Type: application/json' -d '{"experience":[{"description": "organizing projects with agile and scrum methodologies"}]}' 35.230.26.112/model/similar_jobs | python -m json.tool | head -22
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  7535  100  7445  100    90   8638    104 --:--:-- --:--:-- --:--:--  8636
{
    "results": [
        {
            "probability": 0.24560086752139812,
            "title": "technical project manager"
        },
        {
            "probability": 0.09362546705168302,
            "title": "quality assurance engineer"
        },
        {
            "probability": 0.07340485510020563,
            "title": "quality assurance analyst"
        },
        {
            "probability": 0.05443605668438692,
            "title": "ux engineer"
        },
        {
            "probability": 0.05370892876346319,
            "title": "program manager"
        },
```
