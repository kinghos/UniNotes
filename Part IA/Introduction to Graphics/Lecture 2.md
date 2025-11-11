#### Intersection of ray and sphere
Write sphere equation as $(P-C)\cdot(P-C)-r^2=0$
Then replace P with equation of line
#### Shading
- After finding the intersection of a ray, you can find the normal to the object at that intersection point. 
- Shoot rays from that point to all of the light sources, and calculate the diffuse and specular reflections off the object at that point.
- Shadows can also be calculated by checking if another object is between the intersection and the light, and hence is casting a shadow.
- Reflection can be handled by spawning new rays to find the contribution to the pixel's colour given by the reflection.
- Transparency works by letting objects through when rays are cast to the light source.
- Refractive indexes can bend the rays as they pass through objects.
- Both transparency and reflection can mean that a ray splits into two parts

#### Illumination
Dürer's method allows calculating what part of the scene is visible in any pixel. Colour depends on lighting, shadows and properties of surface material.
Some surfaces will have specular or diffuse reflection. Some surfaces will absorb some wavelengths of light.

#### Diffuse shading
Assumptions:
- There is only diffuse reflection
- All light falling on a surface comes directly from a light source
	- There is no interaction between objects
- No object casts shadows on any other
	- So we can treat each surface as it were the only object in the scene
- Light sources are considered to be infinitely distant from the object
	- The vector to the light is the same across the whole surface
The colour of a flat surface will be uniform across it, dependent only on the colour and position of the object and the colour and position of the light sources.

![[DiffuseShading.png]]
L is a normalised vector pointing in the direction of the light source
N is the normal to the surface
$I_{l}$ is the intensity of the light source
$k_{d}$ is the proportion of light which is diffusely reflected by the surface
I is the intensity of the light reflected by the surface

- Diffuse shading can have different $I_l$ and different $k_d$ for different wavelengths (colours)
- watch out for $\cos \theta < 0$ - implies that the light is behind the polygon and so it cannot illuminate this side of the polygon
- One sided vs two sided surfaces:
	- One sided surfaces can only have the side in the direction of the normal vector be illuminated. If $\cos \theta<0$ then both sides are black
	- The sign of $\cos \theta$ determines which side of the polygon is illuminated

#### Imperfect specular reflection
![[SpecularReflection.png]]
$L$ is a normalised vector pointing in the direction of the light source.
$R$ is the vector of perfect reflection
$N$ is the normal to the surface
$V$ is a normalised vector pointing at the viewer
$I_l$ is the intensity of the light source
$k_s$ is the proportion of the light which is specularly reflected by the surface.
$n$ is Phong's ad hoc roughness coefficient
$I$ is the intensity of the specularly reflected light

### Overall equation
Thus the overall equation can be considered to be the ambient illumination plus the diffuse and specular reflections from each light source.
$$
I=I_{a}k_{a}+\sum _{i}{I_{i}k_{d}(L\cdot N)+\sum_{i}I_{i}k_{s}(R\cdot V)^n}
$$
This does not have shadows, and no interaction between surfaces - assume that all light reflected off all other surfaces onto a given surface can be amalgamated into a single constant term: "ambient illumination", adding this onto the diffuse and specular illumination.

#### Sampling
Assuming that each ray passes through the centre of a pixel has problems, such as jagged edges to objects and small objects being missed completely. These artefacts are known as aliasing.

Sampling can be done through
- Shooting a single ray through the pixel's centre
- Super sampling - multiple rays through the pixel and average the result, could be a grid, random, jittered or Poisson
- Adaptive super-sampling - shoot a few rays through the pixel, check the variance of the resulting values, if similar enough stop, otherwise shoot more rays.

##### Super-sampling
- Grid - divide into a number of sub-pixels and shoot a ray through the centre of each. Has the same problems as without anti-aliasing
- Random - shoot at random points. This leads to noise artefacts (which the eye is less sensitive to)
- Poisson disc - shoot at random points with the condition that no two rays will pass through the pixel closer than $\epsilon$ to one another. Better image than pure random sampling, but hard to implement
- Jittered - Divide into sub-pixels than shoot at a random point in each sub-pixel. For N rays, it is better than pure random sampling, and acts as an approximation to Poisson disc sampling, and hence easier to implement.

