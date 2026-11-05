# Final Project Guidelines

The final project is where you stop following tutorials and use what you have
learned on a real geospatial problem you choose yourself. It is an
**individual project** worth **150 points, or 15% of your course grade**. It
also replaces a final exam: GEOG 312 has no exam during finals week.

| Component | Points |
|---|---|
| Project notebook (your written report) | 100 |
| Presentation | 50 |
| **Total** | **150** |

You are encouraged to talk ideas and approaches over with classmates and with
me. The analysis and the code you submit must be your own. Use online and
library resources freely to shape the project, and cite everything you use.

## Timeline

| Date | Milestone |
|---|---|
| Fri, Nov 13 | One-page project proposal due on Canvas |
| Nov 16 to Dec 3 | Project work; bring questions to class and office hours |
| **Fri, Dec 4, 11:59 p.m.** | Project notebook and recorded presentation due on Canvas |

[Canvas](https://utk.instructure.com) has the exact submission links, and it
wins if anything here disagrees with it.

## Choosing a Topic

A good project asks a specific question about a specific place, and answers it
with data you can actually get. "Climate change" is a topic. "Which census
tracts in Knox County gained the most impervious surface between 2016 and 2021,
and do they overlap with FEMA flood zones?" is a project.

When you pick a topic, check three things:

1. **The data exists and you can load it.** Before you commit, open the dataset
   in a notebook. Many projects die because the data turned out to be
   paywalled, too large, or only available as a PDF.
2. **The scope fits about three weeks.** One clear question, one study area,
   and one or two datasets you combine is plenty. You can always add a second
   question if the first one goes quickly.
3. **The analysis uses the course tools.** The project should show real GIS
   programming: reading and cleaning spatial data, analysis such as joins,
   overlays, zonal statistics, terrain or time series, and maps. A notebook that
   only displays one dataset on a web map is not enough.

Some directions that fit the course well:

- **Urban:** access to parks, grocery stores, or transit by neighborhood; urban
  heat islands from Landsat surface temperature; building footprints and
  population density.
- **Hydrology and hazards:** watershed delineation and flow paths with
  WhiteboxTools; flood exposure of roads or buildings; wildfire burn severity
  from Sentinel-2.
- **Land cover change:** forest loss, urban growth, or surface water change over
  time with Earth Engine and geemap, or with time series in Xarray.
- **Environment and health:** air quality monitors joined to census
  demographics; drought indices over farmland; species occurrences against
  protected areas.
- **Tools:** a small, reusable Solara dashboard or Python package that solves a
  real workflow problem, documented with a worked example.

### Where to Find Data

- [Earth Engine Data Catalog](https://developers.google.com/earth-engine/datasets)
  and the community
  [awesome-gee-community-catalog](https://gee-community-catalog.org)
- [Microsoft Planetary Computer](https://planetarycomputer.microsoft.com/catalog)
  and other STAC catalogs, which leafmap can search directly
- [Source Cooperative](https://source.coop) and
  [Overture Maps](https://overturemaps.org) for cloud-native GeoParquet,
  readable with DuckDB
- [US Census Bureau TIGER/Line and ACS data](https://www.census.gov/data.html)
- [USGS The National Map](https://apps.nationalmap.gov/downloader/) for
  elevation, hydrography, and land cover
- [Natural Earth](https://www.naturalearthdata.com) for base layers
- City, county, and state open data portals, such as the
  [Tennessee GIS portal](https://tnmap.tn.gov)

## Project Proposal (Due Nov 13)

Submit a one-page proposal on Canvas. The proposal is **required but will not
be graded**; it earns no points. I use it to catch topics that are too broad or
data that will not work before you have spent two weeks on them. Include:

1. **Title** and a one-sentence research question.
2. **Study area** and time period.
3. **Data:** each dataset you plan to use and a link to it. Say whether you have
   already loaded it successfully.
4. **Methods:** the main analysis steps and the libraries you expect to use.
5. **Expected outputs:** the maps, charts, or tool you plan to produce.
6. **Risks:** what is most likely to go wrong, and your fallback if it does.

I will reply with feedback within a week. If I suggest narrowing the scope,
please take that seriously.

## The Project Notebook (100 Points)

Your report is a single Jupyter notebook. Write it for a reader who knows some
GIS but has never seen your project: Markdown cells explain what you are doing
and why, and code cells show how. There is no separate written report. Start
from the [project notebook template](template.md), which already has the
sections below.

### 1. Problem Statement

- State the real-world problem and your research question clearly and briefly.
- Explain why the problem matters and who would care about the answer.
- Explain what a spatial, programmatic approach adds that a table or a single
  map would not.

### 2. Data

For each dataset, describe:

- **Source:** a link or citation, and the date you accessed it.
- **Metadata:** format, attributes you use, coordinate reference system,
  spatial and temporal resolution or scale, and extent.
- **Preparation:** every preprocessing step, such as cleaning, filtering,
  reprojecting, clipping, merging, or resampling, and why you needed it.

### 3. Analysis

- Describe the spatial analysis and visualization techniques you used, and
  justify why you chose them over the alternatives.
- Document the process step by step, including key geoprocessing tasks,
  algorithms, and tools.
- Keep code readable: meaningful variable names, functions for anything you
  repeat, and comments on the steps that are not obvious.

### 4. Results and Discussion

- Present results with effective visuals: maps with legends and titles,
  charts with labeled axes and units, and tables where exact values matter.
- Interpret every figure. Say what it shows and how it answers your research
  question.
- Discuss limitations, such as data quality, resolution, or assumptions, and
  what you would do next with more time.

### 5. References

List the data sources, papers, documentation, and code you drew on. Cite code
you adapted in a comment next to it as well.

### Reproducibility Requirements

A notebook I cannot run is a notebook I cannot fully grade. Before you submit:

- **Install cell first.** Put every `pip install` your notebook needs in the
  first code cell, so it runs in a fresh Google Colab session.
- **No local file paths.** Load data from URLs, Earth Engine, or cloud storage.
  If a file only exists on your computer, upload it somewhere public (a GitHub
  repository or a public Google Drive link) and download it in the notebook.
- **Keep it reasonable.** The whole notebook should run in about 15 minutes in
  Colab. If an analysis step is slow, run it once, save the result, and load the
  saved file, explaining in a Markdown cell what you did.
- **Restart and run all.** Click **Runtime → Restart and run all** and make sure
  every cell runs top to bottom with its outputs showing.
- **Secrets stay out.** Never paste API keys or passwords into the notebook. Use
  Colab Secrets or environment variables instead.
- **AI disclosure.** If you used an AI coding assistant, say which tool and what
  you used it for in the disclosure cell at the top of the template. The
  [AI policy in the syllabus](../about/syllabus.md) applies: you must be able to
  explain every line you submit.

## The Presentation (50 Points)

There are no presentations in class. Instead, record a video presentation of
**about 10 minutes** and upload it to Canvas. Cover:

1. The problem and your research question
2. An overview of your data and methods
3. Key results and what they mean, with your best maps front and center
4. Challenges you ran into, how you handled them, and what you learned

Record your screen with your voice, and your face if you like. Present from
slides, from the notebook, or both; a short demo of an interactive map works
well on video. Zoom, PowerPoint's built-in recorder, and
[OBS Studio](https://obsproject.com) all work, and so does any other tool that
produces a common video file such as MP4.

Before you upload, watch the recording once all the way through. Check that the
audio is clear and that the text and maps on screen are readable.

## How to Submit

Submit the following on Canvas by **11:59 p.m. on Friday, December 4**:

1. **Notebook link.** A link to your notebook in Google Colab, shared as
   **Anyone with the link**. Paste it into a Chrome Incognito window first to
   confirm it opens. The [lab submission instructions](../labs/instructions.md)
   walk through the sharing steps. You may instead submit the `.ipynb` file, or a
   link to a public GitHub repository that contains it.
2. **Recorded presentation.** Upload the video file to Canvas. If the file is
   too large to upload, put it on YouTube (unlisted is fine) or Google Drive
   and submit the link, checking that it opens in an Incognito window.

If something will stop you from submitting on time, contact me **before** the
deadline. Course grades are due shortly after December 4, so there is very
little room for late work.

## Grading Rubric

| Criterion | Points | What earns full credit |
|---|---|---|
| Problem statement | 20 | A clear, specific question; a convincing case for why it matters and why a spatial approach fits |
| Data | 20 | Every dataset sourced and cited; CRS, resolution, and attributes described; every preparation step explained |
| Analysis | 40 | Appropriate, well-justified methods that go beyond displaying data; clean, commented code; the notebook runs top to bottom in a fresh Colab session |
| Results and visualization | 20 | Clear, well-labeled maps and charts; interpretation tied back to the question; honest discussion of limitations |
| Presentation | 50 | Covers all four points above in about 10 minutes; well organized; results explained clearly to a general GIS audience; clear audio and readable visuals |
| **Total** | **150** | |

The notebook criteria add up to 100 points and the presentation to 50.

## Tips

- **Start early.** Finding a topic, getting the data to load, and debugging take
  longer than the analysis. Aim to have every dataset loading by
  the time you submit your proposal on November 13.
- **Get something working first.** Build a rough version of the whole pipeline,
  from data to a map, before polishing any one step.
- **Document as you go.** Writing the Markdown cells at the end is much harder
  than writing them while you still remember why you made each choice.
- **Make the maps count.** Maps and figures are how people will judge your
  work. Choose sensible color schemes, and add legends, titles, and units.
- **Rehearse before recording.** Time yourself once. Most first runs of a
  10-minute talk take 15.
- **Ask for help.** Post questions on the
  [GitHub Discussion board](https://github.com/giswqs/gispro-fall26/discussions)
  or come to office hours. Helping classmates there also counts toward extra
  credit.

Good luck. I am looking forward to seeing what you build.
