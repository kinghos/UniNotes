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
- 