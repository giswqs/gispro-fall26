# Lab Submission Instructions

There are ten lab assignments in GEOG 312, each worth 60 points, together making
up 60% of your grade. Labs are posted here as they are assigned. See the
[schedule](../about/schedule.md) for which lab goes with which week.

## Due Dates and Late Work

Each lab is assigned in the week shown on the schedule and is **due the
following week**. The exact date and time for each lab are posted on
[Canvas](https://utk.instructure.com), which is the authority if anything here
disagrees. Late labs lose **10% per day**.

It is your responsibility to make sure the correct file is submitted before the
deadline. Once an assignment has been graded, additional files will not be
accepted. If you think a lab was graded incorrectly, tell me within one week of
the grade being posted.

## How to Submit

The video below walks through the whole process end to end. The written steps
that follow say the same thing.

```{iframe} https://www.youtube.com/embed/f9Sh8XYrP2Y
:width: 100%
:label: lab-submission-video

How to submit lab assignments through Google Colab
```

1. Click the **Open in Colab** badge at the top of the lab notebook. This opens
   the lab in Google Colab.

2. Save a copy to your Google Drive. It lands in **My Drive → Colab Notebooks →
   Copy of lab_x.ipynb**. Rename it back to **lab_x.ipynb**.

   ![Saving a copy of the notebook to Google Drive from the Colab File menu](https://i.imgur.com/1bxdiTz.png)

3. Follow the directions in the notebook and write code to complete the
   exercises.

4. When you are finished, click **Runtime → Restart and run all**. Make sure the
   notebook runs cleanly from top to bottom and that every code cell shows its
   output. A notebook that only works out of order will not be graded as
   working.

   ![The Restart and run all command in the Colab Runtime menu](https://i.imgur.com/6juNLRG.png)

5. Click **Share** in the top right corner and change general access from
   Restricted to **Anyone with the link**.

   ![Changing Colab general access from Restricted to Anyone with the link](https://i.imgur.com/FmNZSdx.png)

6. Click **Copy link**.

   ![The Copy link button in the Colab share dialog](https://i.imgur.com/3v1DNoj.png)

7. Open a Chrome Incognito window, paste the link, and confirm you can see the
   notebook content. If you cannot, your grader cannot either. Fix the sharing
   setting before you submit.

8. Paste the link into the Lab Submission page on
   [Canvas](https://utk.instructure.com) and submit.

If you prefer to work locally in VS Code or JupyterLab rather than in Colab,
that is fine. Upload the finished `.ipynb` to your Drive and share it the same
way, or submit the `.ipynb` file directly to Canvas.

## Collaboration and AI Assistants

You are encouraged to talk with each other about approaches and to help each
other debug. Helping a classmate find a bug is a good thing to do. Copying a
classmate's solution, or handing yours over to be copied, is plagiarism.

AI coding assistants are permitted on labs, provided that you can explain every
line you submit and that you disclose the tool in a short note at the top of the
notebook. They are not permitted on quizzes or the midterm. See the
[syllabus](../about/syllabus.md) for the full policy.

Reusing code you find online or in the documentation is fine and normal. Cite it
in a comment.

## Getting Unstuck

Post on the
[GitHub Discussion board](https://github.com/giswqs/gispro-fall26/discussions).
Include the error message and the code that produced it. Someone else has
almost certainly hit the same wall, and up to 30 extra credit points are
reserved for students who help answer classmates' questions.

## Labs

- [Lab 1](lab_01.md) — Variables, Data Types, and Data Structures
- [Lab 2](lab_02.md) — String Operations and Looping
- [Lab 3](lab_03.md) — Functions, Classes, Files, and Exception Handling
- [Lab 4](lab_04.md) — NumPy, Pandas, and GeoPandas
- [Lab 5](lab_05.md) — Raster Data with Rasterio
- [Lab 6](lab_06.md) — Xarray and Rioxarray
- [Lab 7](lab_07.md) — Interactive Mapping with Leafmap
- [Lab 8](lab_08.md) — 3D Mapping with MapLibre
- [Lab 9](lab_09.md) — Earth Engine and geemap
- [Lab 10](lab_10.md) — Cloud-Native GIS with GeoLibre
