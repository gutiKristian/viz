# Fundamentals of visualization

Topics:
- Basic metrics for evaluating the quality of visualization
- Visual variables 
- Basic visualization techniques for 1D, 2D, 3D and 4D data. - Volumetric datam, visualization of explicit and implicit surfaces. Geovisualization - choropleth maps, cartograms.

Sources:

 [PV251](https://is.muni.cz/auth/predmet/fi/podzim2023/PV251) lecture 1, 2, 4

[Ward et al.](https://doi.org/10.1201/9780429108433)
# Visualisation - quick review

**What is visualisation:**

  *Displaying a given information using a graphical representation.*

  *Tool to enable a User insight into Data.* &rarr; in most intuitive and informative way


  **Goal of visualisation research:** 

Study how people react and perceive the visualisations.
Based on this, create techniques and principles corresponding to the understanding.

**Visualisation pipeline:**

<span style="color: orange">*1. Data Modeling*</span>

Preparing the data form file or database. This is also a step where user would prepare them for faster access e.g., re-sample map data for a different zoom

<span style="color: orange">*2. Data Selection*</span>

Similar to the clipping in computer graphics (CG) pipeline. We choose what data should be visible.


<span style="color: orange">*3. Data to visual mappings*</span>


Mapping to graphical entities or their attributes.
The data can control:
- size of a point
- thickness of a line
- position
- color

And many more...

<span style="color: orange">*4. Scene parameter settings*</span>

Colour scheme, light, sound..,
these paramters are independent of the data.


<span style="color: orange">*5. Rendering (generation of visualisation)*</span>

Basically rendering the visualisation, in addition it can render additional information like annotations to improve the understanding.

**"How visualisation works:"**

Data generation &rarr; Data visualisation &rarr; Data interaction

Based on these phases three types of visualisations are identified:

1. Passive visualisation. All three phases are strictly separated. we process the data, visualise them and video or animation is a product. User cannot interact with the data.

2. Interactive visualsiation. Data generation phase is separated.

3. Interactive steering. Approach that allows user to interact with all three phases.


# Visualisation Metrics

We define two basci visualisation metrics that can be applied in all phases of the visualisation pipeline.

These metrics are *expressivness* and *effectivness*.

## Expressivness
- the ability of the visualization to convey the full range and depth of the data

It measures the concentration of information in a visualization, expressed as the ratio $M_{exp}$ of displayed information to intended information.

- $M_{exp}$ = 1:  Ideal expressiveness, where the visualization accurately conveys the intended information
- $M_{exp} < 1$: The visualization is ineffective, displaying less information than intended
- $M_{exp} > 1$: The visualization is problematic, displaying more information than necessary, potentially introducing errors and confusing the intended message

## Effectivness
- measures how quickly and accurately information can be interpreted and rendered at a reasonable cost

- can be quantified using $M_{eff}$

$M_{eff} = \frac{1}{1 + interpret + render}$

where "interpret" is the time to understand the visualisation, and "render" is time required to display it

$0 \leq M_{eff} \leq 1$, where higher $M_{eff}$ indicate short render time and quick interpretation...

# Visual Variables

The application of graphics to communicate information requires an understanding of graphics primitives and their properties. These graphics primitives are also called *marks*. We can encode different data to different marks.

The marks themselves do not convey required information, their spatial arrangement is crucial for effective communication – how they are placed in the screen space.

*In general, we can distinguish eight ways in which graphical objects can encode information:*

1. Position
2. Shape
3. Size
4. Brightness
5. Colour
6. Orientation
7. Texture
8. Movement

One should be able to talk about them with their own words, there's really no need to memorise this text, it serves as a helping hand:

## Position
- the location of individual graphic elements in the screen space
- has the greatest impact on the display of information,
because the spatial arrangement of graphics is the first step in understanding visualization

However, when all data is mapped to graphic symbols placed all in one place, we see only the symbol that was rendered last and lose information. In the best case scenario we would map each graphical symbol to its unique position but we are limited by the screen resolution.

To enhance the understanding another graphical elements may be added into the visualisation. For instance to describe the space, where we put these objects.
One common example of such additional graphics is axes.

## Shape
Shape or mark: points, lines, areas, volumes, and their combinations. We also call them glyphs or tags. When we talk about them, we can't take into account their size, birghtness, and orientation. These are completely different variables.
When using them we should consider whether we can easily distincs between them.

Shape and position variables formed the basis of all visualizations. Without them, it would be impossible to create a visualization. The remaining variables affect the way individual
representations are displayed.

## Size
Can be easily mapped to continuous and interval data variables.
Size is especially useful for datasets with low cardinality, because it is very difficult to distinguish glyphs that differ very little in size.

Some tips:


When the size is encoded to the thickness of a line, we can use only a very limited number of thickness threshold values to still assure that the differences are distinguishable.

Be careful about using perspective projection as this substantially influences the perception of size differences.

## Birghtness
We should keep in mind human perception, which cannot distinguish all existing brightness levels.

It is recommended that the brightness scale be linear to maximise the perceptibility of the differences.

## Colour
The difference between brightness and color is that color is defined by two
parameters - hue and saturation.

Using colour to display information requires mapping data values to individual colors. For this purpose, it is first necessary to define a so-called colormap

This is quite good adept for a question: Problems with the rainbow scale

The main issue of using the rainbow color scheme is the non-uniformity in the distribution of the individual colors and in perception. Using this scheme can lead to creating sharp artificial boundaries between colors (particularly involving yellow) that are not necessarily present in the underlying data.

## Orientation
Associated with subconscious perception, cannot be used for all shapes of marks (circle). The most suitable markers for displaying orientation are those that have their "main axis".

## Texture