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
<br>

## Travel Time Difference at AM Rush

Mean travel time at AM rush period in March 2019 and March 2020 are also compared.

![daily-mean-diff]({{ site.url }}{{ site.baseurl }}/assets/images/amdiff.png)

<br>
From the figure, the time differences vary from around less than +15 minutes to -20 minutes. The range of differences becomes larger. Furthermore, more census tracks have decreased more than 10 minutes of traveling time, and less census tracks have increased travel time. However, a few areas have much higher increase of time.
<br>

## Travel Time Difference at PM Rush

Similarly, mean travel time at PM rush period in March 2019 and March 2020 are compared.

![daily-mean-diff]({{ site.url }}{{ site.baseurl }}/assets/images/pmdiff.png)

<br>
Based on the figure, the time differences vary from +10 minutes to -30 minutes and more. The majority of regions increase the travel time. Areas where have decreased travel time show larger magnitude of change.
<br>
Overall, about the impacts of COVID on Uber traveling time, there are no clear evidences that the shutdown policy generally decreases travel time. Maybe the aggregated dataset lead to unclear changes because the decrease of time at the later month is not reflected in the data. Or at the early stage of pandemic, the policy does not alter a lot of people’s daily traveling activities.
