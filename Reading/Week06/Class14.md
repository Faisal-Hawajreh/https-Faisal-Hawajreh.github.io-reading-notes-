# Readings: Data Visualization
### Matplotlib
Matplotlib is a comprehensive library for creating static, animated, and interactive visualizations in Python. Matplotlib makes easy things easy and hard things possible.

- Create publication quality plots.
- Make interactive figures that can zoom, pan, update.
- Customize visual style and layout.
- Export to many file formats .
- Embed in JupyterLab and Graphical User Interfaces.
- Use a rich array of third-party packages built on Matplotlib.
- 
### IPython

One of Python’s most useful features is its interactive interpreter. It allows for very fast testing of ideas without the overhead of creating test files as is typical in most programming languages. However, the interpreter supplied with the standard Python distribution is somewhat limited for extended interactive use.

The goal of IPython is to create a comprehensive environment for interactive and exploratory computing. To support this goal, IPython has three main components:

- An enhanced interactive Python shell.
- A decoupled two-process communication model, which allows for multiple clients to connect to a computation kernel, most notably the web-based notebook provided with Jupyter.
- An architecture for interactive parallel computing now part of the `ipyparallel` package.

All of IPython is open source (released under the revised BSD license).

if you want to read more about IPython [Link](https://ipython.readthedocs.io/en/stable/overview.html)

### pyplot

matplotlib.pyplot is a collection of functions that make matplotlib work like MATLAB. Each pyplot function makes some change to a figure: e.g., creates a figure, creates a plotting area in a figure, plots some lines in a plotting area, decorates the plot with labels, etc.

## Plot by using matplotlib

These are some plots:
![plot example](https://miro.medium.com/max/1400/1*swPzVFGpYdijWAmbrydCDw.png)

And these links can help us to know how to write code and what are the features that can we add on our graph:
- [pyplot tutorial](https://matplotlib.org/2.0.2/users/pyplot_tutorial.html)
- [pyplot API](https://matplotlib.org/2.0.2/api/pyplot_api.html)

there are many types of plots, figures and animetions.. such as : 
- plot
- scatter
- bar 
- stem 
- step
- fill between
- imshow 
- pcolormesh
- counter
- counterf
- barbs
- quiver
...

## Overview of seaborn plotting functions
Most of your interactions with seaborn will happen through a set of plotting functions.

Similar functions for similar tasks
The seaborn namespace is flat; all of the functionality is accessible at the top level. But the code itself is hierarchically structured, with modules of functions that achieve similar visualization goals through different means. Most of the docs are structured around these modules: you’ll encounter names like “relational”, “distributional”, and “categorical”.
![image](https://seaborn.pydata.org/_images/function_overview_8_0.png)

## What is Bokeh
Bokeh is an interactive visualization library that targets modern web browsers for presentation. It is good for:

Interactive visualization in modern browsers
Standalone HTML documents, or server-backed apps
Expressive and versatile graphics
Large, dynamic or streaming data
Easy usage from python (or Scala, or R, or...)
And most importantly:

**NO JAVASCRIPT REQUIRED**

Bokeh is an interactive visualization library for modern web browsers. It provides elegant, concise construction of versatile graphics, and affords high-performance interactivity over large or streaming datasets. Bokeh can help anyone who would like to quickly and easily make interactive plots, dashboards, and data applications.

------
this cheat sheet will summirize everything about plot:

- [Seaborn Cheat Sheet](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Python_Seaborn_Cheat_Sheet.pdf)


### Rescourses:
- [Matplotlib Tutorial](https://github.com/rougier/matplotlib-tutorial#figures-subplots-axes-and-ticks)
- [Seaborn Tutorial](https://seaborn.pydata.org/tutorial.html)
- [Bokeh Tutorial](https://mybinder.org/v2/gh/bokeh/bokeh-notebooks/master?filepath=tutorial%2F00%20-%20Introduction%20and%20Setup.ipynb)
