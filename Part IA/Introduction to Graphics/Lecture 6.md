#### OpenGL rendering pipeline
![[OpenGLRenderingPIpeline.png]]

- Vertex shader - processing of vertices, normals, uv texture coordinates
- Primitive assembly - organises vertices into primitives and prepares them for rendering
- Clipping - remove or modify vertices so that they all lie within the viewport
- Rasterisation - generates fragments to be drawn for each primitive
- Fragment shader - computes colour per each fragment. Can lookup colour in the texture and modify their depth value
![[OpenGLOO.png]]

#### GLSL
- Similar to C and