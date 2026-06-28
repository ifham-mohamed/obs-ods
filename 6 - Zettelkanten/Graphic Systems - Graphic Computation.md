
2024-07-28 16:29

Status:

Tags: #UOM #L2S2-S4 #Graphic-Design


# Graphic Computation

### <mark style="background: #FF5582A6;">Framebuffer</mark>

*Framebuffer s a memory area that stores information related to a picture definitions and intensity values*

- B&W - 1 bit per pixels is needed to control the intensity of screen positions.
- True Color - 24 its per pixel is needed in frame buffer.

![[Process of Display The images.png]]

### **When you want to draw a rectangle, How do we describe it to the computer ?**

1. Partition the Space
	  - Define a set of points (vertices) in 2D space.  
	  - Given a set of vertices, draw lines between consecutive vertices.
  
2. Record Every Position
	  - Bitmap – A rectangular array of bits mapped one-to-one with pixels.
  
3. Position Relative
	- What are the properties needed to draw the rectangle ?   
		- x, y   
		- Width , height   
		- Fill   
		- Stroke (color), stroke width   
	- Vector display system - graphical output system that was based on strokes (as opposed to pixels). Also known as: random, calligraphic, or stroke displays.

4. Model File for Rectangle
	- Vertex Method is the most common method of representing objects 
	- v 4 e 4 
	- ( 7, 3 ) , ( 7, 9 ), ( 14, 9 ), ( 14, 3 )
	- ( 1, 1 ), ( 1, 3 ), ( 3, 1 ), ( 3, 3 )

![[Graphic Systems Rectangular Represent#^group=8Hf5rI5qOR9d9PAI0M1yV| 800]]


### **How do we store this ?**

We need to allocate memory to hold the results of the computation stage.

#### **Frame Buffer** 
- Framebuffer- A block of memory, dedicated to graphics output, that holds the contents of what will be displayed. 
- Pixel - one element of the framebuffer

#### **Framebuffer in Memory** 
1. **Framebuffer Size**:
    - If we want a framebuffer with a resolution of 640 pixels by 480 pixels, we can calculate the total memory needed:
        - Framebuffer size = 640 pixels × 480 pixels = 307,200 pixels
        - If we allocate 1 bit per pixel (for monochrome display), the total memory required would be 307,200 bits.
2. **Color Depth**:
    - The number of bits used to represent each pixel determines the color depth.
    - A higher color depth allows for more colors to be displayed.
    - Let’s explore the color depth options:
        - **1 Bit (Monochrome)**:
            - With 1 bit per pixel, you can represent only two colors: typically black and white (on/off).
            - Each pixel is either fully on (white) or fully off (black).
            
        - **8 Bits (256 Colors)**:
            - With 8 bits per pixel, you can represent 256 different colors.
            - Each pixel can take one of 256 color values (e.g., shades of red, green, blue, or combinations).
            
        - **16 Bits (High Color)**:
            - High color uses 16 bits per pixel.
            - Commonly, 5 bits are allocated for red, 5 bits for green, and 5 bits for blue (plus an extra bit for transparency or other purposes).
            - This results in a potential palette of 65,536 colors.
            
        - **24 Bits (True Color)**:
            - True color uses 24 bits per pixel.
            - Typically, 8 bits are allocated for each of red, green, and blue channels.
            - This allows for a vast range of colors (over 16 million).
3. **Summary**:
    - 1 bit per pixel: Monochrome (2 colors)
    - 8 bits per pixel: 256 colors
    - 16 bits per pixel: High color (65,536 colors)
    - 24 bits per pixel: True color (over 16 million colors)

#### If we want a framebuffer of 640 pixels by 480 pixels, we should allocate: 
`Framebuffer size = 640 pixels × 480 pixels = 307,200 pixels`


1. **Monochrome (1 bit per pixel)**:
    - For monochrome (black and white) display, we need 1 bit per pixel.
    - Framebuffer size = 640 pixels × 480 pixels = 307,200 bits.

1. **8-Bit Color Depth (256 colors)**:
    - With 8 bits per pixel, we can represent 256 colors.
    - Framebuffer size = 640 pixels × 480 pixels × 8 bits = 1,228,800 bits (or 153,600 bytes).

1. **16-Bit Color Depth (High Color)**:
    - High color uses 16 bits per pixel.
    - Framebuffer size = 640 pixels × 480 pixels × 16 bits = 2,457,600 bits (or 307,200 bytes).

1. **24-Bit Color Depth (True Color)**:
    - True color uses 24 bits per pixel.
    - Framebuffer size = 640 pixels × 480 pixels × 24 bits = 3,686,400 bits (or 460,800 bytes).


![[Graphic Systems Rectangular Represent#^group=EsdyFJs5| 800]]

![[Graphic Systems Rectangular Represent#^group=rS9C0DA0| 800]]

### <mark style="background: #FF5582A6;">Video Controller</mark>
- In Addition to the CPU, a special processor know as Video Controller is used to control the operations of the display system.
- Fixed Area in the system memory is given for the frame buffer, and the video controller is direct access to the framebuffer

Q. Why Refresh Rates Matter ?
The **refresh rate** of a display, whether it’s a monitor or a TV, refers to how many times per second the image on the screen updates. It’s measured in **hertz (Hz)**. Here’s why refresh rates matter:
- **Smoother Motion**
- **FPS vs. Refresh Rate**: While related, **frames per second (fps)** and refresh rate serve different functions. FPS measures how many frames your graphics card can render and push to the monitor per second. Ideally, your fps should match or exceed the monitor’s refresh rate for the best viewing experience. Mismatched fps and refresh rate can lead to **screen tearing**, where a new frame is displayed before the previous one is fully drawn, resulting in a visible split in the image. Technologies like adaptive sync help synchronize them for smoother visuals.
- **High Refresh Rate Monitors**: Traditional monitors had a **60Hz** refresh rate, suitable for everyday tasks. However, high refresh rate gaming monitors (e.g., **120Hz**, **144Hz**, and **240Hz**) have become popular among gamers.


![[2 - Source Material/Lecture Resourses/Graphic Systems Rectangular Represent.md#^group=o5M4cIpk | 800]]
# Reference
 ![[Graphic Systems Graphic Systems Video Controller.png]]
 
 ![[Graphic Systems Lecture 2 - Graphic  Systems - Frambuffer.pdf]]