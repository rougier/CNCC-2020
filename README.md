# Computational Neuroscience Crash Course

<br/>

![](./data/XKCD.png)

Given the increasing complexity of neural data and the generalized use of
theoretical models in neuroscience, more and more neuroscientists rely on
computationnal tools for modelling or data analysis. We would like to offer the
possibility to those who feel that their maths/informatics background is a bit
short to update their maths and to get familiar with basic techniques for data
analysis/modelling using the Python language. The course will span over two
years, with a first part (2019) focusing on the maths and programming
pre-requisites, and a second part next year (2020) on data analysis (and
possibly modelling to follow).

<img alt="Arthur Leblois (CNRS) & Nicolas P. Rougier (Inria)" align="right"/>


<br/><br/>
## Forewords

The course is free and open to everyone (student, post-docs, researchers...)
but we'll give priority to master and PhD students given the limited number of
places (24). Just send us an email (arthur.leblois@u-bordeaux.fr or
nicolas.rougier@inria.fr) by end of March if you're interested.  For all
courses (maths and programming), we'll provide some theoretical background,
propose small exercices for participant to work on their own and then solve the
exercices together and make sure everybody has acquiered the related concepts
and techniques. Courses will be taught in English.

#### Warning

> Prior to this course, you need to install [Anaconda](https://www.anaconda.com/distribution/) that is the easiest way to
> have access to the scientific Python stack on Linux, Windows, or Mac OS
> X. After installation, make sure you can start a Jupyter notebook from the
> Anaconda navigator because we'll use it extensively during this course.

<br/><br/>
## Important dates

### Mathematical pre-requisites

Date  | Time | Place | Topic | Tutor 
----- | ---- | ----- | ----- | -----
April  5, 2019 | 9:30-11:30 | [ED Building], room 30 | [Linear Algebra](#linear-algebra) | Arthur Leblois
April 12, 2019 | 9:30-11:30 | [ED Building], room 30 | [Differential Equations](#differential-equations) | Arthur Leblois
April 26, 2019 | 9:30-11:30 | [ED Building], room 30 | [Signal Processing](#signal-processing) | Arthur Leblois

<br/>

### Programming pre-requisites

Date  | Time | Place | Topic | Tutor 
----- | ---- | ----- | ----- | -----
July   1, 2019 |  9:00-12:00 | [ED Building], room 30 | [Python programming]()  | Nicolas Rougier
               | 14:00-17:00 | [ED Building], room 30 | [Numerical Computing]() | Nicolas Rougier

<br/>

### Crash course & Project

Date  | Time | Place | Topic | Tutor 
----- | ---- | ----- | ----- | -----
July   2, 2019 |  9:00-12:00 | [ED Building], room 30 | [Data Exploration]()    | Nicolas Rougier & Arthur Leblois 
               | 14:00-17:00 | [ED Building], room 30 | [Project (part 1)]()    | -
July   4, 2019 |  9:00-12:00 | [ED Building], room 30 | [Data Processing]()     | Nicolas Rougier & Arthur Leblois 
               | 14:00-17:00 | [ED Building], room 30 | [Project (part 2)]()    | -
July   5, 2019 |  9:00-12:00 | [ED Building], room 30 | [Data Analysis](#project) | Nicolas Rougier & Arthur Leblois
               | 14:00-17:00 | [ED Building], room 30 | [Project (part 3)]()    | -

[ED Building]: https://www.openstreetmap.org/#map=19/44.82505/-0.60734



<br/><br/><br/>
## Program

### A. Mathematical pre-requisites

#### Linear Algebra <img src="https://img.shields.io/badge/-2_Hours-orange.svg?style=flat-square" align="right"/>


This course will introduce vectors and matrices, how to peform operations such
as addition & multiplication on these objects and the correspondence with
geometry and the resolution of a system of linear equations.

#### Differential Equations <img src="https://img.shields.io/badge/-2_Hours-orange.svg?style=flat-square" align="right"/>

We'll cover first-order differential equations (that can for example describe
the evolution of a membrane potential). We'll see how to analyze and solve such
equation. 

#### Signal Processing <img src="https://img.shields.io/badge/-2_Hours-orange.svg?style=flat-square" align="right"/>

We'll explain first what is the Fourier transform that is ubiquituous in signal
processing, what is spectral analysis and how to compute correlation in order
to reveal similarity between signals. Instruction on how to install Python on
your machine will be given.



<br/><br/><br/>
### B. Crash course


#### [Python introduction]() <img src="https://img.shields.io/badge/-3_Hours-red.svg?style=flat-square" align="right"/>

During this course, we'll first check that everyone has a functional Python
installation with special attention to the Jupyter notebook.  We'll start
programming in Python and review basic types, control flow & functions. We'll
then give some maths reminder and in the meantime, we'll explain how to apply
them using Python and a dedicated scientific library.


#### [Numerical computing]() <img src="https://img.shields.io/badge/-3_Hours-red.svg?style=flat-square" align="right"/>

This lesson gives an overview of [NumPy](https://www.numpy.org/), the core
library for performant numerical computing, with support for large,
multi-dimensional arrays and matrices, along with a large collection of
high-level mathematical functions to operate on these arrays.


#### [Data exploration]() <img src="https://img.shields.io/badge/-3_Hours-red.svg?style=flat-square" align="right"/>

We'll introduce the project that students will have to complete by the end of
the week. We'll present additional programming material that will be necessary
to load and visualize the data as well as primitive data curation
techniques. Students will work in pair and will start exploratory data analysis
while tutors will be present the whole afternoon to give feedbacks and help if
necessary. The next goal of the project will be introduced such that students
can work on their own on the next day.


#### [Data processing]() <img src="https://img.shields.io/badge/-3_Hours-red.svg?style=flat-square" align="right"/>

We'll briefly introduce the spectral analysis tools available in NumPy, the
scientific library of Python. Students will work in pair and will apply various
spectral analysis tools to the data to determine if and how the spectral
content of the data can be used to classify various data categories. During the
afternoon, students continue working on the project, applying selected spectral
analysis tools to the whole data set and extracting relevant indexes.


#### [Data analysis]() <img src="https://img.shields.io/badge/-3_Hours-red.svg?style=flat-square" align="right"/>


<br/><br/>

### C. Project

<img src="data/pixar.jpg" align="right"/>

The goal of the project is to analyze audio recordings of birds such as to
discriminate between adults and juveniles. This analysis will be based on the
material introduced during the course and you'll have to define some criteria
for discrimination and to take care of noisy signals.  The objective is to
produce a final report detailing your analysis, including images, statistical
test and formulas. This report will take the form of a single Jupyer notebook
that will be exported to HTML.

The dataset is available from the Zenodo directory.



<br/><br/><br/>
## Bibliography

* [From Python to NumPy](), N.P. Rougier, Zenodo, 2017.
* [100 Numpy exercises](), N.P. Rougier, GitHub, 2017.
* [Matplotlib tutorial](), N.P. Rougier, Zenodo, 2015.
* [Ten simple rules for better figures](),
  N.P. Rougier, M. Droettboom & P. E. Bourne, Plos Computational Biology, 2014.
* [How to transform code into scientific contribution](),
  N.P. Rougier & F.Benureau, Frontiers in Neuroinformatics, 2018.
<br/>



## Copyright notice

This course has been written in March 2019 using  
<img src="https://img.shields.io/badge/OSX-10.14.3-999999.svg?style=flat-square"/> <img src="https://img.shields.io/badge/Emacs-26.1-999999.svg?style=flat-square"/> <img src="https://img.shields.io/badge/Git-2.20.1-999999.svg?style=flat-square"/> <img src="https://img.shields.io/badge/Python-3.7.2-999999.svg?style=flat-square"/> <img src="https://img.shields.io/badge/Numpy-1.15.2-999999.svg?style=flat-square"/> <img src="https://img.shields.io/badge/Scipy-1.1.0-999999.svg?style=flat-square"/> <img src="https://img.shields.io/badge/Matplotlib-3.0.0-999999.svg?style=flat-square"/> <img src="https://img.shields.io/badge/Cython-0.28.2-999999.svg?style=flat-square"/> <img src="https://img.shields.io/badge/Numba-0.40.0-999999.svg?style=flat-square"/>

Copyright © 2019 Arthur Leblois & [Nicolas P. Rougier](http://www.labri.fr/perso/nrougier) – 
Released under a [CC-BY 4.0 International](https://creativecommons.org/licenses/by/4.0/legalcode) license.  
Banner image copyright © Randall Monroe ([XKCD #353](https://xkcd.com/353/)) – 
"For the Birds" image copyright © Pixar Studios


[Anaconda]:   https://www.anaconda.com/
[Emacs]:      http://www.emacs.org/
[vim]:        https://www.vim.org/
[Atom]:       https://atom.io/
[Notepad++]:  https://notepad-plus-plus.org/
[IPython]:    http://www.ipython.org/
[Jupyter]:    http://www.jupyter.org/
[NumPy]:      http://www.numpy.org/
[Scipy]:      http://www.scipy.org/
[Matplotlib]: http://www.matplotlib.org/
[Cython]:     https://cython.org/
[Numba]:      https://numba.pydata.org/
