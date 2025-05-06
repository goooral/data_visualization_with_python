---
title: Colors
layout: default
nav_order: 8
parent: Core design principles
---
# Colors

Color is a powerful tool in data visualization. It can guide attention, group related elements, and evoke emotions. Implementing color intentionally helps create more effective and impactful visualizations. 

> **You can try to paste the code snippets into a [Jupyter notebook](https://colab.research.google.com){:target="_blank"} and see how it works.**

## Corporate colors implementation

Incorporating corporate colors into your visualizations helps maintain brand consistency and recognition.

### Key principles:

1. **Use the primary brand color for emphasis**: Highlight key data points or important information.
2. **Incorporate secondary colors**: Use these for supporting elements or to create contrast.
3. **Create a consistent color palette**: Develop a set of colors that complement your brand colors for use across all visualizations.
4. **Consider color harmony**: Ensure your corporate colors work well together in various combinations.

> **Tip:** Use [Adobe Color Tool](https://color.adobe.com/pl/create/color-wheel) to create your colour palettes.

> **Tip:** Seaborn is equipped with quite a few color palettes by default. Take a look at [this part of its documentation](https://seaborn.pydata.org/tutorial/color_palettes.html){:target="_blank"}.

### Example:

![A chart with bars in four different colors](https://github.com/goooral/data_visualization_with_python/blob/main/images/colors1.png?raw=true)

```python
import matplotlib.pyplot as plt

# Define corporate colors
primary_color = '#007bff'    # Blue
secondary_color = '#6c757d'  # Gray
accent_color = '#ffc107'     # Yellow
extra_color = '#28a745'      # Green 

categories = ['A', 'B', 'C', 'D']
values = [4, 7, 1, 8]

# Assign different colors to each bar
bar_colors = [primary_color, secondary_color, accent_color, extra_color]

plt.bar(categories, values, color=bar_colors)
plt.title('Sales by Category', color=secondary_color)
plt.xlabel('Category', color=secondary_color)
plt.ylabel('Sales', color=secondary_color)
plt.show()
```

## Accessibility considerations

Ensuring your visualizations are accessible to all users, including those with color vision deficiencies, is crucial.

### Key principles:

1. **Don't rely solely on color**: Use patterns, labels, or icons in addition to color to convey information.
2. **Ensure sufficient color contrast**: Make sure text and important elements stand out from the background.
3. **Use colorblind-friendly palettes**: Choose color combinations that are distinguishable by people with various types of color blindness.
4. **Provide alternative text**: Include descriptive alt text for images in digital formats.
   
### Example of a colorblind-friendly palette

A colorblind-friendly palette example looks like this:

![Eigth color stripes with highly contrasting colors](https://github.com/goooral/data_visualization_with_python/blob/main/images/colorblind.png?raw=true)

> **Tip:** If you want to learn more about colorblind-friendly colors, take a look at [this extensive exploration of the topic](https://jfly.uni-koeln.de/color/){:target="_blank"}.

### Example of a colorblind-friendly chart:

And this is what a colorblind-palette looks like in action: 

![A chart with seven bars in highly contrasting colors](https://github.com/goooral/data_visualization_with_python/blob/main/images/colors2.png?raw=true)

```python
import matplotlib.pyplot as plt

# Colorblind-friendly palette
cb_colors = ['#E69F00', '#56B4E9', '#009E73', '#F0E442', '#0072B2', '#D55E00', '#CC79A7']

categories = ['A', 'B', 'C', 'D', 'E', 'F', 'G']
values = [4, 7, 1, 8, 3, 6, 5]

plt.bar(categories, values, color=cb_colors)
plt.title('Sales by Category (Colorblind-friendly)')
plt.show()
```

## Emotional impact of colors

Colors can evoke different emotions and associations, which can be leveraged to enhance the message of your visualization.

### Common color associations:

- **Red**: Warning, importance, negative.
- **Green**: Growth, nature, positive.
- **Blue**: Trust, calm, professionalism.
- **Yellow**: Optimism, energy, caution.
- **Purple**: Luxury, creativity, mystery.
- **Orange**: Enthusiasm, adventure, confidence.
- **Gray**: Neutrality, calm.

### Key Principles:

1. **Choose colors that match your message**: Use colors that reinforce the emotion or idea you're trying to convey.
2. **Especially pay attention to green and red**: It is common to associate green with *good* and red with *bad*. Keep this in mind and use these two colours accordingly.
3. **Use color**: Maintain the same palette most of the time, using other colors to highlight elements when necessary.

### Example:

![A chart presenting four bars where low score=red and high score=green](https://github.com/goooral/data_visualization_with_python/blob/main/images/colors3.png?raw=true)

```python
import matplotlib.pyplot as plt

categories = ['Q1', 'Q2', 'Q3', 'Q4']
values = [10000, 15000, 13000, 17000]

colors = ['#F44336', '#FFC107', '#FF9800', '#4CAF50']  # Green is good, red is bad
plt.bar(categories, values, color=colors)
plt.title('Quarterly Sales Performance')
plt.ylabel('Sales ($)')
plt.show()
```

In this example, we use a color gradient from green to red to show sales performance, leveraging the emotional associations of these colors. This color scheme quickly communicates the progression of sales performance throughout the year, even before the viewer examines the specific values.

## Conclusion

Color selection plays a crucial role in creating **effective and impactful data visualizations**. Remember these key points:

1. Use corporate colors strategically to maintain brand identity while ensuring clarity in your visualizations.
2. Always consider accessibility to make your visualizations inclusive and understandable for all audiences.
3. Leverage the emotional associations of colors to reinforce your message and guide viewer interpretation. At the same time, be careful of potential contradictions between your message and chosen colours.