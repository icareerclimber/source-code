+++
title = "Front-End Architecture"
date = "2018-07-26"
author = "iCareer Climber Team"
+++

+++
title = "Front-End Architecture"
date = "2018-07-26"
author = "iCareer Climber Team"
+++

</br>

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/frontend.png" width="500">

## UI Layer
UI layer has three components: A grid layout is created using Bootstrap, User interaction logic and state is maintained React JS; and D3.js is for visualization. The javascript libraries are sourced directlhy from cdn, while the Ajax style communication between the UI and the frontend web server is faciliate by Axios JS library. To simplify design, user input is passed to frontend server via http extension header instead of the traditional http form POST method. Given the nature of user submission, where resume is rarely bigger than 16kB, such design is sufficient for practical purpose.

## Frontend Server
The frontend server is implemented with Python Flask, packaged as Docker container, and deployed to Google Cloud with Kubernetes. The server is mostly stateless except the current active http transactions. The server and the UI layer is loosely coupled with RestAPI. And the server's major responsibility is to translate data formats between the UI layer and backend server, that is, between key-value pair in http header to json that is required by backend server.

## Interface to Backend Server
The communication between frontend and backend is also through RestAPI, and backend service discovery is made simple by Kubernetes deployment tool.

## Lessons Learned
Integrating multiple javascript library (and different versions of each) is difficult.
Modular design from the beginning is mandatory for non-trivial javascript app.
UX testing needs to be done early and often.

## Next Steps
Big fix
Add an upload link to upload resume and parse contents
Refactor spaghetti code
Making user interaction more friendly, maybe using a chatbot.
