# Analyzing Survey Data

We are studying the species and weight of animals caught in plots in our study area.
The data sets are stored in .csv each row holds information for a single animal,
and the columns represent record_id,month,day,year,plot,species,sex,wgt
The first few rows of our first file look like this:

"63","8","19","1977","3","DM","M","40"

"64","8","19","1977","7","DM","M","48"

"65","8","19","1977","4","DM","F","29"

"66","8","19","1977","4","DM","F","46"

"67","8","19","1977","7","DM","M","36"

### We want to:

* load that data into memory,
* calculate the average weight of the animals across all animals, and
* plot the result.
To do all that, we'll have to learn a little bit about programming.

### Objectives
* Explain what a library is, and what libraries are used for.
* Load an Pyhon/pandas library and use the things it contains.
* Read tabular data from a file into a program.
* Assign values to variables.
* Learn about data types
* Select individual values and subsections from data.
* Perform operations on arrays of data.
* Display simple graphs.

## Loading Data
----------------

Words are useful, but what's more useful are the sentences and stories we use them to build.
Similarly, while a lot of powerful tools are built into languages like Python,
even more lives in the libraries they are used to build.
Importing a library is like getting a piece of lab equipment out of a storage locker
and setting it up on the bench.
Once it's done, we can ask the library to do things for us.

If someone want to use python for data analysis the best solution is to use [Python Data Analysis Library](http://pandas.pydata.org/) (a.k.a. pandas). It provides data structures, produces high quality plots with [matplotlib](http://matplotlib.org/), and integrates nicely with other libraries that expect [NumPy](http://www.numpy.org/) arrays.

### Installing pandas

If you use pip installing pandas should be easy:

```
[user@host:python]$sudo pip install pandas
```

For more complex scenarios, please see the [installation instructions](http://pandas.pydata.org/pandas-docs/stable/install.html).

To start working with pandas user should open ipython shell in folder with python lessons

```
[user@host:python]$ipython
```

then import pandas library into python shell

```python
import pandas
```

Secondly, let's locate and read our data. Because it is in a CSV file, we can use pandas' `read_csv` function to pull it directly into a [DataFrame](http://pandas.pydata.org/pandas-docs/stable/dsintro.html#dataframe). We

```python
pandas.read_csv("data/surveys.csv")
```

which gives **output**:

```
       record_id  month  day  year  plot species  sex  wgt
0              1      7   16  1977     2     NaN    M  NaN
1              2      7   16  1977     3     NaN    M  NaN
2              3      7   16  1977     2      DM    F  NaN
3              4      7   16  1977     7      DM    M  NaN
4              5      7   16  1977     3      DM    M  NaN
5              6      7   16  1977     1      PF    M  NaN
6              7      7   16  1977     2      PE    F  NaN
7              8      7   16  1977     1      DM    M  NaN
8              9      7   16  1977     1      DM    F  NaN
9             10      7   16  1977     6      PF    F  NaN
10            11      7   16  1977     5      DS    F  NaN
11            12      7   16  1977     7      DM    M  NaN
12            13      7   16  1977     3      DM    M  NaN
13            14      7   16  1977     8      DM  NaN  NaN
...
[35549 rows x 8 columns]
```

We could see, that there were 33549 rows parsed, each of them consisting 8 columns. Our call to `pandas.read_csv` read our file, but it haven't saved any data in memory. If we want that, we need to assign the data frame to a variable. A variable is just a name for a value, such as x, current_temperature, or subject_id. We can create a new variable simply by assigning a value to it using `=`. For example,

```python
weight_kg = 55
```

When we gave variable a value, we can print it:

```python
weight_kg
```

which gives **output**

```
55
```

and manipulate whit it, for example multiply it:

```python
3.5*weight_kg
```

which gives **output**

```
192.5
```

We can also change a variable's value by assigning it a new one and print out the information using 'print' to add text and values together:

```python
weight_kg = 52
print "person lost some weight and now weights", weight_kg
```

which gives **output**

```
person lost some weight and now weights  52
```

If we imagine the variable as a sticky note with a name written on it, assignment is like putting the sticky note on a particular value. This means that assigning a value to one variable does not change the values of other variables. For example, let's store the animal's weight in pounds in a variable:

```python
weight_lb = 2.2 * weight_kg
print "animal's weight in kilograms:", weight_kg, "and in pounds:", weight_lb
```

which gives **output**

```
animal's weight in kilograms: 52 and in pounds: 114.4
```

and then change variable weight_kg

```python
weight_kg = 80
print "animal weight in kilograms:", weight_kg, "but in pounds is still", weight_lb
```

which gives **output**

```
animal's weight in kilograms: 80 but in pounds is still 114.4
```

**Updating a Variable**

Since variable `weight_lb` doesn't "remember" where its value came from, it isn't automatically updated when variable `weight_kg` changes. This is different from the way spreadsheets work.

**Challenges**

Draw diagrams showing what variables refer to what values after each statement in the following commands:

```python
mass = 47.5
age  = 122
mass = mass * 2.0
age  = age - 20
```

**What is your answer?**


Variables also could be vectors or matricies.

```python
vector = [0,2.5]
matrix = [[0,2],[0,1]]
print vector, matrix
```


Therefore, we can also add to variable that are vectors, and update them by making them longer. 
For example, if we are creating a vector of animal weights, we could update that vector using its iternal `append` method. 

```print
weights = [100]
print weights
weights.append(80)
print weights
```

which gives **output**

```
[100]
[100, 80]
```
mns
```

**Output**

