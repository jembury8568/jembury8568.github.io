---
title: "iNaturalist Meta-Analysis"
date: 2022-06-09 09:00

categories:
  - Research
tags:
  - Spatial Analysis
  - Scripting
  - Databases
  - Mapping
 
classes: wide
layout: single

header:
  image: /assets/images/globes-header.jpg
  caption: "Photo by [Arthur Edelmans](https://unsplash.com/@arthuredelmans_) on [Unsplash](https://unsplash.com/)"

sidebar:
  title: "Sections"
  children:
    - title: Objectives & Questions
      url: #objectives--questions
    - title: Data
      urlL: #data
    - title: Skills & Tools
      url: #skills--tools
    - title: Methods
      url: #methods
    - title: Results
      url: #results
    - title: Learn More
      url: #learn-more
      
---

In an exploration of citizen science, this collaborative project investigated the behavior of iNaturalist users across space and time. 

The 3-minute project video provides details about the analysis.

{% include video id="MSizZulIYZw" provider="youtube" %}

***

### Objectives & Questions

In my analysis of iNaturalist users in the United States, I addressed two research questions:
1. How has the spatial distribution of iNaturalist users changed from 2014 to 2020?
2. What is the typical behavior of an iNaturalist user?

***

### Data
* iNaturalist GBIF DarwinCore Archive - [Link](https://www.gbif.org/dataset/50c9509d-22c7-4a22-a47d-8c48425ef4a7)
* American Community Survey - [Link](https://www.census.gov/programs-surveys/acs)
* TIGER/Line Shapefiles - [Link](https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html)

***

### Skills & Tools
* Database Management
  * PostgreSQL
  * PostGIS
* Scripting
  * Python
  * Pandas
  * Matplotlib
* Cartography
  * ArcGIS Pro

***

### Methods

I loaded the data into a PostgreSQL database, then cleaned and preprocessed the data with SQL commands. I used the PostGIS extension for spatial operations - such as calculation of observation centroids and observation-centroid distances. I then used Python's Pandas and Matplotlib libraries to find summary statistics and genrate graphs. I created maps in ArcGIS Pro.

***

### Results

***Spatial Distribution of iNaturalist Users in the US***  
Early iNaturalist observations were centered around San Francisco and Los Angeles, then spread in the Eastern Seaboard and Texas. By 2016, hot spots in the Pacific Northwest, the Great Lakes region, and Denver began to emerge. By September of 2020, additional hot spots in Florida, Arizona, and throughout the Eastern United States appeared.

![A heat map of the US showing growth of the iNaturalist platform as it spreads from urban centers.]({{ site.url }}{{ site.baseurl }}/assets/images/research-inat-map.gif)  
*iNaturalist users spread across the United States as the community grew from 8,998 users in 2014 to 138,990 users in 2020, as of September 25th.* 

***Additional Insights***  
The total number of users and total observations grew rapidly, especially during 2018 - 2019. Although 2020 data ends at September 25th, total users and observations still increased. However, the number of observations per user and the mean distance from the user centroids both decreased in 2020, possibly idue to COVID-19 shut down orders. The mean distance between observations and a user's centroid indicate whether individual observations tend to be spread out across large distances or tightly clustered. 

![Line graphs showing number of users and observations from 2014 to 2020 with steady growth early on that increased more rapidly in 2018 and 2019. Other line graphs show the number of observations per user (highest in 2017-2018) and mean distance from user centroid (extreme decrease in 2020).]({{ site.url }}{{ site.baseurl }}/assets/images/research-inat-graphs.png) 

***

### Learn More
Visit the project's [website](https://sites.google.com/view/inaturalistmetaanalysis/home) for more information.
