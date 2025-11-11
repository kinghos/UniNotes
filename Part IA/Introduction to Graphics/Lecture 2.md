#### Intersection of ray and sphere
Write sphere equation as $(P-C)\cdot(P-C)-r^2=0$
Then replace P with equation of line
#### Shading
After finding the intersection of a ray, you can find the normal to the object at that intersection point. 
Shoot rays from that point to all of the light sources, and calculate the diffuse and specular reflections off the object at that point.
Shadows can also be calculated by checking if another object is between the intersection and the light, and hence is casting a shadow.
Reflection can be handled by spawning new rays to find the contribution