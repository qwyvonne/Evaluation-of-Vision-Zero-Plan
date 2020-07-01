# Evaluation-of-Vision-Zero-Plan

**KEYWORDS** <br/>
GIS, mapping, spatial analysis, death and injury rate, regression model, time series analysis 

**PROBLEM** <br/>
Evaluate NYC Vision Zero Plan https://www1.nyc.gov/content/visionzero/pages/<br/>
<br/>
**TECHNIQUES**<br/>
Python(data cleaning and exploratory analysis), time series analysis, spatial analysis, Tableau 

**SOLUTIONS**<br/>
Calculate decrease in number of death and injury; identify seasonal trend; focus on three initiatives for improvement

**DATA SOURCE**<br/>
NYC OPEN DATA https://data.cityofnewyork.us/browse?tags=vzv <br/>

#
## Background 
Cycling to work in NYC has grown **TWICE faster** as other major cities between 2012 and 2017. On a typical day, there are about 490,000 cycling trips made in New York City. Nearly one quarter of adult New Yorkers ride a bike, which are nearly 1.6 million people. Because of the high demand of cycling trends in nyc, **vision zero plan was created by New York City Mayor Bill de Blasio in 2014. Its purpose is to eliminate fatalities and serious injuries on New York City streets by 2024.**

<img src = "bikernumber.png" weight = "400" height = "400">

Vision Zero in New York City is based on a similar program of the same name that was implemented in Sweden. The original Swedish theory hypothesizes that pedestrian deaths are not as much "accidents" as they are a failure of street design. The deaths in New York City have been decreasing from implementation of the plan through 2018, however, **traffic injuries and crashes have been increasing**. Therefore, it is important for us to **examine the effectiveness of Vision Zero**. 
<br/>
Out of 206 initiatives, three initiatives that are most relevant to cyclists are picked<br/>
<br/>
- Speed Humps<br/> 
- Arterial Slow Zone<br/>
- Bike Priority Area<br/>
<br/>

###### Speed Humps: a raised area of roadway designed to reduce vehicle speed<br/>
###### Arterial Slow Zone: a combination of a lower speed limit, signal timing changes, distinctive signs and increased enforcement<br/>
###### Bike Priority Areas: neighborhoods with high numbers of cyclist KSI(Killed or Seriously Injured) and few dedicated bike facilities<br/>
<br/>

## Research Questions<br/>
Q1: Do the current 10 priority bicycle districts best represent the areas that need ridership safety attention?<br/>
Q2: What is the impact of Speed Hump Policy on bicycle fatalities and injuries?<br/>
Q3: What is the probability that a cyclist gets killed or injured with different initiatives implemented?<br/>

<p align = 'center'>
  <img src = "time series.png" weight = "150" height = "150">
  <img src = "time series seperate.png" weight = "300" height = "300">
</p>

There was a huge increase of cyclists getting injured from 2015 to 2016, which may seem like the roads have become more dangerous. However, it is not true. It is because the total cyclists population has increased significantly during that period of time because of 2 reasons.<br/>
1) NYPD started to use an electronic reporting system, which allows NYPD to record more data than before.<br/>
2) introduction of bike share that encouraged more people cycling. 



<p align = 'center'>
  <img src = "cyclist safety map and bike priority district.png" weight = "400" height = "400">
</p>


<br/>
<p align = 'center'>
  <img src = "spatial analysis.png" weight = "300" height = "300">
</p>
