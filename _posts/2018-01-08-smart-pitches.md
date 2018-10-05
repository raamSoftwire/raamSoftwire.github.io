---
layout: post
title: Smart Pitches
image: /img/smartPitches/heatmapLogo.png
subtitle: Dashboard Web App
---

![Pitch heatmap](/img/smartPitches/heatmap.png)

Work in progress.

## Introduction

This was my first commercial project, and I was working in a small team with another new developer, a tech lead and a project manager. All of us were new to our roles but we were very successful and were billed as the _happiest team in Softwire_.

This project was a collaboration with an image recognition and machine-learning company. They used their technology to track football players on the pitch to build up detailed heatmaps as a function of time. They were collecting live data from a large number of pitches from around the country. Our role was to build a web app to display the large amount of  data in real time, in a way that was easy to understand at a glance.

## Architecture

The first challenge in this project was to manage the huge amount of data being produced and to store it in a way that would allow us to extract the necessary information. We used Cloud Functions for Firebase with cronjobs to run our backend code every five minutes to ingest the data from the client API and to pipe it into our NoSQL database provided by Google's Firestore.

The second challenge was to process the data and to display meaningful metrics in a user-friendly dashboard. We built from a [Create React App](https://github.com/facebook/create-react-app) with Typescript, which provided a lot of the initial infrastructure for free, including build tools and a testing framework. 

The site was hosted on Google's Firebase, and the code was kept in a GitHub repository. As well as source control we also used GitHub for our code reviews, which meant that I was able to see an alternative to Crucible. I came to prefer Github as it integrated seamlessly with pushing new branches and making pull requests when merging feature branches to master.

The project was set up with continuous integreation using the Travis CI plugin for Github. This would run the test suite when new code was pushed to let us know of any breaking changes, so that we could be confident in the new code and continue to roll out new features quickly.

IMAGE of logos of the techstack.


## Key Features

### Code Style

We wrote the code for this site in VS Code, which I found much more light-weight and user-friendly than IntelliJ IDEA. We used TSLint on this project which defined a clear set of rules for code style, which were then automatically enforced throughout the codebase.

![Linting hint](/img/smartPitches/linting.png)

### Structuring the Data

One of the first data analysis tasks on this project was to determine the correct structure for the data that was coming in and how we wanted to store it in the database. We used the Unified Modeling Language (UML) to understand how our data should be structured. 

![Unified Modeling Language](/img/smartPitches/uml.png)

This allowed us to understand the relationships between the different entities, for example there was a one to many relationship between facilities and pitches. A facility could have multiple pitches, but a pitch could only belong to exactly one facility.

### Determining Useful Metrics

The raw data provided by the client's API was provided in five minute chunks of two types. One was player data, which contained a unique ID, a timestamp, the average number of players on the pitch, a 2D array of positions for the heatmap and an photograph of the pitch used to verify the data. The other set of data was gathered from tracking maintenance vehicles and followed a similar pattern.

{% highlight javascript linenos %}
export interface Usage {
    id: string;
    timestamp: Date;
    playerCount: number;
    heatmap: HeatmapData;
    peakTimeSnapshots?: PeakTimeSnapshots;
}
{% endhighlight %}

An important part of our brief was to process this data to create useful metrics and figures, including the amount of usage on the pitch over a given timeframe and the predicted amount of time until the next required maintenance.

![Deciding on the important metrics](/img/smartPitches/metrics.png)

This included many discussions as a team and with the client to extract the most useful statistics. We approached this by considering each page at a time, and imagining the user's journey through the site.

### Analysis Algorithms

A big challenge was converting the data we had to be comparable with industry standards for the maintenance of sports pitches. This involved making sure X.

Raam also developed the data analysis algorithms and the final render of the data into a user-friendly dashboard. Arrow functions. JS idioms. ES6. Map. Array manipulation. Heatmaps saved as arrays of data. Function for converting array to heatmap.

Can take a variety of data and business requirements and convert them into basic analysis artefacts to understand and clarify the intended use of the proposed software	Understanding maintenance indicators. Calculation of maintenance indication. Came up with he algorithms and implememented the maths.

### Agile


Sprints. Sprint planning. Retro. 


### UX focus

Throughout this project we had a strong focus on the user experience, to ensure that the large amount of information was presented in a clear and aesthetically pleasing manner. It was important that the data was useful rather than overwhelming.This was done by using visual representations to display the key values and metrics. 

Breaking down the data into the useful metrics.
![Deciding on the important metrics](/img/smartPitches/heatmapStats.png)
![Deciding on the important metrics](/img/smartPitches/maintenance.png)

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