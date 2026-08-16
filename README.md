# GEOG 312: Introduction to GIS Programming

**Fall 2026 · University of Tennessee, Knoxville**

Course website: <https://gispro-fall26.gishub.org>

[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/giswqs/gispro-fall26/blob/main)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/giswqs/gispro-fall26/HEAD)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

This repository holds the lecture notebooks, lab assignments, syllabus, and
schedule for GEOG 312, an introduction to GIS programming with Python taught by
[Dr. Qiusheng Wu](https://gishub.org) in the Department of Geography and
Sustainability. No prior programming experience is assumed.

Everything here is public. You are welcome to work through the material even if
you are not enrolled at UT.

## Quick Links

| | |
|---|---|
| Course website | <https://gispro-fall26.gishub.org> |
| Syllabus | <https://gispro-fall26.gishub.org/book/about/syllabus> |
| Syllabus (PDF) | [Google Drive](https://drive.google.com/file/d/1-6kP86o-0i62JV5HAAhpTRe9Mo-J6RXX/view?usp=sharing) |
| Schedule | <https://gispro-fall26.gishub.org/book/about/schedule> |
| Labs | <https://gispro-fall26.gishub.org/book/labs/instructions> |
| Q&A | <https://github.com/giswqs/gispro-fall26/discussions> |
| Canvas (enrolled students) | <https://utk.instructure.com> |

## Meeting Times

Tuesdays and Thursdays, 12:55 to 2:10 p.m., Burchfiel Geography Building (BGB)
206, August 17 to December 1, 2026.

## Textbook

> Wu, Q. (2025). _Introduction to GIS Programming: A Practical Python Guide to
> Open Source Geospatial Tools_. Independently published.
> ISBN 979-8286979455 (print), 979-8993859712 (PDF).
> <https://amazon.com/dp/B0FFW34LL3>

The book's own repository, with all of its code examples, is at
[giswqs/intro-gispro](https://github.com/giswqs/intro-gispro). Its website is
<https://gispro.gishub.org>.

## Repository Layout

```
book/
  about/       Syllabus, schedule, textbook, and instructor pages
  software/    Software setup chapters
  python/      Python programming fundamentals
  geospatial/  Geospatial programming chapters
  labs/        Lab assignments and submission instructions
myst.yml       Site configuration and table of contents
```

Chapter pages are paired `.md` and `.ipynb` files managed with
[jupytext](https://jupytext.readthedocs.io). Edit the `.md` file; the notebook
is what Colab and Binder open.

## Building the Site Locally

```bash
npm install -g mystmd
myst start
```

The site deploys automatically to GitHub Pages and Netlify on every push to
`main`.

## Previous Offerings

The Fall 2024 offering is archived at <https://geog-312.gishub.org>
([giswqs/geog-312](https://github.com/giswqs/geog-312)), along with its lecture
recordings.

## License

Course materials are released under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The text and figures
of the printed textbook remain copyrighted by the author and are not reproduced
in this repository.
