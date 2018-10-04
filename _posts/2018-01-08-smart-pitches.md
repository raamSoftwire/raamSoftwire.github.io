---
layout: post
title: Smart Pitches
image: /img/smartPitches/heatmapLogo.png
subtitle: Dashboard Web App
---

![Pitch heatmap](/img/smartPitches/heatmap.png)

Work in progress.

## Introduction

This was my first commercial project, and I was working in a small team with another new-starter, a tech lead and a project manager. All of us were new to our roles but we were very successful and were billed as the _happiest team in Softwire_.

This project was a collaboration with an image recognition and machine-learning company. They used their technology to track football players on the pitch to build up detailed heatmaps as a function of time. They were collecting live data from a large number of pitches from around the country. Our role was to build a web app to display the large amount of  data in real time, in a way that was easy to understand at a glance.

## Architecture

The first challenge in this project was to manage the huge amount of data being produced and to store it in a way that would allow us to extract the necessary information. We used Cloud Functions for Firebase with cronjobs to run our backend code every five minutes to ingest the data from the client API and to pipe it into our NoSQL database provided by Google's Firestore.

The second challenge was to process the data and to display meaningful metrics in a user-friendly dashboard. We built the frontend by extending a [Create React App](https://github.com/facebook/create-react-app) which used Typescript, which provided a lot of the initial infrastructure for free, including build tools and a testing framework. 

<!-- We chose to use Typescript to benefit from static type checking. React meant that we were writing JSX code rather than pure HTML. We used SASS. -->

The site was hosted on Google's Firebase, and the code was kept in a GitHub repository. As well as source control we also used GitHub for our code reviews, which meant that I was able to see an alternative to Crucible. I greatly preferred Github as it integrated seamlessly with pushing new branches and making pull requests when merging feature branches to master.

The project was set up with continuous integreation using the Travis CI plugin for Github. This would run the test suite when new code was pushed to let us know of any breaking changes, so that we could be confident in the new code and continue to roll out new features quickly.

IMAGE of logos of the techstack.


## Key Features

### Code Style

We wrote the code for this site in VS Code, which I found much lighter-weight and user-friendly than IntelliJ IDEA. We used TSLint on this project which defined a clear set of rules for code style, which were then automatically enforced throughout the codebase.

![Linting hint](/img/smartPitches/linting.png)

### Analysis Algorithms

The raw data provided by the client API was centred around the pitch usage by players and the maintenance carried out by groundsmen, and was structured as X. Part of our brief was to process this data to create useful metrics and figures, including the amount of usage on the pitch over a given timeframe and the predicted amount of time until the next required maintenance.

A big challenge was converting the data we had to be comparable with industry standards for the maintenance of sports pitches. This involved making sure X.



Raam also developed the data analysis algorithms and the final render of the data into a user-friendly dashboard. Arrow functions. JS idioms. ES6. Map. Array manipulation. Heatmaps saved as arrays of data. Function for converting array to heatmap.

Can take a variety of data and business requirements and convert them into basic analysis artefacts to understand and clarify the intended use of the proposed software	Understanding maintenance indicators. Calculation of maintenance indication. Came up with he algorithms and implememented the maths.

### Determining Useful Metrics

Breaking down the data into the useful metrics.
![Deciding on the important metrics](/img/smartPitches/metrics.png)
![Deciding on the important metrics](/img/smartPitches/heatmapStats.png)
![Deciding on the important metrics](/img/smartPitches/maintenance.png)



### NoSQL Database

NoSQL database for storing pitch data. Used UML to determine relationships between facilities, pitches, usage and maintenance.

![Unified Modeling Language](/img/smartPitches/uml.png)

### Redux Chrome DevTool

We used Redux to manage state within our React project. Explain state and a simple use case.

Redux Chrome devtools were useful for seeing what was in the state at a given point in time.

### Agile

### State Management

Sprints. Sprint planning. Retro. 

### Continuous Integration

Continuous integration, relying on the tests passing. TravisCI.

Used continuous integration, which meant tht everytime a branch was pushed it ran the tests to see if it could be added without causing problem. Therefore important to have comprehensive tests

### UX focus

Throughout this project we had a strong focus on the user experience, to ensure that the large amount of information was presented in a clear and aesthetically pleasing manner. It was important that the data was useful rather than overwhelming.This was done by using visual representations to display the key values and metrics. 

![Unified Modeling Language](/img/smartPitches/usageGraph2.png)

We had been given InVision boards by the client, showing us how they wanted the finished website to look. This helped to guide us as we built the site, and meant that we had a well defined target to aim for. 

IMAGE of comparison between InVision board and site.

![The original designs](/img/smartPitches/compEnvision.png)
![The finished product](/img/smartPitches/compReal.png)

### Working Closely with the Client

On this project we were lucky that our client worked in the same building and so they were able to attend our morning standups. This really benefitted the team because we were able to keep our development effort closely aligned with their requirements. 

We also gave weekly demos of the site, which acted as a chance for them to step back and to see the work as a whole. These regular meetings were important to gain feedback and also to identify bugs. This allowed us to iterate development quickly.

## Conclusion

First client project. Really enjoyed the client interaction and building something useful.

[Client site](http://intelligent-play.co.uk/)