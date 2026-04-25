
## **Window to Viewport Transformation**

### **Introduction**
* **Window to Viewport Transformation** is the process of mapping 2D world-coordinate objects to device coordinates.
* Objects located inside the world coordinate area (or clipping window) are mapped to the viewport, which represents the physical area on the screen where the objects will be displayed.
* **Core Concept:** The window defines what is to be viewed, whereas the viewport defines where it is to be displayed.

---

### **Key Terminology**
* **World Coordinate:** The Cartesian coordinate system used to define the actual objects or diagram. It uses boundaries such as $X_{wmin}$, $X_{wmax}$, $Y_{wmin}$, and $Y_{wmax}$.
* **Window:** A specific area within the world coordinates that is selected for display.
* **Device Coordinate:** The screen coordinate system where the graphics are ultimately rendered. It uses boundaries such as $X_{vmin}$, $X_{vmax}$, $Y_{vmin}$, and $Y_{vmax}$.
* **Viewport:** The designated area on the display device where the window's contents are mapped and shown.

---

### **The Need for Mathematical Transformation**
It is common for the size of the Viewport to be much smaller or larger than the Window. Because of this size discrepancy, mathematical calculations are required to properly scale (increase or decrease) the size of the Window to fit the Viewport. 

If we have a known point $(X_w, Y_w)$ on the Window, our goal is to calculate the corresponding point $(X_v, Y_v)$ on the Viewport.

---

### **The Transformation Process**
The mapping involves a three-step process:
1. **Translation:** Translate the Window coordinates to a normalized coordinate system (falling within the range of $0$ to $1$).
2. **Scaling:** Scale the normalized coordinates so they match the dimensions of the device coordinate system (the viewport).
3. **Translation:** Translate the scaled coordinates into their final position on the Device coordinate (viewport) system.

---

### **Mathematical Derivation**
To ensure the image looks correct, the relative placement of the point in the Viewport must be identical to its relative placement in the Window. 

We achieve this by equating the normalized point on the Window to the normalized point on the Viewport:

$$\frac{X_w - X_{wmin}}{X_{wmax} - X_{wmin}} = \frac{X_v - X_{vmin}}{X_{vmax} - X_{vmin}}$$

By solving for the viewport coordinates $(X_v, Y_v)$, we get the following transformation equations:

$$X_v = X_{vmin} + (X_w - X_{wmin})S_x$$

$$Y_v = Y_{vmin} + (Y_w - Y_{wmin})S_y$$

Where $S_x$ and $S_y$ represent the scaling factors for the x and y coordinates, respectively:

$$S_x = \frac{X_{vmax} - X_{vmin}}{X_{wmax} - X_{wmin}}$$

$$S_y = \frac{Y_{vmax} - Y_{vmin}}{Y_{wmax} - Y_{wmin}}$$

---

### **Solved Example**

**Given Data:**
* **Window Boundaries:** $X_{wmin}=20$, $X_{wmax}=80$, $Y_{wmin}=40$, $Y_{wmax}=80$.
* **Viewport Boundaries:** $X_{vmin}=30$, $X_{vmax}=60$, $Y_{vmin}=40$, $Y_{vmax}=60$.
* **Point on Window:** $(X_w, Y_w) = (30, 80)$.

**Objective:** Calculate the corresponding point $(X_v, Y_v)$ on the viewport.

**Step 1: Calculate the Scaling Factors ($S_x$ and $S_y$)**
* $S_x = (60 - 30) / (80 - 20) = 30 / 60 = 0.5$
* $S_y = (60 - 40) / (80 - 40) = 20 / 40 = 0.5$

**Step 2: Calculate the Viewport Coordinates ($X_v, Y_v$)**
* $X_v = 30 + (30 - 20) \times (30 / 60) = 30 + (10 \times 0.5) = 35$
* $Y_v = 40 + (80 - 40) \times (20 / 40) = 40 + (40 \times 0.5) = 60$

**Final Answer:**
The point $(30, 80)$ on the window correctly maps to the point $(35, 60)$ on the viewport.


## **Clipping in Computer Graphics**

### **Introduction to Clipping**
* When displaying a large picture, scaling and translation are not enough; the visible part of the picture must also be identified.
* This process is complex, as certain parts of an image may be completely inside the display area, while others are only partially inside.
* Elements or lines that are only partially visible will have their invisible portions omitted.
* The specific process used to decide which portions are visible and which are invisible is called clipping.
* Clipping separates elements into visible and invisible portions, selecting the visible part for display and discarding the invisible part.

---

### **The Clip Window**
* The boundary against which an object is clipped is known as a clip window.
* Clip windows can be curved or rectangular in shape.

---

### **Categories of Lines**
During the clipping process, lines generally fall into one of three categories:
* **Visible Lines:** A line is entirely visible if it lies completely within the window (both endpoints are inside) and will be displayed exactly as it is.
* **Not Visible (Invisible) Lines:** If a line lies completely outside the window, it is considered invisible and is rejected entirely.
* **Clipping Case (Mixed Lines):** If a line is neither completely visible nor completely invisible, it is a clipped case. The portion outside the window is rejected, while the portion inside is accepted.

---

### **Applications of Clipping**
* Extracting a specific desired part of an image.
* Identifying visible and invisible areas in both 2D and 3D objects.
* Assisting in general drawing operations.
* Performing operations like deleting, copying, or moving specific parts of an object.

---

### **Types of Clipping**
Various types of clipping techniques exist, including:
* Point Clipping
* Line Clipping
* Area (Polygon) Clipping
* Curve Clipping
* Text Clipping
* Exterior Clipping

---

## **Cohen-Sutherland Line Clipping Algorithm**

### **Overview**
* The Cohen-Sutherland algorithm is the most popular line clipping method.
* It speeds up the processing of line segments by performing initial tests that reduce the number of mathematical intersections that need to be calculated.

---

### **Finding Intersecting Points**
To clip a line, we must find where it intersects with the window boundaries using the slope $m$ and the line equation:
* **Left Boundary ($x = x_{wmin}$):** $y = y_1 + m(x_{wmin} - x_1)$.
* **Right Boundary ($x = x_{wmax}$):** $y = y_1 + m(x_{wmax} - x_1)$.
* **Bottom Boundary ($y = y_{wmin}$):** $x = x_1 + (y_{wmin} - y_1) / m$.
* **Top Boundary ($y = y_{wmax}$):** $x = x_1 + (y_{wmax} - y_1) / m$.

---

### **Region Codes**
Every line endpoint is assigned a 4-digit binary code called a region code, which identifies its location relative to the clipping window boundaries. The bits are set as follows:
* **Bit 1 (Left):** Set to 1 if $x < x_{min}$. Indicates intersection with the left boundary.
* **Bit 2 (Right):** Set to 1 if $x > x_{max}$. Indicates intersection with the right boundary.
* **Bit 3 (Bottom/Below):** Set to 1 if $y < y_{min}$. Indicates intersection with the bottom boundary.
* **Bit 4 (Top/Above):** Set to 1 if $y > y_{max}$. Indicates intersection with the top boundary.

![alt text](image-18.png)

**Region Code Table Reference:**
* Top-Left: 1001
* Top-Center: 1000
* Top-Right: 1010
* Center-Left: 0001
* Inside Window: 0000
* Center-Right: 0010
* Bottom-Left: 0101
* Bottom-Center: 0100
* Bottom-Right: 0110

---

### **Algorithm Steps**
* **Step 1:** Assign a region code to the two endpoints of the given line.
* **Step 2:** If both endpoints have a code of 0000, the line is completely inside and is accepted.
* **Step 3:** Else, perform a logical AND operation on both region codes.
    * **Step 3.1:** If the result is not 0000, the line is completely outside and is rejected.
    * **Step 3.2:** Else, the line is partially inside.
        * **Step 3.2.1:** Choose an endpoint that is outside the given rectangle.
        * **Step 3.2.2:** Find the intersection point with the rectangular boundary.
        * **Step 3.2.3:** Replace the outside endpoint with this intersection point and update its region code.
        * **Step 3.2.4:** Repeat from Step 2 until the clipped line is either trivially accepted or rejected.
* **Step 4:** Repeat Step 1 for any other lines in the picture.

---

### **Solved Examples**

#### **Example 1: Left and Top Edge Intersections**
* **Given:** Clipping window from lower-left $(2,1)$ to upper-right $(7,5)$. Line points are $P1(1,3)$ and $P2(5,6)$.
* **Initial Codes:** $P1$ region code is 0001 and $P2$ region code is 1000.
* **Check:** $P1$ AND $P2$ (0001 AND 1000) equals 0000, meaning it is a candidate for clipping.

**Clipping P1 (Left Edge):**
* $P1$ intersects the left edge where $X=2$.
* Slope $m = (6-3) / (5-1) = 3/4 = 0.75$.
* Calculate $Y$: $y = 3 + 0.75(2-1) = 3.75$.
* New $P1$ is $(2, 3.75)$ with an updated region code of 0000.

**Clipping P2 (Top Edge):**
* $P2$ intersects the top edge where $Y=5$.
* Calculate $X$: $x = 5 + (5-6) / 0.75 = 5 - 1.33 = 3.66$.
* New $P2$ is $(3.66, 5)$ with an updated region code of 0000.

**Conclusion:** Both $P1$ and $P2$ region codes are now 0000. The line is completely accepted and the algorithm stops.

#### **Example 2: Bottom and Top Edge Intersections**
* **Given:** Clipping window from lower-left $(2,1)$ to upper-right $(7,5)$. Line points are $P1(6,0)$ and $P2(5,6)$.
* **Initial Codes:** $P1$ region code is 0100 and $P2$ region code is 1000.
* **Check:** $P1$ AND $P2$ (0100 AND 1000) equals 0000.

**Clipping P1 (Bottom Edge):**
* $P1$ intersects the below edge where $Y=1$.
* Slope $m = (6-0) / (5-6) = 6/-1 = -6$.
* Calculate $X$: $x = 6 + (1-0) / -6 = 6 - 0.1667 = 5.83$.
* New $P1$ is $(5.83, 1)$ with a new region code of 0000.

**Clipping P2 (Top Edge):**
* $P2$ intersects the above edge where $Y=5$.
* Calculate $X$: $x = 5 + (5-6) / -6 = 5 + 0.167 = 5.167$.
* New $P2$ is $(5.167, 5)$ with a new region code of 0000.

**Conclusion:** Both endpoints are 0000, so the line is accepted and the process stops.

#### **Example 3: Multi-Boundary Intersection**
* **Given:** Window from $(2,2)$ to $(4,4)$. Line from $P1(8,3)$ to $P2(3,6)$.
* **Initial Codes:** $P1 = 0010$ and $P2 = 1000$.
* **Check:** $P1$ AND $P2$ equals 0000.

**Calculations:**
* Slope $m = (6-3) / (3-8) = 3/-5 = -0.6$.

**First Intersection (Top Boundary $Y=4$):**
* $x = 8 + (4-3) / -0.6 = 8 - 1.67 = 6.33$.
* Point becomes $(6.33, 4)$, but its region code is still 0010 (outside on the right).

**Second Intersection (Right Boundary $X=4$):**
* $y = 4 + (-0.6)(4-3) = 4 - 0.6 = 3.4$.
* Point becomes $(4, 3.4)$ with an updated region code of 0000.

**Conclusion:** The point reaches complete acceptance conditions (0000) with no further intersections, so the process stops.

## **Sutherland-Hodgeman Polygon Clipping Algorithm**

### **Algorithm Overview**
* The Sutherland-Hodgeman algorithm is performed by processing the boundary of a polygon against each window corner or edge.
* The process works sequentially: first, the entire polygon is clipped against one edge.
* The resulting, newly formed polygon is then considered and clipped against the second edge.
* This sequential process is repeated for all four edges of the clipping window.

---

### **The Four Clipping Rules (Cases)**
When processing each edge of the polygon (evaluating from the first vertex to the second vertex) against a window boundary, the algorithm applies one of four rules:

* **Case 1: Outside to Inside**
  * **Condition:** The first vertex is outside the window, and the second vertex is inside the window.
  * **Output:** The point of intersection between the window boundary and the polygon side (edge) is added to the output list, and the second vertex is also added to the output list.
* **Case 2: Inside to Inside**
  * **Condition:** Both the first and second vertices are inside the window boundary.
  * **Output:** Only the second vertex is added to the output list.
* **Case 3: Inside to Outside**
  * **Condition:** The first vertex is inside the window, and the second vertex is outside the window.
  * **Output:** Only the edge that intersects with the window (the point of intersection) is added to the output list.
* **Case 4: Outside to Outside**
  * **Condition:** Both vertices are completely outside the window.
  * **Output:** Nothing is added to the output list.

---

### **Disadvantage of the Algorithm**
* A primary disadvantage of this algorithm (referred to in the text as the Cohen-Hodgman Algorithm) is that it requires a considerable amount of memory.

---

### **Step-by-Step Polygon Clipping Trace**
The document provides a tabular breakdown of the algorithm applying the four rules to a polygon with vertices A, B, C, D, and E across multiple stages.

**Stage 1: Clipping Against the First Boundary (Left Edge)**
| Vertex | Case | Output |
| :--- | :--- | :--- |
| AB | in in | B |
| BC | in in | C |
| CD | in in | D |
| DE | in out | D' |
| EA | out in | E'A |
*Source Table 1*

**Stage 2: Clipping Against the Second Boundary (Right Edge)**
| Vertex | Case | Output |
| :--- | :--- | :--- |
| AB | in out | A' |
| BC | out in | B'C |
| CD | in in | D |
| DD' | in in | D' |
| D'E' | in in | E' |
| E'A | in in | A |
*Source Table 2*

**Stage 3: Clipping Against the Third Boundary (Bottom Edge)**
| Vertex | Case | Output |
| :--- | :--- | :--- |
| AA' | in in | A' |
| A'B' | in in | B' |
| B'C | in in | C |
| CD | in out | C' |
| DD' | out in | D'' D' |
| D'E' | in in | E' |
| E'A | in in | A |
*Source Table 3*

**Stage 4: Clipping Against the Fourth Boundary (Top Edge)**
| Vertex | Case | Output |
| :--- | :--- | :--- |
| AA' | out in | A'' A |
| A'B' | in in | B' |
| B'C | in in | C |
| CC' | in in | C' |
| C'D'' | in in | D'' |
| D''D' | in in | D' |
| D'E' | in in | E' |
| E'A | in out | E'' |
*Source Table 4*

![alt text](image-19.png)
![alt text](image-20.png)

## **Three-Dimensional Viewing Pipeline**

### **Overview**
* The steps required for the computer generation of a view of a three-dimensional scene are somewhat analogous to the processes involved in taking a photograph. 

---

### **Detailed Stage Descriptions**

* **Modeling & World Coordinates:** The process begins by constructing the shape of individual objects in a scene within modeling coordinates. Deciding the dimensions of how much of the scene to capture is called the modeling transformation. This step involves placing the objects into appropriate positions within the scene to fit them into the frame's world coordinates. 
* **Viewing Transformation:** This stage is analogous to setting the position and orientation of the camera. 
* **Viewing Coordinates:** Appropriate scaling up or down is performed so that the proper view becomes available within the camera window coordinates, which are also known as viewing coordinates. 
* **Projection Transformation:** This step converts the viewing coordinate description of the scene into coordinate positions on the projection plane. This is analogous to adjusting the focus of the camera and the direction of light, resulting in an image formed in the camera frame or film projection coordinates. 
* **Workstation Transformation:** This final step involves the window-to-viewport transformation. It is similar to clicking the camera button, resulting in the final image being formed on the camera screen, represented by device coordinates.

![alt text](image-21.png)


## **Projections in Computer Graphics**

### **Introduction to Projections**
* Once the world-coordinate descriptions of objects in a scene are converted into viewing coordinates, the 3D objects can be projected onto a 2D view plane. 
* The projected view of an object is determined by calculating the points of intersection between the projection lines and the view plane. 

---
![alt text](image-22.png)

### **Basic Projection Methods**
There are two fundamental methods of projection: 

* **Parallel Projection:**
  * Coordinate positions are transformed onto the view plane along parallel lines. 
  * **Characteristics:** It preserves the relative proportions of the objects. While it provides accurate views of the various sides of an object, it does not produce a realistic representation of a 3D object. 

* **Perspective Projection:**
  * Coordinate positions are transferred to the view plane along lines that converge to a single, specific point. 
  * This point of convergence is referred to as the projection reference point or the center of projection. 
  * **Characteristics:** It produces a highly realistic view of an object, but it fails to preserve the object's relative proportions. 

---

### **Classification of Parallel Projections**
Parallel projections are categorized into two main branches: 
* **Orthographic Projections:** This includes Top, Front, Side, and Axonometric projections. 
* **Oblique Projections:** This includes Cavalier and Cabinet projections. 

---

### **Orthographic Projections**
* In an orthographic projection, the direction of projection is strictly normal (perpendicular) to the projection plane. 
* The standard types of orthographic projections are: 
  * Front Projection. 
  * Top Projection (often called the plan view). 
  * Side Projection. 
* **Transformation Equations:** The mathematical transformations for an orthographic parallel projection are straightforward. If a view plane is placed at position zvp along the z-axis, any point (x, y, z) in the viewing coordinate system is transformed to projection coordinates simply as xp = x and yp = y. 

---

### **Orthographic Projections of a Unit Cube**
The text details the coordinates for projecting a 3D unit cube (with vertices A through H) onto three distinct 2D planes: 

![alt text](image-23.png)


**1. Projection onto the X = 0 Plane (YZ Plane Projection):** * A(0,0,0) projects to A'(0,0,0). 
* B(0,0,1) projects to B'(0,0,1). 
* C(1,0,1) projects to C'(0,0,1). 
* D(1,1,1) projects to D'(0,1,1). 
* E(0,1,1) projects to E'(0,1,1). 
* F(1,0,0) projects to F'(0,0,0). 
* G(1,1,0) projects to G'(0,1,0). 
* H(0,1,0) projects to H'(0,1,0). 

**2. Projection onto the Y = 0 Plane (XZ Plane Projection):** * A(0,0,0) projects to A'(0,0,0). 
* B(0,0,1) projects to B'(0,0,1). 
* C(1,0,1) projects to C'(1,0,1). 
* D(1,1,1) projects to D'(1,0,1). 
* E(0,1,1) projects to E'(0,0,1). 
* F(1,0,0) projects to F'(1,0,0). 
* G(1,1,0) projects to G'(1,0,0). 
* H(0,1,0) projects to H'(0,0,0). 

**3. Projection onto the Z = 0 Plane (XY Plane Projection):** * A(0,0,0) projects to A'(0,0,0). 
* B(0,0,1) projects to B'(0,0,0). 
* C(1,0,1) projects to C'(1,0,0). 
* D(1,1,1) projects to D'(1,1,0). 
* E(0,1,1) projects to E'(0,1,0). 
* F(1,0,0) projects to F'(1,0,0). 
* G(1,1,0) projects to G'(1,1,0). 
* H(0,1,0) projects to H'(0,1,0). 

---

### **Isometric Projections**
* **Axonometric Projections:** When an orthographic projection shows more than one side of an object at the same time, it is classified as an axonometric orthographic projection. 
* **Isometric Projection:** This is the most common form of an axonometric projection. 
* **Key Feature:** In an isometric projection, the projection plane intersects each of the three coordinate axes in the model coordinate system at an equal distance. 
* **Properties:** This type of projection successfully preserves the parallelism of lines, but it does not preserve accurate angles.


## **Oblique Projection**

### **Overview**
* Oblique projection involves projecting a plane along parallel lines that are not perpendicular to the projection plane.
* There are two primary types of oblique projection: Cavalier Projection and Cabinet Projection.

![alt text](image-24.png)

### **Cavalier Projection**
* This projection preserves the original lengths of lines that are perpendicular to the projection plane.
* The projection line makes a 45-degree angle with the projection plane.

### **Cabinet Projection**
* Lines that are perpendicular to the viewing surface are projected at one-half of their original size.
* The projection line makes an angle of 63.4 degrees with the projection plane.
* Cabinet projections appear more realistic than Cavalier projections because the reduction in the length of perpendiculars better simulates human vision and depth.

![alt text](image-25.png)

### **Transformation Equations for Oblique Projection**
* The goal is to transform a coordinate position $(x, y, z)$ to a position $(x', y')$ on the 2D view plane.
* The initial transformation components are represented as $x' = x + m$ and $y' = y + n$.
* Using trigonometric ratios from the projection vectors, we define $m = L \cos(\phi)$ and $n = L \sin(\phi)$.
* Substituting these yields the intermediate equations: $x' = x + L \cos(\phi)$ and $y' = y + L \sin(\phi)$.
* The length variable $L$ can be calculated using the relation $\tan(\alpha) = \frac{z}{L}$, which rearranges to $L = z \cot(\alpha)$.
* Substituting $L$ provides the final equations: $x' = x + z \cot(\alpha) \cos(\phi)$ and $y' = y + z \cot(\alpha) \sin(\phi)$.
* In homogeneous coordinates, this is achieved by multiplying the coordinate matrix by the following transformation matrix:

$$
\begin{bmatrix} 
1 & 0 & \cot(\alpha) \cos(\phi) & 0 \\ 
0 & 1 & \cot(\alpha) \sin(\phi) & 0 \\ 
0 & 0 & 0 & 0 \\ 
0 & 0 & 0 & 1 
\end{bmatrix}
$$

---

## **Perspective Projection**

### **Overview & Characteristics**
* In perspective projection, distances and angles are not preserved.
* Parallel lines do not remain parallel; instead, they all converge at a single point called the center of projection or the projection reference point.
* Parallel lines that are already parallel to the view plane will still be projected as parallel lines.
* Any set of parallel lines representing objects that are not parallel to the projection plane will project into converging lines.

### **Vanishing Points**
* The point at which a set of projected parallel lines appears to converge is called a vanishing point.
* A different set of projected parallel lines will always converge to a separate vanishing point.
* The vanishing point for any set of lines that are parallel to one of the object's principal axes is specifically referred to as the principal vanishing point.

### **Types of Perspective Projections**
* **One-Point Perspective Projection:** This is simple to draw and features exactly one principal vanishing point.
* **Two-Point Perspective Projection:** This method gives a much better impression of depth and features two principal vanishing points.
* **Three-Point Perspective Projection:** This is the most difficult type of perspective projection to draw mathematically.

![alt text](image-26.png)
![alt text](image-27.png)

### **Transformation Equations for Perspective Projection**
* Coordinates can be derived using the geometric ratios of similar triangles formed by the projection lines.
* The ratio for the x-coordinate is $\frac{x'}{x} = \frac{d}{z+d}$.
* Rearranging this gives the final x-coordinate: $x' = \frac{x \cdot d}{z+d}$.
* The ratio for the y-coordinate is $\frac{y'}{y} = \frac{d}{z+d}$.
* Rearranging this gives the final y-coordinate: $y' = \frac{y \cdot d}{z+d}$.
* In homogeneous coordinates, the perspective transformation matrix is represented as follows:

$$
\begin{bmatrix} x_h \\ y_h \\ z_h \\ h \end{bmatrix} = \begin{bmatrix} d & 0 & 0 & 0 \\ 0 & d & 0 & 0 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 1 & d \end{bmatrix} \times \begin{bmatrix} x \\ y \\ z \\ 1 \end{bmatrix}
$$


## **Visible Surface Detection (Hidden-Surface Removal)**

### **Overview**
* When viewing a picture that contains non-transparent objects and surfaces, the objects located behind closer objects cannot be seen.
* To obtain a realistic screen image, these hidden surfaces need to be removed.
* This process of identifying and removing obscured surfaces is known as Hidden-Surface Removal or Visible Surface Detection.

---

### **Methods of Visible Surface Detection**
The hidden surface problem can be solved using two primary methods:

* **Object-Space Method:**
  * Implemented in the physical coordinate system.
  * It compares objects and parts of objects to each other within the scene definition to determine which surfaces, as a whole, should be labeled visible.

* **Image-Space Method:**
  * Implemented in the screen coordinate system.
  * Visibility is decided point-by-point at each pixel position on the projection plane.
  * Most visible surface detection algorithms use image-space methods.

---

## **Depth Buffer Algorithm (Z-Buffer Algorithm)**

![alt text](image-28.png)
### **Introduction**
* The Depth Buffer Algorithm is also called the Z-Buffer Algorithm.
* It is the simplest image-space algorithm available.
* For each pixel on the display screen, the algorithm keeps a record of the depth of the object that lies closest to the observer.
* In addition to recording the depth, it also records the intensity that should be displayed to accurately show the object.

---

### **Algorithm Steps**
1. **Initialization:** Initialize the depth buffer and the refresh buffer so that for all buffer positions $(x,y)$:
  * `depth(x,y) = 0`
  * `refresh(x,y) = Ibackground` (where `Ibackground` is the value of the background intensity).

2. **Visibility Comparison:** For each position on every polygon surface, calculate the depth $z$ and compare it to the previously stored values in the depth buffer.
  * If $z > depth(x,y)$, then update the buffers:
    * Set `depth(x,y) = z`.
    * Set `refresh(x,y) = Isurf(x,y)`.
  * *Note:* `Isurf(x,y)` is the projected intensity value for the surface at the specific pixel position $(x,y)$.

3. **Completion:** After all surfaces have been processed, the depth buffer will contain the depth values for all visible surfaces, and the refresh buffer will contain the final visible intensities to be drawn.

---

## **Mathematical Depth Calculations**

### **Surface Equation & Initial Depth**
* The mathematical equation of the surface is given by: $AX + BY + CZ + D = 0$.
* The depth calculation along the z-axis for any point is derived as: $Z = \frac{-AX - BY - D}{C}$.

### **Horizontal Scan Line (Next Point)**
* Once the depth at a current pixel position $(x, y)$ is obtained, the depth for the next point on the same horizontal scan line $(x+1, y)$ can be calculated simply by substituting $x$ as $x+1$.
* $z' = \frac{-A(x+1) - By - D}{C}$
* Expanding this equation yields $Z' = \frac{-Ax - A - By - D}{C} = \frac{-Ax - By - D}{C} - \frac{A}{C}$.
* Simplified: $z' = z - \frac{A}{C}$.

### **Vertical Scan Line (Next Scan Line)**
* After finishing one scan line, you do not start from the beginning of the next scan; instead, you start from the polygon edge point of the next line.
* The vertically next polygon point depth is located at $(x - \frac{1}{m}, y - 1)$.
* Substituting these into the depth equation: $z' = \frac{-A(x - \frac{1}{m}) - B(y - 1) - D}{C}$.
* Expanding this yields: $z' = \frac{-Ax + \frac{A}{m} - By + B - D}{C} = \frac{-Ax - By - D}{C} + \frac{\frac{A}{m} + B}{C}$.
* Simplified: $z' = z + \frac{\frac{A}{m} + B}{C}$.

---

## **Advantages and Disadvantages of Depth Buffer**

### **Advantages**
* It is highly simple to use.
* It can be implemented easily in both object space or image space.

### **Disadvantages**
* It requires a substantial amount of memory.
* Processing the algorithm is time-consuming.


### **Scan Line Algorithm**

**Overview & Characteristics**
* The Scan Line Algorithm is an image-space method used to identify visible surfaces.
* It serves as an extension of the scan line algorithm originally used for polygon filling.
* Unlike the depth buffer method (which can process only one surface at a time), the scan line method is capable of processing more than one surface at a time.
* A key characteristic of this method is that it holds depth information for only a single scan line at a time.
* To acquire one scan-line of depth values, the algorithm must group and process all polygons intersecting a given scan-line simultaneously before it can proceed to process the next scan-line.

**Data Structures**
The algorithm maintains two important tables to manage the data:
* **The Edge Table:** This table contains the coordinate endpoints for each line in the scene, the inverse slope of each line, and pointers that connect the edges to their corresponding surfaces in the polygon table.
* **The Polygon Table:** This table contains the plane coefficients, color information for the particular polygon, and a flag that is initially set to false.

**Algorithm Process**
* For all polygons (surfaces) that intersect a given scan line, the faces are processed systematically from left to right.
* For each scan line, an active list of edges (the edges currently intersected by the scan line) is maintained and sorted in the order of increasing x values.
* As the line is processed, the face flag is turned ON at the leftmost position of a face and set to OFF at the rightmost position.
* If overlapping faces are detected (multiple flags are ON), the depth is determined to identify which face is nearest to the view plane. The intensity of that nearest face is then entered into the refresh buffer.

![alt text](image-29.png)

**Processing Example (Scan Lines 1, 2, and 3)**
Assuming a scene with two polygon faces, ABCD (Surface 1 / S1) and EFGH (Surface 2 / S2):
* **Scan Line 1:**
  * The Active Edge List contains {AB, BC, EH, FG}.
  * Between edges AB and BC, the flag for surface S1 is ON, and its intensity is entered into the refresh buffer.
  * Between edges BC and EH, both flags for S1 and S2 are OFF, meaning no intensity is stored.
  * Between edges EH and FG (noted as EG/FG), only the flag for S2 is ON, and its intensity is entered into the refresh buffer.
  * Because there is no overlapping region on this line, no depth calculation is required.
* **Scan Line 2:**
  * The Active Edge List is {AD, EH, BC, FG}.
  * Between AD and BC, the flag for S1 is ON, and its intensity is stored in the refresh buffer.
  * Between EH and BC, the flags for both S1 and S2 are ON. In this scenario, the algorithm calculates the depth from the viewpoint to both surfaces and enters the intensity of the nearest surface into the refresh buffer.
* **Scan Line 3:**
  * This line takes advantage of the coherence property.
  * Because scan line 3 has the same active edge list and regularities as scan line 2, the algorithm avoids recalculating the depth separately. Instead, it uses the depth information previously calculated for scan line 2 and stores the same intensity details.

**Advantages & Disadvantages**

* **Advantages:** * Any number of overlapping surfaces can be processed at the same time.
  * The algorithm efficiently takes advantage of coherence properties.
* **Disadvantages:** * The method fails to work correctly for surfaces that cut through or cyclically overlap each other.

![alt text](image-30.png)