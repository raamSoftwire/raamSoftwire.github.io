---
layout: post
title: Smart Pitches
image: /img/smartPitches/heatmapLogo.png
subtitle: Dashboard Web App
---

![Pitch heatmap](/img/smartPitches/heatmap.png)

## Introduction

This project was a collaboration with an image recognition and machine-learning company. They used their technology to track football players on the pitch to build up detailed heatmaps as a function of time. They were collecting live data from a large number of pitches from around the country. Our role was to build a web app to display the large amount of  data in real time, in a way that was easy to understand at a glance.

## Architecture

The first challenge in this project was to manage the huge amount of data being produced and to store it in a way that would allow us to extract the necessary information. We used Cloud Functions for Firebase with cronjobs to run our backend code every five minutes to ingest the data and to pipe it into our NoSQL database provided by Google's Firestore.

The second challenge was to process the data and to display meaningful metrics in a user-friendly dashboard. We built the frontend by extending a [Create React App](https://github.com/facebook/create-react-app), which provided a lot of the initial infrastructure for free. We chose to use Typescript to benefit from static type checking. We used Redux to manage state within our React project. React meant that we were writing JSX code rather than pure HTML. We used SASS.

The site was hosted on Firebase, and the code was kept in a GitHub repository. We also used GitHub for our code reviews. VS Code. Travis CI

## Key Features

### Ingesting the data

He worked on the functional data processing of information from a client API into digestible formats. 5 minute chunks.

### Analysis Algorithms
Raam also developed the data analysis algorithms and the final render of the data into a user-friendly dashboard. Arrow functions. JS idioms. ES6. Map. Array manipulation. Heatmaps saved as arrays of data. Function for converting array to heatmap.

Can take a variety of data and business requirements and convert them into basic analysis artefacts to understand and clarify the intended use of the proposed software	Understanding maintenance indicators. Calculation of maintenance indication. Came up with he algorithms and implememented the maths.

### Determining Useful Metrics

Breaking down the data into the useful metrics.

### NoSQL Database

Database. NoSQL database for storing pitch data. Used UML to determine relationships between facilities, pitches, usage and maintenance.

### Redux Chrome DevTool

Redux Chrome devtools were useful for seeing what was in the state at a given point in time.

### Agile

Sprints. Sprint planning. Retro. 

### Continuous Integration

Continuous integration, relying on the tests passing.

Used continuous integration, which meant tht everytime a branch was pushed it ran the tests to see if it could be added without causing problem. Therefore important to have comprehensive tests

### UX focus

Throughout this project, he focussed on the UX to ensure that the large amount of information was presented in a clear and aesthetically pleasing manner.

Worked with designers and the InVision Boards.

Worked with InVision boards to design site. Worked closely with the designer on tweeking the existing site and making my own suggestions.

### Working Closely with the Client

Attended weekly meetings with the client to discuss data processing and gather feedback.

Regular demos to ensure that we were working within the clients requirements.

Can fix bugs and deal with change requests	Bugs found by client and TL
Can adapt to the employer's domain and context for software development and interpret and follow the software development approach being followed	Linter enforce strong coding preferences to make code consistent throughout the team. 


## Conclusion