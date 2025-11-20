### Rasterisation
```
FOR every triangle in the scene
	transform its vertices using MVP matrices
	IF the triangle is within a view frustum
		clip the triangle to the screen border
		FOR each fragment in the triangle
			interpolate fragment position and attributes between vertices
			compute fragment colour
			IF the fragment is closer to the camera than any pixel drawn so far, update the screen pixel with the fragment colour
			END IF ;
		END FOR ;
	END IF ;
END FOR ;
```
A fragment is a candidate pixel in the triangle.
Vertex attributes inside the triangle are interpolated
#### Homogeneous barycentric coordinates
- Homogeneous barycentric coordinates are used to interpolate colours, normals, texture coordinates and other attributes inside the triangle.
$\alpha=\frac{f_{cb}(x,y)}{f_{cb}(x_{a},y_{a})}$
$\beta=\frac{f_{ac}(x,y)}{f_{ac}(x_{a},y_{a})}$
$f_{ab}(x,y)=(y_{a}-y_{b})x+(x_{b}-x_{a})y+x_{a}y_{b}-x_{b}y_{a}$

![[TriangleInterpolation.png]]
#### Surface normal vector interpolaiton
- For a polygonal model, interpolate normal vector between the vertices
	- Calculate colour for each pixel
	- Diffuse component can be either interpolated or computed for each pixel

#### Occlusions
Using the Z-Buffer algorithm:
- Initialise the depth buffer and image buffer for all pixels
```
  colour(x,y) = background colour
  depth(x, y) = zmax // position of the far clipping plane
  ```
  ```
  for every triangle in a scene do
	  for every fragment (x,y) in this triangle do
		  calculate z for current (x,y)
		  if (z < depth(x,y) and z > zmin) then
			  depth(x,y) = z
			  colour(x,y) = fragment_colour(x,y)
```
The Z-Buffer must store depth with sufficient precision
- Consider bit depth/and float/int
- Often it is stored as $\frac{1}{z}$ so there is risk of zero division

### GPUs
- Optimised for floating point operation on large arrays of data
- Performs all low-level tasks and a lot of high-level tasks
	- Clipping, rasterisation, hidden surface removal
	- Procedural shading, texturing, animation, simulation
	- Ray tracing
	- Video rendering
	- Physics engines
- Full programmability at several pipeline stages
	- but optimised for massively parallel operations

Modern GPUs:
- Contain between hundreds and thousands of SIMD processors and can operate on large arrays of data
- >>1000GB/s memory access

#### GPU APIs
- OpenGL
	- Open standard
	- Multi-platform
		- OpenGL ES on mobile, stripped down version
		- WebGL, JavaScript library
	- General focus
- DirectX
	- Windows/Xbox
	- Proprietary
	- Focus on games
- Vulkan
	- Open standard
	- Cross platform
	- Reduced CPU load
	- Better support for multi-core and finer control of GPU
	- Intended for game engines and highly optimised code
GPGPU:
- OpenGL and DirectX are not meant to be used for general purpose computing
- CUDA - C-like language used for parallel computing (Nvidia only)
- OpenCL - open standard alternative to CUDA

#### OpenGL programming model
CPU code:
- gl* functions that
	- Create OpenGL objects
	- Copy data CPU <-> GPU
	- Modify OpenGL state
	- Enqueue operations
	- Synchronise CPU and GPU
- C99 library
- Wrappers in most programming languages

GPU code:
- Fragment shaders
- Vertex shaders
- Written in GLSL
	- Similar to C