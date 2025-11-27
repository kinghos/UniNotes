#### Render buffers
Colour buffers: Four components (RGBA), typically 8 bits per component
Depth: to resolve occlusions through Z-buffer. Usually >8 bits
Stencil: To block rendering selected pixels, usually 8 bits
Front and back buffers:
- Front buffer is what is shown on the screen
- The back buffer is not shown, and the GPU draws onto that buffer
- When drawing is finished, swap the two buffers
- Triple buffer can be use