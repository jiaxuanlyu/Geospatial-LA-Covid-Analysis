---
title: "Analysis: Traffic Collision Difference"
date: 2020-12-20
published: true
tags: [dataviz, altair]
excerpt: "Visualize differences of traffic collisions by using altair."
altair-loader:
  altair-chart-5: "charts/collision19_plot.json"
  altair-chart-6: "charts/collision20_plot.json"
toc: true
toc_sticky: true
---

The traffic collision data are obtained from Traffic Collision Data from 2010 to Present, Los Angeles Open Data by using API requests. Later, the data was merged with Los Angeles CSA to gain geometries. The traffic cases were summed up by each geometry point.
<br>
<br>

## Traffic Collisions in March, 2019

<div id="altair-chart-5"></div>

![daily-mean-diff]({{ site.url }}{{ site.baseurl }}/charts/collision19.png)

## Traffic Collisions in March, 2020

<div id="altair-chart-6"></div>

![daily-mean-diff]({{ site.url }}{{ site.baseurl }}/charts/collision20.png)


<br>
From the upper left part of both figures, we could see there are fewer and more discrete traffic collisions. Similarly, at the right downside, points of traffic collisions become fewer and more scatter. Based on the graphs, we could conclude that the traffic collisions are fewer at year 2020. In other words, the COVID and the shutdown lead to decreasing number of traffic collisions to some extent.
