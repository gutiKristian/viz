# Visualization methods

 Visualization of multidimensional data - scatterplot matrix, parallel coordinates, dimension stacking. Visualization of hierarchical structures - treemaps, radial techniques. Basic classes of interaction techniques, techniques used in screen space, object space, data, data structures.

PV251- lecture-07

 ## Multi-dimensional data

Consist of multiple types of attributes such as weitght, height, shoe size. Futhermore these triplets ($w_i$, $h_i$, $s_i$) form a set of multi-dimensional/ multi-variate data.

### Curse of dimensionality

The dimensionality affects the efficiency of algorithm. Data becomes sparse -- missing data.
When using such data for training ML algorithms the number of training samples grows exponentially with the number of dimensions.


The visualization of high dimensional data should provide us:

- way to detect clusters
- find regularities and irregularities
- identify relevant dimensions

# Techniques to visualize multi-dimensional data

**Hierarchical structures** -- store information about the relationships between data. The techniques to visualise such data can be divided into two categories:
- space filling -- making maximum use of screen space
- non-space filling -- the above is not a prioirity



## Line based
Vertical axis -- possible range of values, horizontal axis -- arrangment of records in a given dataset. Obviously this technique is not only for multivariatge data but rather single variable and juxtapositioning or superimpositioning is used to extend it to the multivariate datasets. 

The problem is overlaping lines:

- If dimensionss have common units.
  - stacked line chart technique (graph of the previous dimension is used as the basis for each additional dimension)
  - we could sort the records by one dimension
- dimensions do not have common units
  - multiple vertical axes with different labeling


## Radial techniques

Can be used to visualise hierarchical structures. For instance space-filling method to visualize the data is sunburst displays.

### RadViz
Force driven technique. Find equilibrium position of a point. For an N-dimensional data set, N "anchor" points are placed on the circumference of the circle, which represent the fixed ends of the N strings assigned to each data point. Usually to simplify things the circle has radius of 1 and the center is the origin.

Note that different placement and arrangement of anchors leads to different results and the transformation is lossy.


### Others
**Radial line chart**
-  drawn lines represent the offset from the circular 

**Radar**, **Star chart**, **Polar chart**, **Radial stacked bar chart**, **Radial bar charts**

## Treemaps

Common approach to visualize hierarchical structures. For instance sapce-filling rectangular treemap. The rectangle is divided into segments alternating the horizontal and vertical division.



# GPT Summary of lecture 7, 8, 9

## Summary of Visualization Techniques from "Vizz.pdf"

### Visualization Methods

**Scatterplots**
- *Scatterplot Matrix*: A grid of scatterplots, each representing a pair of dimensions. It visualizes N² pairs for N dimensions, with symmetry along the main diagonal, often used to show histograms for individual dimensions.
  
- *Parallel Coordinates*: Plots each dimension on a parallel axis, allowing for visualization of high-dimensional data by connecting data points across these axes.

- *Dimension Stacking*: Maps multidimensional data into a 2D space by hierarchically dividing the dimensions and displaying them in nested grids
  
### Visualization of Multidimensional Data

**Multiple Displays**
- *Dimension Subsetting*: Allows selection of a subset of dimensions to visualize. Utilizes algorithms to identify dimensions with the most relevant information.

- *Dimension Reduction*: Techniques like PCA (Principal Component Analysis) or Multidimensional Scaling reduce the number of dimensions while preserving relationships between data points.

- *Dimension Embedding*: Maps dimensions to graphic attributes like color, size, and shape 

### Visualization of Hierarchical Structures

**Treemaps**
- Visualizes hierarchical data using nested rectangles. Each branch of the hierarchy is represented by a colored rectangle containing smaller rectangles representing sub-branches.

**Radial Techniques**
- Represent hierarchical data in a circular layout, with the root at the center and branches radiating outward. This includes techniques like Radial Tree and Sunburst diagrams 
  
### Basic Classes of Interaction Techniques

**Screen Space Techniques**
- Techniques focused on optimizing the use of available screen space for visualization. Examples include:
  - *Zooming*: Allows users to focus on a specific area by enlarging it.
  - *Panning*: Moves the view to different parts of the visualization.
  - *Focus+Context*: Combines detailed views (focus) with an overview (context) to maintain orientation.

**Object Space Techniques**
- Interaction techniques that involve manipulation of the data objects themselves, such as:
  - *Selecting*: Highlighting or isolating particular data points for detailed examination.
  - *Filtering*: Removing data points that do not meet certain criteria to reduce clutter.
  - *Rearranging*: Changing the order or position of data points to reveal patterns.

**Data Interaction Techniques**
- Techniques for interacting directly with the data, including:
  - *Dynamic Queries*: Allow users to interactively change parameters of the data query and instantly see the results. This can involve sliders, checkboxes, or other controls to filter data on-the-fly.
  - *Brushing*: Highlighting data points across multiple linked visualizations to show their relationships.
  - *Linking*: Connecting different visualizations such that interactions in one (e.g., selecting a data point) are reflected in another.

**Data Structure Techniques**
- Focus on manipulating the underlying data structures, such as:
  - *Sorting*: Arranging data points based on a particular order, like ascending or descending values.
  - *Grouping*: Clustering data points into categories based on shared attributes.
  - *Clustering*: Using algorithms to group similar data points together to identify patterns 