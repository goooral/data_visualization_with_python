---
title: Color theory
layout: default
nav_order: 8
parent: Core design principles
---
# Color theory
<!-- color theory without Color Wheel and three basic maethods of color picking (opposite, triad, square)? bit strange... -->
Color is a powerful tool in data visualization. It can guide attention, group related elements, and evoke emotions. Understanding color theory helps create more effective and impactful visualizations. Feel free to paste the code bits into a [Jupyter notebook](http://colab.research.google.com/) and see how each of them works.
<!-- lack of consistency. Here is a Jupyter link, in previous subpage at same point isn't... -->
## Corporate colors implementation

Incorporating corporate colors into your visualizations helps maintain brand consistency and recognition.

### Key principles:

1. **Use the primary brand color for emphasis**: Highlight key data points or important information.
<!-- not working without showing the example on picture -->
2. **Incorporate secondary colors**: Use these for supporting elements or to create contrast.
<!-- not working without showing the example on picture -->
3. **Create a consistent color palette**: Develop a set of colors that complement your brand colors for use across all visualizations.
<!-- not working without showing the example on picture -->
4. **Consider color harmony**: Ensure your corporate colors work well together in various combinations.
<!-- not working without showing the example on picture -->
> **Tip:** Use [Adobe Color Tool](https://color.adobe.com/pl/create/color-wheel) tool to create your colour palettes.
<!-- maybe not full, but at least approximate name of the tool. User need basic sense of cybersecurity (THIS word can reffer also to unkown, unsecure webpage) -->
> **Tip:** Seaborn is equipped with quite a few color palettes by default. Take a look [HERE](https://seaborn.pydata.org/tutorial/color_palettes.html)

### Example:
<!-- Here should be an image, how this code is rendered -->
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
<!-- code snippet works -->
## Accessibility considerations

Ensuring your visualizations are accessible to all users, including those with color vision deficiencies, is crucial.

### Key principles:

1. **Don't rely solely on color**: Use patterns, labels, or icons in addition to color to convey information.
<!-- not working without showing the example on picture -->
2. **Ensure sufficient color contrast**: Make sure text and important elements stand out from the background.
<!-- not working without showing the example on picture -->
3. **Use colorblind-friendly palettes**: Choose color combinations that are distinguishable by people with various types of color blindness.
<!-- not working without showing the example on picture -->
4. **Provide alternative text**: Include descriptive alt text for images in digital formats.
<!-- show the examples of good alttext -->
### Example of a colorblind-friendly palette

![Eigth color stripes with highly contrasting colors](https://github.com/goooral/data_visualization_with_python/blob/main/images/colorblind.png?raw=true)
<!-- not working without description. Are those primary colors or other palette? What is the specification of this colorset and why is it recommended for this doc -->
### Example of a colorblind-friendly chart:
<!-- Here should be an image, how this code is rendered -->
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
<!-- code snippet works -->
> **Tip:** If you want to learn more about colorblind-friendly colors, try [HERE}(https://jfly.uni-koeln.de/color/).

## Emotional impact of colors

Colors can evoke different emotions and associations, which can be leveraged to enhance the message of your visualization.
<!-- show the examples. Color-call-to-action an so on -->
### Common color associations:

- **Red**: Warning, importance, negative.
- **Green**: Growth, nature, positive.
- **Blue**: Trust, calm, professionalism.
- **Yellow**: Optimism, energy, caution.
- **Purple**: Luxury, creativity, mystery.
- **Orange**: Enthusiasm, adventure, confidence.
- **Gray**: Neutrality, calm.
<!-- **Blue** should be blue in text. Or put icon with this color next to the color name. Group it in a logical way: from  cold to warm (warm to cold) in brightness order -->
### Key Principles:

1. **Choose colors that match your message**: Use colors that reinforce the emotion or idea you're trying to convey.
<!-- not working without showing the example on picture -->
2. **Especially pay attention to green and red**: It is common to associate green with *good* and red with *bad*. Keep this in mind and use these two colours accordingly.
<!-- not working without showing the example on picture -->
3. **Use color**: Maintain the same palette most of the time, using other colors to highlight elements when necessary.

### Example:
<!-- Here should be an image, how this code is rendered -->
```python
import matplotlib.pyplot as plt

categories = ['Q1', 'Q2', 'Q3', 'Q4']
values = [10000, 15000, 13000, 17000]

colors = ['#4CAF50', '#FFC107', '#FF9800', '#F44336']  # Green to Red
plt.bar(categories, values, color=colors)
plt.title('Quarterly Sales Performance')
plt.ylabel('Sales ($)')
plt.show()
```
<!-- code snippet works -->
In this example, we use a color gradient from green to red to show sales performance, leveraging the emotional associations of these colors:

- Green (Q1): Indicates a positive start, growth.
- Yellow (Q2): Suggests caution or a transition.
- Orange (Q3): Implies increasing urgency or attention needed.
- Red (Q4): Signifies importance or a critical period.

This color scheme quickly communicates the progression and urgency of sales performance throughout the year, even before the viewer examines the specific values.

## Conclusion

Color theory plays a crucial role in creating **effective and impactful data visualizations**. Remember these key points:

1. Use corporate colors strategically to maintain brand identity while ensuring clarity in your visualizations.
2. Always consider accessibility to make your visualizations inclusive and understandable for all audiences.
3. Leverage the emotional associations of colors to reinforce your message and guide viewer interpretation. At the same time, be careful of potential contradictions between your message and chosen colours.