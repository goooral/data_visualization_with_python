---
title: Chart selection framework
layout: default
nav_order: 7
parent: Core design principles
---
# Chart selection framework

Choosing the right chart type is crucial for effective data visualization. The right chart can make your data easy to understand, while the wrong one can confuse or mislead your audience. Here's a basic framework to help you select the most appropriate chart for your data.

> **You can try to paste the code snippets into a [Jupyter notebook](https://colab.research.google.com){:target="_blank"} and see how it works.**

## Basic principles of chart selection

1. **Understand your data**: 
   - What type of data do you have? (categorical, numerical, time series).
   - How many variables are you comparing?
   - Does it sum up to 100%?

2. **Know your purpose**:
   - What's the main message you want to convey?
   - Are you showing comparison, composition, distribution, or relationship?

3. **Keep it simple**:
   - Choose the simplest chart type that effectively communicates your message.
   - Don't add on unnecessary elements to the chart. Stick with the minimum.

## Common chart types and when to use them

### 1. Bar charts
**Use when**: Comparing categories or showing ranking

**Example**: *Comparing sales figures across different product categories.*

![A chart showing sales of four categories of products]({{ '/images/chart1.png' | relative_url }})

```python
import matplotlib.pyplot as plt

categories = ['A', 'B', 'C', 'D']
values = [40, 70, 10, 80]

plt.bar(categories, values)
plt.title('Sales by product category')
plt.xlabel('Category')
plt.ylabel('Sales')
plt.show()
```

**Tips**:
- Unless there is a specific reason not to do so, try to rank the data largest to smallest in order to improve readablity. In the example above, the reason not to rank them is the order of the categories resented on the chart.
- Consider your goal when decding between showing individual values and presenting numerical ranges on the axes.

### 2. Line charts
**Use when**: Showing trends over time

**Example**: *Revenue growth in 2024.*

![A line chart showing uneven price growth between January and May]({{ '/images/chart2.png' | relative_url }})

```python
import matplotlib.pyplot as plt

months = ['Jan', 'Feb', 'Mar', 'Apr', 'May']
prices = [100, 120, 110, 140, 130]

plt.plot(months, prices)
plt.title('Revenue growth in 2024')
plt.xlabel('Month')
plt.ylabel('Price')
plt.show()
```

**Tips**:
- Line charts are good at showing trends, not individual values.

### 3. Pie charts
**Use when**: Showing composition or parts of a whole 

**Example**: *Breakdown of company expenses.*

![A pie chart showing a breakdown of a few categories of typical company expenses]({{ '/images/chart3.png' | relative_url }})

```python
import matplotlib.pyplot as plt

expenses = ['Rent', 'Salaries', 'Supplies', 'Marketing']
values = [30, 45, 15, 10]

plt.pie(values, labels=expenses, autopct='%1.1f%%')
plt.title('Company Expense Breakdown')
plt.show()
```

**Tips**: 
- The values must sum up to 100%.
- Reconsider using this type of a chart if you have too many values to present.

### 4. Scatter plots
**Use when**: Showing relationship between two variables

**Example**: *Relationship between advertising spend and sales.*

![A chart showing five items and their positions on the sales and ad spend axes]({{ '/images/chart4.png' | relative_url }})

```python
import matplotlib.pyplot as plt

ad_spend = [10, 20, 30, 40, 50]
sales = [100, 140, 180, 200, 220]

plt.scatter(ad_spend, sales)
plt.title('Sales vs. Advertising Spend')
plt.xlabel('Ad Spend ($1000s)')
plt.ylabel('Sales ($1000s)')
plt.show()
```
### 5. Histograms
**Use when**: Showing distribution of a single variable

**Example**: *Distribution of test scores in an internal training programme.*

![A histogram showing statistical distribution of test scores]({{ '/images/chart5.png' | relative_url }})

```python
import matplotlib.pyplot as plt
import numpy as np

scores = np.random.normal(70, 10, 100)

plt.hist(scores, bins=10)
plt.title('Distribution of test scores')
plt.xlabel('Score')
plt.ylabel('Frequency')
plt.show()
```

>**Tip:** *This may look like a bar chart, however it presents a fundamentally different type of data. Take a look at [this blogpost](https://www.storytellingwithdata.com/blog/2021/1/28/histograms-and-bar-charts){:target="_blank"} to read more about the difference.*
