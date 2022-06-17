# Data Analysis using Numpy and Pandas
## Created By **Md. Ariful Islam**



[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

> When python was created, the main focus was on creating applications (web and otherwise) with the least anount of effort. Python, at that time, boasted of a python command line where one could run pieces of code to test them and once they worked fine, they could be incorporated into the main application code. So, a lot of programming time was saved, and people (including me) liked it. (I happen to come from a C and Perl background before I befriended Python, and I fell in love at the first sight).

>Out came some of python's wonderful packages, frameworks and libraries to handle big data, numerical analysis, spatial analysis (things like face recognition), etc, and the two major packages in use today for such purposes are Numpy and Pandas. So here, we will take a rather shallow view of them since space is limited, but we will try to cover all aspects of the packages mentioned above (Each of these 2 packages can be written as books with atleast 300 pages each, so trying to go deep into them would not be possible here).



### **Below are  some of the common features provided by the NumPy library:**

- Enable to work on homogenous datasets using the easy and fast framework
- Helps to build data objects with multiple dimensions
- Provides robust matrix manipulation methods
- Helps to broadcast the applied operations
- Consists of various other packages such as Seaborn, Matplotlib, etc, which can make your work easier and efficient
- Functions as a universal data structure in OpenCV for filter kernels, images, etc


### **Below are some of the common features provided by Pandas library:**

- It helps to pivot the datasets
- Pandas enable you to join and merge various datasets
- It enables to handle the missing data and data alignment
- It helps to deal with integrated indexing
- Pandas include the tools for reading and writing data in-memory data structures and multiple file formats
- It supports hierarchical axis indexing for converting high-dimensional data into lower-dimensional data

### **Installation**
```python
C:\Users\Your Name>pip install pandas
```
### **Import Pandas**
Once Pandas is installed, import it in your applications by adding the ***import*** keyword:
```python
import pandas
```
Now Pandas is imported and ready to use.
```python
mydataset = {
  'cars': ["BMW", "Volvo", "Ford"],
  'passings': [3, 7, 2]
}
myvar = pandas.DataFrame(mydataset)
print(myvar)
```


### **Pandas as pd**
Pandas is usually imported under the **pd** alias
> alias: In Python alias are an alternate name for referring to the same thing.
```python
import pandas as pd
```
### **Checking Pandas Version**

```python
import pandas as pd
print(pd.__version__)
```

## **Pandas Series**
### **What is a Series?**
> A Pandas Series is like a column in a table.
It is a one-dimensional array holding data of any type.

```python
import pandas as pd
a = [1, 7, 2]
myvar = pd.Series(a)
print(myvar)
```

### **Labels**
> If nothing else is specified, the values are labeled with their index number. First value has index 0, second value has index 1 etc.

```python
print(myvar[0])
```
### **Create Labels**
> With the index argument, you can name your own labels.
```python
import pandas as pd
a = [1, 7, 2]
myvar = pd.Series(a, index = ["x", "y", "z"])
print(myvar)
```
### **Key / value Objects as series**
> Create a simple Pandas Series from a dictionary:
```python
import pandas as pd
calories = {"day1": 420, "day2": 380, "day3": 390}
myvar = pd.Series(calories)
print(myvar)
```
## **DataFrames**
> Data sets in Pandas are usually multi-dimensional tables, called DataFrames.
Series is like a column, a DataFrame is the whole table.
```Python
import pandas as pd
data = {
  "calories": [420, 380, 390],
  "duration": [50, 40, 45]
}
myvar = pd.DataFrame(data)
print(myvar)
```
### ***What is a Dataframe?***
> A Pandas DataFrame is a 2 dimensional data structure, like a 2 dimensional array, or a table with rows and columns.

```Python
import pandas as pd
data = {
  "calories": [420, 380, 390],
  "duration": [50, 40, 45]
}
#load data into a DataFrame object:
df = pd.DataFrame(data)
print(df) 
```
### **Locate Row**
> Pandas use the loc attribute to return one or more specified row(s)
```Python
#refer to the row index:
print(df.loc[0])
```

### **Named Indexes**
> With the index argument, you can name your own indexes.

```Python
import pandas as pd
data = {
  "calories": [420, 380, 390],
  "duration": [50, 40, 45]
}
df = pd.DataFrame(data, index = ["day1", "day2", "day3"])
print(df) 
```
### **Locate Named Indexes**
> Use the named index in the loc attribute to return the specified row(s).

```Python
#refer to the named index:
print(df.loc["day2"])
```
### **Load Files Into a DataFrame**
> If your data sets are stored in a file, Pandas can load them into a DataFrame.

```Python
import pandas as pd
df = pd.read_csv('data.csv')
print(df) 
```
## **Pandas Read CSV**
### **Read CSV Files**
- A simple way to store big data sets is to use CSV files (comma separated files).
- CSV files contains plain text and is a well know format that can be read by everyone including Pandas.
- In our examples we will be using a CSV file called 'data.csv'.
- **Download data.csv**. or **Open data.csv**

```Python
import pandas as pd
df = pd.read_csv('data.csv')
print(df.to_string()) 
```
> Print the DataFrame without the to_string() method:

```Python
import pandas as pd
df = pd.read_csv('data.csv')
print(df) 
```

### **Max_rows**
> You can check your system's maximum rows with the ***pd.options.display.max_rows*** statement.
```Python
import pandas as pd
print(pd.options.display.max_rows) 
```
> Increase the maximum number of rows to display the entire DataFrame:
```Python
import pandas as pd
pd.options.display.max_rows = 9999
df = pd.read_csv('data.csv')
print(df) 
```
## **Pandas Read JSON**
### **Read JSON**

- Big data sets are often stored, or extracted as JSON.
- JSON is plain text, but has the format of an object, and is well known in the world of programming, including Pandas.
- In our examples we will be using a JSON file called **'data.json'**.
```Python
import pandas as pd
df = pd.read_json('data.json')
print(df.to_string()) 
```

### **Dictionary as JSON**

> JSON = Python Dictionary
> JSON objects have the same format as Python dictionaries.

```Python
import pandas as pd
data = {
  "Duration":{
    "0":60,
    "1":60,
    "2":60,
    "3":45,
    "4":45,
    "5":60
  },
  "Pulse":{
    "0":110,
    "1":117,
    "2":103,
    "3":109,
    "4":117,
    "5":102
  },
  "Maxpulse":{
    "0":130,
    "1":145,
    "2":135,
    "3":175,
    "4":148,
    "5":127
  },
  "Calories":{
    "0":409,
    "1":479,
    "2":340,
    "3":282,
    "4":406,
    "5":300
  }
}
df = pd.DataFrame(data)
print(df)
```

## **Pandas - Analyzing DataFrames**
### **Viewing the Data**
> One of the most used method for getting a quick overview of the DataFrame, is the head() method.
 The head() method returns the headers and a specified number of rows, starting from the top.

```Python
import pandas as pd
df = pd.read_csv('data.csv')
print(df.head(10))
```
> Print the first 5 rows of the DataFrame:

```Python
import pandas as pd
df = pd.read_csv('data.csv')
print(df.head())
```
> There is also a tail() method for viewing the last rows of the DataFrame.
The tail() method returns the headers and a specified number of rows, starting from the bottom.

> Print the last 5 rows of the DataFrame:
```Python
print(df.tail()) 
```

### **Info About the Data**
> The DataFrames object has a method called info(), that gives you more information about the data set.
```Python
print(df.info()) 
```

### **Null Values**

> The info() method also tells us how many Non-Null values there are present in each column, and in our data set it seems > like there are 164 of 169 Non-Null values in the "Calories" column.

> Which means that there are 5 rows with no value at all, in the "Calories" column, for whatever reason.

# **Cleaning Data**
> Data cleaning means fixing bad data in your data set.

Bad data could be:
- Empty cells
- Data in wrong format
- Wrong data
- Duplicates

## **Pandas - Cleaning Empty Cells**
### **Remove Rows**
> One way to deal with empty cells is to remove rows that contain empty cells.
This is usually OK, since data sets can be very big, and removing a few rows will not have a big impact on the result.

> Return a new Data Frame with no empty cells:
```Python
import pandas as pd
df = pd.read_csv('data.csv')
new_df = df.dropna()
print(new_df.to_string())
```
> Remove all rows with NULL values:
```Python
import pandas as pd
df = pd.read_csv('data.csv')
df.dropna(inplace = True)
print(df.to_string())
```

### **Replace Empty Values**
> Another way of dealing with empty cells is to insert a new value instead.
This way you do not have to delete entire rows just because of some empty cells.
The **fillna()** method allows us to replace empty cells with a value:

>Replace NULL values with the number 130:
```Python
import pandas as pd
df = pd.read_csv('data.csv')
df.fillna(130, inplace = True)
```

### **Replace Only For Specified Columns**
> The example above replaces all empty cells in the whole Data Frame.
 To only replace empty values for one column, specify the column name for the DataFrame:

> Replace NULL values in the "Calories" columns with the number 130:

```Python
import pandas as pd
df = pd.read_csv('data.csv')
df["Calories"].fillna(130, inplace = True)
```

### **Replace Using Mean, Median, or Mode**
> A common way to replace empty cells, is to calculate the mean, median or mode value of the column.
Pandas uses the mean() median() and mode() methods to calculate the respective values for a specified column:

> Calculate the MEAN, and replace any empty values with it:

```Python
import pandas as pd
df = pd.read_csv('data.csv')
x = df["Calories"].mean()
df["Calories"].fillna(x, inplace = True)
```

> Calculate the MEDIAN, and replace any empty values with it:

```Python
import pandas as pd
df = pd.read_csv('data.csv')
x = df["Calories"].median()
df["Calories"].fillna(x, inplace = True)
```
> Calculate the MODE, and replace any empty values with it:

```Python
import pandas as pd
df = pd.read_csv('data.csv')
x = df["Calories"].mode()[0]
df["Calories"].fillna(x, inplace = True)
```
## **Pandas - Cleaning Data of Wrong Format**
### **Data of Wrong Format**
> Cells with data of wrong format can make it difficult, or even impossible, to analyze data.
To fix it, you have two options: remove the rows, or convert all cells in the columns into the same format.

### **Convert Into a Correct Format**
> In our Data Frame, we have two cells with the wrong format. Check out row 22 and 26, the 'Date' column should be a string that represents a date:
Let's try to convert all cells in the 'Date' column into dates.
Pandas has a to_datetime() method for this:

```Python
import pandas as pd
df = pd.read_csv('data.csv')
df['Date'] = pd.to_datetime(df['Date'])
print(df.to_string())
```
### **Removing Rows**
> The result from the converting in the example above gave us a NaT value, which can be handled as a NULL value, and we can remove the row by using the dropna() method.

> Remove rows with a NULL value in the "Date" column:
```Python
df.dropna(subset=['Date'], inplace = True)
```

## **Pandas - Fixing Wrong Data**
### **Wrong Data**
> "Wrong data" does not have to be "empty cells" or "wrong format", it can just be wrong, like if someone registered "199" instead of "1.99".
Sometimes you can spot wrong data by looking at the data set, because you have an expectation of what it should be.

### **Replacing Values**
> Set "Duration" = 45 in row 7:
```Python
df.loc[7, 'Duration'] = 45
```

### **Removing Rows**
> Delete rows where "Duration" is higher than 120:
```Python
for x in df.index:
  if df.loc[x, "Duration"] > 120:
    df.drop(x, inplace = True)
```

## **Pandas - Removing Duplicates**
### **Discovering Duplicates**
> Duplicate rows are rows that have been registered more than one time.

> Returns True for every row that is a duplicate, othwerwise False:
```Python
print(df.duplicated())
```

### **Removing Duplicates**
> Remove all duplicates:
```Python
df.drop_duplicates(inplace = True)
```
## **Pandas - Data Correlations**
### **Finding Relationships**

- A great aspect of the Pandas module is the corr() method.
- The corr() method calculates the relationship between each column in your data set.
- The examples in this page uses a CSV file called: 'data.csv'.
- Download **data.csv**. or Open **data.csv**

>Show the relationship between the columns:
```Python
df.corr()
```

> **What is a good correlation?** It depends on the use, but I think it is safe to say you have to have at least 0.6 (or -0.6) to call it a good correlation.

> **Perfect Correlation:**
We can see that "Duration" and "Duration" got the number 1.000000, which makes sense, each column always has a perfect relationship with itself.

>   **Good Correlation:**
"Duration" and "Calories" got a 0.922721 correlation, which is a very good correlation, and we can predict that the longer you work out, the more calories you burn, and the other way around: if you burned a lot of calories, you probably had a long work out.

> **Bad Correlation:**
"Duration" and "Maxpulse" got a 0.009403 correlation, which is a very bad correlation, meaning that we can not predict the max pulse by just looking at the duration of the work out, and vice versa.

## **Pandas - Plotting**
> Pandas uses the plot() method to create diagrams.
We can use Pyplot, a submodule of the Matplotlib library to visualize the diagram on the screen.

> Import pyplot from Matplotlib and visualize our DataFrame:
```Python
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('data.csv')
df.plot()
plt.show()
```

## **Scatter Plot**
> Specify that you want a scatter plot with the kind argument:
kind = 'scatter'
A scatter plot needs an x- and a y-axis.

```Python
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('data.csv')
df.plot(kind = 'scatter', x = 'Duration', y = 'Calories')
plt.show()
```

> A scatterplot where there are no relationship between the columns:
```Python
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('data.csv')
df.plot(kind = 'scatter', x = 'Duration', y = 'Maxpulse')
plt.show()
```

### **Histogram**
> Use the kind argument to specify that you want a histogram:
kind = 'hist'
A histogram needs only one column.

```Python
df["Duration"].plot(kind = 'hist')
```
# **Numpy**

### **Installation**

```Python
pip install numpy
```
### **load numpy**

```Python
import numpy as np
```
### **The Basics**
```Python
a=np.array([1,2,3],dtype='int32')
b = np.array([[1.0,2.0,3.0],[3.0,4.0,5.0]])
```
### **Get Dimension**
```python
a.ndim
```

### **Get Shape**
```python
a.shape
```
### **Get Type**
```python
a.dtype
```

### **Get Size**
```python
a.itemsize
```
### **Get Total size**
```python
a.size
```

## **Accessing / changing specific elements, rows, columns etc**
```python
a=np.array([1,2,3,4,5,6,7],[8,9,10,11,12,13,14])
```
### **Get specific element [ row, column ]**
```Python
a[1,5]
```
### **Get a specific row**
```Python
a[0,:]
```
### **Get a specific column**
```Python
a[:,2]
```
### **Getting a little more fancy [startindex,stopindex,stepsize]**
```Python
a[0,1:-1:2]
```
### **Change an element**
```Python
a[1,5]=20
```

## **Initializing Different Arrays**

### **ALL 0s matrix**
```Python
np.zeros(5)
```
### **ALL 1s matrix**
```Python
np.ones(4,2,2)
```
### **Any other number**
```Python
np.full((2,2),99,dype='float32')
```

### **Any other number(full_like)**
```Python
np.full_like(a.shape,4)
```

### **Random Decimal Numbers**
```Python
np.random.rand(4,2)
```
### **Random Integer Numbers**
```Python
np.random.randint(7)
```
### **identity matrix**
```Python
np.indetity(3)
```
