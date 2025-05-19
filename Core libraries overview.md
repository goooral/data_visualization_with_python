---
title: Core python visualization libraries
layout: default
nav_order: 5
parent: An overview
---
# Core python visualization libraries

This section covers three fundamental libraries for data visualization in Python:
1. Matplotlib.
2. Seaborn.
3. Plotly.
  
Each library has its strengths and ideal use cases.

> **You can try to paste the code snippets into a [Jupyter notebook](https://colab.research.google.com){:target="_blank"} and see how it works.**

## Matplotlib: the foundation

Matplotlib is the base library for creating static, animated, and interactive visualizations in Python.

### Benefits:
- Highly customizable.
- Supports many plot types.
- Works well with NumPy and Pandas.

### When to use:
- For basic plots (line, scatter, bar).
- When you need fine-grained control over plot elements.
- When you're making a guide on data visualization with Python and need to show all basic libraries - this is as basic as it gets.

> **Tip:** *If you choose to take a look at the code snippets in action, simply create a new [Jupyter notebook](http://colab.research.google.com/){:target="_blank"}, paste the code into the code cell on your screen and click the "play" button next to the cell.*

### Example:

![A simple line chart done in matplotlib]({{ '/images/lib1.png' | relative_url }})

```python
import matplotlib.pyplot as plt
import numpy as np

# Create some sample data
x = [1, 2, 3, 4, 5]
y = [2, 4, 6, 8, 10]

# Create a new figure and axis
fig, ax = plt.subplots()

# Plot the data as a line chart
ax.plot(x, y, 'b-o')  # 'b-o' means blue line with circle markers

# Add labels and title
ax.set_xlabel('X-axis')
ax.set_ylabel('Y-axis')
ax.set_title('Simple Line Chart')

# Add a grid for better readability
ax.grid(True)

# Display the plot
plt.show()
```
>**Tip:** *Check out the [Matplotlib documentation](https://matplotlib.org/stable/index.html){:target="_blank"}.*

## Seaborn: aesthetically pleasing statistical visualizations

Seaborn is built on top of Matplotlib and provides a high-level interface for drawing attractive statistical graphics.

### Benefits:
- Attractive default styles.
- Built-in themes for professional-looking plots.
- Integrates well with Pandas DataFrames.

### When to use: 
- For statistical data visualization.
- When working with dataframes.
- To create plots quickly with less code.

### Example:

![A seaborn scatterplot with a regression line in a pleasant blue palette]({{ '/images/lib2.png' | relative_url }})

```python
import seaborn as sns
import pandas as pd

# Load a sample dataset
tips = sns.load_dataset("tips")

# Create a scatter plot with a regression line
sns.regplot(x="total_bill", y="tip", data=tips)
plt.title('Tip vs Total Bill')
plt.show()
```
>**Tip:** *Check out the [Seaborn documentation](https://seaborn.pydata.org){:target="_blank"}.*

## Plotly: interactive plots

Plotly creates interactive, publication-quality graphs that can be easily integrated into web applications.

### Benefits:
- Highly interactive plots.
- Supports a wide range of chart types.
- Easy to integrate with web applications.

### When to use:
- For creating interactive dashboards.
- When you need to share interactive plots online.
- For complex visualizations like 3D plots or animations.

### Example:

![A snapshot of a plotly scatterplot]({{ '/images/lib3.png' | relative_url }})

>**Tip:** *In this case, trying the code snippet by yourself is especially recommended. The picture above is merely a snapshot of this interactive plot.*

```python
import plotly.express as px
import pandas as pd

# Load a sample dataset
df = px.data.gapminder().query("year == 2007")

# Create an interactive scatter plot
fig = px.scatter(df, x="gdpPercap", y="lifeExp", size="pop", color="continent",
                 hover_name="country", log_x=True, size_max=60)
fig.show()
```
>**Tip:** *Check out the [Plotly documentation](https://plotly.com/python/){:target="_blank"}.*