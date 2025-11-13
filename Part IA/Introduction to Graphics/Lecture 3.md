#### Distributed ray tracing
- Distribute the samples for a pixel over the pixel area
	-  Get random or jittered super-sampling
	- Used for anti-aliasing
- Distribute the rays going to a light source over some area
	- Allows area light sources in addition to point and directional light source
	- Produces soft shadows with penumbrae
- Distribute the camera position over some area
	- Allows simulation of a camera with a finite aperture lens
	- Produces depth of field effects
- Distribute the samples in time
	- Produces motion blur effects on any moving objects


### Problems with ray tracing
- Computationally expensive
- Video games and user interfaces need something faster
- Rasterisation is preferred
	- Model surfaces as polyhedra - meshes of polygons
	- Use composition to build scenes
	- Apply perspective transformation and project into the plane of the screen
	- Work out which surface was closest
	- Fill pixels with the colour of the nearest visible polygon
- Graphics cards have hardware to support this

#### Polygons in 3D
- 3 vertices must be planar, >3 not necessarily
- Most GPUs are optimised to draw triangles. Bigger polygons are split into triangles

### Basic 2D transformations
- Scale about origin by factor m - $x'=mx, y'=my$
- Rotate about origin by angle $\theta$ - $x'=x\cos \theta-y\sin \theta , y;=x\sin \theta + y\cos \theta$
- Translate along vector $(x_{0},y_{0})$ - $x'+x_{0},y'=y+y_{0}$
- Shear parallel to x axis by factor a - $x'=x+ay, y'=y$

#### Matrix representations
![[MatrixTransformations.png]]
