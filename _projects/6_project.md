---
layout: page
title: NYC Crime Visual Analytics
description: Visualizing and exploring crime patterns in New York City from 2018 to 2021
img: 
importance: 6
category: visualization and analytics
---

## Project Overview

This project focuses on visualizing and exploring crime patterns in New York City from 2018 to 2021 using large-scale NYPD data. The goal is to transform complex, high-volume data into intuitive visual insights that reveal spatial distribution, temporal trends, and demographic patterns, with particular attention to changes during the COVID-19 period.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/nyc_map.png" title="Crime Density Map" class="img-fluid rounded z-depth-1" style="height:200px;"%}
    </div>
</div>
<div class="caption">
    Crime Density Map of New York City, 2018-2021
</div>

## Data Overview

The dataset contains approximately 775,000 crime records across NYC boroughs, including information on crime type, location (borough and coordinates), and victim and suspect demographics. The richness of the data enables multi-dimensional visualization across space, time, and population groups.

## Visualization Strategy

The analysis is centered on building clear and interpretable visualizations to communicate key patterns. Techniques include time-series plots to track trends over time, geospatial heatmaps to highlight crime concentration, and mosaic and correlation plots to explore relationships between demographic variables. Additional visual tools, such as word clouds, are used to summarize categorical distributions and highlight dominant patterns.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/nyc_plot.png" title="Word Cloud" class="img-fluid rounded z-depth-1" style="height:200px;"%}
    </div>
</div>
<div class="caption">
    Word Cloud of Crime Location in New York City, 2018-2021
</div>

## Key Visual Insights

Visualizations reveal that crime is concentrated in Manhattan, Brooklyn, and the Bronx, with residential areas showing the highest activity. Time-series analysis highlights a sharp decline in crime during the early stages of COVID-19, followed by a rebound in 2021. Demographic visualizations indicate that victims are most commonly aged 25–44, with clear relationships between victim and suspect characteristics across categories.

## Impact

This project demonstrates the power of data visualization in making large, complex datasets accessible and actionable. By translating raw crime data into clear visual narratives, the analysis supports better understanding of urban dynamics and provides a foundation for future work in predictive modeling and policy evaluation.