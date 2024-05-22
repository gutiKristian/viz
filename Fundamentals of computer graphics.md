# Fundamentals of computer graphics
(PB009, PV112, PV227)

- [x] Types of graphical primitives
- [ ] Principle of rasterization, framebuffer
- [ ] OpenGL
  - [ ] Block diagram
  - [ ] GLSL - vertex and fragment shader
  - [ ] Creating a GLSL program
  - [ ] Basic types of input and output variables
- [ ] Vertex Buffer Objects and Vertex Array Objects
- [ ] Textures: mapping, filtering, synthesis


## Graphical Primitives

### Point
The simplest graphical primitive.

### Line
Line is described by two endpoints (vertices). Two consecutive
vertices are always taken from the input array of vertices to form a line. If we have an odd number of vertices, the last vertex is ignored.


### Line Strip
Extension to a line. Allows us to draw poly-line. The first two vertices define the starting segment (line) of the polyline, and each additional vertex adds a new segment to the polyline. $N$ vertices define a polyline with $N-1$ segments. It's more effective in context of memory as we don't have to same vertices twice.

### Line Loop
Minor modification of the previous, first and last points are connected.

### Triangle
Triangle is the simplest primitive that represents surface and can be drawn in many graphics api. Defined by 3 consecutive vertices. If the number of vertices are not divisible by three, then the remaining vertices are discarded. Triangles are a convex shapes with good properties (fast algorithms). Consequently, triangular meshes are used to define complex meshes.

### Triangle Strip
First three vertices define the first triangle. Each additional defines a new triangle, which has common edge (last two vertices) with triangle that was added before.

### Triangle Fan
Triangles have one vertex in common. Good for drawing spherical cap.
Both Triangle Fan and Triangle Strip save memory.

*There are also other primtives but might be special to the implementation of the API. For instance: LINES_ADJACENCY, LINE_STRIP_ADJACENCY,TRIANGLES_ADJACENCY, TRIANGLE_STRIP_ADJACENCY a GL_PATCHES*

Source: PV112 - Lecture 2

## Principle of Rasterization, Framebuffer
Rasterization process is fairly fast comapred to ray tracing. But many optimizations such as clipping, .., are done before hand. Rasterization converts geometry and pixel data into fragments. Color of each fragment is decided inside the fragment shader, which runs for every fragment.

*Fragment - rectangular area, contains: color, depth, line width, anti-aliasing calculations, each framgment corresponds to pixel in the framebuffer*

*Framebuffer - consists of several separate buffers – the most important are the color buffer, Z-buffer (depth memory), stencil buffer (stencil memory), and accumulation buffer.*

Raster images are preffered because of each pixel can be processed indenpendently on the GPU (thread <--> pixel). Displays use discrete pixels. However it is a discrete format and as we zoom in we lose detail.


Source: PV112 - Lecture 1

### Line rasterization
Line equation: $y = mx + b$, where $m$ is slope, $b$ is y intercept

$m = \frac{\Delta\text{y}}{\Delta\text{x}}$

#### Line rasterization algorithms
- Digital Differential Analyzer (DDA)
- Mid-Point Algorithm
- Bresenham Algorithm

#### DDA
Uses floating point arithmetic, we must consider rounding errors (points drift away).

#### Mid-Point Algorithm
Also uses floating point arithmetics but controls the error. Pixel center that is closer to the line is considered.

#### Bresenham Algorithm
...

### Triangle Rasterization
Flood fill:  4-connected, 8-connected filling

Naive approaches:
- iterate over every pixel in the image, this is ineffective.
- introduce bounding boxes, iterate over pixels inside bbox


Source: PB009- Lecture 3

## OpenGL
OpenGL provides the following features:
- drawing triangles, points
- texturing
- shading - meant in terms of lighting model selection, shaders are used for the rest
- visibility calculation
- alpha blending
- accumulation buffer
- stencil buffer



Sources:
FI MUNI: PB009, PV112, PV227 courses