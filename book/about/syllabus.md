# Syllabus

**GEOG 312: Introduction to GIS Programming**
Fall 2026 · 3 Credit Hours · Letter Graded
Department of Geography and Sustainability · University of Tennessee, Knoxville

📄 **[Download the syllabus as a PDF](https://drive.google.com/file/d/1-6kP86o-0i62JV5HAAhpTRe9Mo-J6RXX/view?usp=sharing)**

The PDF is the version of record and is also posted on Canvas. This page mirrors
it; if the two ever disagree, the PDF on Canvas wins.

## Course and Instructor

| Course | Instructor |
|---|---|
| **Meetings:** Tuesdays and Thursdays, 12:55 to 2:10 p.m. | **Name:** Dr. Qiusheng Wu |
| **Location:** Burchfiel Geography Building (BGB) 206 | **Office:** BGB 309 |
| **Credit:** 3 hours, letter graded | **Email:** <qwu18@utk.edu> |
| **Term:** August 17 to December 1, 2026 | **Website:** <https://gishub.org> |
| **Course site:** <https://gispro-fall26.gishub.org> | **Office hours:** Wednesdays and Thursdays, 8:00 to 9:00 a.m., and by appointment |
| **Canvas:** <https://utk.instructure.com> | **Response time:** Within one business day |
| **Q&A:** [GitHub Discussions](https://github.com/giswqs/gispro-fall26/discussions) | **Department:** BGB 304 · <https://geography.utk.edu> |

## Course Description

An in-depth introduction to GIS programming with Python. Students learn to use
open source Python libraries to read, process, analyze, and visualize geospatial
data, starting from programming fundamentals and progressing through vector and
raster analysis, interactive and 3D web mapping, cloud-based geospatial
computing, and reproducible workflows. No prior programming experience is
assumed. (3 credit hours)

## Course Purpose

GEOG 312 is a programming course taught through geography. You will spend the
first half of the semester learning Python itself and the second half applying
it to real geospatial data with the open source tools that working geospatial
analysts and researchers actually use. Nearly every meeting involves writing
code in class. The course aims to:

1. Build a working command of Python from the ground up: variables, data
   structures, strings, control flow, functions and classes, file handling,
   exception handling, NumPy, and Pandas.
2. Give you practical fluency with the open source geospatial Python stack
   (GeoPandas, Rasterio, Xarray, Leafmap, MapLibre, WhiteboxTools, geemap, and
   DuckDB) so that you can pick the right tool for a problem instead of the only
   one you know.
3. Move you from following tutorials to solving your own problems, through
   weekly labs and a final project of your own design that you present to the
   class.

## Student Learning Outcomes

By the end of the semester, you will be able to:

- Write, debug, and document Python programs that use variables, data
  structures, control flow, functions, and classes.
- Read, write, and convert common geospatial data formats (Shapefile, GeoJSON,
  GeoParquet, GeoTIFF, Cloud Optimized GeoTIFF, and NetCDF) using GeoPandas,
  Rasterio, Xarray, and GDAL/OGR.
- Perform vector and raster analysis in Python, including spatial joins,
  reprojection, clipping, zonal statistics, and terrain analysis with
  WhiteboxTools.
- Build interactive 2D and 3D web maps with Leafmap and MapLibre, and publish
  them as reproducible notebooks or dashboards.
- Access and analyze cloud-hosted geospatial datasets using Earth Engine,
  geemap, and DuckDB.
- Use virtual environments, version control, and exception handling to produce
  code that other people can run and that fails gracefully when data is missing
  or malformed.
- Independently research, evaluate, and apply an unfamiliar geospatial Python
  library to a problem of your own choosing, and communicate the result.

## Materials and Preparation

### Required Textbook

> Wu, Q. (2025). _Introduction to GIS Programming: A Practical Python Guide to
> Open Source Geospatial Tools_. Independently published.
> ISBN 979-8286979455 (print), 979-8993859712 (PDF).

See the [textbook page](textbook.md) for print, PDF, and EPUB options, the free
code examples, and the companion video tutorials.

### Course Websites

- **Course site:** <https://gispro-fall26.gishub.org> for the syllabus,
  schedule, lecture notebooks, lab assignments, and video recordings.
- **Canvas:** <https://utk.instructure.com> for announcements, lab submissions,
  quizzes, and grades.
- **GitHub Discussions:**
  <https://github.com/giswqs/gispro-fall26/discussions> for all technical
  questions and answers, plus the course source code.

### Software and Hardware

- Bring a laptop to every meeting. This is a hands-on class and you will be
  typing code during class time. If you do not have a laptop you can use, tell
  me in the first week and we will arrange one.
- You will install Miniconda (Python 3.12 or newer), Visual Studio Code, and
  Git, and create a free GitHub account. We do this together in Week 1, so do
  not worry if none of that means anything to you yet.
- Everything we use is free and open source and runs on Windows, macOS, and
  Linux. Google Colab is a fully browser-based fallback if your machine gives
  you trouble. QGIS and ArcGIS Pro are useful companions but are not required.

### Weekly Preparation

Read the assigned chapter before the first meeting of the week and run its
notebook. Class time builds on the reading rather than repeating it; the
students who read first are consistently the ones who finish labs in an hour
instead of an evening.

## Course Format

We meet twice a week for 75 minutes. Meetings combine short explanations with
live coding: I write code on the screen, you write it along with me, and it
breaks in interesting ways for both of us. Bring questions about anything that
did not work when you ran the notebooks on your own. Debugging someone else's
error in front of the room is one of the most useful things we do.

Labs are started in class and finished on your own. You are encouraged to talk
with each other about approaches and to help each other debug; the code you
submit must be your own. See Academic Integrity and Use of AI Coding Assistants
below for where that line sits.

## Requirements and Grading

The course is worth 1,000 points, distributed as follows.

| Component | Points | Weight |
|---|---|---|
| 10 lab assignments | 600 | 60% |
| 10 in-class quizzes | 100 | 10% |
| Midterm exam (Thu, Oct 8) | 150 | 15% |
| Final project | 150 | 15% |
| **Total** | **1,000** | **100%** |

### Labs

Ten lab assignments, one roughly every week, each worth 60 points. Labs are
distributed as Jupyter notebooks on the course site and submitted through
Canvas. Each is assigned in the week shown on the [schedule](schedule.md) and is
due the following week; the exact date and time are posted on Canvas. Late labs
lose 10% per day. Once an assignment has been graded, additional files will not
be accepted. See the
[submission instructions](../labs/instructions.md).

### Quizzes

Ten short in-class quizzes, 10 points each, covering the assigned reading and
the previous week's material. Quiz days are announced at least one class in
advance. Quizzes are closed-book and closed-assistant.

### Midterm Exam

One midterm exam on Thursday, October 8, covering software setup and Python
programming fundamentals (the first half of the book). It must be taken on the
scheduled day unless you make arrangements with me beforehand; an unexcused
absence on exam day earns a zero. See the make-up policy below.

### Final Project

An individual project on a geospatial problem of your own choosing, using the
tools from the course. A one-page proposal is due Thursday, November 5. You will
present your work to the class in the final two weeks and submit a notebook and
short written report by Friday, December 4. Projects are graded on technical
execution, reproducibility, and how clearly you explain what you did and why.

### Extra Credit

Up to 30 extra credit points (3% of the total grade) are reserved for students
who actively and helpfully answer other students' questions on the GitHub
Discussion board. Answering a classmate's question well is worth as much to your
own learning as finishing your own lab, which is why it is worth points.

### Grading Scale

| Letter Grade | Percentage of Points |
|---|---|
| A | 94.00 to 100% |
| A- | 90.00 to 93.99% |
| B+ | 87.00 to 89.99% |
| B | 84.00 to 86.99% |
| B- | 80.00 to 83.99% |
| C+ | 77.00 to 79.99% |
| C | 74.00 to 76.99% |
| C- | 70.00 to 73.99% |
| D | 60.00 to 69.99% |
| F | 0.00 to 59.99% |

### Regrade Requests

If you believe an assignment was graded incorrectly, tell me within one week of
the grade being posted. Requests made more than one week after grading will not
be considered.

## Attendance and Participation

Attendance is expected at every meeting. Because so much of the work happens
live in class, missing sessions is the single strongest predictor of struggling
in this course. A student who misses more than 25 percent of the meetings
without a valid university excuse will receive a grade of F.

If you must miss class, tell me in advance and I will help you catch up.
Absences for illness, religious observance, university-sanctioned travel,
conference presentation, or family emergency are expected and easily
accommodated. The only thing I ask is that you let me know.

### Make-up Exams and Quizzes

Exams and quizzes may be made up only with a valid university excuse and
supporting documentation:

- **Medical:** documentation on official letterhead, signed and dated by a
  licensed medical or mental health provider, including dates of treatment and
  the anticipated return date. Do not send medical records; they will not be
  accepted.
- **Death in the family:** an obituary, memorial service program, or similar
  item identifying you as related to the deceased, with the date and location of
  the service.
- **Military or legal obligations:** military orders or court papers, signed and
  dated by a commanding officer, designee, judge, or lawyer, including dates of
  departure and return.
- **Academic conferences:** tell me at least two weeks before the exam or quiz
  and provide a letter from a faculty member explaining the importance of the
  conference.

### Illness

:::{important}
**Please do not come to class if you are sick.** If you are ill, have tested
positive for a contagious illness, or have been in close contact with someone
who has, stay home. Sessions are recorded and posted when possible, and we will
find a way for you to catch up or to join by Zoom. If you would feel safer
attending remotely for any other reason, let me know. No lecture here is worth
risking your health for.
:::

## Use of AI Coding Assistants

AI coding assistants (ChatGPT, Claude, GitHub Copilot, and their successors) are
now a normal part of professional geospatial work, and pretending otherwise
would not serve you. In this course they are permitted on labs and the final
project, under three conditions:

1. You must be able to explain every line of code you submit. If you cannot
   explain it, you did not write it, and it does not count as your work.
2. Disclose it. Add a short note at the top of your notebook naming the tool and
   what you used it for. Disclosure costs you nothing; undisclosed use is an
   integrity violation.
3. Never on quizzes or the midterm. Those are closed-assistant, and they exist
   precisely to check what you can do unaided.

A word of advice, offered rather than enforced: in the first half of the
semester, reach for the assistant last rather than first. The syntax you
struggle through is the syntax you keep. Once you can read code fluently, an
assistant makes you faster; before that, it mostly makes you dependent.

## Classroom Conduct

This will be a professional, comfortable, and safe environment for everyone in
it. Programming classes attract students with wildly different levels of prior
experience, and a beginner's question is never a waste of anyone's time.
Disagreement about ideas and approaches is welcome; disrespect toward the
instructor or your peers is not. A student who is disrespectful will be spoken
with after class or asked to leave.

## Academic Integrity

You are held to the standards of the university's Honor Statement: "An essential
feature of the University of Tennessee, Knoxville, is a commitment to
maintaining an atmosphere of intellectual integrity and academic honesty. As a
student of the university, I pledge that I will neither knowingly give nor
receive any inappropriate assistance in academic work, thus affirming my own
personal commitment to honor and integrity."

Discussion among students is enthusiastically encouraged, and helping a
classmate find a bug is a good thing to do. Copying a classmate's solution, or
handing yours over to be copied, is plagiarism, and all involved parties are
penalized under the Academic Integrity Policy. Reusing code you find online or
in documentation is fine and normal; cite it in a comment. When in doubt, ask me
before you submit rather than after.

- Hilltopics: <http://hilltopics.utk.edu/academics>
- Academic dishonesty procedures: <https://studentconduct.utk.edu>

## Accessibility and Accommodations

The University of Tennessee seeks to comply fully with the Americans with
Disabilities Act (ADA). Students requesting accommodations based on the impact
of a disability must register with Student Disability Services (SDS), Blount
Hall first floor, 1534 White Avenue; 865-974-6087; <sds@utk.edu>;
<https://sds.utk.edu>. Please share your accommodation letter with me as early
in the term as you can so that arrangements are in place before you need them.
If something about the format of this course (the pace of live coding, the color
scheme of the slides, the screen readability of the notebooks) is creating a
barrier, tell me even if you are not registered with SDS.

## Title IX and Nondiscrimination

The university does not discriminate on the basis of race, color, religion,
national origin, sex, sexual orientation, gender identity, age, disability, or
veteran status. Sexual harassment, sexual assault, dating and domestic violence,
and stalking are prohibited. As an instructor I am a mandatory reporter: if you
disclose an incident of sexual misconduct to me, I am required to share it with
the Title IX office. If you would prefer to speak with someone confidentially
first, the Student Counseling Center is a confidential resource. Title IX:
865-974-9600, <titleix@utk.edu>, <https://titleix.utk.edu>.

## Civility

Civility is genuine respect and regard for others. It enhances academic freedom
and integrity and is a prerequisite to the free exchange of ideas and knowledge
in a learning community. Affirming the value of each member of the university
community, the campus asks that all of its members adhere to the principles of
civility and community adopted by the campus: <https://civility.utk.edu>.

## Well-being and Campus Resources

College is demanding, and asking for help early is a skill rather than an
admission of weakness. If you are struggling, academically, financially, or
personally, please come talk to me, and use the resources below.

| Resource | Contact |
|---|---|
| Student Counseling Center | 865-974-2196 · counselingcenter.utk.edu (confidential) |
| UT 24-hour help line | 865-974-HELP (4357) · limited confidentiality |
| 988 Suicide & Crisis Lifeline | Call or text 988 |
| Student Health Center | 865-974-3135 · studenthealth.utk.edu |
| Student Disability Services | 865-974-6087 · sds@utk.edu · sds.utk.edu |
| Title IX Office | 865-974-9600 · titleix@utk.edu · titleix.utk.edu |
| Student Success Center | studentsuccess.utk.edu (tutoring, academic coaching) |
| Writing Center | writingcenter.utk.edu |
| Center for Career Development | 865-974-5435 · career.utk.edu |
| Big Orange Pantry (food security) | basicneeds.utk.edu |
| OIT HelpDesk (software and computing) | 865-974-9900 · help.utk.edu |
| University Libraries | lib.utk.edu |
| International Student & Scholar Services | 865-974-3177 · international.utk.edu |

## Communication

- **Technical questions go on GitHub.** All course-related questions, including
  installation problems, error messages, and "why does my code do this," belong
  on the [GitHub Discussion
  board](https://github.com/giswqs/gispro-fall26/discussions) so that everyone
  benefits from the answer. Others have almost certainly hit the same error, and
  searching the board before posting is a real skill worth practicing.
- **Private matters go to email.** Anything personal or private, such as grades,
  accommodations, or family circumstances, should come to <qwu18@utk.edu> with
  "GEOG-312" in the subject line. I reply within one business day and ask the
  same of you.
- **Canvas and email.** Announcements, grades, and lab submissions live on
  Canvas. Check Canvas and your UT email at least once each weekday.
- **Office hours.** Wednesdays and Thursdays, 8:00 to 9:00 a.m. in BGB 309, or
  by appointment. You do not need a reason to come, though bringing broken code
  is a perfectly good one.

## Schedule

See the [weekly schedule](schedule.md) for topics, readings, and due dates.

## Course Assessment

At UT it is our collective responsibility to improve the state of teaching and
learning. During the semester you may be asked to assess aspects of this course,
either in class or at its completion. Please respond; feedback about pacing, lab
length, and which tools were worth the time genuinely shapes how this course is
taught the next time around.

## Syllabus Change Policy

I may adjust this syllabus during the semester if doing so serves the course.
Any substantive change will be announced in class and posted on Canvas, and the
revised syllabus will replace this one in the Canvas site.
