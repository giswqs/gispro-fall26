# Introduction to GIS Programming

**Fall 2026 · Department of Geography and Sustainability · University of Tennessee**

[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/giswqs/gispro-fall26/blob/main)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/giswqs/gispro-fall26/HEAD)
[![Docker](https://img.shields.io/badge/docker-giswqs%2Fpygis%3Abook-blue?logo=docker)](https://hub.docker.com/r/giswqs/pygis/tags)

This is the course website for GEOG 312. It holds the lecture notebooks, lab
assignments, syllabus, and schedule for the Fall 2026 offering. Everything here
is public, so you are welcome to work through it even if you are not enrolled.

## Course at a Glance

| | |
|---|---|
| **Meetings** | Tuesdays and Thursdays, 12:55 to 2:10 p.m. |
| **Location** | Burchfiel Geography Building (BGB) 206 |
| **Term** | August 17 to December 1, 2026 |
| **Credit** | 3 hours, letter graded |
| **Instructor** | [Dr. Qiusheng Wu](book/about/instructor.md), BGB 309 |
| **Office hours** | Wednesdays and Thursdays, 8:00 to 9:00 a.m., and by appointment |
| **Email** | <qwu18@utk.edu> |

Start with the [syllabus](book/about/syllabus.md), also available as a
[PDF](https://drive.google.com/file/d/1-6kP86o-0i62JV5HAAhpTRe9Mo-J6RXX/view?usp=sharing),
and the [weekly schedule](book/about/schedule.md).

## What You Will Learn

GEOG 312 is a programming course taught through geography. No prior programming
experience is assumed. The first half of the semester covers Python itself. The
second half applies it to real geospatial data using the open source tools that
working analysts and researchers actually use.

By the end of the semester you will be able to:

- Write, debug, and document Python programs using variables, data structures,
  control flow, functions, and classes.
- Read, write, and convert common geospatial formats such as Shapefile, GeoJSON,
  GeoParquet, GeoTIFF, Cloud Optimized GeoTIFF, and NetCDF.
- Perform vector and raster analysis, including spatial joins, reprojection,
  clipping, zonal statistics, and terrain analysis.
- Build interactive 2D and 3D web maps and publish them as reproducible
  notebooks or dashboards.
- Access and analyze cloud hosted geospatial datasets.

## Course Materials

| Section | What is in it |
|---|---|
| [Course Information](book/about/syllabus.md) | Syllabus, schedule, textbook, instructor |
| [Software Setup](book/software/overview.md) | Installing Python, VS Code, Git, Colab, JupyterLab, Docker |
| [Python Programming Fundamentals](book/python/variables.md) | Variables, data structures, strings, loops, functions, files, NumPy and Pandas |
| [Geospatial Programming with Python](book/geospatial/get-started.md) | GeoPandas, Rasterio, Xarray, Leafmap, WhiteboxTools, MapLibre, geemap, HyperCoast, DuckDB, GDAL, Solara, Sedona |
| [Labs](book/labs/instructions.md) | Ten lab assignments and how to submit them |

## Textbook

The required textbook is
[_Introduction to GIS Programming: A Practical Python Guide to Open Source Geospatial Tools_](book/about/textbook.md)
by Qiusheng Wu (2025). Every code example from the book is free and runs in your
browser, so you can follow along from day one while you sort out where to buy a
copy. See the [textbook page](book/about/textbook.md) for print, PDF, and EPUB
options, and for the companion video tutorials.

## Running the Code

Every chapter page has **Open in Colab** and **Binder** badges at the top. Click
either one and you are running the notebook in a few seconds with nothing
installed. That is the fastest way to start, and it is a perfectly good fallback
all semester if your laptop gives you trouble.

We will also set up a local environment together in Week 1, because being able
to run code on your own machine matters once your projects outgrow a browser
tab. See [Software Setup](book/software/overview.md).

If you prefer Docker:

```bash
docker pull giswqs/pygis:book
docker run -it -p 8888:8888 -v $(pwd):/app/workspace giswqs/pygis:book
```

## Getting Help

- **Technical questions** belong on the
  [GitHub Discussion board](https://github.com/giswqs/gispro-fall26/discussions).
  Installation problems, error messages, and "why does my code do this" are all
  fair game, and posting there means everyone benefits from the answer. Up to 30
  extra credit points are reserved for students who help answer classmates'
  questions.
- **Private matters** such as grades, accommodations, or family circumstances go
  to <qwu18@utk.edu> with "GEOG-312" in the subject line.
- **Announcements, submissions, and grades** live on
  [Canvas](https://utk.instructure.com).
- **Office hours** are Wednesdays and Thursdays, 8:00 to 9:00 a.m. in BGB 309.
  You do not need a reason to come, though bringing broken code is a perfectly
  good one.

## License

Course materials in this repository are released under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The text and figures
of the printed textbook are copyrighted by the author and are not reproduced
here. See the [textbook page](book/about/textbook.md) for details.
