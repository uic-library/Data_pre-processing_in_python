---
title: "Visualizing data in Python"
teaching: 0
exercises: 0
questions:
- "What do you need to visualize data in python?"
- "Types of plots in python"
objectives:
- "To understand Visualization in python"
---

## What do you need to visualize data in python?

To graph data in python, we need to use the __matplotlib__ library. More specifically, the __pyplot__ module of this library is the most useful module to plot data. To install this, type - __pip install matplotlib__

## Types of plots in python

We can plot the following graphs in python

* line
* Bar Chart
* Histogram
* Scatter plot
* Pie-chart

## Line Graph
Draws a line between x-axis and corresponding y-axis values.
- Define the x-axis and corresponding y-axis values as lists.
- Plot them on canvas using .plot() function.
- Give a name to x-axis and y-axis using .xlabel() and .ylabel() functions.
- Give a title to your plot using .title() function.
- Finally, to view your plot, we use .show() function.

~~~

import matplotlib.pyplot as plt


x = [1,2,3,4,5]

y = [1,4,9,16,25]

# plotting the points
plt.plot(x, y, color='green', linestyle='dashed', linewidth = 3,
         marker='o', markerfacecolor='blue', markersize=12)


plt.xlabel('x - axis: numbers')

plt.ylabel('y - axis: Square(x)')


plt.title('x^2')


plt.show()

~~~
{: .language-python}

## Bar Graph
- The plt.bar() function is used to plot a bar chart.
- x-coordinates of the left side of bars are passed along with the heights of bars.
- Name to x-axis coordinates by defining tick_labels
~~~
import matplotlib.pyplot as plt

# x-coordinates of left sides of bars
left = [1, 2, 3, 4, 5]

# heights of bars
height = [10, 24, 36, 40, 5]

# labels for bars
tick_label = ['one', 'two', 'three', 'four', 'five']

# plotting a bar chart
plt.bar(left, height, tick_label = tick_label,
		width = 0.8, color = ['red', 'green'])

# naming the x-axis
plt.xlabel('x - axis')
# naming the y-axis
plt.ylabel('y - axis')
# plot title
plt.title('My bar chart!')

# function to show the plot
plt.show()


~~~
{: .language-python}

## Histogram
- plt.hist() is used function to plot a histogram. 
- Frequencies are passed as a list. 
- The range is set by defining a tuple containing min and max values. 
- The next step is to “bin” the range of values. Binning means dividing the entire range of values into a series of intervals and then count how many values fall into each interval.

~~~
import matplotlib.pyplot as plt

# frequencies
ages = [2,5,70,40,30,45,50,45,43,40,44,
		60,7,13,57,18,90,77,32,21,20,40]

# setting the ranges and no. of intervals
range = (0, 100)
bins = 10

# plotting a histogram
plt.hist(ages, bins, range, color = 'green',
		histtype = 'bar', rwidth = 0.8)

# x-axis label
plt.xlabel('age')
# frequency label
plt.ylabel('No. of people')
# plot title
plt.title('My histogram')

# function to show the plot
plt.show()

~~~
{: .language-python}

## Scatter Plot

- plt.scatter() function is used to plot a scatter plot.
- Define x and corresponding y-axis values.
- Marker argument is used to set the character to use as a marker. Its size can be defined using the s parameter.

~~~
import matplotlib.pyplot as plt

# x-axis values
x = [1,2,3,4,5,6,7,8,9,10]
# y-axis values
y = [2,4,5,7,6,8,9,11,12,12]

# plotting points as a scatter plot
plt.scatter(x, y, label= "stars", color= "green",
			marker= "*", s=30)

# x-axis label
plt.xlabel('x - axis')
# frequency label
plt.ylabel('y - axis')
# plot title
plt.title('My scatter plot!')
# showing legend
plt.legend()

# function to show the plot
plt.show()

~~~
{: .language-python}

## Pie Chart

- Plot a pie chart by using plt.pie() method.
- Define the labels using a list called activities.
- Then, a portion of each label can be defined using another list called slices.
- Color for each label can also be defined using a list.

~~~
import matplotlib.pyplot as plt

# defining labels
activities = ['eat', 'sleep', 'work', 'play']

# portion covered by each label
slices = [3, 7, 8, 6]

# color for each label
colors = ['r', 'y', 'g', 'b']

# plotting the pie chart
plt.pie(slices, labels = activities, colors=colors,
		startangle=90, shadow = True, explode = (0, 0, 0.1, 0),
		radius = 1.2, autopct = '%1.1f%%')

# plotting legend
plt.legend()

# showing the plot
plt.show()

~~~
{: .language-python}
