#### OpenGL rendering pipeline
![[OpenGLRenderingPIpeline.png]]

- Vertex shader - processing of vertices, normals, uv texture coordinates
- Primitive assembly - organises vertices into primitives and prepares them for rendering
- Clipping - remove or modify vertices so that they all lie within the viewport
- Rasterisation - generates fragments to be drawn for each primitive
- Fragment shader - computes colour per each fragment. Can lookup colour in the texture and modify their depth value
![[OpenGLOO.png]]

#### GLSL
- Similar to C and Java
- Primitive and aggregate data types
- Structures and arrays
- Arithmetic operations on scalars, vectors and matrices
- Flow control (if, switch, for, while)
- Functions

```c
vec3 V = vec3( 1.0, 2.0, 3.0 ); 
```
Indexing and subscripting works the same as in C.
Specific elements of an aggregate type can be selected.
```c
vec4 rgba_color( 1.0, 1.0, 0.0, 1.0 );
vec3 rgb_color = rgba_color.rgb;
vec3 bgr_color = rgba_color.bgr;
vec3 grayscale = rgba_color.ggg;
```
##### Storage qualifiers
- `const` - read only, fixed
- `in` - input to the shader
- `out` - output from the shader
- `uniform` - parameter passed from the application, constant for the drawn geometry.
- `buffer` - GPU memory buffer, read and write access
- `shared` - shared with a local work group
![[ShaderInputsOutputs.png]]

#### Application flow
Initialise OpenGL -> Set up inputs -> Draw a frame -> Free resources
Initialising:
- Render window and OpenGL context
- Send geometry to the GPU
- Load and compile shaders
Drawing:
- Clear screen buffer
- Set model-view-projection matrix
- Render geometry
- Flip screen buffers

### Texture mapping
1. Define your texture function (image) $T(u,v)$
2. Define the correspondence between the vertices on the 3D object and the texture coordinates
3. When rendering, for every surface point compute texture coordinates. Use the texture function to get texture value. Use as colour or reflectance

#### Up-sampling
- Larger image with the texture will have more pixels than texels, so values need to be interpolated
- Smaller image has fewer pixels than texels, values need to be averaged over an area (usually using a mipmap)

Nearest neighbour - pick the nearest texel
Bilinear interpolation - interpolate first along x-axis, then along y axis between interpolated points.
If one pixel in the texture map covers several pictures in the final image, you get visible artefacts. High resolution textures are needed.