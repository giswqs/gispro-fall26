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

# Final Project Template

[![image](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/giswqs/gispro-fall26/blob/main/book/project/template.ipynb)

Open this notebook in Colab, save a copy to your Drive, and replace the
instructions in each section with your own work. Delete the instruction text
before you submit. See the [final project guidelines](final-project.md) for what
each section needs and how it is graded.

---

**Title:** _Your project title_

**Author:** _Your name_

**Course:** GEOG 312, Fall 2026

**AI disclosure:** _Name any AI coding assistant you used and what you used it
for, or write "None."_

+++

## Setup

Install every package your notebook needs here, so it runs in a fresh Colab
session. Then import everything in one place.

```{code-cell} ipython3
# %pip install -q leafmap geopandas
```

```{code-cell} ipython3
import geopandas as gpd
import leafmap
```

+++

## 1. Problem Statement

_State the real-world problem and your research question. Explain why it
matters, who would care about the answer, and what a spatial, programmatic
approach adds._

+++

## 2. Data

_For each dataset, give the source (link and access date), the format, the
attributes you use, the coordinate reference system, the spatial and temporal
resolution, and the extent. Load data from URLs or cloud services, not local
paths._

```{code-cell} ipython3
# data_url = "https://..."
# gdf = gpd.read_file(data_url)
# gdf.head()
```

### Data Preparation

_Describe and run each preprocessing step: cleaning, filtering, reprojecting,
clipping, merging, or resampling. Say why each step is needed._

```{code-cell} ipython3

```

+++

## 3. Analysis

_Explain each analysis step before the code that runs it, and justify your
choice of method. Use functions for anything you repeat. Add as many
subsections as you need._

```{code-cell} ipython3

```

+++

## 4. Results and Discussion

_Show your maps, charts, and tables. After each figure, explain what it shows
and how it answers your research question. End with the limitations of your
analysis and what you would do next._

```{code-cell} ipython3
# m = leafmap.Map()
# m.add_gdf(gdf, layer_name="Study area")
# m
```

+++

## 5. Conclusion

_Summarize your answer to the research question in a short paragraph._

+++

## References

_List the data sources, papers, documentation, and code you used._

1. _Author or organization (Year). Title. URL. Accessed Month Day, Year._
