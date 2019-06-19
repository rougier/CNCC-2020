# Computational Neuroscience Crash Course (2019)

Given the increasing complexity of neural data and the generalized use of
theoretical models in neuroscience, more and more neuroscientists rely on
computationnal tools for modelling or data analysis. We would like to offer the
possibility to those who feel that their maths/informatics background is a bit
short to update their maths and to get familiar with basic techniques for data
analysis/modelling using the Python language. The Computational Neuroscience
Crash Course (CNCC) will span over two years, with a first part (2019) focusing
on the maths and programming pre-requisites, and a second part next year (2020)
on data analysis (and possibly modelling to follow).  

The course is free and open to everyone (student, post-docs, researchers...)
but we'll give priority to master and PhD students given the limited number of
places (n=24). For all courses (maths and programming), we'll provide some
theoretical background, propose small exercices for participant to work on
their own and then solve the exercices together and make sure everybody has
acquired the related concepts and techniques. Courses will be taught in
English.  

<br/>


## Important dates

**Registration deadline**: 31/03/2019 (registrations are now **CLOSED**)  

If you were not able to register but want to be kept up to date, you can send
us an email (arthur.leblois@u-bordeaux.fr or nicolas.rougier@inria.fr). We'll
send email when new material is online and you can ask us for help if you
encounter some diffculties.


### Mathematical lessons

Date  | Time | Place | Topic | Tutor 
----- | ---- | ----- | ----- | -----
April  5, 2019 | 9:30-11:30 | [ED Building], room 30 | [Linear Algebra] | Arthur Leblois
April 12, 2019 | 9:30-11:30 | [ED Building], room 30 | [Differential Equations] | Arthur Leblois
April 26, 2019 | 9:30-11:30 | [ED Building], room 30 | [Signal Processing] | Arthur Leblois

### Programming lessons

Date  | Time | Place | Topic | Tutor 
----- | ---- | ----- | ----- | -----
July   1, 2019 |  9:00-12:00 | [ED Building], room 30 | [Introduction] | Nicolas Rougier
               | 14:00-17:00 | [ED Building], room 30 | [Numerical Computing] | Nicolas Rougier
July   2, 2019 |  9:00-12:00 | [ED Building], room 30 | Data Visualization | Nicolas Rougier 
               |  14:00-17:00 | [ED Building], room 30 | Signal processing  | Nicolas Rougier


### Project

Date  | Time | Place | Topic | Tutor 
----- | ---- | ----- | ----- | -----
July   3, 2019 |  9:00-12:00 | [ED Building], room 30 | Presentation | Nicolas Rougier & Arthur Leblois 
               | 14:00-17:00 | [ED Building], room 30 | Team work (part 1) | -
July   4, 2019 |  9:00-12:00 | [ED Building], room 30 | Update | Nicolas Rougier & Arthur Leblois 
               | 14:00-17:00 | [ED Building], room 30 | Team work (part 2) | -
July   5, 2019 |  9:00-12:00 | [ED Building], room 30 | Restitution |  Nicolas Rougier & Arthur Leblois 
               | 14:00-16:00 | [ED Building], room 30 | Wrap-up | Nicolas Rougier & Arthur Leblois 


[ED Building]: https://www.openstreetmap.org/#map=19/44.82505/-0.60734
[Linear Algebra]: #linear-algebra
[Differential Equations]: #differential-equations
[Signal Processing]: #signal-processing
[Installation]: #installation
[Introduction]: #introduction
[Numerical Computing]: #numerical-computing


<br/><br/><br/>

## Mathematical lessons

### [Linear Algebra](lessons/01-linear-algebra.pdf)

<img src="data/indent.png" align="left"/>

This course will introduce vectors and matrices, how to peform operations such
as addition & multiplication on these objects. The correspondence with geometry
and the resolution of a system of linear equations will be explained.

**Prerequisites**: None  
**See also**:
[Wikipedia | Linear Algebra](https://en.wikipedia.org/wiki/Linear_algebra)
& [Mathematics for Computational Neuroscience](https://www.sheffield.ac.uk/polopoly_fs/1.13304!/file/maths.pdf)

<br/>

### [Differential Equations](02-differential-equations.pdf)

<img src="data/indent.png" align="left"/>

We'll cover first-order differential equations (that can for example describe
the evolution of a membrane potential). We'll see how to analyze and solve such
equation. 

**Prerequisites**: None  
**See also**:
[Wikipedia | Differential Equations](https://en.wikipedia.org/wiki/Differential_equation) &
[Mathematics for Computational Neuroscience](https://www.sheffield.ac.uk/polopoly_fs/1.13304!/file/maths.pdf)

<br/>

### Signal Processing

<img src="data/indent.png" align="left"/>

We'll explain first what is the Fourier transform that is ubiquituous in signal
processing, what is spectral analysis and how to compute correlation in order
to reveal similarity between signals.

**Prerequisites**: None  
**See also:**
[MATLAB for Neuroscientists](https://www.sciencedirect.com/book/9780123838360/matlab-for-neuroscientists) ($)


<br/><br/>

## Programming lessons

### [Installation](lessons/01-installation.md)

<img src="data/indent.png" align="left"/>

This lesson aims at providing the student with a clean development environment,
including Python installation and essential packages, a decent text editor, and
a shell. We'll also introduce the Python & IPython shells, the Jupyter notebook
and explains how to run a python script from the command line.  

**Prerequisites**: None  
**See also**: [Anaconda installation](https://docs.anaconda.com/anaconda/install/)  
<br/>


### [Introduction](lessons/02-introduction.md)

<img src="data/indent.png" align="left"/>

We introduce here Python, a powerful and easy to learn programming language. It
has *efficient high-level data structures and a simple but effective approach
to object-oriented programming* (Python website). However, we'll only
cover the strict minimum necessary for getting started with numerical computing.

**Prerequisites**: [Installation](#installation)  
**See also**: [Official Python tutorial](https://docs.python.org/tutorial) & [Dive into Python](http://www.diveintopython.net/)  
<br/>


### Numerical computing

<img src="data/indent.png" align="left"/>

This lesson gives an overview of NumPy, the core library for performant
numerical computing, with support for large, multi-dimensional arrays and
matrices, along with a large collection of high-level mathematical functions to
operate on these arrays.

**Prerequisites**: [Introduction](#introduction)  
**See also**: [Scipy Lecture Notes](https://scipy-lectures.org/) & [From Python to Numpy](https://www.labri.fr/perso/nrougier/from-python-to-numpy/)
<br/>



<br/><br/>

## Project

The goal of the project is to automatically classify bird songs depending on
whether the bird is an adult or a juvenile. You can start by listening the
different files to see if you can hear any difference.

<br/><br/>

##  

[Computational Neuroscience Crash Course (CNCC 2019)](https://github.com/rougier/NeuroComp-Bordeaux-2019)  
Copyright © 2019 Arthur Leblois & [Nicolas P. Rougier](http://www.labri.fr/perso/nrougier) – [CC-BY 4.0 International](https://creativecommons.org/licenses/by/4.0/legalcode) license.

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
