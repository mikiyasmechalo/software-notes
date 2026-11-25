---
title: Computer Graphics
---
# CH1 Part 1: A Survey of Computer Graphics
**Application of Computer Graphics** 
- CAD - Computer aided design
- Presentation Graphics - bar chart, pie chart
- Computer art- fine art(math) & commercial art
- Entertainment
- Education and training - simulations & models
- Visualization - data, scientific or business
- Image Processing - improving quality and machine visual perception
- GUIs

- Aspect Ratio = Width ÷ Height.
For any width w and height h:
GCF (Greatest Common Factor/ Divisor) = $gcd(w, h)$ 
Simplified ratio = $(w / gcd) : (h / gcd)$ 

The raster coordinate system is also called image-space or screen-space coordinates.

**Types of coordinate systems**
- Cartesian coordinate
- Raster/Screen coordinate
- Homogenous - adds w as a coordinate (x, y, z, w) finally converted into 2D display coordinates. w - enables matrix transformations using a single unified model.
- Normalized Device Coordinates NDC - used by OpenGL, Vulkan and Web-GPU, for consistency.
- Window and viewport coordinates. - 3D real world to 2D displays. Model → World → View → Clip → NDC → Raster


**Image Representation** 
1. Raster(bitmap) - uses pixels and stores images as a matrix of pixel color nodes (RGB values). - we may use compression like PNG, TIFF (lossless), JPEG, Web-P (lossy) for small file sizes.
	- useful for colorful and realistic pics, UI, digital painting ... loses quality when resized.
2. Vector - stored as mathematical description of shapes and lines. uses formulas. small size.
	- best for logos, line art, typography, icons ... less realistic colors and gradients only. PDF, SVG...

**Displays** 

| Type                         | Description                                                 | Features                                    |
| ---------------------------- | ----------------------------------------------------------- | ------------------------------------------- |
| CRT (Cathode Ray Tube)       | Uses electron beams striking a phosphor-coated screen.      | Legacy tech; deep color but bulky.          |
| LCD (Liquid Crystal Display) | Controls light through liquid crystal alignment.            | Lightweight, low power, common in monitors. |
| LED (Light Emitting Diode)   | LCD variant with LED backlight.                             | High contrast and energy-efficient.         |
| OLED (Organic LED)           | Each pixel emits light; enables true black and flexibility. | Used in modern smartphones, TVs, VR.        |
| MicroLED / QLED / MiniLED    | Advanced LED-based displays with superior brightness.       | HDR monitors, large displays.               |
| VR/AR Headsets               | Dual high-refresh screens providing stereoscopic vision.    | Immersive 3D experiences.                   |


**Image File Structure** 
Header and Data
Header includes

| Field                          | Description                                                |
| ------------------------------ | ---------------------------------------------------------- |
| File Format / Version          | Identifies the image type (e.g., PNG, JPEG, BMP).          |
| Image Width & Height           | Specifies dimensions in pixels.                            |
| Color Depth (Bits per Pixel)   | Number of bits used to represent each pixel’s color.       |
| Color Model                    | Defines color representation (e.g., RGB, CMYK, Grayscale). |
| Compression Type               | Algorithm used to reduce file size (JPEG, LZW, DEFLATE).   |
| Interlacing / Progressive Info | Indicates how image data loads or displays.                |

**Types of Digital Images (by Bit Depth)** 
how many bits are used to represent the color of a single pixel in an image or display.

A.	*Monochrome Image (1-bit)* - 0 black or 1 white, File Size = (width × height) / 8 bytes
B. *8-bit Grayscale Image* - 256 shades of gray, File Size = width × height bytes, each pixel=1byte.
C.	*8-bit Color Image* (Indexed or Lookup Table) - uses a *LUT* (256 pre-defined colors), each pixel has an index, used in GIF and old systems, FS=width x height + pallet size. PS=256 x 3 bytes = 768
D. *24-bit True Color Image* - 8 bits for RGB values, 24 bits per pixel, FS = W x H x 3 bytes, JPEG
E. *32-bit image with alpha channel* for transparency RGBA - PNG, PSD .., FS = W x H x 4 bytes

**Color Models** 
A.	RGB (Additive Model) - 1 byte for R G and B, 24 bits (3 bytes), 256 d/t levels, 16.1m colors
B. CMY and CMYK (subtractive model) - starts with white, CMY(1,1,1) or % based. The K (black) - is added wider range of colors. 
```
RBG tp CMY. C-M-Y=(1-R-G-B/255), R-G-B=255x(1-CMY) - to RGB, C-M-Y : separate
CMYK to RGB. C=(1-R'-K)/(1-k), R=255*(1-C) * (1-K),- to RGB, R' = R/255 
```
The conversion formulas for CMYK from normalized RGB values (R*, G*, B*, ranging from 0 to 1) are: 
$$(K=1-\max (R^{*},G^{*},B^{*})), \text{and if} (K\ne 1), 
(C=\frac{1-R^{*}-K}{1-K}), (M=\frac{1-G^{*}-K}{1-K}), (Y=\frac{1-B^{*}-K}{1-K}); if (K=1), \text{then} (C=M=Y=0). \text{ if } K=0 \text{ then the same as RGB to CMY}$$ 
C.	HSV (Hue, Saturation, Value) - used for intuitive color selection,  H (0-360 degree), S & V - 100%
D.	YUV / YCbCr - Used in TV and video compression. Separates brightness (Y) from color (U/V or Cb/Cr) for efficient transmission.


GPU - optimized for parallel small operations. - has VRAM, cache and shared mem. for the cores.

Graphics API Evolution
- Fixed-Function Era: APIs managed lighting, shading, and transformations automatically (OpenGL 1.0).
- Programmable Pipeline Era: Developers gained control through shaders (OpenGL 2.0+, DirectX 9+).
- Modern Era (Low-Level APIs): Fine-tuned performance, multi-threading, and explicit memory management.

A graphics framework (or graphics engine) is a higher-level software layer built on top of APIs.
e.g. open scene graph, unity, unreal engine, Babylon.js

**Rendering Pipeline** 
![[Pasted image 20251201124823.png]]

| Stage           | Description                                              |
| --------------- | -------------------------------------------------------- |
| Vertex Shader   | Processes vertex attributes and applies transformations. |
| Geometry Shader | Creates new geometry (optional).                         |
| Rasterization   | Converts geometry into pixel fragments.                  |
| Fragment Shader | Computes final pixel color and texture blending.         |
| Frame Buffer    | Stores the rendered image for display.                   |


# CH1 Part 2: Overview of Graphics Systems
**Computer Graphics** 
A branch of computer science that deals with the theory and technology for computerized image
synthesis.
The use of computers to create and manipulate images. 2D or 3D.
CG is the algorithms and hardware required to produce realistic and/or useful images on a computer.
- Imaging - representing 2D images
- Modeling - Representing 3D objects
- Rendering - constructing 2D images from 3D models
- Animation - Simulating changes over time
Image is composed of pixels in a rectangular area called **raster**.

### VIDEO DISPLAY DEVICES
**CRT** - cathode-ray-tube
A beam of electrons (cathode rays), emitted by an electron gun, passes through focusing and deflection systems that direct the beam toward specified positions on the phosphor-coated screen.
- a *refresh CRT* redraws to the screen rapidly to not lose the picture from the phosphor fading.
- CRT uses a heated metal cathode, heat is supplied from a coil of wire called filament.
- In the vacuum the free negatively charged electrons are accelerated towards the phosphor by a high positive voltage. the voltage may come from d/t places: metal coting, accelerating anode.
- The intensity of the electron gun is controlled by the negative voltage on the control grid . A highly negative voltage repels the electrons and completely shuts off the beam. Conversely, making the control grid less negative reduces the repulsion, allowing more electrons to pass through, thereby increasing the display brightness.
- Focusing is achieved using electric or magnetic fields.
Persistence is defined as the time it takes the emitted light from the screen to decay to one-tenth of its original intensity. Lower persistence phosphor means faster refresh rate is needed.
- we usually use persistence range from 10-60 microseconds.
- The maximum number of points that can be displayed without overlap on a CRT is referred to as the **resolution**. usually 1280 x 1024 Spots.
-  Thus, resolution of a CRT is dependent on the type of phosphor, the intensity to be displayed, and the focusing and deflection systems. 

**Raster-Scan Displays**
The most common type of graphics monitor employing a CRT is the raster-scan display, based on television technology.
- The electron beam is swept across the screen in a line (scan line), with beam intensity turned on and off to control the pattern of illuminated spots.
- Picture definition is stored in a memory area called the refresh buffer or frame buffer.
- Each screen point is referred to as a pixel or pel (shortened forms of picture element).
Intensity range for pixel positions depends on the capability of the raster system. 
- for black and white, only 1 bit is required per pixel to control intensity.
- for color and intensity variations additional bits are required, up to 24.
- 24 bit with a 1024 x 1024 requires 3mb of storage for the frame buffer.
- For a black and white (1 bit) system the frame buffer is called **bitmap**. for multiple bits we call it **`pixmap`**.
- on raster-scan displays refreshing is done 60 to 80 times per second or higher.
- when the returns to the left side after finishing a scan is called a **Horizontal Retrace** of the beam.
- when the beam returns to the top left after 1 frame we call that a **Vertical Retrace**. 
*Interlaced Raster-scan display* 
Interlaced refresh is a procedure used in raster-scan systems (like TV) to display a single frame in **two passes** .
1.  **Pass 1:** The electron beam sweeps every other scan line (e.g., odd lines).
2.  **Pass 2:** The beam sweeps the remaining, skipped scan lines (e.g., even lines).
This technique effectively **doubles the perceived refresh rate** (e.g., turning a 30-frame-per-second rate into 60 fields-per-second). Its primary purpose is to **reduce screen flicker** in systems with otherwise slower refresh rates, provided adjacent scan lines hold similar display information.

**Random-Scan Displays** 
A CRT only directs the beam only to the parts of the screen where the picture is to be drawn.
- They draw picture one line at a time and referred to as **Vector Displays** (stroke-writing or calligraphic displays).
- The component lines of a picture can be drawn and refreshed by a random-scan system in any order.
- A *pen-plotter* is an example of a random scan display.
Picture definition is now stored as a set of line-drawing commands in an area of memory refed to as the refresh display file. (display list, display program, or simply the refresh buffer)
- The system cycles through line-drawing commands to render a picture. then looping back to the beginning.
- Refresh rate: 30–60 times per second.
- High-end systems can draw ~100,000 short lines per cycle.
- If fewer lines are displayed, refresh is slowed to prevent exceeding 60 fps, which could damage the phosphor.

Random-scan systems are designed for line-drawing applications and can not display realistic shaded scenes. 
- But they have higher resolution than raster systems. 
- and can produce smooth lines because the the electron just follows the line path. while a raster produces jagged lines plotted at discrete points.


**Color CRT Monitors**
This happens by using a combination of phosphor that emit different colored light.

The two basic techniques for producing color displays with a CRT are:
*Beam-Penetration method* - used with random scan displays. 
- Two layers of phosphor, usually red and green are coated in the inside of the CRT screen and the displayed color depends on how much the electron penetrates the phosphor layers.
- two intermediate colors orange and yellow are shown at 1/2 and 3/2 beam speeds.
- The speed of the electron, and hence the screen color at any point is controlled by the beam-acceleration voltage.
- This is inexpensive but only produces 4 colors and the quality is not very good.

*Shadow-Mask method* - used in raster-scan displays.
- has 3 phosphor color dots at each pixel position. R G and B.
- and a shadow mask grid behind the phosphor coated screen.
- the RGB dots can be aligned in a triangular shape(delta-delta) or on the scan line horizontally.
- we obtain color by varying the intensity levels on the three electron beams.
- cheap displays has only on or off to the beams allowing only 8 colors but we can add intermediate intensities to produce millions of colors.
- An RGB color system with 24 bits of storage per pixel is generally referred to as a full-color system or a *true-color system*.


**Direct-View Storage Tubes** 
A type of CRT that **retains an image on the screen** without continuous refreshing.
* **How it Works:** It uses a **Writing Gun** to create a pattern of positive charge on a **Storage Mesh** behind the screen. A **Flood Gun** then constantly beams low-energy electrons, which are only attracted to the charged areas of the mesh, causing the phosphor to glow and sustain the image.
* **Benefit**: very complex pictures can be displayed at very high resolutions without flicker.
* **Key Trade-offs:** DVSTs allow for **high-resolution, flicker-free** static images, but they **cannot display color** and are **poor for animation** because erasing requires clearing and redrawing the entire screen.

**Flat-Panel Displays** 
Flat-panel displays fall into two categories:
1.  **Emissive Displays (Emitters):** These devices **convert electrical energy directly into light**. Examples include **Plasma panels**, **thin-film electroluminescent displays**, and **LEDs**. (Flat CRTs exist but are less successful,{parallel gun and $90\degree$ deflection}).
2.  **Non-emissive Displays (Non-emitters):** These devices **use optical effects to convert external light** (sunlight or backlight) into a graphics pattern. The primary example is the **Liquid-Crystal Display (LCD)**.

*Plasma panels*, also called gas-discharge displays, are constructed by filling the region between two glass plates with a mixture of gases that usually includes *neon*.

*Liquid crystal displays (LCDS)* are non-emissive devices produce a picture by passing polarized light from the surroundings or from an internal light sow through a liquid-crystal material that can be aligned to either block or transmit the light.

**Three-Dimensional Viewing Techniques**
1. Varifocal Mirrors (True 3D Volume)
This technique uses a **vibrating, flexible mirror**  and a CRT display. The mirror's changing focal length is synchronized with the image display, reflecting each point into a specific **spatial position** that corresponds to its distance from the viewer. This creates a **true volumetric image** that can be viewed from different angles, used in applications like medical analysis (CAT scans) and geological modeling.

2. Stereoscopic Views (Depth Effect)
This method creates the illusion of depth by displaying **two separate views** of a scene—one for the left eye and one for the right eye. When these two views merge in the observer's brain, a **three-dimensional effect** is perceived.
* **Mechanism:** One common way is using a raster system to display the left and right views on **alternate refresh cycles**, viewed through special **liquid-crystal shutter glasses**  synchronized with the screen.
* **Application:** This is a core component of modern **virtual-reality (VR) systems**, where a headset tracks the viewer's position to allow interactive "walk-throughs" of the scene.


# CH-2: Output Primitives
### Points and Lines
**Point** - drawn d/t based on screen tech,
- on random scans: the point-plot instructions are stored and converted into deflection angles.
- on black and white and RGB screens: the point pixel's value will be 1 or the color it should be.

**Lines** - accomplished by calculating intermediate positions along the path b/n two points.
- For random scan displays these are smooth from one point to another.
- points b/n two end points are calculated from the line equation, b/c screen locations are integer values plotted points may be approximate of the actual values. (makes lines Jagged)


#### Line Drawing Algorithms
The Cartesian slope-intercept equation for a straight line is 
$$y=m x + b$$
- m - slope and b - y-intercept
given the two endpoints of a line segment ($x_1, y_1$) and ($x_2, y_2$) we can find m and b using
$$m=\frac{y_2-y_1}{x_2-x_1}$$
$$b=y_1-m*x_1$$

If given x interval $\Delta x$ along a line, we can compute y interval $\Delta y = m~\Delta x$ 
Similarly given $\Delta y$ , $\Delta x = \frac{\Delta y}{m}$.

##### DDA Algorithm
The digital differential analyzer (DDA) is a scan-conversion line algorithm based on calculating either $\Delta y$ or $\Delta x$,
This section describes how line-drawing algorithms determine the next pixel based on slope, always stepping along the axis with the largest change.

1.  **Shallow Slope ($|m| \le 1$ or $dx>dy$):**
    * Sample at **unit $x$ intervals** ($\Delta x = 1$).
    * Compute $y$: $$y_{k+1} = \text{round}(y_k + m)$$
2.  **Steep Slope ($|m| > 1$):** 
    * Reverse roles and sample at **unit $y$ intervals** ($\Delta y = 1$).
    * Compute $x$: $$x_{k+1} = \text{round}(x_k + 1/m)$$
*Direction:* If the line is drawn from right-to-left, the unit step ($\Delta x$ or $\Delta y$) is simply **$-1$**, and the equations change from addition to subtraction.

*DDA Summary in MATH*
Let the line endpoints be $(x_a, y_a)$ and $(x_b, y_b)$.
First, calculate the differences and determine the number of steps:

$$
\Delta x = x_b - x_a \quad \text{and} \quad \Delta y = y_b - y_a
$$
$$
steps = \max(|\Delta x|, |\Delta y|)
$$
$$
m = \frac{\Delta y}{\Delta x} \quad \text{(Slope)}
$$
**Algorithm**
Given two endpoints: (x1, y1) and (x2, y2)
1. Compute the differences:
	$dx=x_2-x_1$ 
	$dy=y_2-y_1$
2. Determine the number of steps:
	$steps=max(\mid dx\mid , \mid dy\mid )$ 
3. Calculate the increments:
	$x_{inc}=\frac{dx}{steps}$ 
	$y_{inc}=\frac{dy}{steps}$ 
4. Initialize starting point:
	$x=x_1$ 
	$y=y_1$ 
For each step (from 1 to steps):
- Plot the pixel at (round(x), round(y))
- Increment:
	$x=x+x_{inc}$ 
	$y=y+y_{inc}$ 

**Algorithm (again, can ignore)**
The algorithm then calculates the required increments ($\Delta x_{\text{inc}}$ and $\Delta y_{\text{inc}}$) needed to advance from one pixel $(x_k, y_k)$ to the next $(x_{k+1}, y_{k+1})$.
1. Case: Horizontal Dominant ($|\Delta x| > |\Delta y|$)
In this case, the line is relatively shallow. The step size on the $x$-axis is always $1$ or $-1$.

| Condition (Direction)           | $\Delta x_{\text{inc}}$ | $\Delta y_{\text{inc}}$ | Next Point Equation |
| :------------------------------ | :---------------------- | :---------------------- | :------------------ |
| **$x_a < x_b$** (Left to Right) | $+1$                    | $+m$                    | $x_{k+1} = x_k + 1$ |
|                                 |                         |                         | $y_{k+1} = y_k + m$ |
| **$x_a > x_b$** (Right to Left) | $-1$                    | $-m$                    | $x_{k+1} = x_k - 1$ |
|                                 |                         |                         | $y_{k+1} = y_k - m$ |

2. Case: Vertical Dominant ($|\Delta y| \ge |\Delta x|$)
In this case, the line is relatively steep. The step size on the $y$-axis is always $1$ or $-1$.

| Condition (Direction)           | $\Delta x_{\text{inc}}$ | $\Delta y_{\text{inc}}$ | Next Point Equation   |
| :------------------------------ | :---------------------- | :---------------------- | :-------------------- |
| **$y_a < y_b$** (Bottom to Top) | $+1/m$                  | $+1$                    | $x_{k+1} = x_k + 1/m$ |
|                                 |                         |                         | $y_{k+1} = y_k + 1$   |
| **$y_a > y_b$** (Top to Bottom) | $-1/m$                  | $-1$                    | $x_{k+1} = x_k - 1/m$ |
|                                 |                         |                         | $y_{k+1} = y_k - 1$   |
**Note:** After calculating $x_{k+1}$ and $y_{k+1}$, both values are **rounded** to the nearest integer for plotting the pixel.
We can improve the performance of the DDA algorithm by separating the increments m and l/m into integer and fractional parts so that all calculations are reduced to integer operations.


##### `Bresenham's` Line Algorithm
An accurate and efficient raster line generating algorithm, scans lines using only incremental *integer calculations* that can be adapted to display circles and other curves.

`Bresenham's` Line-Drawing Algorithm for $|m| < 1$ 

This algorithm uses a **decision parameter** ($p_k$) to choose the next pixel by determining which of two candidate pixels is closest to the true line path, based on whether the line is above or below the midpoint between them.
Step 1: Initialization
1.  **Input & Start:** Input the two endpoints and ensure the **left endpoint** is stored as $(x_0, y_0)$.
2.  **Plot First Point:** Load $(x_0, y_0)$ into the frame buffer (plot the starting pixel).
3.  **Calculate Constants:** 
    $$
    \begin{aligned}
    \Delta x &= x_{\text{end}} - x_0 \\
    \Delta y &= y_{\text{end}} - y_0
    \end{aligned}
    $$
4.  **Initial Decision Parameter ($p_0$):** 
    $$
    p_0 = 2\Delta y - \Delta x
    $$

Step 2: Iterative Plotting

Starting at $k=0$ (the first plotted point), repeat the following logic $\mathbf{\Delta x}$ times (since $\Delta x$ is the larger change for slopes $\le 1$):

$$
(x_{k+1}, y_{k+1}) = \text{Next Pixel Location}
$$

| Condition on Decision Parameter $\mathbf{p_k}$ | Next Pixel Choice | Next Parameter $\mathbf{p_{k+1}}$ Update |
| :--- | :--- | :--- |
| **If $p_k < 0$** | **Move East** (E): $$(x_k + 1, y_k)$$ | $p_{k+1} = p_k + 2\Delta y$ |
| **If $p_k \ge 0$** | **Move North-East** (NE): $$(x_k + 1, y_k + 1)$$ | $p_{k+1} = p_k + 2\Delta y - 2\Delta x$ |

---

In essence, if $p_k < 0$, the closest next pixel is purely horizontal; otherwise, the closest next pixel is diagonal. By using only additions, subtractions, and comparisons with zero, `Bresenham's` algorithm achieves remarkable performance.

Generalizing `Bresenham's` Algorithm

`Bresenham's` algorithm is generalized to handle lines with arbitrary slope by exploiting the symmetry of the Cartesian plane.

1. Handling Steep Lines ($∣m∣>1$)
For steep lines, the roles of x and y are simply interchanged:
- The algorithm steps along the y-direction in unit increments (Δy=±1).
- It calculates successive x values nearest the line path.

2. Handling Direction and Octants
The algorithm is adjusted for all eight octants (directions) of the plane:
- Reversed Direction: If the line is drawn from right-to-left (e.g., x decreases), the step direction for both x and y is negated (Δx=−1, Δy=−1).
- Consistency: A rule is applied to ensure that the exact same set of pixels is plotted regardless of which endpoint is chosen as the starting point.

2. Special Cases
Certain lines are handled outside the main loop for efficiency:
- Horizontal (Δy=0), Vertical (Δx=0), and Diagonal (∣Δx∣=∣Δy∣) lines can be plotted directly without the decision parameter logic.


In Code: this handles all possible line orientations (steep/gentle, positive/ negative slope).
```python
Step 1: Compute differences
    dx = |x2 - x1|
    dy = |y2 - y1|

Step 2: Determine direction of increment
    sx = 1 if x1 < x2 else -1
    sy = 1 if y1 < y2 else -1

Step 3: Initialize
    x = x1
    y = y1
    Plot(x, y)

Case 1: |dx| > |dy| (Gentle slope)
    p = 2*dy - dx
    while x != x2:
        x = x + sx
        if p < 0:
            p = p + 2*dy
        else:
            y = y + sy
            p = p + 2*(dy - dx)
        plot(x, y)

Case 2: |dy| ≥ |dx| (Steep slope)
    p = 2*dx - dy
    while y != y2:
        y = y + sy
        if p < 0:
            p = p + 2*dx
        else:
            x = x + sx
            p = p + 2*(dx - dy)
        plot(x, y)

```

##### Midpoint Circle Drawing Algorithm
For a given radius r and screen center position ($x_c$, $y_c$,), we can first set up our algorithm to calculate pixel positions around a circle path centered at the coordinate origin (0,0). 
Then each calculated position (x, y) is moved to its proper screen position by adding $x_c$, to x and $y_c$, to y. 
The technique relies on two key principles:
1.  **Symmetry:** we only need to calculate the pixels for a **small $45^\circ$ section** of the circle, called an **octant**. The positions for the remaining seven sections can be found by simply mirroring those calculated points.
2.  **Decision Parameter:** Since the curve is smooth, when you move one unit in the $x$ direction, the $y$ position only needs to change by a small amount (either $0$ or $-1$). A mathematical **decision parameter** (based on the midpoint) is used to quickly determine which of those two small steps is **closer to the true circle curve**, making the process very fast and avoiding complex square-root calculations.

To apply the midpoint method, we define a circle function: 
$$f_{circle}(x,y)=x^2+y^2-r^2$$

Any point (x, y) on the boundary of the circle with radius r satisfies the equation $f_{circle}(x,y) = 0$. 
The relative position of any point (x. v) can be determined by checking the sign of the circle function:

| Mathematical Result    | Position of $(x, y)$ Relative to the Circle   |
| :--------------------- | :-------------------------------------------- |
| $f_{circle}(x, y) < 0$ | The point is **inside** the circle boundary.  |
| $f_{circle}(x, y) = 0$ | The point is **on** the circle boundary.      |
| $f_{circle}(x, y) > 0$ | The point is **outside** the circle boundary. |
**If a point is on the circle:** The distance from the origin ($\sqrt{x^2 + y^2}$) equals the radius $r$. Substituting $r^2$ for $x^2 + y^2$ gives $r^2 - r^2 = 0$.


###### Midpoint Circle Algorithm Steps

**Algorithm - short** 
1. Initialize:
	- $x=0,~ y=r,~ p=1-r$ 
2. While $x<y$:
	- Plot eight symmetric points.
	- If $p<0$:
		-  $p=p+2x+3$ 
	- Else:
		- $p=p+2\left(x-y\right)+5,\ \ y=y-1$ 
	- Increment $x=x+1$ 


**Algorithm - again**
1. Initialization
First, you need the **radius ($r$)** and the screen center **($x_c, y_c$)** of the final circle. The algorithm starts by assuming the circle is centered at the origin $(0, 0)$.
The **starting point** for calculation is the top-most point on the circle:
$$(x_0, y_0) = (0, r)$$

2. Initial Decision Parameter
Calculate the starting value of the **decision parameter** ($p_0$).
$$p_0 = 1 - r$$

3. Iterative Pixel Selection (for one Octant)
Starting at $k = 0$, you move one step in the positive $x$ direction ($x_{k+1} = x_k + 1$) and use the current parameter $p_k$ to decide the $y$ position:

* **Case 1: If $p_k < 0$** (The midpoint is inside the circle, so the closer pixel is the one with the same $y$-coordinate):
    * The next point is $(x_{k+1}, y_k)$.
    * Update the decision parameter: $p_{k+1} = p_k + 2x_{k+1} + 1$.

* **Case 2: If $p_k \ge 0$** (The midpoint is outside or on the circle, so the closer pixel is the one with a lower $y$-coordinate):
    * The next point is $(x_{k+1}, y_k - 1)$.
    * Update the decision parameter: $p_{k+1} = p_k + 2x_{k+1} + 1 - 2y_{k+1}$. (d/t than the above b/c we do x+1 and y-1 first)

4. Symmetry and Translation
For every pixel $(x, y)$ calculated in Step 3:
* **Symmetry:** Determine the **seven symmetry points** in the other octants.
* **Translation:** Move the eight calculated points to the correct screen position by adding the center coordinates:
    * $x_{\text{plot}} = x + x_c$ 
    * $y_{\text{plot}} = y + y_c$ 
* **Plot** the final translated coordinates.

5. Loop Condition
Repeat Steps 3 and 4 until ($x \ge y$). This completes the $45^\circ$ arc calculation.

The 8 octets: $(x,y), (y,x), (−y,x), (−x,y), (−x,−y), (−y,−x), (y,−x), (x,−y)$


###### `Bresenham’s` Circle Drawing Algorithm
At each step, choose between two pixels: one to the east (E) and one to the southeast (SE), based on a decision parameter (p).
**Algorithm**
1. Initialize:
	- $x=0$
	- $y=r$
	- $p=3-2r$
2. While $x\le y$:
	- Plot the 8 symmetric points:
		- $(xc±x,~ yc±y)$ 
		- $(xc±y,~ yc±x)$ 
	- If p < 0:
		- $p=p+4x+6$ 
	- Else:
		- $p=p+4\left(x-y\right)+10$ 
		- $y=y-1$ 
	- Increment $x=x+1$ 



###### Ellipse Drawing (Midpoint Ellipse Algorithm)
draws an ellipse centered at $(x_c,y_c)$with radii $r_x(horizontal)$ and $r_y(vertical)$.

Given center $(x_c, y_c)$ and radii $(r_x, r_y)$, equation:
$$\frac{(x-x_c)^2}{r_x^2}+\frac{(y-y_c)^2}{r_y^2}=1$$  
We plot points in the first quadrant (from topmost point to rightmost point), then reflect them 
across the other quadrants to get the full ellipse.

$$\mathrm{slope}=\frac{dy}{dx}=-\frac{r_y^2x}{r_x^2y}$$ 
At some point, the slope equals –1 (i.e., the tangent makes a 45° angle).
That point divides the first quadrant of the ellipse into two regions:

Region 1 — The “Upper” Region
- Here, the slope of the tangent satisfies $\mid dy/dx\mid>1.$ 
- The curve is steep — y changes faster than x.
- We increase x pixel by pixel and decide when to decrement y.
- The algorithm tests a decision parameter p_1to determine when to move diagonally.
Stop Region 1 when the slope becomes –1, i.e. when:
$$r_y^2x=r_x^2y$$ 

Region 2 — The “Lower” Region
- Here, the slope of the tangent satisfies $\mid dy/dx\mid<1$.
- The curve is flat — x changes faster than y.
- We decrease y pixel by pixel and decide when to increment x.
- The decision parameter $p_2$ is used here.
Continue until y=0.

**Algorithm** 
1. Start at $(x, y) = (0, ry)$
2. Region 1 decision parameter:
	- $p_1=ry^2-rx^2ry+\frac{1}{4}rx^2$ 
3. While $2ry^2x<2rx^2y$:
	- Plot 4 symmetric points
	- If $p_1<0: \ \ \ x++,\ \ \ \ \ \ \ p_1=p_1+2ry^2x+ry^2$ 
	- Else:    $x++,\ \ \ \ \ \ \ y--,\ \ \ \ \ \ \ \ \ p_1=p_1+2ry^2x-2rx^2y+ry^2$ 
4. Region 2 decision parameter:
	- $p_2=ry^2(x+0.5)^2+rx^2(y-1)^2-rx^2ry^2$ 
5. While $y\geq0$:
	- Plot 4 symmetric points
	- If $p_2>0:     y--,\ \ \ \ \ \ p_2=p_2-2rx^2y+rx^2$ 
	- Else:     $x++,\ \ \ \ \ \ y--,\ \ \ \ \ \ \ p_2=p_2+2ry^2x-2rx^2y+rx^2$ 



*Example:* 
Draw an ellipse with center: $(cx, cy) = (4,5)$ and $rx = 2, ry = 3$, using Mid-point algorithm.

| #   | x   | y   | p1  | p2    |
| --- | --- | --- | --- | ----- |
| 1   | 0   | 3   | -2  | -     |
| 2   | 1   | 3   | 25  | -     |
| 3   | 2   | 2   | 54  | 24.25 |
| 4   | 2   | 1   | 54  | 20.25 |
| 5   | 2   | 0   | 54  | 24.25 |

#### Filling Algorithms
##### Introduction to Filling Algorithms
Filling algorithms are used to determine which pixels within a closed region (such as a polygon, rectangle, or circle) should be colored (illuminated).

They are essential for:
- Coloring the interior of geometric shapes
- Rendering filled objects in 2D and 3D graphics
- Implementing paint-bucket tools and texture fills in applications

**Classification of Filling Algorithms** 
Filling algorithms can be classified based on the type of region being filled:

| Category                 | Description                                      | Typical Algorithms        |
| ------------------------ | ------------------------------------------------ | ------------------------- |
| General Enclosed Regions | Regions bounded by a border or continuous area   | Boundary Fill, Flood Fill |
| Polygonal Regions        | Defined by connected edges forming closed shapes | Scan-Line Polygon Fill    |

**Line**	- A single straight path between two endpoints.
**Polyline**	- Multiple connected line segments, not necessarily closed.
**Polygon** -	A closed set of connected lines forming an enclosed area. - the only enclosed area.


*Types of Polygons* 
Polygons can be classified by their shape and edge relationships.

| Type            | Description                                                                                     | Example                      |
| --------------- | ----------------------------------------------------------------------------------------------- | ---------------------------- |
| Convex Polygon  | All interior angles < 180°, and any line drawn through the polygon intersects it at most twice. | Triangle, rectangle, hexagon |
| Concave Polygon | At least one interior angle > 180°, line through it may intersect more than twice.              | Star, arrowhead              |
| Complex Polygon | Self-intersecting; edges cross one another.                                                     | Bow-tie, infinity (∞) shapes |

*Filling convex polygons* is straightforward.
*Concave and complex polygons* require inside–outside tests and careful edge handling.

**Filling Algorithms for Enclosed Regions** 
Two major algorithms handle general enclosed regions:
- Boundary Fill
- Flood Fill
These are used when you know a starting point inside the shape and either a boundary color (for boundary fill) or a region color (for flood fill).
When filling a region, the algorithm must decide which neighboring pixels are considered connected to the current pixel.
Connectivity determines how the fill propagates through the region.
There are two common connectivity models in raster graphics:

**Connectivity Models** 
When filling a region pixel-by-pixel, the algorithm must define what it means for two pixels to be "connected."
A. *4-Connected Region*
- Logic: A pixel is connected only to its immediate horizontal and vertical neighbors: (x±1,y) and (x,y±1).
- Pros: Simpler and faster to compute.
- Cons: Cannot propagate across diagonals. If a diagonal line of pixels separates a region, a 4-connected fill might stop prematurely.

B. *8-Connected Region*
- Logic: A pixel is connected to all 8 surrounding neighbors, including diagonals: (x±1,y±1).
- Pros: Smoother, more complete filling that can "leak" through diagonal gaps if the boundary isn't perfectly closed.
- Cons: More computationally intensive (checks 8 directions vs 4).

In practice, Boundary Fill and Flood Fill can use either 4- or 8-connectivity. 
The choice depends on whether diagonal pixels are considered part of the same region.

##### Pixel-Based Filling Algorithms (Seed Fill)
These algorithms rely on a starting point (seed) inside the region and propagate outward. They are typically implemented using **recursion** or a **stack**.

A. **Boundary Fill Algorithm** 
Best used when the region has a distinct, uniform **boundary color**.
* **Concept:** Start at a seed point inside the shape. Check if the current pixel is the boundary color or already filled. If not, fill it and recursively check its neighbors.
* **Parameters:** `(x, y, fillColor, boundaryColor)`
* **Termination:** Stops when it hits the specific `boundaryColor`.
* can be implemented with recursion (below), stack or a queue.
```
BoundaryFill(x, y, fillColor, boundaryColor): 
	currentColor = getPixel(x, y) 
	if currentColor != boundaryColor and currentColor != fillColor: 
		setPixel(x, y, fillColor) 
		BoundaryFill(x + 1, y, fillColor, boundaryColor)   # Right 
		BoundaryFill(x - 1, y, fillColor, boundaryColor)   # Left 
		BoundaryFill(x, y + 1, fillColor, boundaryColor)   # Up 
		BoundaryFill(x, y - 1, fillColor, boundaryColor)   # Down
```

B. **Flood Fill Algorithm** 
Best used when the region has a uniform **interior color** (regardless of the border).
* **Concept:** Start at a seed point. Replace the existing color (`oldColor`) with a `newColor`. Continue recursively for all connected neighbors that match `oldColor`.
* **Parameters:** `(x, y, oldColor, newColor)`
* **Termination:** Stops when the pixel color is different from `oldColor`.

| Feature | Boundary Fill | Flood Fill |
| :--- | :--- | :--- |
| **Stop Condition** | Hits a specific **border color** | Hits a **different color** |
| **Use Case** | Shapes with clear outlines | Recolorizing solid areas |
```
FloodFill(x, y, oldColor, newColor): 
currentColor = getPixel(x, y) 
	if currentColor == oldColor: 
		setPixel(x, y, newColor) 
		FloodFill(x + 1, y, oldColor, newColor)   # Right 
		FloodFill(x - 1, y, oldColor, newColor)   # Left 
		FloodFill(x, y + 1, oldColor, newColor)   # Up 
		FloodFill(x, y - 1, oldColor, newColor)   # Down
```


##### Scan-Line Polygon Fill Algorithm (Polygon filling algo)
Unlike seed fills which flood pixel-by-pixel, this geometric algorithm fills the polygon row-by-row (scan line by scan line). It is generally faster and more standard for rendering polygons defined by vertices.

Core Logic
1.  **Intersect:** For a specific horizontal scan line $y$, find all intersection points with the polygon edges.
2.  **Sort:** Sort these intersection points by their $x$-coordinate (left to right).
3.  **Pair & Fill:** Fill pixels between pairs of intersections.
    * *Example:* If intersections are at $x=2, 6, 10, 15$, the algorithm fills spans $[2, 6]$ and $[10, 15]$.

*Data Structures* 
To make this efficient, two tables are used:
* **Edge Table (ET):** Stores all edges sorted by their minimum $y$-coordinate. Each entry contains:
    * $y_{max}$ (where the edge ends).
    * $x_{min}$ (x-value at the bottom of the edge).
    * $1/m$ (inverse slope to increment x for the next scan line).
* **Active Edge Table (AET):** Stores only the edges that currently intersect the scan line being processed. This list is updated as the scan line moves up (adding new edges from ET, removing finished edges).

##### Inside-Outside Tests
For **Concave** and **Complex** polygons, simply connecting edges isn't enough to define the interior. We need mathematical tests to decide if a point $P$ is inside.

A. Even-Odd Rule (Ray Casting)
* **Method:** Draw a ray from point $P$ to infinity (usually rightward). Count how many polygon edges it crosses.
* **Rule:**
    * **Odd** number of crossings $\rightarrow$ Point is **Inside**.
    * **Even** number of crossings $\rightarrow$ Point is **Outside**.
* **Limitation:** Fails for self-intersecting (complex) polygons.

B. Winding Number Method
* **Method:** Calculate the total number of times the polygon winds around point $P$
    * Edge going **up** (relative to point): $+1$ 
    * Edge going **down** (relative to point): $-1$ 
* **Rule:**
    * Total Sum $\neq 0$ $\rightarrow$ Point is **Inside**.
    * Total Sum $= 0$ $\rightarrow$ Point is **Outside**.
* **Advantage:** Accurately handles complex, self-intersecting shapes where the Even-Odd rule fails.
* But is more expensive to calculate


### 2.4 Character Generation
*Methods of Character Generation* 
There are three primary techniques used to generate characters:
##### A) Bitmap (Dot Matrix) Method
In this method, each character is defined by a fixed grid of dots (pixels), such as $5 \times 7$, $7 \times 9$, or $9 \times 15$ matrices.
* **Storage:** The specific grid pattern for each character is stored in a **Character Generator ROM (CG-ROM)**.
* **Rendering:** When a character is needed, the system reads the pattern from the ROM and copies the corresponding pixels to the screen.

* **Advantages:**
    * Simple and very fast to display.
    * Ideal for low-resolution systems or console terminals.
* **Disadvantages:**
    * **Poor Scaling:** enlarging or rotating the character causes "jaggies" (aliasing) and distortion.
    * **Memory Usage:** Each different font size requires a completely separate pattern table.

##### B) Stroke (Vector) Method
Here, characters are formed using a series of straight lines or curves, known as **strokes**.
* **Storage:** Defined by the start and end coordinates of the strokes.
* **Rendering:** The system draws the strokes using standard line-drawing algorithms (like DDA or `Bresenham`).

* **Advantages:**
    * **Scalable:** Can be resized or rotated without any loss of quality.
    * **Flexible:** Easy to modify or animate.
* **Disadvantages:**
    * **Slower:** Requires more computation to render compared to simply copying a bitmap grid.

##### C) Starburst Method
This is a specialized vector-based technique used in systems with limited memory or specific hardware constraints (like oscilloscopes or radar displays).

* **Concept:** Characters are drawn using lines (rays) that radiate from a common center point. Imagine a fixed set of evenly spaced radial lines (like a starburst pattern).
* **Rendering Steps:**
    1.  Generate $n$ evenly spaced radial lines from an origin.
    2.  Use a lookup table to determine which specific rays correspond to a character.
    3.  Activate (light up) only the relevant rays to form the shape.
    * *Example:* To form an 'A', the system might light two outer diagonal rays and a connecting segment.

* **Advantages:**
    * **Memory Efficient:** Stores only angles and ray indices.
    * **Simple Implementation:** Great for hardware-controlled vector displays.
* **Disadvantages:**
    * **Low Quality:** Not suitable for complex or aesthetic fonts.
    * **Spacing Issues:** Difficult to achieve precise proportional spacing.

Summary

| Method        | Representation     | Advantages                        | Disadvantages                |
| :------------ | :----------------- | :-------------------------------- | :--------------------------- |
| **Bitmap**    | Dot/Pixel pattern  | Fast, simple implementation       | Poor scaling (distortion)    |
| **Stroke**    | Line segments      | Scalable, rotatable, editable     | Slower rendering computation |
| **Starburst** | Radial rays        | Low memory use, hardware friendly | Limited accuracy/quality     |
| **Outline**   | Curves and vectors | High-quality, flexible            | Complex to compute           |

### Line, Color, and Area/Character Attributes

##### 1. Line Attributes
Line attributes customize the appearance of lines, which is crucial for distinguishing between different object types (e.g., hidden edges vs. construction lines) in visualization and CAD systems.

1.  **Line Type:** Determines the pixel pattern used to draw the line.
    * **Types:** Solid, Dashed, Dotted, Dash-Dot.
    * **Generation:** Achieved by systematically turning pixel plotting **on** and **off** along the line path. 
2.  **Line Width:** Defines the thickness. Thicker lines are generated by plotting **additional pixels** adjacent to the theoretical line path.
3.  **Line Color:** Specifies the color chosen from the system's available color palette.
4.  **Join and Cap Styles:** Control how lines meet and end.
    * **Join Styles:** Control corners (e.g., **Miter**, **Round**, or **Bevel**).
    * **Cap Styles:** Define the shape at the line endpoints (e.g., **Butt**, **Round**, or **Projecting**).

##### 2. Color and Gray Scale Levels
The visual quality of a display depends on how color and intensity are represented numerically.
1.  **Color Models:** Systems use standard models to define colors:
    * **RGB (Red, Green, Blue):** An **additive** model primarily used for **monitors** and display devices (mixing light).
    * **CMY/CMYK (Cyan, Magenta, Yellow, Black):** A **subtractive** model primarily used for **printing** devices (mixing pigments).
    * **HSV/HSL (Hue, Saturation, Value/Lightness):** Represents color in terms of human perception.
2.  **Gray Scale Levels:** In monochrome (black and white) displays, intensity is defined by shades of gray.
    * An $n$-bit system can represent $2^n$ distinct intensity levels.
    * *Example:* An **8-bit** system provides $2^8 = 256$ shades of gray.
3.  **Color Resolution:** The total number of simultaneously displayable colors is determined by the **bits per pixel (bpp)**.
    * **24-bit Color:** Uses 8 bits for each of the R, G, and B components, yielding $2^{24} = 16,777,216$ colors (often called **True Color**).



##### 3. Area Fill and Character Attributes

**A. Area Fill Attributes**
These attributes define the appearance of regions bounded by lines.
* **Fill Style:** Determines the pattern of the interior: **solid**, **hatch**, **crosshatch**, **dotted**, or a user-defined pattern.
* **Fill Color:** Specifies the primary color for the filled area.
* **Fill Opacity (Transparency):** Controls how much the background shows through the filled region.
* **Advanced Fills:** **Tiling** (repeated texture) and **Gradient Fills** (smooth color transitions).

**B. Character Attributes (Typography)** 
These attributes define the style, size, orientation, and color of displayed text, greatly impacting readability and aesthetic appeal.

1.  **Font Type:** The set of characters with consistent visual features (stroke width, spacing, ornamentation).
    * **Serif Fonts:** Include small decorative strokes (**serifs**) at the ends of the main letter strokes. They often have variable stroke widths and aid visual flow in long text blocks (e.g., Times New Roman). 
    * **Sans-Serif Fonts:** (French for "without serifs") Omit the decorative endings. They typically have uniform stroke widths and simple, geometric forms, often preferred for digital screens and headings (e.g., Arial, Helvetica).
2.  **Other Attributes:**
    * **Font Size:** Determines the character's height and width.
    * **Text Color:** The color used to draw the character.
    * **Orientation and Alignment:** Rotation angle and positioning.
    * **Style Modifications:** Effects like **Bold**, *Italic*, underline, and shadow.



# CH-3: 2D Transformations and Views
Transformations:
- Translation
- Scaling
- Rotation/ Reflection
- Shearing (distort).

Using matrices allows multiple transformations to be combined (or composed) into a single operation, improving both efficiency and precision.

To represent transformations such as translation (which is not purely linear), we extend our coordinate system using homogeneous coordinates — a powerful mathematical trick that makes all transformations compatible with matrix multiplication.

**Viewing Concepts** 
Once an object’s geometry has been defined and transformed, we decide how it should appear in the final display.
This process, known as *viewing*, involves:
- Choosing a viewing coordinate system
- Selecting a window (portion of the world to display)
- Mapping that window to a viewport (the actual screen area)
- Clipping: trimming objects that lie outside the viewable region
These steps together form the Viewing Pipeline, which ensures that the final image accurately represents the desired part of the scene.

##### Translation 
$P(x,y)$ to $P(x',y')$ where:
- $x'=x+t_x$ 
- $y'=y+t_y$ 

Matrix Form (Homogeneous Coordinates):
$$
  T(x,y) =
  \begin{bmatrix}
  1 & 0 & t_x \\
  0 & 1 & t_y \\
  0 & 0 & 1
  \end{bmatrix}
$$

##### Scaling
If $S_x$ and $S_y$ are scaling factors, then:
- $x'=S_x * x$,
- $y'=S_y * y$ 

Matrix Form: (respect to origin)
$$
  S(x,y) =
  \begin{bmatrix}
  s_x & 0 & 0 \\
  0 & s_y & 0 \\
  0 & 0 & 1
  \end{bmatrix}
$$

Effects:
- $S_x=S_y>1$: uniform enlargement
- $S_x=S_y<1$: uniform reduction
- $S_x\neq S_y$: non-uniform scaling (distortion)

Matrix form (respect to any arbitrary point $P(a,b$)): -> translate -> scale -> translate back
  $$S(x,y) =
  \begin{bmatrix}
  s_x & 0 & -as_x+a \\
  0 & s_y & -bs_y+b \\
  0 & 0 & 1
  \end{bmatrix}$$
  $T(-a,-b) \rightarrow  S(s_x,s_y)\rightarrow T(a,b)$ 
  $$
\begin{bmatrix}
1 & 0 & a \\
0 & 1 & b \\
0 & 0 & 1
\end{bmatrix}
\cdot
\begin{bmatrix}
s_x & 0 & 0 \\
0 & s_y & 0 \\
0 & 0 & 1
\end{bmatrix}
\cdot
\begin{bmatrix}
1 & 0 & -a \\
0 & 1 & -b \\
0 & 0 & 1
\end{bmatrix}
=
\begin{bmatrix}
s_x & 0 & -a s_x + a \\
0 & s_y & -b s_y + b \\
0 & 0 & 1
\end{bmatrix}
$$
(the right matrix is the first. (bs))


##### Rotation
- about an angle $\theta$.
For counter clockwise rotation about thee origin:
- $x'=x\cos \theta-y\sin\theta$ 
- $y'=x\sin\theta+y\cos\theta$ 

Matrix:
$$
  R(\theta) =
  \begin{bmatrix}
  \cos\theta & -\sin\theta & 0 \\
  \sin\theta & \cos\theta & 0 \\
  0 & 0 & 1
  \end{bmatrix}
$$

##### Reflection
About X-axis	
$$\begin{bmatrix}1&0&0\\0&-1&0\\0&0&1\end{bmatrix}$$
About Y-axis	$$\begin{bmatrix}-1&0&0\\0&1&0\\0&0&1\end{bmatrix}$$
About X=Y	$$\begin{bmatrix}0&1&0\\1&0&0\\0&0&1\end{bmatrix}$$
About Origin	$$\begin{bmatrix}-1&0&0\\0&-1&0\\0&0&1\end{bmatrix}$$ 
##### Shearing
There are two types:
-	X-shear: shifts x-coordinates proportionally to y.
-	Y-shear: shifts y-coordinates proportionally to x.
$x^\prime=x+sh_x\cdot y$,
$y^\prime=y+sh_y\cdot x$ 

Matrix:
$$  H =
  \begin{bmatrix}
  1 & k_x & 0 \\
  k_y & 1 & 0 \\
  0 & 0 & 1
  \end{bmatrix}$$  


### Transformations About Origin vs. About Pivot Point
All the formulas above assume transformations occur around the origin (0, 0).
But in practice, we often need to rotate, scale, or shear about an arbitrary point $(x_p, y_p)$ called the pivot point.

**Steps for Transformation About a Pivot Point**:
Let the pivot be $P(x_p,y_p)$, and suppose we want to apply a transformation T (e.g., rotation or scaling) around it.
1. Translate the object so the pivot moves to the origin.
2. Apply the desired transformation
	- e.g., Rotation $R(\theta)$ or Scaling $S(s_x,s_y)$ 
3. Translate back to the original pivot position
	- $T(x_p,y_p)$ 

### Matrix Representation and Homogeneous Coordinates
Each point $P(x,y)$ is represented as a column vector:
- $\mathbf{P}=\begin{bmatrix}x\\ y\end{bmatrix}$ 
A transformation T is represented as a matrix:
- $P'=T*P$ 

**Benefits of using matrices:**
1. *Uniform representation*: All transformations (except translation in standard 2×2 form) are linear and can be expressed using matrices.
2. *Composite transformations*: Multiple transformations can be combined into a single matrix, reducing computation.
3. *Hardware-friendly*: Matrix multiplication is highly parallelizable, which modern graphics hardware (GPUs) excels at.

**Why Homogenous Coordinates?** 
Standard 2×2 matrices can handle rotation, scaling, reflection, and shear, but translation cannot be expressed using a 2×2 linear matrix.
so: $(x,y)->(x,y,1)$ 

### Composite Transformations
Multiple transformations applied in sequence.
**Order Matters**: Applying rotation before translation gives a different result than translation before rotation.
Are achieved by multiplying matrices in the correct sequence:
$$M=T\times R\times S$$
The resulting matrix M is used to transform the Object.

When we want to perform a transformation (rotation, scaling, shear, etc.) about an arbitrary pivot point rather than the origin, we can efficiently use composite transformations.
$$M_{composite}=T(x_p,y_p)\cdot T_{transform}\cdot T(-x_p,-y_p)$$ 
Where:
-	$𝑇(−𝑥_𝑝,−𝑦_𝑝)$moves the pivot to the origin
-	$𝑇_{transform}$ is the matrix of the desired transformation (scale, rotate, etc.)
-	$𝑇(𝑥_𝑝,𝑦_𝑝)$ moves the object back so the pivot stays fixed



### The Viewing Pipeline
Is the process of converting objects defined in world coordinates into device coordinates (screen pixels).
It ensures that only the relevant portion of the scene is displayed from a specific viewpoint.
The major stages are:
1. *Modeling Transformation* – Converts object coordinates to world coordinates.
2. *Viewing Transformation* – Aligns the scene according to the camera or observer’s viewpoint.
3. *Projection Transformation* – Projects 3D or 2D scenes onto a 2D view plane.
4. *Clipping* – Removes parts of objects outside the visible area.
5. *Viewport Transformation* – Maps the visible part of the scene to the actual screen coordinates.
This pipeline guarantees that the visual output correctly reflects the virtual scene setup.

### Viewing Coordinate Reference Frame

AKA camera coordinate system - defines how the scene is observed.
In 2D, it determines which region of the world coordinates will appear on the screen.

It is established by:
- Choosing a *view reference point* (VRP) — the center of the view.
- Defining the *view up direction* (VUP) — orientation of the camera.
- Setting the *view window* (or window rectangle) — the area of the world that will be visible.

This transformation converts coordinates from world space → view space, allowing flexible camera movement and zooming.

### Window-to-Viewport Coordinate Transformation
After defining the view window (the part of the world we want to see), it must be mapped to a viewport (the part of the display screen where it will appear).

Let:
- Window: ($xw_{min}, xw_{max}, yw_{min}, yw_{max})$ 
- Viewport: $(xv_{min}, xv_{max}, yv_{min}, yv_{max})$ 
The mapping equations are:
$$
x_v=x_vmin+\frac{(x_w-x_{wmin})(x_{vmax}-x_{vmin})}{x_{wmax}-x_{wmin}}$$$$
y_v=y_vmin+\frac{(y_w-y_{wmin})(y_{vmax}-y_{vmin})}{y_{wmax}-y_{wmin}}$$
This process preserves aspect ratio and ensures the visible portion of the scene fits correctly within the display region.

### Point, Line and Polygon Clipping

The clipping window is usually rectangular in 2D graphics and is defined by its minimum and maximum x and y coordinates:
$$x_{min},x_{max},y_{min},y_{max}$$ 
Types of clipping:
- **Point clipping**: A point is visible if it lies within the clipping window.
- **Line clipping**: Uses algorithms like Cohen–Sutherland or Liang–Barsky to efficiently clip lines.
- **Polygon clipping**: Algorithms like Sutherland–Hodgman ensure that polygons are properly trimmed to fit within the window.

##### Point Clipping
A point is either inside the clipping window (and thus visible) or outside (and discarded).
Algorithm:
1. Check the x-coordinate:
	- $x_{min}\le x\le x_{max}$
2. Check the y-coordinate:
	- $y_{min}\le y\le y_{max}$
3. Decision:
	- If both conditions are satisfied → point is inside (visible).
	- Otherwise → point is outside (clipped).


##### Line Clipping
**Basic Idea** 
- Represent the line by its endpoints $P_1(x_1,y_1)$ and $P_2(x_2,y_2)$.
- Check whether each endpoint is inside or outside the window.
- Compute intersections with the window boundaries if necessary.
- Return the visible segment inside the clipping window.

 **a) Cohen–Sutherland Line Clipping Algorithm**
Steps:
1. *Assign `outcodes` to endpoints*  
	- Each endpoint is given a 4-bit `outcode` that indicates its position relative to the clipping window: 
		- Bit 1 (Top)
		- Bit 2 (Bottom) 
		- Bit 3 (Right) 
		- Bit 4 (Left) 
	- Give ‘1’ if the region is in the right place of TBRL and give ‘0’ otherwise.

2. *Trivial accept/reject tests* 
	- If both `outcodes` = 0 → both endpoints lie inside the window → **accept the line**. 
	- If the logical AND of the two `outcodes` ≠ 0 → line lies completely outside → **reject the line**. 
3. *Iterative clipping process* 
	- Select an endpoint that lies outside the window.  
	- Compute the intersection of the line with the relevant boundary (top, bottom, left, or right). 
	- Replace the outside endpoint with this intersection point.  
	- Recalculate the `outcodes` and repeat until the line is either accepted or rejected. 

*Mathematical Intersection Formulas*:
If a line is being clipped against a vertical or horizontal boundary, we use the slope $m = \frac{y_2 - y_1}{x_2 - x_1}$ to find the intersection point $(x_h, y_v)$:
- Left/Right Boundary ($x$ is fixed): $$y = y_1 + m \cdot (x_{boundary} - x_1)$$
- Top/Bottom Boundary ($y$ is fixed): $$x = x_1 + \frac{(y_{boundary} - y_1)}{m}$$

**b) Liang–Barsky Line Clipping Algorithm** 
An alternative, more mathematical approach:
- Uses parametric line equations:
$$x=x_1+t(x_2-x_1),~~~y=y_1+t(y_2-y_1),~0\le t\le1$$ 
- Calculates *t values* where the line intersects the clipping boundaries.
- Determines the entering and leaving points efficiently.

*ALGORITHM*:
Step 1: Initialize Parameters
* Calculate $\Delta x = x_2 - x_1$ 
* Calculate $\Delta y = y_2 - y_1$ 
* Set $u_1 = 0$ (the start of the line)
* Set $u_2 = 1$ (the end of the line)

Step 2: Define Boundary Pairs ($p$ and $q$)
For each of the four boundaries, calculate the $p_k$ (the direction relative to the boundary) and $q_k$ (the distance from the boundary).

| $k$ | Boundary   | $p_k$       | $q_k$           |
| --- | ---------- | ----------- | --------------- |
| 1   | **Left**   | $-\Delta x$ | $x_1 - x_{min}$ |
| 2   | **Right**  | $\Delta x$  | $x_{max} - x_1$ |
| 3   | **Bottom** | $-\Delta y$ | $y_1 - y_{min}$ |
| 4   | **Top**    | $\Delta y$  | $y_{max} - y_1$ |

Step 3: Test for Parallelism and Visibility

For each $k$ (from 1 to 4), perform the following checks:
1. **If $p_k = 0$:** The line is parallel to boundary .
	* If $q_k < 0$, the line is entirely outside the window. **Stop and discard the line.**
2. **If $p_k < 0$:** The line is moving from the **outside to the inside** of that boundary.
	* Calculate $r = q_k / p_k$.
	* Update $u_1 = \max(u_1, r)$.
3. **If $p_k > 0$:** The line is moving from the **inside to the outside** of that boundary.
	* Calculate $r = q_k / p_k$.
	* Update $u_2 = \min(u_2, r)$.

Step 4: Final Validity Check
After checking all four boundaries:
* **If $u_1 > u_2$:** The line segment is entirely outside the clipping region. **Discard the line.**
* **If $u_1 \leq u_2$:** The line is visible between the two new points.

Step 5: Calculate Clipped Coordinate
If the line passed the validity check, use the final  and  values to find the new endpoints $(x_1', y_1')$ and $(x_2', y_2')$:
* **New Start Point ($P_1'$):**
$$x_1' = x_1 + u_1 \Delta x$$
$$y_1' = y_1 + u_1 \Delta y$$

* **New End Point ($P_2'$):**
$$x_2' = x_1 + u_2 \Delta x$$
$$y_2' = y_1 + u_2 \Delta y$$


# CH-4: 3D-Transformations

**Translation** 
$$
  T(x,y,z) =
  \begin{bmatrix}
  1 & 0 & 0 & t_x \\
  0 & 1 & 0 & t_y \\
  0 & 1 & 1 & t_z \\
  0 & 0 & 0 & 1
  \end{bmatrix}
$$
**Scaling** 
$$
  S(x,y,z) =
  \begin{bmatrix}
  sx & 0 & 0 & 0 \\
  0 & sy & 0 & 0 \\
  0 & 0 & sz & 0 \\
  0 & 0 & 0 & 1
  \end{bmatrix}
$$
**Rotation** 
- about z-axis: same as 2D, z-axis not affected.
$$
  R(\theta) =
  \begin{bmatrix}
  \cos\theta & -\sin\theta & 0 & 0\\
  \sin\theta & \cos\theta & 0 & 0\\
  0 & 0 & 1 & 0 \\
  0 & 0 & 0 & 1
  \end{bmatrix}
$$
- about y-axis
$$
  R(\theta) =
  \begin{bmatrix}
  \cos\theta & 0 & -\sin\theta & 0\\
  0 & 1 & 0 & 0 \\
  \sin\theta & 0 & \cos\theta & 0\\
  0 & 0 & 0 & 1
  \end{bmatrix}
  $$
  - about y-axis
$$
  R(\theta) =
  \begin{bmatrix}
  1 & 0 & 0 & 0 \\
  0 & \cos\theta & \sin\theta & 0\\
  0 & -\sin\theta & \cos\theta & 0\\
  0 & 0 & 0 & 1
  \end{bmatrix}
  $$
