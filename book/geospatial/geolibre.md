---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.19.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

[![image](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/giswqs/gispro-fall26/blob/main/book/geospatial/geolibre.ipynb)
[![image](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/giswqs/gispro-fall26/main?urlpath=lab/tree/book/geospatial/geolibre.ipynb)

# Cloud-Native GIS with GeoLibre

## Introduction

## Learning Objectives

## Environment Setup

```{code-cell} ipython3
# %pip install geolibre
```

```{code-cell} ipython3
from geolibre import Map
```

## Creating a Map

```{code-cell} ipython3
m = Map(center=(-100, 40), zoom=4, height="700px")
m
```

```{code-cell} ipython3
m.add_basemap("dark")
m.set_center(-122.4, 37.77, zoom=10)
```

### Map Options

```{code-cell} ipython3
m = Map(
    center=(-83.92, 35.96),
    zoom=12,
    basemap="liberty",
    height="700px",
    layout="embed",  # "embed", "full", or "maponly"
    theme="light",
)
m
```

## Adding Vector Data

```{code-cell} ipython3
url = (
    "https://github.com/opengeos/datasets/releases/download/world/world_cities.geojson"
)
m = Map(center=(0, 20), zoom=2, height="700px")
m.add_geojson(url, name="World Cities", circleRadius=4, fillColor="#ef4444")
m
```

```{code-cell} ipython3
m.add_vector(
    "https://github.com/opengeos/datasets/releases/download/us/us_states.parquet",
    name="US States",
    fillOpacity=0.2,
)
```

### Points from a CSV

```{code-cell} ipython3
m = Map(center=(-100, 40), zoom=3, height="700px")
m.add_csv(
    "https://github.com/opengeos/datasets/releases/download/world/world_cities.csv",
    x="longitude",
    y="latitude",
    name="Cities",
)
m
```

### Marker Clusters and Heatmaps

```{code-cell} ipython3
m = Map(center=(-100, 40), zoom=3, height="700px")
m.add_marker_cluster(
    "https://github.com/opengeos/datasets/releases/download/world/world_cities.geojson",
    name="City Clusters",
)
m
```

```{code-cell} ipython3
m = Map(center=(-100, 40), zoom=3, height="700px")
m.add_heatmap(
    "https://github.com/opengeos/datasets/releases/download/world/world_cities.geojson",
    name="City Density",
    radius=30,
)
m
```

## Data-Driven Symbology

```{code-cell} ipython3
m = Map(center=(-100, 40), zoom=4, height="700px")
m.add_choropleth(
    "https://github.com/opengeos/datasets/releases/download/us/us_counties.geojson",
    column="CENSUSAREA",
    name="County Area",
    colormap="blues",
    scheme="quantile",
    class_count=6,
)
m
```

### Legends and Colorbars

```{code-cell} ipython3
m.add_colorbar(
    colormap="blues",
    vmin=0,
    vmax=5000,
    label="Census Area",
    units="sq mi",
)
```

```{code-cell} ipython3
m = Map(center=(-100, 40), zoom=4, height="700px")
m.add_cog(
    "https://github.com/opengeos/datasets/releases/download/raster/nlcd_2021_land_cover_90m.tif",
    name="NLCD 2021",
)
m.add_legend(builtin="nlcd", title="NLCD Land Cover")
m
```

## Adding Raster Data

```{code-cell} ipython3
m = Map(center=(-119.5, 37.75), zoom=10, height="700px")
m.add_cog(
    "https://github.com/opengeos/datasets/releases/download/raster/dem.tif",
    name="DEM",
    colormap="terrain",
)
m
```

```{code-cell} ipython3
m.add_colorbar(colormap="terrain", vmin=0, vmax=4000, label="Elevation", units="m")
```

### Comparing Two Rasters with a Swipe

```{code-cell} ipython3
m = Map(center=(22.6, 32.75), zoom=12, height="700px")
before = m.add_cog(
    "https://github.com/opengeos/datasets/releases/download/raster/Libya-2023-07-01.tif",
    name="Before",
)
after = m.add_cog(
    "https://github.com/opengeos/datasets/releases/download/raster/Libya-2023-09-13.tif",
    name="After",
)
m.split_map(before, after)
m
```

## 3D Visualization

```{code-cell} ipython3
m = Map(center=(-74.0, 40.72), zoom=15, basemap="dark", height="700px")
m.add_geojson(
    "https://github.com/opengeos/datasets/releases/download/places/nyc_buildings.geojson",
    name="NYC Buildings",
    extrusionEnabled=True,
    extrusionHeightProperty="height_avg",
    extrusionColor="#f59e0b",
)
m.set_pitch(60)
m.set_bearing(-20)
m
```

## Managing Layers

```{code-cell} ipython3
m.layer_names
```

```{code-cell} ipython3
buildings = m.find_layer("NYC Buildings")
buildings.opacity = 0.7
buildings.set_style(extrusionColor="#22d3ee")
```

```{code-cell} ipython3
buildings.column("height_avg")[:10]
```

## Two-Way Sync

```{code-cell} ipython3
project = m.to_project()
print("center:", project["mapView"]["center"])
print("zoom:", round(project["mapView"]["zoom"], 2))
print("layers:", [layer["name"] for layer in project["layers"]])
```

```{code-cell} ipython3
m.describe()
```

## Saving and Reloading a Project

```{code-cell} ipython3
m.save_project("my-map.geolibre.json")
```

```{code-cell} ipython3
m2 = Map(height="700px")
m2.load_project("my-map.geolibre.json")
m2
```

## Geoprocessing in the Browser

```{code-cell} ipython3
m = Map(center=(-119.5, 37.75), zoom=10, height="700px")
m
```

```{code-cell} ipython3
tools = m.list_whitebox_tools()
len(tools)
```

```{code-cell} ipython3
dem = m.get_layer(
    m.add_raster(
        "https://github.com/opengeos/datasets/releases/download/raster/dem.tif",
        name="DEM",
    )
)
result = m.run_whitebox_tool("slope", {"input": dem, "units": "degrees"})
result["resultLayerIds"]
```

## Key Takeaways

## Exercises

### Exercise 1: Building a Map from Vector Data

### Exercise 2: Choropleth Symbology and Legends

### Exercise 3: Raster Layers and Swipe Comparison

### Exercise 4: 3D Building Extrusions

### Exercise 5: Saving and Sharing a Project
