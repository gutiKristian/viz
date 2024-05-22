# Fundamentals of visualization

Topics:
- Basic metrics for evaluating the quality of visualization
- Visual variables 
- Basic visualization techniques for 1D, 2D, 3D and 4D data. - Volumetric datam, visualization of explicit and implicit surfaces. Geovisualization - choropleth maps, cartograms.

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
