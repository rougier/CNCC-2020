[Computational Neuroscience Crash Course (2019)](https://github.com/rougier/NeuroComp-Bordeaux-2019) — Arthur Leblois (CNRS) & Nicolas P. Rougier (Inria)<br/>

# Computational Neuroscience Crash Course

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
places (n=24). For all courses (maths and programming), we'll provide some
theoretical background, propose small exercices for participant to work on
their own and then solve the exercices together and make sure everybody has
acquired the related concepts and techniques. Courses will be taught in
English.

### Warning

> For the programming part, you'll need to come with your own computer and to
> have [Anaconda](https://www.anaconda.com/distribution/) installed on your
> machine (see [Installation](#installation-) below). Anaconda is the easiest way to access the
> scientific Python stack on Linux, Windows, or Mac OS X. After installation,
> make sure you can start a Jupyter notebook from the Anaconda navigator
> because we'll use it extensively during this course.

<br/><br/>
## Important dates

**Registration deadline**: 31/03/2019 (registrations are now **CLOSED**)  

If you were not able to register but want to be kept up to date, you can send
us an email (arthur.leblois@u-bordeaux.fr or nicolas.rougier@inria.fr). We'll
send email when new material is online and you can ask us for help if you
encounter some diffculties.


### Mathematical pre-requisites

Date  | Time | Place | Topic | Tutor 
----- | ---- | ----- | ----- | -----
April  5, 2019 | 9:30-11:30 | [ED Building], room 30 | [Linear Algebra](#linear-algebra)         | Arthur Leblois
April 12, 2019 | 9:30-11:30 | [ED Building], room 30 | [Differential Equations](#differential-equations) | Arthur Leblois
April 26, 2019 | 9:30-11:30 | [ED Building], room 30 | [Signal Processing](#signal-processing)      | Arthur Leblois

<br/>

### Programming pre-requisites

Date  | Time | Place | Topic | Tutor 
----- | ---- | ----- | ----- | -----
July   1, 2019 |  9:00-12:00 | [ED Building], room 30 | Python programming  | Nicolas Rougier
               | 14:00-17:00 | [ED Building], room 30 | Numerical Computing | Nicolas Rougier


### Project

Date  | Time | Place | Topic | Tutor 
----- | ---- | ----- | ----- | -----
July   2, 2019 |  9:00-12:00 | [ED Building], room 30 | Data Exploration | Nicolas Rougier & Arthur Leblois 
               | 14:00-17:00 | [ED Building], room 30 | Project (part 1) | Nicolas Rougier & Arthur Leblois
July   3, 2019 |  9:00-12:00 | [ED Building], room 30 | Team work        | -
               | 14:00-17:00 | [ED Building], room 30 | Team work        | -
July   4, 2019 |  9:00-12:00 | [ED Building], room 30 | Data Processing  | Nicolas Rougier & Arthur Leblois 
               | 14:00-17:00 | [ED Building], room 30 | Project (part 2) | Nicolas Rougier & Arthur Leblois 
July   5, 2019 |  9:00-12:00 | [ED Building], room 30 | Data Analysis    | Nicolas Rougier & Arthur Leblois
               | 14:00-17:00 | [ED Building], room 30 | Project (part 3) | Nicolas Rougier & Arthur Leblois 
               | 17:00-20:00 | Neurocampus            | Social event     | Everyone

[ED Building]: https://www.openstreetmap.org/#map=19/44.82505/-0.60734



<br/><br/><br/>

## Mathematical pre-requisites

### Linear Algebra <img src="https://img.shields.io/badge/-2_Hours-orange.svg?style=flat-square" align="right"/>

<img src="data/indent.png" align="left"/>

This course will introduce vectors and matrices, how to peform operations such
as addition & multiplication on these objects. The correspondence with geometry
and the resolution of a system of linear equations will be explained.

**See also**:
[Wikipedia | Linear Algebra](https://en.wikipedia.org/wiki/Linear_algebra)
& [Mathematics for Computational Neuroscience](https://www.sheffield.ac.uk/polopoly_fs/1.13304!/file/maths.pdf)

<br/>

### Differential Equations <img src="https://img.shields.io/badge/-2_Hours-orange.svg?style=flat-square" align="right"/>

<img src="data/indent.png" align="left"/>

We'll cover first-order differential equations (that can for example describe
the evolution of a membrane potential). We'll see how to analyze and solve such
equation. 

**See also**:
[Wikipedia | Differential Equations](https://en.wikipedia.org/wiki/Differential_equation)
& [Mathematics for Computational Neuroscience](https://www.sheffield.ac.uk/polopoly_fs/1.13304!/file/maths.pdf)

<br/>

### Signal Processing <img src="https://img.shields.io/badge/-2_Hours-orange.svg?style=flat-square" align="right"/>

<img src="data/indent.png" align="left"/>

We'll explain first what is the Fourier transform that is ubiquituous in signal
processing, what is spectral analysis and how to compute correlation in order
to reveal similarity between signals.

**See also:**
[MATLAB for Neuroscientists](https://www.sciencedirect.com/book/9780123838360/matlab-for-neuroscientists) ($)


<br/><br/><br/>
## Programming pre-requisites

### [Installation](lessons/01-installation.md) <img src="https://img.shields.io/badge/-1_Hour-orange.svg?style=flat-square" align="right"/>

<img src="data/indent.png" align="left"/>

This lesson aims at providing the student with a clean development environment,
including Python installation and essential packages (using the [Anaconda]
installer), a decent text editor (e.g. [emacs], [vim], [atom], [notepad++]), a
git command line and a shell. We'll also introduce the Python & [IPython]
shells, the [Jupyter] notebook and explains how to run a python
script from the command line or from inside the [IPython] shell.  
<a href="lessons/01-installation.md"><img alt="→ Go to installation" align="right"/></a>

<br/>



<br/><br/>

##  

Copyright © 2019 Arthur Leblois & [Nicolas P. Rougier](http://www.labri.fr/perso/nrougier) – 
Released under a [CC-BY 4.0 International](https://creativecommons.org/licenses/by/4.0/legalcode) license.

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
