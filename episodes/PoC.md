---
title: "Coduing Up A Proof Of Concept"
teaching: 15 # teaching time in minutes
exercises: 0 # exercise time in minutes
---

# Beginning a new software project

Before we do anything to our project we should talk about:

## Organisation

Organisation is key to a good project. Every time you start a new project or explore a new idea it is a good idea to create a new space for that project. This means creating a new directory for you to collect all the relevant data, software, and documentation. You will be involved in many projects through your career and often will have to manage multiple projects simultaneously. It is therefore not just a good idea to organise each project, but to have a consistent organisation structure between projects. In this section we will make some recommendations for organising a software project.

### Put each project in its own directory, which is named after the project.

The location of this directory will depend on a higher level organisation scheme. For example you may separate your projects based on funding, based on collaboration, or based on research area.

Within you software project directory we recommend the following structure:

> .
> ├── README.md          <- Description of this project
> ├── bin                <- Your compiled code can be stored here (not tracked by git)
> ├── config             <- Configuration files, e.g., for doxygen or for your model if needed
> ├── data
> │   ├── external       <- Data from third party sources.
> │   ├── interim        <- Intermediate data that has been transformed.
> │   ├── processed      <- The final data sets for analysis.
> │   └── raw            <- The original, immutable data dump.
> ├── docs               <- Documentation, e.g., doxygen or reference papers (not tracked by git)
> ├── notebooks          <- Jupyter or R notebooks
> ├── reports            <- For a manuscript source, e.g., LaTeX, Markdown, etc., or any project reports
> │   └── figures        <- Figures for the manuscript or reports
> └── src                <- Source code for this project
>     ├── external       <- Any external source code, e.g., pull other git projects libraries
>     └── tools          <- Any helper scripts go here


Setting up an empty structure such as the above can be done either by making an template and then copying that every time you start a new project. Additionally there are python packages such as `cookiecutter` ([pypi](https://pypi.org/project/cookiecutter/), [rtfd](https://cookiecutter.readthedocs.io/en/1.7.2/), [github](https://github.com/audreyfeldroy/cookiecutter-pypackage)) that can automate this process for you, and offer a range of templates to work with.

### Name all files to reflect their content or function.

It is also convenient to use a consistent and descriptive naming format for all your files and sub-folders. For example, use names such as `galaxy_count_table.csv`, `manuscript.md`, or `light_curve_analysis.py`. Do not using sequential numbers (e.g., `result1.csv`, `result2.csv`) or a location in a final manuscript (e.g., `fig_3_a.png`), since those numbers will almost certainly change as the project evolves (and are meaningless on their own).

## Starting our project
Now we are ready to actually start doing something with our project.

### Project evolution

In the typical project cycle for an astronomer or research software engineer (or RSE, a formal name for people who combine professional software expertise with an understanding of research), you will not sit down and have a detailed discussion about what the project is, where it needs to go, what the user stories and milestones are, and who will be involved. Usually research evolves organically through informal discussions with colleagues, or a sudden thought in the shower. Similarly our software projects evolve in an organic manner, often beginning with a small script of function to do just this one thing, which then over time gets used, reused, augmented, shared, and thus evolves into a software project. This evolution of ideas and code does not fit will with much of the more formal structures that professional software developers adhere to, and so we will not try to fit our projects to such a scheme. Instead we will create a path for our software that will be suited to our work style, but which draws on the knowledge and experience of professional software developers. Thus we will begin with a proof of concept code – a short bit of work that proves that something works using the minimal amount of effort.

### Example project

The example project that we will work with will involve tasks that are familiar to many astronomers. The work that is being done is mostly for demonstration purposes – existing libraries will be able to do this task faster and easier that we will. The point of this example project is not the content, but the methodology that we use as we pass through various cycles of development.


# Example project: an astronomy catalogue simulator
The example project that we will be developing will simulate a catalogue of foreground stars in the direction of the Andromeda galaxy. The initial requirements are as follows:

Stars should have randomised sky positions around the Andromeda galaxy
Positions should fall within 1 degree of the central location
Each star should have a unique ID
The star ID and position should be saved in a csv file to be analysed by other programs
This program is intended to be used by the developer and their research group which includes people who are not proficient python programmers.

It is intended that the software will grow in capability and complexity only as needed to support a current research project.

With this in mind we move to the first stage of our software project – the proof of concept.


:::::::::::::::::::::::::::::::::::::::::::: challenge
## SOLO Activity: Project structure
Consider the astronomy catalogue simulator project mentioned in the previous lesson.

Come up with a planned project structure that would be appropriate for this project.
How much of the structure would change if you were to use a different language (e.g. Python vs C)?
The scope of work is quite modest and could be achieved with a flat file structure or a single file.
Which statements in the previous lesson suggest that a good project structure will be beneficial to future work?

::::::::::::::::::::::::::::::::::::::::::::::::::::::

# Proof of concept code

The first iteration of our code is shown below. It was written in a stream-of-conscious mode with a focus on getting a minimum working example that proves that the work can be done.

:::::::::: language-python

#! /usr/bin/env python
# Demonstrate that we can simulate a catalogue of stars on the sky

# Determine Andromeda location in ra/dec degrees
import numpy as np
import math
# from wikipedia
ra = '00:42:44.3'
dec = '41:16:09'

d, m, s = dec.split(':')
dec = int(d)+int(m)/60+float(s)/3600

h, m, s = ra.split(':')
ra = 15*(int(h)+int(m)/60+float(s)/3600)
ra = ra/math.cos(dec*math.pi/180)

# make 1000 stars within 1 degree of Andromeda
ra_offsets = np.random.uniform(-1, 1, size=1000)
dec_offsets = np.random.uniform(-1, 1, size=1000)

ras = ra + ra_offsets
decs = dec + dec_offsets

# now write these to a csv file for use by my other program
with open('catalog.csv', 'w') as f:
    print("id,ra,dec", file=f)
    for i in range(1000):
        print("{0}, {1:7.4f}, {2:7.4f}".format(i, ras[i], decs[i]), file=f)

::::::::::::::::::::::::::

The above code was saved as `sim.py`. When run from the command line it produces a file (`catalog.csv`) with a header, one thousand rows, and columns showing the id/ra/dec of the simulated points on the sky. Right now the code runs without error and at first glance does what we need.

If we plot the ra/dec locations of the catalog we get the following output:

![catalogue plot](episodes/fig/poc/catalog_plot.png)

Sky plot of the catalog that comes from the sim.py program.