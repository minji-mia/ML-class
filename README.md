# CSCI 574: Machine Learning

This repository contains materials and instructions for our graduate level
CSci 574: Machine Learning class from
[Texas A&M University - Commerce](http://tamuc.edu), the
[Department of Computer Science](https://new.tamuc.edu/department-of-computer-science-and-information-systems/).

I would like to thank [Dr. Derek Harter](https://derekharter.github.io/) for teaching Machine learning class


## Getting Started

One of the goals of this course is to get actual experience using some of the
tools and libraries commonly used by current professional machine learning
practitioners and data scientists.  The
[Python Data Science Stack](https://speakerdeck.com/jakevdp/pythons-data-science-stack-jsm-2016)
is one of the most popular collections of libraries and tools used by
professional data scientists and machine learning specialists.

We have made available a full python data science stack in a Vagrant
virtual box.  It is imperative that you have your environment up and
running, preferably by the end of the first day of class.  I will usually
ask all students to send me a report by e-mail on the first day either
acknowledging that they have gotten their environment set up and running
using the steps outlined below, or detailing what step they are having
difficulty with completing.

In general, no matter which OS you have on your personal system, you need
to perform the following steps:

1. Install [git](https://git-scm.com/)
distributed revision control system tools if they are not
already available on your personal computing system.

#### 1. Download and Install git client

If you are on MacOS or Linux you most likely have git already installed.

**Windows OS Instructions**

- Download the git installer for Windows from the official
[git-scm Downloads](https://git-scm.com/download/win)
site that develops the git tools.
- This is a standard windows installer, so once downloaded run it.  You should
be fine accepting all of the default settings for this installer.
- After installing, open a
[command line terminal](https://www.computerhope.com/issues/chusedos.htm)
and test that you have the git command line tool available:
```
C:\Users\username> where git
C:\Program Files\Git\cmd\git.exe
```
```
C:\Users\username> git --version
git version 2.27.0.windows.1
```
If you instead see the message `INFO: Could not find files for the given patern(s).` then git was either not installed, or it was not added to your
[PATH environment variable](https://www.computerhope.com/issues/ch000549.htm)
correctly.  Make sure git is installed and runnable
from the command line before proceeding to the next step.

**MacOS and Linux Instruction**

Git should most likely already be installed on your system by default.
To test, open a terminal and try finding the `git` command:
```
$ which git
/usr/bin/git
```
```
$ git --version
git version 2.25.1
```

On MacOS if you need to install Git, you can go to the link above for
the Windows OS and download the git installer for MacOS.  This is a
standard MacOS based app installer.  Alternatively I recommend installing
the [brew package manager](https://brew.sh/),
which adds open source package management to a
standard MacOS system.  With brew installed, you can use it to install git:

```
$ sudo brew install git
```

On a Linux OS system, use your distributions package manager to
install the git package.  This is most likely either the `apt` or `yum`
command depending on which distribution of Linux you are using:
```
# debian based systems like Ubuntu use apt package manager
$ sudo apt install git
```
```
# Fedora based systems like CentOS likely use yum
$ sudo yum install git
```


#### 2. Clone the Class Git Repository

At this point you should successfully have all of the tools you need for the
class installed.  We will now use them to clone the class repository and
create and provision our class dev environment.

The clone step is easy.  You can use graphical git tools if you are more
familiar with them. We will not be using git in the usual way in this class,
for shared software development.  You will simply use git to pull down the
class files and assignments onto your system, and to receive updates and
fixes while the class is being conducted.

To clone the class repository from the command line, change to the directory you
want to clone a copy of the class files into, then run the git command. I
usually prefer to have a directory named `repos` in my home directory where I
keep all of my repositories.  On Windows, MacOS and Linux you can use `mkdir`,
`cd`, and the `git` command to accomplish this from a command line terminal
or shell:
```
# create a directory called repos, this assumes you are currently in your home directory
$ mkdir repos
```
```
# change into the repos directory to be your current working subdirectory
$ cd repos
```
```
# clone the class repository into your current directory
$ git clone https://bitbucket.org/dharter/ml-python-class.git
```

The clone is basically like a download of the files.  If you are in the
repos directory, there will now be a new subdirectory named `ml-python-class`
that contains all of the files for the class that were just downloaded.


The JupyterHub server uses the
[Anaconda](https://www.anaconda.com/)
Python3 distribution.  The default kernel that was created has the following
Python libraries installed (as well as many others):

- NumPy
- SciPy
- Matplotlib
- Seaborn
- Pandas
- scikit-learn
- statsmodels
- Tensorflow
- Keras

The tensorflow and CUDA GPU tools have been installed which may or may not be
able to take advantage of an NVidia GPU graphics card you have on your host
system.  (This capability is still being tested as of the writing of this
README).

There are many good video introduction to using Jupyter notebooks and the
JupyterLab/JupyterHub server environment:

- [Jupyter Tutorial](https://www.tutorialspoint.com/jupyter/index.htm)
- [Getting Started with JupyterLab](https://dzone.com/articles/getting-started-with-jupyterlab)
- [SciPy 2019 Tutorial](https://www.youtube.com/watch?v=RFabWieskak)

# Additional Course Information and Resources

## Machine Learning Textbooks

The required course textbook is:

- Aurelian Geron (2019). [Hands-On Machine Learning with SciKit-Learn and TensorFlow: Concepts, tools, and techniques to build intelligent systems](https://www.oreilly.com/library/view/hands-on-machine-learning/9781492032632/). 2nd Edition, O'Reilly Media.
  - There is a [GitHub repository](https://github.com/ageron/handson-ml) of code examples from this book that
    might be useful to look at and use.

The following are some recommended additional textbooks if you are looking for
additional reading sources.  

- Marsland. (2009). [Machine Learning: An Algorithmic Perspective](http://www.amazon.com/Machine-Learning-Algorithmic-Perspective-Recognition/dp/1420067184/ref=sr_1_1?ie=UTF8&qid=1376624555&sr=8-1&keywords=machine+learning+an+algorithmic+perspective).
  More examples of Python ML.  [Code examples](http://seat.massey.ac.nz/personal/s.r.marsland/MLbook.html)

- Muller and Guido (2016). [Introduction to Machine Learning with Python](https://www.oreilly.com/library/view/introduction-to-machine/9781449369880/). O'Reilly Media.

- Conway & White. (2012).
  [Machine Learning for Hackers](http://www.amazon.com/Machine-Learning-Hackers-Drew-Conway/dp/1449303714/ref=sr_1_1?ie=UTF8&qid=1376624747&sr=8-1&keywords=machine+learning+for+hackers). [github repo of book source and data](https://github.com/johnmyleswhite/ML_for_Hackers)
  Case studies for this book are written in R.  This site
  [Will it Python](http://slendermeans.org/pages/will-it-python.html)
  has example reimplementations in iPython notebooks.

- Murphy (2012).  [Machine Learning: A Probabilistic Perspective](https://www.amazon.com/gp/product/0262018020/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=0262018020&linkCode=as2&tag=petacrunch-20&linkId=a52c63d00ba9f01f29e1db95d6b4c171).
  MIT Press.


Suggested material for learning python:

- [Think Python: How to think like a computer scientist](https://greenteapress.com/wp/think-python-2e/) 2nd Edition.  Free online textbook, very good resource for not only Python but learning to program in general.
- [Google Developers Python Class](https://developers.google.com/edu/python/?hl=ru&csw=1) short course with videos, might be helpful for those looking for video tutorials of Python.
- [Software Carpentry](http://swcarpentry.github.io/python-novice-inflammation/) section on learning Python is also very good, and also includes videos.


Additional useful links:

- [Full Stack Python](https://www.fullstackpython.com/introduction.html)

## Class Video lectures

- [CSci 574 Official Class YouTube Video Lecture Playlist](https://www.youtube.com/playlist?list=PLKELFBqOW0CfJyA2H1EiF_rqs0RiBcEpi)
- [Andrew Ng Machine Learning Coursera Course Videos](https://www.youtube.com/playlist?list=PLZ9qNFMHZ-A4rycgrgOYma6zxF4BZGGPW)

#### Class Project Structure

In general the directory structure for this project/class repository follows
suggestions and best practices for create data science projects.
See for example
[Cookie Cutter data science](https://drivendata.github.io/cookiecutter-data-science/)
and [Python data science projects](https://gist.github.com/ericmjl/27e50331f24db3e8f957d1fe7bbbe510)

Here is the overview of the class repository structure:

```
$ pwd
/path/to/local/repos/ml-python-class

$ tree
.
├── assignments
│   ├── Assg-01-name.ipynb
│   ├── Assg-02-name.ipynb
│   ├── ...
│   └── Assg-XX-name.ipynb
├── data
│   ├── data-file-1.csv
│   ├── data-file-2.csv
│   ├── ...
│   └── data-file-X.csv
├── docs
│   ├── csci574-sem-YEAR-syllabus.docx
│   └── csci574-sem-YEAR-syllabus.pdf
├── figures
│   ├── figure-01.png
│   ├── figure-02.png
│   ├── ...
│   └── figure-XX.png
├── lectures
│   ├── Lecture-01-name.ipynb
│   ├── Lecture-02-name.ipynb
│   ├── Lecture-02a-Numpy.ipynb
│   ├── ...
│   └── Lecture-XX-name.ipynb
├── scripts
│   ├── bootstrap-anaconda3-python.sh
│   ├── bootstrap-jupyterhub-server.sh
│   ├── bootstrap.sh
│   └── script-name.py
├── src
│   ├── ml_python_class
│   │   ├── custom_funcs.py
│   │   ├── __init__.py
│   └── setup.py
├── LICENSE
├── README.md
└── Vagrantfile
```

**assignments/**

Jupyter/iPython notebooks for assignments and test materials for the
class go here.

**data/**

All data files used for assignments and used in the lecture notebooks
go here.  Some data files are local to the repository, but for larger data
files, scripts may be used to download a larger data file to this
repository data directory for local use.

**figures**/

All static image files used in documents and notebooks. Images may
be generated by code and saved as part of a notebook or workflow, or
may be static images captured for use in documentation.

**lectures**/

Jupyter/iPython notebooks used for course lectures, video lectures and in
general the main resource with the course textbook and assignments for  
learning the course concepts.

**scripts**/

Separate executable scripts used to set up project aspects, load data for
the project, etc.  Bootstrap scripts are used by the Vagrant box
provisioning process to set up the virtual vagrant box for use by the
project.

**src**/

Project package(s) for this class.  Functions and classes that are of
general use in more than one notebook are pulled out as functions
(into the `custom_funcs.py` file), or separate functions and classes.
The `ml_python_class` module can be installed in the normal Python way on the system using
the `setup.py` file if needed, or it can be dynamically added to the
python path using for example:

```python
import sys
sys.path.append('../src')

from ml_python_class.custom_funcs import version_information
version_information()
```

**README.md, LICENSE**

Top level markdown files holding general project information.  
README.md markdown files may also be given in subdirectories for
further information about aspects of the project.


#### History

Material developed for [Texas A&M University -
Commerce](http://tamuc.edu) course CSci 574: Introduction to Machine
Learning and Data Analysis.  These materials were developed in the
Fall of 2013 semester.  The original iPython notebooks were created in
2012 by Hannes Schulz, Andreas Mueller and Nenard Birešev at the
University of Bonn
[original github repo](https://github.com/amueller/tutorial_ml_gkbionics).
I have taken the original material and expanded it for our course.

The materials have been updated for the Fall of 2015 semester.  Materials
from Dr. Ng Coursera [machine learning](https://www.coursera.org/learn/machine-learning/home/welcome) course were used extensively for the updates and assignments.

The materials have been updated in Fall 2019 and Fall 2020.  We are now using
the Geron textbook *Hands-On Machine Learning with SciKit-Learn and Tensorflow*
second edition as our primary textbook.  Materials in the course use the
textbook, Dr. Ng course videos and our own videos.

The materials have been updated in Fall 2020.
It is indeed an honor to take Machine learning class from [Dr.Derek Harter](https://derekharter.github.io/).
