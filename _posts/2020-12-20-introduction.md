---
title: "Introduction"
date: 2020-12-20
published: true
tags: [dataviz, folium]
excerpt: "Introduction."
folium-loader:
  folium-chart-1: ["charts/covid.html", "550"] # second argument is the height
toc: true
toc_sticky: true
---

## Background

A new coronavirus (called SARS-CoV-2), which generates symptoms such as fever, cough, trouble breathing, diarrhea and etc. <a href="https://www.cdc.gov/coronavirus/2019-ncov/symptoms-testing/symptoms.html">(CDC, 2020)</a> brought lots of changes to people’s daily lives. In order to alleviate the spread of COVID, the World Health Organization suggests people to wear masks and keep social distance <a href="https://www.who.int/emergencies/diseases/novel-coronavirus-2019/advice-for-public">(WHO, 2020)</a>. At March 11, 2020, the first death case of Coronavirus was reported in Los Angeles <a href="https://www.nbclosangeles.com/news/local/a-coronavirus-timeline/2334100/">(Kandel, 2020)</a>. Few days later, LA County ordered the closure of bars and gyms. Meanwhile, LAUSD (Los Angeles Unified School District) announced the closure of schools <a href="https://www.nbclosangeles.com/news/local/a-coronavirus-timeline/2334100/">(Kandel, 2020)</a>. More and more amenities were closed during the following days.
<br>
<br>
As background information, the accumulated COVID cases is visualized by using `Folium`. The data are referenced from <a href="http://dashboard.publichealth.lacounty.gov/covid19_surveillance_dashboard/">County of Los Angeles, Public Health</a>. In addition, the Los Angeles community data are referenced from <a href="https://egis-lacounty.hub.arcgis.com/datasets/countywide-statistical-areas-csa/data">County of Los Angeles, Countywide Statistical Areas (CSA)</a>.
<br>

<div id="folium-chart-1"></div>


<br>

### Method

```python
#set up
from matplotlib import pyplot as plt
import numpy as np
import pandas as pd
import geopandas as gpd
np.random.seed(42)
%matplotlib inline

pd.options.display.max_columns = 999

import folium
```
```python
#load covid data
covid = pd.read_csv("path")

#load LA Community data
LAcommunity = gpd.read_file("https://opendata.arcgis.com/datasets/7b8a64cab4a44c0f86f12c909c5d7f1a_23.geojson")
```

```python
#merge the LA community geometries with Covid data
LA_joined = pd.merge(LAcommunity, covid, left_on="LABEL", right_on="geo_merge")

##normalize
# Minimum
min_val = LA_joined["cases_final"].min()

# Maximum
max_val = LA_joined["cases_final"].max()

# Calculate a normalized column
normalized = (LA_joined["cases_final"] - min_val) / (max_val - min_val)

# Add to the dataframe
LA_joined["normalized_covid"] = normalized

##convert data to geojson
#select used columns
LA_joined_sel = LA_joined[["LABEL", "cases_final", "normalized_covid", "geometry"]]
#change column names
LA_joined_sel.columns = ["Community Name", "Covid Cases", "normalized_covid", "geometry"]
#change to json file
covid_json = LA_joined_sel.to_json()
```
```
##Folium Map

import matplotlib.colors as mcolors
# set up color scheme
cmap = plt.get_cmap('BuPu')

#style function
def get_style(feature):
    """
    Given an input GeoJSON feature, return a style dict.
    
    Notes
    -----
    The color in the style dict is determined by the 
    "percent_no_internet_normalized" column in the 
    input "feature".
    """
    # Get the data value from the feature
    value = feature['properties']['normalized_covid']
    
    # Evaluate the color map
    # NOTE: value must between 0 and 1
    rgb_color = cmap(value) # this is an RGB tuple
    
    # Convert to hex string
    color = mcolors.rgb2hex(rgb_color)
    
    # Return the style dictionary
    return {'weight': 1, 'color': "#5B8BB5", 'fillColor': color, "fillOpacity": 0.95}
    
    
#highlight function
def get_highlighted_style(feature):
    """
    Return a style dict to use when the user highlights a 
    feature with the mouse.
    """
    
    return {"weight": 3, "color": "#0E3F6F"}


#Plot
# STEP 1: Initialize the map
m = folium.Map(location=[34.2287077, -118.2526917], tiles='cartodbpositron', zoom_start=9)

# STEP 2: Add the GeoJson to the map
folium.GeoJson(
    covid_json, # The geometry + data columns in GeoJSON format
    style_function=get_style, 
    highlight_function=get_highlighted_style, 
    tooltip=folium.GeoJsonTooltip(["Community Name", "Covid Cases"])
).add_to(m)




#save map
m.save('covid.html')
```
