#### Images
- Images are stored as a 2D array of pixels.
- Usually each pixel takes 3 bytes (RGB)
![[ImageStorage.png]]
To calculate pixel component index in memory:
For row-major order (grayscale): $i(x,y)=x+y\cdot n_{cols}$
For column-major order (grayscale): $i(x,y)=x\cdot n_{rows}+y$
For interleaved row-major (colour): $i(x,y,c)=x\cdot{3}+y\cdot{3}\cdot n_{cols}+c$
General case: $i(x,y,c)=x\cdot s_{x}+y\cdot s_{y}+c\cdot s_{c}$ where $s_x, s_y$ and $s_c$ are the strides for the x, y and colour dimensions.

#### Padded images and stride
Stride is the distance from one pixel to the next.
Sometimes it is desirable to pad an image with extra pixels, or to define a region of interest (ROI).
For row-major, interleaved, colour: $i_{first}=(x_{0}+p)\cdot{3}+(y_{0}+p)\cdot{3}\cdot(n_{cols}+2p)\cdot{3}$

#### Pixel formats
| Format     | Bytes    |
| ---------- | -------- |
| Grayscale  | 1        |
| Highcolour | 2        |
| Truecolour | 3        |
| Deepcolour | $\geq$ 4 |
More bytes means less colour banding

#### Pixels
Pixels are points - no dimensions, no area, cannot be seen. It has coordinates, and is a sample.
Sampling is the process of mapping continuous functions to discrete functions. Quantisation is the process of mapping a continuous variable to a discrete one.

#### Ray tracing
Identify point on surface and calculate illumination
Given a set of 3D objects, shoot a ray from the eye through the centre of every pixel and see what surface it hits.

A ray can be modelled as the equation of a line.
$$P=O+s\hat{D}$$
where $P=[x, y, z]$