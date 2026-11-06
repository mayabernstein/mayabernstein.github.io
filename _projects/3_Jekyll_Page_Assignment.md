---
name: IS445 Jekyll Webpage Assignment
tools: [Python, Altair, vega-lite]
image: assets/pngs/cars.png // change
description: This is a "showcase" project that uses vega-lite for interactive viz! // change
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---
# **Jekyll Webpage Assignment Description**
[[[
    Include two paragraphs in your write up, one for each of your visualizations in the Jekyll portion of the assignment. This write up should include:

for EACH PLOT:
a description of what you are visualizing
what design choices you made: specifically what encoding types you are using, and if you are using a color scheme -- what variables you are coloring by and why you chose a specific color scheme
discussion of any data transformations that you did on the analysis side of things in your Python notebook
for your interactivity: specify what interactivity you chose for one (or more) plots and how this helps your visualization be more clear or interesting
Expect about a paragraph for each plot and another few sentences for discussion of interactivity.
]]]

## Heatmap & Histogram Interactive Chart (placeholder title)

This will explore different ways of doing the same plot with different plot sizes. 

<vegachart schema-url="{{ site.baseurl }}/assets/json/precipitation_probability_intensity_chart.json" style="width: 100%"></vegachart>

## Interactive Line Chart (placeholder title)

<vegachart schema-url="{{ site.baseurl }}/assets/json/seasonal_precipitation_intensity_illinois.json" style="width: 100%"></vegachart>

<!-- 
<vegachart schema-url="{{ site.baseurl }}/assets/json/simpleLines.json" style="width: 100%"></vegachart>
-->


<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/UIUC-iSchool-DataViz/is445_bcu_fall2026/blob/main/week10/inClass_week11.ipynb" text="The Analysis" %} // change
</div>

