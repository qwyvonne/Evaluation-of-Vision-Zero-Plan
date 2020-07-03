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

## Time Series Analysis<br/>
<p align = 'center'>
  <img src = "time series.png" weight = "150" height = "150">
  <img src = "time series seperate.png" weight = "300" height = "300">
</p>
<br/>
Observations = Trend + Seasonality + Residual

**Trend**<br/>
There was a huge increase of cyclists getting injured from 2015 to 2016, which may seem like the roads have become more dangerous. However, it is not true. It is because the total cyclists population has increased significantly during that period of time because of 2 reasons.<br/>
1) NYPD started to use an electronic reporting system, which allows NYPD to record more data than before.<br/>
2) introduction of bike sharing system (Citi Bike) had encouraged more people cycling, and therefore leading to more injury and dead cases. <br/>

Due to data quality concern, we decide to remove 2015 to 2016 data and focus on analysis between 2013 versus 2014 and 2017 versus 2018

**Seasonality**<br/>

The majority of cyclist injuries and fatalities occurred from March to September of each year<br/>

## Spatial Analysis<br/>
**Change of the number of cyclist killed or injured by zipcode**<br/>
<br/>
<p align = 'center'>
  <img src = "spatial analysis.png" weight = "300" height = "300">
</p>



1) most of the places are becoming safer especially Midtown Manhattan<br/>
2) Number of cyclist injured or killed increased in Bronx and Staten Island<br/>

Further investigation of the regions that are fairly safe and unsafe needs to be conducted, will we take midtown Manhattan and Bronx as an example.<br/>

**Implementation of the initiaive in midtown Manhattan and Bronx**<br/>
|                     | Midtown Manhattan | Bronx |
| ------------------- | ----------------- | ----- |
| Speed Hump          | 1700              |6370   |
| Arterial Slow Zone  | 7427              |4078   |
| Signal Timing       | 33067             |9818   |
| Left Turn Traffic Calming| 8094         |227    |

Midtown Manhattan **outnumbered** Bronx in many other initiatives 
Bronx has more speedhump, but it is becoming more dangerous 

## Logistics Regression 

Observations: among all collision events, only collision events near or within 7 initiatives regions are considered (i.e. arterial, bike, cross, slow, left, signal, speed_hump)<br/>
Features: time (i.e. year, month, day_of_week, and hour) and whether an event is before/after initiatives (-> False/True) <br/>
Output: whether the number of cyclists injured or killed is zero or nonzero (-> False/True)<br/>

Result:<br/>
(1) the probability output of the logistic regression can be interpreted as a conditional probability - given a collision event, how likely the event involves cyclist injured or killed (i.e. non-zero number of cyclists injured or killed).<br/>
(2) statistically significant (negative): Arterial_Slow_Zones<br/>
(3) statistically significant (positive): Neighborhood_Slow_Zones, Signal_Timing<br/>
(4) statistically insignificant: Bike_Priority_Districts, Enhanced_Crossings, Left_Turn_Traffic_Calming, Speed_Humps<br/>

conclusion: Suppose that a collision event occurs, **Arterial_Slow_Zones** reduce the chance of a cyclist injured or killed in an car accident.<br/>

<p align = 'center'>
  <img src = "cyclist safety map and bike priority district.png" weight = "400" height = "400">
</p>


