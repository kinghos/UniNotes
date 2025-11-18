#### Projection
- Parallel projection: $(x,y,z) \to (x,y)$
	- Useful in CAD, architecture, etc.
	- Looks unrealistic
- Perspective projection: $(x,y,z)\to\left( \frac{x}{z},   \frac{y}{z} \right)$
- Things get smaller as they get farther away
- Looks realistic

![[ProjectionMatrix.png]]
This assumes that:
- The screen is centred at (0, 0, d)
- The screen is parallel to the xy-plane
- The z-axis is into the screen
- The y-axis is up and the x-axis is to the right
- The camera is at (0, 0, 0)
For an arbitrary camera, we can either
- Work out equations for projecting objects about an arbitrary point onto an arbitrary plane
- Transform all objects into our standard coordinate system and use the above assumptions
