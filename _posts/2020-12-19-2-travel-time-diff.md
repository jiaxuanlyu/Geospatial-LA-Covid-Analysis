---
title: "Analysis: Travel Time Difference"
date: 2020-12-20
published: true
tags: [dataviz, matplotlib]
excerpt: "Visualize Uber Travel Time differences by using matplotlib."
toc: true
toc_sticky: true
read_time: false
---

## Uber Travel Time difference

<br>

### Daily Mean Travel Time Difference

Holding an idea that traveling time is an indicator of people’s activities, I would like to know whether the travel time changes during the COVID-period. The data are referenced from <a href=" https://movement.uber.com/?lang=en-US">Uber Movements</a>. 
<br>
Because the most recent Uber Movements data are in March 2020, I choose to make the comparison between March 2020 and March 2019. Moreover, I would like to see the differences of mean daily travel time, mean am rush travel time and mean pm rush travel time.
<br>
At first, I change the travel time from seconds to minutes. Tables of year 2019 and year 2020 are merged later to calculate travel time differences. Aiming to obtain geometries of the Uber data which is grouped by census tracks, I use cenpy and extract geometries from American Community Survey data. After merging the geometries to Uber data, the data are visualized by using matplotlib.

![daily-mean-diff]({{ site.url }}{{ site.baseurl }}/assets/images/meandiff.png)
