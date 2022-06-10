---
title: "Dry-Cleaning Pollution Risk"
date: 2022-06-09 10:00

categories:
  - Research
tags:
  - Spatial Analysis
  - Geocoding
  - Remote Validation

header:
  image: /assets/images/globes-header.jpg
  caption: "Photo by [Arthur Edelmans](https://unsplash.com/@arthuredelmans_) on [Unsplash](https://unsplash.com/)"

sidebar:
  title: "Post Navigation"
  nav: sidebar-drycleaning
      
---
### Overview
The San Diego Regional Water Quality Control Board and the SDSU Sage Project teamed up to identify high-risk dry cleaning sites in San Diego County. As a project manager, I developed a Python package to geocode business addresses, created a remote validation process to verify site locations, performed spatial analysis to determine each site's potential risk to community health, and built a spatial database.

<p><em>"Hazardous chemicals used in traditional dry-cleaning methods pose a serious threat to population health when spilled or discharged illegally into the environment. Children, the elderly, individuals with certain medical conditions, or those living in disadvantaged communities are at even greater risk. San Diego State University students collaborated with the San Diego Regional Water Quality Control Board to identify current and historic dry-cleaning sites and assess each site’s risk to human health using spatial analysis techniques."</em><br><br>
Embury J. (2021). Identification of High-Risk Dry Cleaning Sites in San Diego County: Spatial Analysis [Technical report], p.6. The Sage Project at San Diego State University. https://digitallibrary.sdsu.edu/islandora/object/sdsu%3A139137</p>{:.notice}

In this 4-minute video, I describe the project's spatial analysis.

{% include video id="umVG5A1Q0uc" provider="youtube" %}

***

### Objectives
The Water Board considered a dry-cleaning site to be "high-risk" if it was located in an underserved community or near a sensitive receptor site.

<p><b>Key Term:</b> Sensitive receptor sites are places where individuals with elevated health risks to pollution exposure spend their time. For the analysis, I included schools, child care centers, hospitals, hospice and long-term care facilities, parks, and residences.</p>{:.notice}

Therefore, our project had two objectives:
1. Identify dry-cleaning sites located in underserved communities.
2. Identify dry-cleaning sites located near sensitive receptor sites.

***

### Data
* San Diego County Dry-Cleaning Site List (Compiled by SDSU students)
* OEHHA CalEnviroScreen 3.0 Data - [Link](https://oehha.ca.gov/calenviroscreen/report/calenviroscreen-30)
* SANDAG Shapefiles - [Link](https://www.sandag.org/index.asp?subclassid=100&fuseaction=home.subclasshome)

***

### Skills & Tools
* Scripting
  * Python
  * OSGeo
  * GeoPy
* GIS (Spatial Analysis & Cartography)
  * ArcGIS Pro
  * ArcGIS Online

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
Visit the project's [website](https://sites.google.com/view/inaturalistmetaanalysis/home){:target="_blank"} for more information.

