# Readings: Data Analysis
## JupyterLab :Overview
JupyterLab enables you to work with documents and activities such as Jupyter notebooks, text editors, terminals, and custom components in a flexible, integrated, and extensible manner. For a demonstration of JupyterLab and its features, you can view this video:

[How to Use JupyterLab + Notebook shortcuts](https://www.youtube.com/watch?v=A5YyoCKxEOU&ab_channel=Jupyter%2FIPython)

You can arrange multiple documents and activities side by side in the work area using tabs and splitters. Documents and activities integrate with each other, enabling new workflows for interactive computing, for example:

- Code Consoles provide transient scratchpads for running code interactively, with full support for rich output. A code console can be linked to a notebook kernel as a computation log from the notebook, for example.

- Kernel-backed documents enable code in any text file (Markdown, Python, R, LaTeX, etc.) to be run interactively in any Jupyter kernel.

- Notebook cell outputs can be mirrored into their own tab, side by side with the notebook, enabling simple dashboards with interactive controls backed by a kernel.

- Multiple views of documents with different editors or viewers enable live editing of documents reflected in other viewers. For example, it is easy to have live preview of Markdown, Delimiter-separated Values, or Vega/Vega-Lite documents.

JupyterLab also offers a unified model for viewing and handling data formats. JupyterLab understands many file formats (images, CSV, JSON, Markdown, PDF, Vega, Vega-Lite, etc.) and can also display rich kernel output in these formats. See File and Output Formats for more information.


## NumPy Tutorial: Data Analysis with Python

NumPy is a commonly used Python data analysis package. By using NumPy, you can speed up your workflow, and interface with other packages in the Python ecosystem, like scikit-learn, that use NumPy under the hood. NumPy was originally developed in the mid 2000s, and arose from an even older package called Numeric. This longevity means that almost every data analysis or machine learning package for Python leverages NumPy in some way.

## What we can do by using Numpy:
Before using NumPy, we’ll first try to work with the data using Python and the csv package. We can read in the file using the csv.reader object, which will allow us to read in and split up all the content from the ssv file.
- Creating A NumPy Array:
  - We can create a NumPy array using the numpy.array function. If we pass in a list of lists, it will automatically create a NumPy array with the same number of rows and columns.
  - We can check the number of rows and columns in our data using the shape property of NumPy arrays: `wines.shape`
- Using NumPy To Read In Files:
  - It’s possible to use NumPy to directly read csv or other files into arrays. We can do this using the numpy.genfromtxt function.
  - Indexing NumPy Arrays: `wines[2,3]`
  - Slicing NumPy Arrays: `wines[0:3,3]`
  - Assigning Values To NumPy Arrays: `wines[1,5] = 10`
- NumPy Data Types:
  - You can find the data type of a NumPy array by accessing the dtype property: `wines.dtype`
  - Converting Data Types:
    - You can use the numpy.ndarray.astype method to convert an array to a different type. The method will actually copy the array, and return a new array with the specified data type. For instance, we can convert wines to the int data type: `wines.astype(int)`
- NumPy Array Operations:
NumPy makes it simple to perform mathematical operations on arrays. This is one of the primary advantages of NumPy, and makes it quite easy to do computations.
    - Single Array Math:
      - If you do any of the basic mathematical operations (/, *, -, +, ^) with an array and a value, it will apply the operation to each of the elements in the array.
- NumPy Array Methods:
  - In addition to the common mathematical operations, NumPy also has several methods that you can use for more complex calculations on arrays.
    - An example of this is the numpy.ndarray.sum method. This finds the sum of all the elements in an array by default: `wines[:,11].sum()`
    - There are several other methods that behave like the sum method, including:
    - numpy.ndarray.mean — finds the mean of an array.
    - numpy.ndarray.std — finds the standard deviation of an array.
    - numpy.ndarray.min — finds the minimum value in an array.
    - numpy.ndarray.max — finds the maximum value in an array.
    - You can find a full list of array methods [here](https://numpy.org/doc/stable/reference/arrays.ndarray.html).
- NumPy Array Comparisons:
    - NumPy makes it possible to test to see if rows match certain values using mathematical comparison operations like <, >, >=, <=, and ==.
- Reshaping NumPy Arrays
  - We can change the shape of arrays while still preserving all of their elements. This often can make it easier to access array elements. The simplest reshaping is to flip the axes, so rows become columns, and vice versa.
- Combining NumPy Arrays
  - With NumPy, it’s very common to combine multiple arrays into a single unified array. We can use numpy.vstack to vertically stack multiple arrays.
  - 
## Free NumPy Cheat Sheet
- If you’re interested in learning more about NumPy, check out our interactive course on [NumPy and Pandas](https://www.dataquest.io/course/python-for-data-science-intermediate/). You can register and do the first lessons for free.

- You also might like to take your NumPy skills to the next level with our [free NumPy cheat sheet](https://s3.amazonaws.com/dq-blog-files/numpy-cheat-sheet.pdf)!

## Bookmark/Skim
- [Numpy Arrays](https://www.tutorialspoint.com/numpy/index.htm)







