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
