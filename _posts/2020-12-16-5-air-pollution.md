---
title: "Analysis: Air Pollution Difference"
date: 2020-12-20
published: true
tags: [dataviz, altair]
excerpt: "Analyze air pollution differences by using altair."
altair-loader:
  altair-chart-1: "charts/pm_com.json"
  altair-chart-2: "charts/pm_apr.json"
  altair-chart-3: "charts/no_mar.json"
  altair-chart-4: "charts/no_apr.json"
toc: true
toc_sticky: true
---

Pollutions like NO2 and PM2.5 are related to vehicle emissions. I would like to see whether the concentrations of pollutants change during the early stage of COVID period in Los Angeles. Because the shutdown policy started at the middle of March in Los Angeles, I compare the pollutants’ data in both March and April.
<br>

## PM 2.5 Comparison: March

<div id="altair-chart-1"></div>


From the PM2.5 concentration comparison in March, we could see that the daily mean PM2.5 concentration is lower in year 2020, especially after 16th. However, there is a peak around 29th, and then the concentration in year 2020 becomes higher and is very close to that in year 2019.

## PM 2.5 Comparison: April

<div id="altair-chart-2"></div>

From the PM2.t concentration comparison in April, there is no clear trend that whether the concentration of pollutant become lower in year 2020.

## NO2 Comparison: March

<div id="altair-chart-3"></div>

## NO2 Comparison: April

<div id="altair-chart-4"></div>
