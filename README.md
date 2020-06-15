# Computational Neuroscience Crash Course (2020)

Given the increasing complexity of neural data and the generalized use
of theoretical models in neuroscience, more and more neuroscientists
rely on computationnal tools for modelling or data analysis. We would
like to offer the possibility to those who feel that their maths /
informatics background is a bit short to update their maths and to get
familiar with basic techniques for data analysis/modelling using the
Python language. The Computational Neuroscience Crash Course (CNCC)
will span over two years, with a first part focusing on the maths and
programming pre-requisites, and a second part next year
on data analysis (and possibly modelling to follow).  

For all courses (maths and programming), we'll provide some
theoretical background, propose small exercices for participant to
work on their own and then solve the exercices together and make sure
everybody has acquired the related concepts and techniques. Courses
will be taught in English.  
 
**Contact**
- Arthur Leblois:  arthur.leblois@u-bordeaux.fr
- Nicolas Rougier: nicolas.rougier@inria.fr

<br/><br/>

## Important dates

This year and ue to the pandemic, the whole course will be online and
this means you'll have to read the different lessons before each
session, following the proposed schedule below:

### Monday 15 June 2020
  Make sure to have read (see below):
  - Math: Linear Algebra 
  - Prog: Installation + Introduction
  
### Tuesday 16 June 2020
  Make sure to have read (see below):
  - Math: Signal Processing + Fourier transform
  - Prog: Numerical computing

### Wednesday 17 June
  Make sure to have read (seel below):
  - Math: Fourier transform
  - Prog: Scientific computing

Each morning (Monday, Tuesday and Wednesday), from 9am to 10am, we'll
try to quickly highlight the main points on each lesson (15mn) and
we'll take 45mn to answer any questions you may have on the lessons or
the project.


## The (mini) project

The goal of the project is to sort (automatically) audio files that
correspond to the recording of adult or juvenile songbirds. If you
listen to the audio files, you will hear that the sound is quite
different between an adult (song) and a juvenile (babbling). This
means we can probably process the audio files in order to decide if it
corresponds to an adult or a juvenile and the goal is thus to write a
function `songsort(directory)` that will automatically sort
all the files present in some-path and label them accordingly.  

For the project, you'll need to team with someone else such as to work
together at one computer ([pair
programming](https://en.wikipedia.org/wiki/Pair_programming)). When
one is typing, the other is reading an commenting and for maximum
efficiency, you'll have to switch roles frequently. This can be done
online by sharing the screen of someone.  

For the project, we'll use Jupyter notebook and we'll start with the
[project/introduction.ipynb](project/introduction.ipynb) notebook.

Data is available here: https://filesender.renater.fr/?s=download&token=77a5fac3-ee68-40af-baab-4b34ab09d6b8




## Mathematical lessons

### [Linear Algebra](lessons/01-linear-algebra.pdf)

<img src="data/indent.png" align="left"/>

This course will introduce vectors and matrices, how to peform operations such
as addition & multiplication on these objects. The correspondence with geometry
and the resolution of a system of linear equations will be explained.

**Prerequisites**: None  
**On-line courses**:

[Wikipedia | Linear Algebra](https://en.wikipedia.org/wiki/Linear_algebra)

[Mathematics for Computational Neuroscience](https://www.sheffield.ac.uk/polopoly_fs/1.13304!/file/maths.pdf): only Part 1, Chapter 2, 1-3 (ignore the least square approx in 4). 

[Ch4 Linear Algebra (Owen&Corrado, Stanford U)](https://web.stanford.edu/class/nbio228-01/handouts/Ch4_Linear_Algebra.pdf)

**Exercices**:
 PDF link: https://drive.google.com/file/d/1i2xM37M35iSrTbXoNOX5qQFARRrH2MTn/view?usp=sharing

<br/>

### Signal Processing

<img src="data/indent.png" align="left"/>

We'll explain first what is the Fourier transform that is ubiquituous in signal
processing, what is spectral analysis and how to compute correlation in order
to reveal similarity between signals.

**Prerequisites**: None  
**On-line courses**:

What is signal processing, and why ? https://www.youtube.com/watch?v=YmSvQe2FDKs

Autocorrelation and crosscorrelation :
https://en.wikipedia.org/wiki/Autocorrelation & 
https://en.wikipedia.org/wiki/Cross-correlation (in both pages, focus on the case of ‘deterministic signals’ and ignore the case of random vectors)

Video explanation and demo : https://www.youtube.com/watch?v=_r_fDlM0Dx0

The case of neurons and spikes : https://www.med.upenn.edu/mulab/analysis.html

Fourier transforms :

https://en.wikipedia.org/wiki/Fourier_transform (up to 5.1 basic properties)

I
ntuitive definition : https://sites.northwestern.edu/elannesscohn/2019/07/30/developing-an-intuition-for-fourier-transforms/
More complete definition : https://physiology.med.cornell.edu/people/banfelder/qbio/resources_2016/S.2_fourier.pdf

A video course on the basics of Fourier transform : https://www.ibiology.org/talks/fourier-transform/

To go beyond, the history and many applications of Fourier transforms : http://www.yalescientific.org/2010/12/fourier-transform-natures-way-of-analyzing-data/

### [Differential Equations (optional)](02-differential-equations.pdf)

<img src="data/indent.png" align="left"/>

We'll cover first-order differential equations (that can for example describe
the evolution of a membrane potential). We'll see how to analyze and solve such
equation. 

**Prerequisites**: None  
**See also**:
[Wikipedia | Differential Equations](https://en.wikipedia.org/wiki/Differential_equation) &
[Mathematics for Computational Neuroscience](https://www.sheffield.ac.uk/polopoly_fs/1.13304!/file/maths.pdf)

<br/>


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
**See also**: [Official Python tutorial](https://docs.python.org/tutorial) & [Dive into Python](https://diveintopython3.problemsolving.io/)  
<br/>


### [Numerical computing](https://docs.scipy.org/doc/numpy/user/quickstart.html)

<img src="data/indent.png" align="left"/>

This lesson gives an overview of NumPy, the core library for performant
numerical computing, with support for large, multi-dimensional arrays and
matrices, along with a large collection of high-level mathematical functions to
operate on these arrays.

**Prerequisites**: [Introduction](#introduction)  
**See also**: [Scipy Lecture Notes](https://scipy-lectures.org/), [Numpy for Matlab users](https://docs.scipy.org/doc/numpy/user/numpy-for-matlab-users.html) &  [From Python to Numpy](https://www.labri.fr/perso/nrougier/from-python-to-numpy/)
<br/>


### [Data Visualization](https://matplotlib.org/3.1.0/tutorials/introductory/pyplot.html)

<img src="data/indent.png" align="left"/>

We'll explore the matplotlib library which is a Python 2D plotting library
which produces publication quality figures in a variety of hardcopy formats and
interactive environments across platforms. Matplotlib can be used in Python
scripts, the Python and IPython shells, the Jupyter notebook, web application
servers, and four graphical user interface toolkits.

**Prerequisites**: [Numerical computing](#numerical-computing)  
**See also**: [Matplotlib tutorial](https://github.com/rougier/matplotlib-tutorial), [Ten Simple Rules for Better Figures](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003833)


### [Scientific computing](http://scipy-lectures.org/intro/scipy.html)

<img src="data/indent.png" align="left"/>

This lesson, from the scipy mlecture notes, will cover scipy which is a
scientific-computing libraries, such as the GSL (GNU Scientific Library for C
and C++), or Matlab’s toolboxes. Scipy is the core package for scientific
routines in Python; it is meant to operate efficiently on numpy arrays, so that
numpy and scipy work hand in hand.

**Prerequisites**: [Numerical computing](#numerical-computing)  
**See also**: [Elegant Scipy](https://github.com/elegant-scipy/elegant-scipy), [Python Data Science Handbook](https://jakevdp.github.io/PythonDataScienceHandbook/)



##  

[Computational Neuroscience Crash Course (CNCC 2020)](https://github.com/rougier/CNCC-2020)  
Copyright © 2020 Arthur Leblois & [Nicolas P. Rougier](http://www.labri.fr/perso/nrougier) – [CC-BY 4.0 International](https://creativecommons.org/licenses/by/4.0/legalcode) license.

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
