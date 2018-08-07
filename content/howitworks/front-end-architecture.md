+++
title = "Front-End Architecture"
date = "2018-07-26"
author = "iCareer Climber Team"
+++

</br>

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/frontend.png" width="500">

## [1] UI Layer
The UI layer has three components: A grid layout is created using Bootstrap, User interaction logic and state is maintained using React JS; and D3.js is used for visualization. The JavaScript libraries are sourced directly from cdn, while the Ajax style communication between the UI and the frontend web server is facilitated by Axios JS library. To simplify design, user input is passed to frontend server via http extension header instead of the traditional http form POST method. Given the nature of user submission, where resume is rarely bigger than 16kB, such design is sufficient for practical purposes.

</br>

## [2] Frontend Server
The frontend server is implemented with Python Flask, packaged as a Docker container, and deployed to Google Cloud with Kubernetes. The server is mostly stateless except the current active http transactions. The server and the UI layer is loosely coupled with RestAPI. The server's major responsibility is to translate data formats between the UI layer and backend server, that is, between key-value pair in http header to json that is required by backend server.

</br>

## [3] Interface to Backend Server
The communication between frontend and backend is also through RestAPI, and backend service discovery is made simple by Kubernetes deployment tool.

</br>

## [4] Lessons Learned
Integrating multiple JavaScript libraries (and different versions of each) is difficult.
Modular design from the beginning is mandatory for non-trivial JavaScript app.
UX testing needs to be done early and often.

</br>

## [5] Next Steps
1. Bug fix
2. Add an upload link to upload resume and parse contents
3. Refactor spaghetti code
4. Making user interaction more friendly, maybe using a chatbot
