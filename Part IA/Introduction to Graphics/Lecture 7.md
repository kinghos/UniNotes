#### Render buffers
Colour buffers: Four components (RGBA), typically 8 bits per component
Depth: to resolve occlusions through Z-buffer. Usually >8 bits
Stencil: To block rendering selected pixels, usually 8 bits
Front and back buffers:
- Front buffer is what is shown on the screen
- The back buffer is not shown, and the GPU draws onto that buffer
- When drawing is finished, swap the two buffers
- Triple buffer can be used to avoid waiting for the swap before drawing
	- this needs more memory and there is more delay between drawing and displaying a frame

#### V-Sync
- Pixels are copied from colour buffer to monitor row by row
- If front and back buffer are swapped during this process, the upper part contains the previous frame and the lower part has the current frame - this is tearing
- When V-Sync is enabled, the buffer waits until the last row is pixels is copied before swapping.
- If a frame takes longer than the refresh rate of the screen to render, then the current frame will be shown for 2 frame lengths, causing lag

### Human vision
- Fovea - high resolution area of the retina
-  Cornea and lens focus light

- Rods - responsible for night vision
- Cones - responsible for daylight vision and colour perception
	- Three types, sensitive to short, medium and long wavelengths
- The fovea has the highest density of cones, and provides the highest resolution vision

Most of the light we see is reflected from objects, which absorb a certain part of the light spectrum.
$$L(\lambda)=I(\lambda)R(\lambda)$$
Reflected light = illumination $\times$ reflectance

Perceived light:
With index S for S-cones:
$$R_{S}=\int S_{S}(\lambda)\cdot L(\lambda)d\lambda$$
This can also be expressed as a discrete sumc

Cone response = $\sum \text{sensitivity}\times \text{reflected  light}$
Metamers - light spectra that appear to have the same colour
Displays do not emit the same light spectra as real-world objects, yet the colours on a display look near identical - this is an application of metamerism

#### Tristimulus Colour Representation
- Any colour can be matched using three linear independent reference colours
- May require negative contribution to test colour
- Matching curves describe the value for matching monochromatic spectral colours of equal intensity
#### Standard Colour Space CIE-XYZ
- Can match all physically realisable colour stimuli
- Cone sensitivity curves can be obtained by a linear transformation of CIE XYZ
Chromaticity values are defined as
$$x=\frac{X}{X+Y+Z}, y=\frac{Y}{X+Y+Z},z=\frac{Z}{X+Y+Z}$$
$$x+y+z=1$$

- The sum of M and L cones are sensitive to achromatic luminance
- L - M is green-red chromatic
- S - M is violet-yellow chromatic

#### Luminance
Measure of light weighted by the response of the achromatic mechanism - units are cd/m$^2$ or nits

#### Visible vs displayable colours
- All physically possible and visible colours form a solid in XYZ space
- Each display device can reproduce a subspace of that space
- A chromacity diagram is a slice taken from a 3D solid in XYZ space
- Colour Gamut - the solid in a colour space
#### SDR and HDR
- HDR devices attempt to capture almost all visible colours
- SDR cameras attempt to reproduce only colours of a standard sRGB colour gamut, mimicking the capabilities of CRT monitors
