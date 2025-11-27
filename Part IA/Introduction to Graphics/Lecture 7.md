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
- 
