---
layout: post
title: "Building Inventory Analysis"
---

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

## Visualization 1: Agency Management
<div id="vis1"></div>

## Visualization 2: Acquisition Trends
<div id="vis2"></div>

### Description & Design Choices

Plot 1

Description: This bar chart visualizes the total square footage managed by various state agencies. 

Design choices: I used Nominal (N) encoding for the Agency Names and Quantitative (Q) for sum of Square Footage. I chose the categoryy20 color scheme to provide distinct visual separation between the multitude of different agencies listed. 

Data transformation: I used Altair's internal aggregation, sum, to calculate the total area per agency


Plot 2

Description: This visualization explores the history of building acquisitions over time, categorizedby their current status. 

Design choices: I used Temporal (T) for Year Aquired, which i binned into 40 distinct periods to provide a clearer view of historical trends of acquisition. The Y axis represents a Quantitative (Q) count of the number of building acquired in those periods, and Nominal (N) color encoding for Bldg Status using the category10 color scheme, which provides high-contrast colors to help readers differentiate between different statuses easily.

Data transformation and interactivity: I implemented a Dropdown Selection Filter linked to the Building Status field. Users can select a specific status from the menu to highlight only those buildings in the chart. I used a conditional Opacity transformation. When a status is selected via the dropdown, the matching bars remain at full opacity (1.0), while the unselected categories fade to (0.1). This interactivity makes the visualization significantly more interesting and clear because it allows the user to "de-clutter" the timeline and focus on specific trends without losing context of the whole dataset


<a href="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv">
    <button type="button">The Data</button>
</a>

<a href="https://github.com/hannahip/hannahip.github.io/blob/main/IS445_HW_5.ipynb">
    <button type="button">The Analysis</button>
</a>

<script>
  vegaEmbed('#vis1', 'plot1.json');
  vegaEmbed('#vis2', 'plot2.json');
</script>
