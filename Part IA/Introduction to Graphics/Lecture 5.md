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
