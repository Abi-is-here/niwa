---
title: Plotly
date created: 2024-08-16T16:41  
date modified: 2024-08-16T16:41 
tags:
- software
- python
---

## Plotly express installation

```bash
pip install plotly plotly-express pandas
```

## plotly snippets

### cloropleth plot with setting size and slider

```python
fig2 = px.choropleth_mapbox(df,
                                   geojson=df.geometry,
                                   locations=df.index,
                                   color="color_variable",
                                   mapbox_style="open-street-map",
                                   animation_frame="time_margin",
                                   center={"lat":0, "lon": 0},
                                   zoom=11,
                                   width=1200, height=1000)
fig2.show()
```
- df : `geopandas.GeoDataFrame`
- geojson geojson column (has to be the GeoDataFrame item)
- color: variable that is used for coloring, detects if it is a gradient or limited list of values automatically
- animation_frame: variable used for the time frames, best if it is the hour/hour group string

### scatter with fixed size depending on one column, color based on prob, time slider and multiple columns in the hover data

```python
fig3 = px.scatter_mapbox(gdf,
                                   lat=gdf.geometry.y,
                                   lon=gdf.geometry.x,
                                   color="prob",
                                   mapbox_style="open-street-map",
                                   animation_frame="time",
                                   size="fixed_col",
                                   size_max=15,
                                   center={"lat": 0, "lon": 0},
                                   hover_data=["a","b","c","d"],
                                   zoom=11,
                                   width=1200, height=800)
fig3.show()
```
