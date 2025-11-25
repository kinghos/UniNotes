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