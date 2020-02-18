# Getting set up for GISC 425
This course explores many of the most widely used free tools used for geographical computing in the [Python](https://python.org) ecosystem. The lab computers have these installed and ready to go and you are free to work on those machines when doing work for this class. This notebook provides instructions and links should you wish to setup an identical environment on your own machine so as to be able to work in other places and at other times.

## A list of what we are using
The tools we will be using are:

+ the [Python](https://python.org) programming language
+ [Conda](https://conda.io) a suite of programs that makes managing Python much easier
+ [JupyterLab](https://jupyterlab.org) a browser-based computing notebook environment (this document is presented in a notebook file)
+ A collection of Python libraries and packages that we will use

I will describe each of these in more detail below, before explaining how to install them on your own machine.

### The Python programming language
[Python](https://python.org) is a widely used, general-purpose programming language. It is regarded as easy to learn, yet it is very powerful. It is good at most things we need a programming language to be good at, the only major exceptions being client-side interactions on websites and really high-performance applications. For our purposes it is ideal, particularly the 'easy to learn' part.


```python
# Don't worry about this code too much
import IPython
IPython.display.IFrame('https://imgs.xkcd.com/comics/python.png',550,620)
```

### Conda
One other weakness of Python, partly a result of its wide applicability, is that deploying it can be a major headache. 

Python comes preinstalled on the MacOS and Linux operating systems, and it is very likely that installed software also comes with its own flavour of Python. For example, *ArcGIS* installs its own copy of Python which can be used for customization tasks. *QGIS* has its own copy too, as do many other applications. This means that it is hard to know what might happen when you type

    python

in a command line, and in particular which version of Python will run. On top of that, when we need to use a whole collection of packages (see below) it is important that we install compatible versions, so that we don't enter ***dependency hell***.


```python
IPython.display.IFrame('https://imgs.xkcd.com/comics/python_environment.png',550,520)
```

The solution to this problem is to use *virtual environments* to manage potentially many different versions of Python on a single machine in such a way that they don't get in one another's way.

[Conda](https://conda.io/en/master/) is a tool for doing just this.

### JupyterLab
[JupyterLab](https://github.com/jupyterlab/jupyterlab) is a browser-based environment that can be used to share program code in a *notebook* format that makes it easy to run the code a piece at a time, to edit code to see how that changes things, and to generally experiment and 'play' with computer code in an interactive way. I have chosen it as the preferred platform within which we will learn Python programming in this class, at least to begin with.

There are better ways to develop and test larger and more complicated software projects than notebooks (and we will look at these towards the end of the course), but to start, I think you will enjoy the notebook environment.

In particular, it allows me to provide you with a lot of help to start out, and slowly reduce the amount of code I provide so that over time you are taking more responsibility for writing your own code, as you become more proficient.

### A bunch of Python geospatial packages
The above three elements provide the basic architecture for the computing environment we will work in during this class. The nuts and bolts, or building blocks that we will be working with are a collection of *modules* (that's their proper name but they often get called *libraries* or *packages*). These provide the kinds of functionality (e.g. reading and writing shapefiles, projecting geographic coordinates) that we need to build geospatial applications and do geographic analysis. 

Some of the packages we'll be working with are listed below.

+ [`GDAL`](https://pypi.org/project/GDAL/) is the Geographic Data Abstraction Library which handles a lot of low-level geospatial data management and manipulation, which lots of other packages need to work properly
+ [`fiona`](https://github.com/Toblerity/Fiona) handles reading and writing data formats and [`shapely`](https://pypi.org/project/Shapely/) deals with basic geometry operations such as buffering and so on
+ [`geopandas`](http://geopandas.org/) is a simple library for dealing with classic geometry-attributes spatial data (shapefiles are an example) in a convenient way
+ [`matplotlib`](https://matplotlib.org/) provides plotting functionality and is used by `geopandas` to make simple maps
+ [`mplleaflet`](https://github.com/jwass/mplleaflet) makes simple (leaflet) web maps from `matplotlib` maps
+ numerical Python [`numpy`](http://www.numpy.org/) and scientifif Python [`scipy`](https://www.scipy.org/) are general purpose scientific computing libraries that provide analytical tools beyond the basic functions in the Python base `math` module
+ [`pysal`](http://pysal.org/) provides a lot of functionality useful for spatial analysis
+ [`networkx`](https://networkx.github.io/) lets us store, manipulate and analyse network data
+ [`arcpy`](https://desktop.arcgis.com/en/arcmap/10.5/analyze/arcpy/what-is-arcpy-.htm) and [`PyQGIS`](https://docs.qgis.org/testing/en/docs/pyqgis_developer_cookbook/index.html) are respectively the Python *Application Programming Interfaces* (APIs) for ESRI's *ArcGIS* and the *QGIS* desktop GIS programs. We won't actually install these&mdash;they come with those platforms&mdash;but we'll probably find reason to access them.

## Installation
That's a lot of stuff. 

Fortunately, installation is not *too* hard, because we will be using Conda to handle all the complexities.  Versions are available for all three major operating systems.  The easiest way to get started is to install `minconda`. The installation instructions are here: [conda.io/projects/conda/en/latest/user-guide/install/index.html#regular-installation](https://conda.io/projects/conda/en/latest/user-guide/install/index.html#regular-installation)

You can check that installation went OK by typing

    conda list

at a command line. If everything is OK, you should see a list of installed packages.

With `conda` installed, at the command line enter (copy and paste it)

    conda create -n g425 -c conda-forge geopandas pysal jupyterlab ipywidgets networkx

Respond to the various prompts and watch as `conda` downloads all the needed packages and builds an environment called `g425` which you'll be able to use for this course.

When it's done, at the command line type either on Mac or Linux type

    source activate g425

or on Windows *at the Anaconda prompt* type

    conda activate g425

to work in the environment. 

Once the environment is running, when you type python related commands they will run using the packages installed in the environment *not* system default packages or others installed by programs such as *ArcGIS*. To check things are working you could open Python and try importing `geopandas` (the colours are to make it easier to read, you likely won't see them on your machine):

```bash
(gisc425) osullid3@geoadmin-XPS-15-9570:~$ python
```
```python
Python 3.7.1 | packaged by conda-forge | (default, Nov 13 2018, 18:33:04) 
[GCC 7.3.0] :: Anaconda, Inc. on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import geopandas
>>>
```

If you get an error message something has gone wrong (ask for help!)

To exit Python, type `exit()`. To terminate the environment type either

`source deactivate` (MacOS or Linux)

or

`conda deactivate` (Windows)


```python

```