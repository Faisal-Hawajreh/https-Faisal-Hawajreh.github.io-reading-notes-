# Pandas
## What kind of data does pandas handle?
To load the pandas package and start working with it, import the package. The community agreed alias for pandas is pd, so loading pandas as pd is assumed standard practice for all of the pandas documentation.
#### pandas data table representation
![image](https://pandas.pydata.org/pandas-docs/stable/_images/01_table_dataframe.svg)

A **DataFrame** is a 2-dimensional data structure that can store data of different types (including characters, integers, floating point values, categorical data and more) in columns. It is similar to a spreadsheet, a SQL table or the data.frame in R.

Each column in a DataFrame is a Series
![image](https://pandas.pydata.org/pandas-docs/stable/_images/01_table_series.svg)

When selecting a single column of a pandas DataFrame, the result is a pandas Series. To select the column, use the column label in between square brackets [].

- A pandas Series has no column labels, as it is just a single column of a DataFrame. A Series does have row labels.
- As illustrated by the max() method, you can do things with a DataFrame or Series. pandas provides a lot of functionalities, each of them a method you can apply to a DataFrame or Series. As methods are functions, do not forget to use parentheses ().
- The describe() method provides a quick overview of the numerical data in a DataFrame. 

Many pandas operations return a DataFrame or a Series. The describe() method is an example of a pandas operation returning a pandas Series or a pandas DataFrame.
- Import the package, aka import pandas as pd
- A table of data is stored as a pandas DataFrame
- Each column in a DataFrame is a Series
- You can do things by applying a method to a DataFrame or Series
 
## How do I read and write tabular data?

pandas provides the read_csv() function to read data stored as a csv file into a pandas DataFrame. pandas supports many different file formats or data sources out of the box (csv, excel, sql, json, parquet, …), each of them with the prefix read_*.

- Getting data in to pandas from many different file formats or data sources is supported by read_* functions.
- Exporting data out of pandas is provided by different to_*methods.
- The head/tail/info methods and the dtypes attribute are convenient for a first check.

## How do I select a subset of a DataFrame?

- When selecting subsets of data, square brackets [] are used.
- Inside these brackets, you can use a single column/row label, a list of column/row labels, a slice of labels, a conditional expression or a colon.
- Select specific rows and/or columns using loc when using the row and column names
- Select specific rows and/or columns using iloc when using the positions in the table
- You can assign new values to a selection based on loc/iloc.

## How to create plots in pandas?

- The .plot.* methods are applicable on both Series and DataFrames
- By default, each of the columns is plotted as a different element (line, boxplot,…)
- Any plot created by pandas is a Matplotlib object.

## How to create new columns derived from existing columns?

- Create a new column by assigning the output to the DataFrame with a new column name in between the [].
- Operations are element-wise, no need to loop over rows.
- Use rename with a dictionary or function to rename row labels or column names.

## How to calculate summary statistics?

- Aggregation statistics can be calculated on entire columns or rows
- groupby provides the power of the split-apply-combine pattern
- value_counts is a convenient shortcut to count the number of entries in each category of a variable

## How to reshape the layout of tables?

- Sorting by one or more columns is supported by sort_values
- The pivot function is purely restructuring of the data, pivot_table supports aggregations
- The reverse of pivot (long to wide format) is melt (wide to long format)

## How to combine data from multiple tables?

- Multiple tables can be concatenated both column-wise and row-wise using the concat function.
- For database-like merging/joining of tables, use the merge function.

## How to handle time series data with ease?

- Valid date strings can be converted to datetime objects using to_datetime function or as part of read functions.
- Datetime objects in pandas support calculations, logical operations and convenient date-related properties using the dt accessor.
- A DatetimeIndex contains these date-related properties and supports convenient slicing.
- Resample is a powerful method to change the frequency of a time series.

## How to manipulate textual data?

- String methods are available using the str accessor.
- String methods work element-wise and can be used for conditional indexing.
- The replace method is a convenient method to convert values according to a given dictionary.

## Videos
- [What is Pandas](https://www.youtube.com/watch?v=dcqPhpY7tWk&t=391s&ab_channel=PythonProgrammer)
## Bookmark/Skim
- [Master Pandas](https://towardsdatascience.com/be-a-more-efficient-data-scientist-today-master-pandas-with-this-guide-ea362d27386)
