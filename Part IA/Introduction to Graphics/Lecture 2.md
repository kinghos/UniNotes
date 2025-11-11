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
