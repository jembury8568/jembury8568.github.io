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

<p><b>Key Term:</b> Sensitive receptor sites are places where individuals with elevated health risks when exposed to pollution spend their time. For the analysis, I included schools, child care centers, hospitals, hospice and long-term care facilities, parks, and residences.</p>{:.notice}

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
***Geocoding & Remote Validation***  
I created a Python package to geocode addresses from a list of dry-cleaning sites. Each geocoded address returned latitude and longitude coordinates from 4 geocoding service providers. I then developed a remote validation procedure to compare the 4 points to satellite imagery and select the most accurate coordinates for the dry-cleaning site.

[Geocoding Package](https://github.com/jlembury/Sage_Project){: .btn .btn--primary .btn--large}{:target="_blank"}

***Spatial Analysis***
Using the validated dry-cleaning locations, I used GIS and a spatial overlay operations to find all sites within [underserved communities](https://oehha.ca.gov/calenviroscreen/sb535). I then generated tables listing all dry-cleaning sites within 300, 500, or 1000 feet of a sensitive receptor site. Spatial analysis results were joined to the dry-cleaning site point features and included in a spatial geodatabase.

***

### Results
A geodatabase with all project data and analysis results was delivered to the Water Board, along with a technical report. The team also presented the project at the June 2021 San Diego Regional Water Quality Control Board meeting.  

37 of the 522 dry-cleaning sites were located in underserved communities. 73% of these sites are in the South and Central regions of the county.  
![A bar chart shows the division of dry-cleaning sites by HHSA region: 131 in North Central, 110 in North Coastal, 77 in East, 54 in South, 55 in Central, and 58 in North Inland.]({{ site.url }}{{ site.baseurl }}/assets/images/research-drycleaning-barchart.png)

***

### Learn More
Read the [technical report](https://digitallibrary.sdsu.edu/islandora/object/sdsu%3A139137){:target="_blank"} for more information.

