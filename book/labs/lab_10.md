---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.16.2
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Lab 10

[![image](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/giswqs/gispro-fall26/blob/main/book/labs/lab_10.ipynb)
[![image](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/giswqs/gispro-fall26/main?urlpath=lab/tree/book/labs/lab_10.ipynb)

## Overview

This lab introduces you to [GeoLibre](https://geolibre.app), a free and open-source cloud-native GIS platform that runs in the browser, on the desktop, and inside Jupyter notebooks. You will use the `geolibre` Python package, which embeds the complete GeoLibre app in a notebook cell and gives you a leafmap-style Python API for driving it.

What makes GeoLibre different from the mapping libraries you have used so far is that state syncs **both ways**. Data you add from Python appears in the app UI, and edits you make in the UI — panning, zooming, toggling layers, restyling — are readable back from Python. The whole map is a single `.geolibre.json` project file that is interchangeable between the notebook, the web app, and the desktop app.

---

## Objectives

By completing this lab, you will be able to:

1. Create and configure a GeoLibre map in a Jupyter notebook and control its camera from Python.
2. Add vector data from several sources and formats, including GeoJSON, CSV, and GeoParquet.
3. Apply data-driven symbology and annotate a map with legends and colorbars.
4. Add raster layers and compare two of them with a swipe control.
5. Build a 3D visualization using building-footprint extrusions.
6. Read live map state back from the UI and save a project for sharing.

```{code-cell} ipython3
# %pip install geolibre
```

## Exercise 1: Creating Your First GeoLibre Map

   - Create a map centered on a city of your choice with an appropriate zoom level, using the `liberty` basemap and a height of `700px`. Display the map.
   - In a second cell, switch the basemap to `dark` and move the view to a different city using `set_center()`. Re-run and confirm the displayed map above updates in place without being recreated.
   - Print the list of available basemap names using `geolibre.basemap_catalog()`.

```{code-cell} ipython3

```

## Exercise 2: Adding Vector Data

Create a new map and add each of the following layers with an appropriate name and style:

   - **GeoJSON from a URL**: world cities as red circles.
     - https://github.com/opengeos/datasets/releases/download/world/world_cities.geojson
   - **CSV point data**: the same cities from a CSV, using `add_csv()` with the `longitude` and `latitude` columns.
     - https://github.com/opengeos/datasets/releases/download/world/world_cities.csv
   - **GeoParquet**: US states, drawn with a semi-transparent fill so the cities stay visible.
     - https://github.com/opengeos/datasets/releases/download/us/us_states.parquet

Then frame the continental US using `set_center()` and `set_zoom()`. (GeoLibre also has
`zoom_to_layer()`, but it asks the live widget for the layer's extent, so it only works
while the map is displayed and connected.)

```{code-cell} ipython3

```

## Exercise 3: Marker Clusters and Heatmaps

   - Create a map and add the world cities dataset as a **marker cluster**. Experiment with the `cluster_radius` and `cluster_max_zoom` parameters and describe in a Markdown cell what each one changes.
   - Create a second map and add the same dataset as a **heatmap**. Adjust `radius` and `intensity` until the population centers read clearly at a continental zoom level.

```{code-cell} ipython3

```

## Exercise 4: Choropleth Symbology and Legends

   - Create a map and add the US counties dataset as a **choropleth** using `add_choropleth()`, classified on the `CENSUSAREA` column.
     - https://github.com/opengeos/datasets/releases/download/us/us_counties.geojson
   - Use a `quantile` classification with 6 classes and a color ramp of your choice. Then create the same map with an `equal-interval` classification and, in a Markdown cell, explain why the two maps look so different for this variable.
   - Add a colorbar with a meaningful label and units.

```{code-cell} ipython3

```

## Exercise 5: Raster Layers and Swipe Comparison

   - **Thematic raster**: Create a map and add the NLCD 2021 land cover raster with the built-in `nlcd` legend.
     - https://github.com/opengeos/datasets/releases/download/raster/nlcd_2021_land_cover_90m.tif
   - **DEM**: Create a map and add the DEM below with the `terrain` colormap and an elevation colorbar.
     - https://github.com/opengeos/datasets/releases/download/raster/dem.tif
   - **Swipe comparison**: Create a map centered on Derna, Libya, add the two images below, and connect them with `split_map()` so the slider compares before and after the September 2023 flood.
     - Before: https://github.com/opengeos/datasets/releases/download/raster/Libya-2023-07-01.tif
     - After: https://github.com/opengeos/datasets/releases/download/raster/Libya-2023-09-13.tif

```{code-cell} ipython3

```

## Exercise 6: 3D Building Extrusions

   - Create a map centered on lower Manhattan with the `dark` basemap and add the NYC buildings dataset below.
     - https://github.com/opengeos/datasets/releases/download/places/nyc_buildings.geojson
   - Enable extrusion and drive the building heights from the `height_avg` property. Set the pitch and bearing so the 3D effect is clearly visible.
   - Retrieve the layer with `find_layer()` and use the layer handle to lower its opacity and change the extrusion color.

```{code-cell} ipython3

```

## Exercise 7: Reading State Back from the UI

   - Using the 3D map from Exercise 6, **pan and zoom the map in the UI**, toggle a layer, then run a cell that calls `to_project()` and prints the live center, zoom, and layer names. Run this cell by hand after you have moved the map; a plain **Restart and run all** executes it before you have touched anything and will just report the values you set in code.
   - Call `describe()` and print the summary. In a Markdown cell, note the feature count reported for the buildings layer.
   - Use `column()` on the buildings layer handle to pull the `height_avg` values, then report the minimum, maximum, and mean building height. You may use NumPy for this.

```{code-cell} ipython3

```

## Exercise 8: Saving and Sharing a Project

   - Save your Exercise 6 map to `lab10.geolibre.json` with `save_project()`.
   - Create a new, empty `Map` and load that file with `load_project()`. Display it and confirm it matches the map you saved.
   - Open <https://web.geolibre.app> in a browser tab, load the same `.geolibre.json` file from the app's **File** menu, and confirm the project opens there too. Describe what you see in a Markdown cell.

```{code-cell} ipython3

```

## Exercise 9: Geoprocessing in the Browser (Bonus, 10 points)

GeoLibre ships more than 1,000 Whitebox geoprocessing tools that run entirely in the browser through WebAssembly. These exercises drive the live widget, so **the map must be displayed and finished loading before the tool call runs**. Put the `Map` in one cell, display it, wait for it to render, then run the tool in the next cell.

   - Create a map, display it, and print how many tools `list_whitebox_tools()` reports.
   - Add the DEM from Exercise 5 as a raster layer, then run the `slope` tool against it with `units` set to `degrees`.
   - Add the resulting slope layer to the map with an appropriate colormap and colorbar.

```{code-cell} ipython3

```
