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

This project was a collaboration with an image recognition and machine-learning company. We used their technology to track football players on the pitch to build up detailed heatmaps and pitch usage data as a function of time. 

![Pitch usage data](/img/smartPitches/usageGraph2.png)

They were collecting live data from a large number of pitches from around the country. Our role was to build a web app to display the large amount of data in real time, in a way that was easy to understand at a glance.

## Architecture

![Logos for Google Firebase, React, Github and Travis CI](/img/smartPitches/logos.png)

The first challenge in this project was to manage the huge amount of data being produced and to store it in a way that would allow us to extract the necessary information. We used Cloud Functions for Firebase with cronjobs to run our backend code every five minutes to ingest the data from the client API and to pipe it into our NoSQL database provided by Google's Firestore.

The second challenge was to process the data and to display meaningful metrics in a user-friendly dashboard. For the front-end we started with a [Create React App](https://github.com/facebook/create-react-app) with Typescript, which provided a lot of the initial infrastructure, including build tools and a testing framework. 

We also used Google's Firebase to host our site and the code was kept in a GitHub repository. As well as source control we also used GitHub for our code reviews, which meant that I was able to see an alternative to Crucible. I came to prefer Github as it integrated seamlessly with pushing new branches and making pull requests when merging feature branches to master.

The project was set up with continuous integreation using the Travis CI plugin for Github. This would run the test suite when new code was pushed to let us know of any breaking changes, so that we could be confident in the new code and continue to roll out new features quickly.

## Key Features

### Working Closely with the Client

On this project we were lucky that our client worked in the same building and so they were able to attend our morning standup meetings. This really benefitted the team because we were able to keep our development effort closely aligned with their requirements. 

We also gave weekly demos of the site, which acted as a chance for them to step back and to see the work as a whole. These regular meetings were important to gain feedback and also to identify bugs.

### Structuring the Data

One of the first data analysis tasks on this project was to determine the correct structure for the data that was coming in and how we wanted to store it in the database. We used the Unified Modeling Language (UML) to understand how our data should be structured. 

![Unified Modeling Language](/img/smartPitches/uml.png)

This allowed us to understand the relationships between the different entities, for example there was a one to many relationship between facilities and pitches. A facility could have multiple pitches, but a pitch could only belong to exactly one facility.

### Determining Useful Metrics

The raw data provided by the client's API was provided in five minute chunks of two types. One was pitch usage data, which contained a unique ID, a timestamp, the average number of players on the pitch, a 2D array of positions for the heatmap and an photograph of the pitch used to verify the data. The other set of data was gathered from tracking maintenance vehicles and followed a similar pattern.

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

This included many discussions as a team and with the client to extract the most useful statistics. We approached this task by considering each page one at a time, and imagining the user's journey through the site.

### Analysis Algorithms

One of the aspects I enjoyed the most about this project was determining the data analysis algorithms to use to process and utilise the data about the pitches. One of the more challenging requests from the client was to create an indicator for when the pitch would next need maintenance work.

In order to solve this problem we had to find a meaningful and reliable way of quantifying current usage and maintenance levels and extrapolating into the future to estimate whether extra maintenance would need to be carried out alongside scheduled maintenance operations. This was particularly interesting because we had to create a system that was robust enough to handle lots of different edge cases.

### Code Style

We wrote the code for this site in VS Code, which I found much more light-weight and user-friendly than IntelliJ IDEA. We used TSLint on this project which defined a clear set of rules for code style, which were then automatically enforced throughout the codebase.

![Linting hint](/img/smartPitches/linting.png)

This also came with handy keyboard shortcuts for auto-correcting linting errors, which made it very easy to stay on top of things and keep the codebase tidy.

### Agile

This project was managed using an Agile approach, which meant that we had short iteration cycles and regularly shared our progress with the client in order to continually reassess and refine what we were building. We worked in week-long _sprints_, and before the start of each sprint we would have a sprint planning meeting. In these meetings we would split up the work into small tasks and estimate points for how difficult we thought each one would be. We would then keep track of how many points we would collect by the end of the sprint. This gave us a metric for team velocity as we went through the project and helped us to determine how much we could reasonably acheive in future sprints.

We would also have weekly retrospective meetings as a team to assess what went well in the last sprint, what didn't work so well and what needed to be changed. Personally, I feel like these were the meetings that helped us work most cohesively as a team as they were a place to share small team victories but also to voice concerns openly and to have them addressed.

### UX focus

Throughout this project we had a strong focus on the user experience, to ensure that the large amount of information was presented in a clear and aesthetically pleasing manner. It was important that the data was useful rather than overwhelming. This balance was found by using visual representations to display the key values and metrics. 

![Visual representations of key values and metrics](/img/smartPitches/heatmapStats.png)

We had been given designs by the client, showing us how they wanted the finished website to look. This helped to guide us as we built the site, and meant that we had a well defined target to work towards. Below is the original design for the Facility page.

![The original designs](/img/smartPitches/compEnvision.png)

And this is how the page looked on the final site. As we worked through the project we worked with the client to tweak the initial designs and to make the site more user-friendly. One example shown here is the use of large green buttons for toggling between different pitches rather than using light grey arrows.

![The finished product](/img/smartPitches/compReal.png)


## Conclusion

I really enjoyed my first billable project and working so closely with an external client. It felt good to be building something useful that someone wanted to pay for and knowing that if we got it right it might be used internationally. 

The [client's site](http://intelligent-play.co.uk/) has a great video on the homepage about the overall vision for this project and also has a separate page about the software we built.