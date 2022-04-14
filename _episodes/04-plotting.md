---
title: "Visualizing data in Python"
teaching: 0
exercises: 0
questions:
- "What are Variables?"
- "How to create a Variable?"
objectives:
- "To understand variables and the rules of naming variables"
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
we use plt.bar() function to plot a bar chart.x-coordinates of the left side of bars are passed along with the heights of bars.You can also give some names to x-axis coordinates by defining tick_labels
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

