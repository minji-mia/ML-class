# CSci 574: Machine Learning

This repository contains materials and instructions for our graduate level
CSci 574: Machine Learning class from
[Texas A&M University - Commerce](http://tamuc.edu), the
[Department of Computer Science](https://new.tamuc.edu/department-of-computer-science-and-information-systems/).

You should start by following the Getting Started instructions next,
to get your required Scientific Python computing stack set up on your
system.  We will be using JupyterHub and iPython notebooks for the
majority of the assignments and lecture materials and activities for
the course.  

Additional information about the class textbooks and materials can also
be found below in this README, or should also be available on the
[MyLeoOnline](https://myleoonline.tamuc.edu/d2l/home)
D2L course shell created for this semester's class.


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
2. Install Oracle's [VirtualBox](https://www.virtualbox.org/)
open source virtualization solution on your system to run the
Vagrant virtual server box.
3. Install the [Vagrant](https://www.vagrantup.com/)
virtualization management tools.
3. Clone this course's repository to your system using `git clone`.
4. Use `vagrant up` to boot up and provision the Python stack
and JupyterHub server vagrant box.

The first 3 steps are system dependent, but should only require use of
a standard installer to accomplish.  Once you have git, VirtualBox
and Vagrant on your  system, you should be able to clone the class
repository, start the vagrant virtual box and provision it, and then
run and access your JupyterHub python stack server in a similar manner
no matter which OS you are using.

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

#### 2. Install VirtualBox Virtualization Tools

You will need to install VirtualBox on your system to use the vagrant box
setup given to you for this class.  A standard app installer/package is provided
on the [VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)
site for Windows, MacOS X and Linux distributions.  Download the
installer and install it in the standard way for your operating system.
You should be able to accept the defaults offered by the installer for your
system.

Once installed, a graphical interface for VirtualBox is available that you
should be able to search for from your start menu and run.  Also a command
line tool should be installed and working.  Open a command line terminal
or shell on your system and test that the `VBoxManage` command is available
and in your path.  On Linux and MacOS X it should be installed in a standard
location that will be on your usual system path:
```
# on MacOX and Linux use the which command, on Windows use where instead
# MacOS / Linux
$ which VBoxManage
/usr/bin/VBoxManage
$ VBoxManage --version
6.1.12r138449
```

On Windows OS the installer does not add the location of the VirtualBox command
line tools to your PATH.  You can either add `C:\Program Files\Oracle\VirtualBox` to your PATH, or you can change to this directory or specify the full path name to run the `VBoxManage.exe` tool from the command
line:
```
# Windows
> "C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" --version
6.1.12r138449
```
The location of the PATH where the executable resides and the version
number may differ slightly.  As of the writing of this README,
you should have at least VirtualBox version 6.1.12 or higher installed on
your system.


#### 3. Install Vagrant Virtualization Management Tools

Vagrant greatly simplifies managing and spinning up virtual box instances.
You have been given a Vagrantfile in the class repository that should
spin up and provision a full Python Stack vagrant box running a JupyterHub
server.

Again standard install packages are provided on the
[Vagrant Download](https://www.vagrantup.com/downloads)
site for Windows, MacOS X and Linux systems.
Download the installer or package appropriate for your system and
install it.  Accept the suggested defaults for all questions for the install.
Both VirtualBox and Vagrant may require a system reboot (especially on Windows),
so once you have Vagrant successfully installed, it is a good idea to reboot
your system at this point before continuing.

**NOTE Windows Users** Before rebooting, you should check and disable Hyper-V
if it is enabled on your system.  If you don't see the Hyper-V feature, you
may instead have Virtualization Based Security (VBS).  If so, you may (or may not)
see issues when you try and install/bootstrap your virtual box. If you have VBS
and run into inssues, contact the instructor.

- [Virtualization applications do not work together with Hyper-V](https://support.microsoft.com/en-us/help/3204980/virtualization-applications-do-not-work-together-with-hyper-v-device-g)

**Reboot System**

When you reboot your system to make sure that the VirtualBox and the
Vagrant installs completely take effect, it would be a good idea to also
check your BIOS settings and make sure that you have hardware virtualization
enabled.  VirtualBox and Vagrant will not work if hardware virtualizaiton
is not enabled.  This is probably enabled now adays by default?  but best
to explicitly check it.

When booting up, enter your system BIOS

- [How to Enter the BIOS on Any PC: Access Keys by Manufacturer](https://www.tomshardware.com/reviews/bios-keys-to-access-your-firmware,5732.html)

Usually the `F2` key should work, but if not there should usually be
a message on your first boot screen telling you what the BIOS access
key is.

In your BIOS, find the setting for hardware Virtualization

- [Enabling Virtualization in your PC BIOS](https://bce.berkeley.edu/enabling-virtualization-in-your-pc-bios.html)

This setting is usually in your BIOS menu under the Processor or CPU settings.
And as the link says, it will probably be called either `VT-x` or  `AMD-V`.
Make sure it is enabled.

**After Reboot**

Again once installed it is a good idea to confirm that the command line
tools are available before moving on.  Since `vagrant` is mainly intended
to be used from the command line, this time if you are a Windows user you should
find that the command has been added to your PATH for you.

To test, use the `where` or `which` command, and try running `vagrant` asking
for the installed version.  If the command cannot be found, you need to
stop and check your install and insure your PATH is set correctly.

```
# MacOS / Linux use which to see if vagrant tool in PATH
$ which vagrant
/usr/bin/vagrant
# WindowsOS use where instead
> where vagrant
C:\HashiCorp\Vagrant\bin\vagrant.exe
```
```
# if it is on your path, test you can run it by determining which version you are on
$ vagrant --version
Vagrant 2.2.9
```
As of the writing and testing of this README, you should have installed Vagrant
version 2.2.9 or higher on your system now.


#### 4. Clone the Class Git Repository

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

#### 5. Start and Provision the JuptyerHub Server vagrant box

Assuming you just completed the previous step 4, you are now in the `repos`
directory, and you just cloned a copy of the `ml-python-class` directory.
Change into the class repository directory from the command line:
```
$ cd ml-python-class
```

In the next step we will attempt to start and provision your vagrant box.
The box will download and start a new virtual machine, install the Anaconda Python distribution
and needed Scientific Python libraries.  It will create a JupyterHub server
and start the server running.  

To start the vagrant box and have it provision itself run the following command
from a terminal in your `ml-python-class` repository directory:
```
$ vagrant up
```

This step will take some time.  On my rural Texas DSL I tend to get 100 to
500 k/sec download when I run this.  The base `virtualbox.box` image will
first be downloaded.  This usually takes about 30-60 minutes or so from my
home to complete.  If the base image successfully downloads, the installer
will then attempt to install Anaconda Python and set up a JupyterHub server.
This will again take probably 30-60 minutes depending on your speed.

If no errors occurs, the last thing you will see when the install finishes is a message from our Bootstrap provisioning script:
```
...
Anaconda Python3 installed successfully, JupyterHub/JupyterLab server running!
```

If you instead see error messages in your terminal at the end, please copy them
and e-mail them to your instructor for advice on proceeding.

At this point, assuming no errors, your vagrant box instance is actually
up and running.  However it is a good idea to shutdown the server and
bring it back up at this point to test that things are working cleanly
and as expected.  Start by doing a halt to shutdown the box:

```
$ vagrant halt
==> default: Unmounting NFS shared folders from guest...
==> default: Forcing shutdown of VM...
```

You should see that the box is shutdown and not get any error messages.
Then bring the box back up again.  Once the base image is downloaded,
and the box is provisioned and set up, bringing it up again should be
relatively quick.  It will boot in a minute or less usually.

```
$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Checking if box 'ubuntu/focal64' version '20200702.0.0' is up to date...
==> default: Clearing any previously set forwarded ports...
==> default: Clearing any previously set network interfaces...
==> default: Preparing network interfaces based on configuration...
    default: Adapter 1: nat
==> default: Forwarding ports...
    default: 8000 (guest) => 8000 (host) (adapter 1)
    default: 22 (guest) => 2222 (host) (adapter 1)
==> default: Running 'pre-boot' VM customizations...
==> default: Booting VM...
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 127.0.0.1:2222
    default: SSH username: vagrant
    default: SSH auth method: private key
==> default: Machine booted and ready!
==> default: Checking for guest additions in VM...
==> default: Mounting shared folders...
    default: /vagrant => /home/dash/repos/ml-python-class
==> default: Machine already provisioned. Run `vagrant provision` or use the `--provision`
==> default: flag to force provisioning. Provisioners marked to run always will still run.

```

Things to check here.  You might get some warnings, like your base box is
out of date, or other things.  Usually warnings are not issues you need to
worry about, but if you have a question send me the warning message.

What you want to ensure here includes:

- Make sure that port 8000 on the guest is shown as forwarding to port 8000
  on the host.  The guest is the virtualbox machine you are running, and the
  host is your computer/os.  JupyterLab is served on port 8000 on the guest, and
  this is how we access it on your host by forwarding that port between the
  two.
- You should see that port 22 on the guest is forwarded to some port on your
  host.  This provides ssh access into your guest machine if needed.
- Hopefully you will see that the GuestAdditions are running ok.  These
  can sometimes have problems.  
- Finally your repository should be mounted from your host machine to
  your guest.  This is the line that says
  ```
  default: /vagrant => /home/dash/repos/ml-python-class
  ```
  The location of the directory on your host will differ, but it should be
  the location of the repository you cloned in step 4 above.  This
  sharing and mounting of your repository directory allows you to access
  and open the files from the JupyterLab IDE inside of the vagrant box.

If you see that the machines is booted and ready! now, you can then
proceed to try and log into your JupyterLab server.


## Using your JupyterHub Class Development Server

If your vagrant box provisions itself and boots up correctly, it will
be running a JupyterHub server providing JupyterLab
with a full Anaconda Python3 data science
stack installed.  The server is mapped to port 8000 of your host machine.
So if the vagrant box is up and running, you should be able to navigate to

[http://localhost:8000](http://localhost:8000)

from a web browser to access your system.  

The system is configured with a standard username/password:

**username:** vagrant

**password:** vagrant

Also the system remotely mounts your repository directory to the guest
JupyterHub machine.  So your `ml-python-class` directory that you cloned
will be visible from your JupyterHub server.  This provides an easy way to
get files into and out of your running dev environment.  Simply placing a
file in your `ml-python-class` directory should make it visible and usable
from your JupyterHub server instance.

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

**docs**/

Additional documentation for the class.  Class syllabus, and possible
assingment descriptions, slides and handouts will be placed here.

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

**Vagrantfile**

A standard vagrant init file.  Contains the configuration and
specifications to download and provision a vagrant box running
Anaconda Python3 and a JupyterHub/JupyterLab server.


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

#### Contact

`derek dot harter @ tamuc dot edu`
