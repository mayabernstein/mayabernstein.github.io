---
name: IS445 Jekyll Webpage Assignment
tools: [Python, Altair, vega-lite]
image: assets/pngs/line_chart_cover.png
description: This webpage features two interactive data visualizations using techniques learned through this course, along with practicing how to publish them on the web through integration with Jekyll.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---
# **Jekyll Webpage Assignment Description**
For this assignment, I will be practicing utilizing the visualization techniques I learned in this class to then export to my Jekyll webpage. The requirement of this assignment is to create two visualizations, where at least one contains some interactivity. For this homework, I have chosen a dataset that contains weather-related measures across all U.S. states. I will go more into depth of what I learned from each of the two visualizations I have created. 

## Heatmap & Histogram Interactive Chart

This plot is quite reflective of what we have seen in the professor's example on week 10's exportation of this kind of visualization onto a Jekyll webpage. The idea behind of this visualization is to explore the relationship between precipitation probability and precipitation intensity across different states. Specifically, I wanted to investigate whether observations with higher precipitation probabilities tend to be associated with greater precipitation intensity, and whether this relationship varies across states. The heatmap displays precipitation probability ranges for each state, while the interactive histogram shows the distribution of precipitation intensity for the selected observations. To make precipitation probabilities easier to interpret, I converted their decimal values into percentages. 

To go more into depth of the design choice, I used a heatmap to compare precipitation probability distributions across states. I binned the continuous precipitation probability values into ranges and used color to encode the number of observations within each state and probability range. This allows viewers to compare the frequency of observations across states and identify which precipitation probability occur more frequently. For the histogram, I decided to use precipitation intensity, which is a numerical variable for this kind of visualization because it would the most appropriate when examining its frequency distribution. From there, both visualizations are connected through the users' selection of particular states and precipitation probability ranges in the heatmap to then see the corresponding precipitation intensity distribution in the histogram on the right-hand side. With this interactivity method of selecting specific observations, viewers can better examine if there is any relationship between these variables, and how the precipitation intensity values vary across states. 

<vegachart schema-url="{{ site.baseurl }}/assets/json/precipitation_probability_intensity_chart.json" style="width: 100%"></vegachart>

## Interactive Line Chart

For this plot, I wanted to focus closely to how the precipitation intensity varies across seasons specifically in Illinois. I used a line chart to visualize changes in precipitation intensity over time, allowing viewers to exmaine potential seasonal patterns and differences. For the design, I used date as the temporal variable on the x-axis and precipitation intensity as the quantitative variable on the y-axis. I also used color to distinguish between seasons, allowing viewers to compare precipitation intensity patterns across the different seasons more easily. 

In order to create this plot, I had to make some decisions in how I cleaned and prepared the data. For example, the dates ranged back to 1980, where there were fewer observations compared to later years. I have decided to better access the relationship between seasons and precipitation intensity over time, I should filter the time range to years that contain more observations (around 2010 to 2017, the most recent period available in the dataset). I also had to change the data type of the date variable from string to datetime, so it could accurately record the values within the line plot. Additionally, with the season categories, I noticed that there was an extra categories called 'Unknown' (a category representing missing value), so I decided to remove that, so users would not see that as an option within the dropdown menu when highlighting the season they want to visualize better/more specifically. 

To explain the interactivity decision further, I chose to incorporate a dropdown menu that allows viewers to select a specific season they want to examine more closely. Without selecting a particular season, the overlapping seasonal trends may make it more difficult to distinguish individual patterns. By selecting a season, the corresponding line is highlighted while the other seasons are grayed out. This makes it easier to focus on the selected season while still retaining the other seasons as a reference for comparison. This in essence won't strain users' eyes as they work to understand the visualization as well as make interpreting seasonal patterns easier. 

<vegachart schema-url="{{ site.baseurl }}/assets/json/seasonal_precipitation_intensity_illinois.json" style="width: 100%"></vegachart>

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/mayabernstein/mayabernstein.github.io/blob/main/python_notebooks/hw_5_jekyll_webpage.ipynb" text="The Analysis" %} 
</div>

