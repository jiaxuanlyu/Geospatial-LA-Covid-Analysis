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

## Daily Mean Travel Time Difference

Holding an idea that traveling time is an indicator of people’s activities, I would like to know whether the travel time changes during the COVID-period. The data are referenced from <a href=" https://movement.uber.com/?lang=en-US">Uber Movements</a>. 
<br>
Because the most recent Uber Movements data are in March 2020, I choose to make the comparison between March 2020 and March 2019. Moreover, I would like to see the differences of mean daily travel time, mean am rush travel time and mean pm rush travel time.
<br>
At first, I change the travel time from seconds to minutes. Tables of year 2019 and year 2020 are merged later to calculate travel time differences. To illustrate, I use the travel time in year 2020 minus travel time in year 2019 to get the time differences. Aiming to obtain geometries of the Uber data which is grouped by census tracks, I use `cenpy` and extract geometries from American Community Survey data. After merging the geometries to Uber data, the data are visualized by using matplotlib. 

![daily-mean-diff]({{ site.url }}{{ site.baseurl }}/assets/images/meandiff.png)

<br>
From the figure, the daily mean travel time differences vary from +5 minutes to -15 minutes. Around the center of the city, compared to March 2019, the travel time increase around five minutes in March 2020. Not a lot of census blocks have decreased more than 10 minutes of traveling time. Based on <a href="https://www.nbclosangeles.com/news/local/a-coronavirus-timeline/2334100/">Kandel, 2020</a>, Los Angeles started to shutdown from the middle of March. Moreover, the data from Uber are aggregated data for one month, which might cause the minor changes in time.
