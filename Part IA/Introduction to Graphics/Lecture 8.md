#### Gamma
Gamma correction is often used to encode luminance or tri-stimulus colour values (RGB) in imaging systems.
$$V_{out}=a\cdot V_{in}^\gamma$$
$V_{out}$ = Luminance
$V_{in}$= Luma
$\gamma$ is usually 2.2
$a$ is gain

Gamma corrected/display encoded pixel values give a scale of brightness levels that is approximately perceptually uniform
At least 12 bits would be needed to encode each colour channel without gamma correction
![[LinearToDisplayEncoded.png]]
e.g. raw image (linear) to JPEG (display encoded)

Luma - pixel brightness in gamma corrected units
$𝐿' = 0.2126𝑅' + 0.7152𝐺' + 0.0722𝐵'$
$R', G', B'$ are gamma corrected values

#### Display encoding
Given:
- Spectrum of the colour to reproduce $L$ (Nx1 vector)
- XYZ sensitivities $S_{XYZ}$ (Nx3 matrix)
- Spectra of the RGB primaries $P_{RGB}$ (Nx3 matrix)
- Display gamma $\gamma=2.2$
To find display-encoded R'G'B' colour values
1. Find XYZ of the colour
$$\begin{bmatrix}
X & Y & Z
\end{bmatrix}^T=S_{XYZ}^TL$$
2. Find a linear combination of RGB primaries
$$S^T_{XYZ}P_{RGB}=M_{RGB\to XYZ}$$
3. Convert and display-encode linear colour values
$$\begin{bmatrix}
R &G&B
\end{bmatrix}^T=M^{-1}_{RGB\to XYZ}\begin{bmatrix}
X&Y&Z
\end{bmatrix}^T$$
$$\begin{bmatrix}
R'&G'&B'
\end{bmatrix}=\begin{bmatrix}
R^{1/\gamma}&G^{1/\gamma}&B^{1/\gamma}
\end{bmatrix}$$

#### RGB
- Can be linear (RGB) or display encoded (R'G'B')
- Can be scene referred (HDR) or display referred (SDR)
- RGB space is a cube
- Can be transformed into CIE XYZ by matrix transformation

#### CMY
- CMY is an inverse of RGB
	- Lights emit light, inks absorb light so the inverse is needed
- Black/Key is needed as inks are not perfect absorbers and mixing CMY gives a muddy grey

#### Munsell's colour classification system
- Three axes
	- Hue - dominant colour
	- Value - bright/dark colours
	- Chroma - vivid/dull colours
- Can be represented on a 3D graph
- Any two adjacent colours are a standard "perceptual" distance apart

#### HSV
- Three axes, same as Munsell's except saturation replaces chroma

### Tone-mapping
Used to:
- Reduce dynamic range
- Customise look (colour grading)
- Simulate human vision (e.g. night vision)
- Simulate a camera (e.g. motion blur)
- To adapt displayed images to a display and viewing conditions
- Make rendered images look more realistic
- **Map from scene to display-referred colours**

##### Exposure/brightness adjustment
$$R_{d}=\frac{R_{s}}{L_{white}}$$
$R$ for red (so same for G and B)
$L_{white}$ is the scene-referred luminance of white (i.e. the peak value of the display)
##### Display coding
$$R'=(R_{d})^\frac{1}{\gamma}$$
This function will give the fully display encoded pixel value from the linear input colour value
#### Tone curves
OpenGL offers sRGB textures to automate RGB to/from sRGB conversion
- sRGB textures store data in gamma-corrected space
- sRGB colour values are converted to RGB colour values on texture lookup (inverse display coding)
- RGB to sRGB conversion when writing to sRGB texture

##### Sigmoidal tone-curves
- Mimic the response of analog film
- Fast to compute
$$R'(x,y)=\frac{R(x,y)^b}{\left( \frac{L_{m}}{a} \right)^b+R(x,y)^b}$$
Where $L_m$ is the geometric mean or mean of logarithms
$$L_{m}=\exp\left( \frac{1}{N}\sum_{(x,y)}\ln(L(x,y)) \right)$$
and $L(x,y)$ is the luminance of the pixel $(x,y)$
