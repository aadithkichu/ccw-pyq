## Computer Graphics: Scan Conversion & Polygon Filling

### 1. Introduction to Scan Conversion
* **Definition:** In Raster Scan displays, scan conversion is the process by which a picture's definition (given in an application program) is digitized into a set of pixel-intensity values.
* **Storage and Display:** These digitized values are stored in the frame buffer. The video controller then accesses this frame buffer and uses the stored picture information to display the final 2D or 3D image on the screen.
* **Hardware:** The device responsible for performing this task is called a Display Processor or a Scan Converter.

---

### 2. Scan Converting Primitives and Side Effects
* **Lines:** To draw a line, the end points are defined, and intermediate pixels are calculated using line-drawing algorithms like DDA or Bresenham's. The points are then stored in and retrieved from the frame buffer.
* **Circles:** Similarly, a set of points along a circular path is determined using circle algorithms, loaded into the frame buffer, and displayed.

**Side Effects of Scan Conversion:**
* **Staircase/Jagged Appearance:** Diagonal or curved primitives often exhibit a staircase-like, jagged look due to the grid nature of pixels.
* **Unequal Intensity:** Different lines may appear to have unequal brightness. An inclined (diagonal) line appears less bright than a vertical or horizontal line. This occurs because pixels along horizontal/vertical lines are 1 unit apart, whereas pixels along a diagonal line are roughly 1.414 units apart, spreading the intensity over a larger physical distance.

---

### 3. Solid Area Scan Conversion
Solid Area Scan Conversion is used to display solid images by determining the pixels inside the solid areas, storing their color values in the frame buffer, and retrieving them for display.

**Two Basic Approaches:**
* **Scan-Line Approach:** Determines the overlap intervals for scan lines that cross the area. This is typically used in general graphics packages to fill polygons, circles, ellipses, and other simple curves.
* **Interior-Point Approach:** Starts from a given interior point and paints outward until a specified boundary condition is met. This is highly useful for complex boundaries and interactive painting systems.

**Primary Area Fill Algorithms:**
* Scan line Polygon fill Algorithm
* Boundary Fill algorithm
* Flood Fill Algorithm

---

### 4. Polygon Representation and Filling
**Types of Filling:**
* **Solid-fill:** All pixels inside the polygon's boundary are illuminated.
* **Pattern-fill:** The polygon is filled with an arbitrary, predefined pattern.

**Representation:**
* **Standard Method:** A polygon is represented by an ordered list of n vertices: $P=\{(x_{1},y_{1}),(x_{2},y_{2}),........,(x_{n^{}},y_{n})\}$. The boundary is drawn by connecting consecutive vertices, closing the shape with a line from $(x_{n},y_{n})$ to $(x_{1},y_{1})$.
* **Optimization for Translation:** The standard method requires applying a translation transformation to every vertex to move the polygon, which is time-consuming for complex shapes. A faster method represents the polygon by the absolute location of its first vertex, with all subsequent vertices represented as relative positions from the previous one. This allows the entire polygon to be translated simply by changing the coordinates of the first vertex alone.

---

### 5. Inside-Outside Tests
When filling polygons, the system must decide if a given point is interior or exterior.

![alt text](image-11.png)

**Odd-Parity (Odd-Even) Rule**
* **Method:** Conceptually draw a line starting from a specific point extending outward to a distant point outside the coordinate extents, ensuring it does not pass directly through any polygon vertex.
* **Condition:** If the number of intersections between this line and the polygon edges is odd, the point is an interior point. Otherwise, it is an exterior point.

**Non-Zero Winding Number Rule**
* **Method:** This algorithm counts how many times the polygon edges wind around a specific point.
* **Condition:** After all crossings are counted, if the final winding number is non-zero, the point is considered interior.

![alt text](image-12.png)

**Execution Steps:**
1. Initialize the winding number to $0$.
2. Draw a conceptual line from point P to the outside, avoiding vertices.
3. Add $1$ to the winding number if a crossed edge goes right to left (counter-clockwise) relative to the line.
4. Subtract $1$ if the crossed edge goes left to right (clockwise).

---

### 6. The Scan-Line Polygon Fill Algorithm
The scan-line polygon fill algorithm is the standard method for determining interior pixel spans.

**Core Process:**
1. Find the Ymin and Ymax limits of the given polygon.
2. Horizontally scan the polygon from Ymin to Ymax.
3. Identify intersection points where the scan line crosses the polygon edges.
4. Sort the intersection points from left to right (increasing order of X coordinates).
5. Fill the interior horizontal lines (pixels between pairs of intersections) with the specified fill color, ignoring alternate pairs.

**Dealing with Vertices**
A scan line passing perfectly through a vertex requires special handling because it intersects two polygon edges at that single position. Additional processing is only necessary for vertices that are not local extrema (i.e., vertices where connecting edges are on opposite sides of the scan line).

**Vertex Splitting Logic:**

![alt text](image-13.png)

* If the endpoint y-coordinates of the two connected edges are continuously increasing (a monotonic path), the y-value of the upper endpoint for the current edge is artificially decreased by one.
* If the y-values are continuously decreasing, the y-value of the upper endpoint of the next edge is decreased by one.
* Mathematically, if $y_{P}<y_{C}<y_{H}$ (where P is previous, C is current, H is next), $y_{C}$ is decreased by one, and a new fractional $x^{\prime}_{C}$ is calculated using the edge slope to prevent overdrawing.

**Coherence & Edge Intersections**
* Calculations take advantage of "coherence properties"—the idea that properties change predictably between successive scan lines.
* Because the slope of an edge is constant, calculating intersections iteratively is highly efficient.
* **Formula:** Given the slope formula $m=(y_{k+1}-y_{k})/(x_{k+1}-x_{k})$. Since we scan line-by-line, $y_{k+1}-y_{k}=1$. Therefore, the x-intersection for the next scan line is simply $x_{k+1}=x_{k}+1/m$.

**Data Structures**
* **Edge Table:** The polygon boundary is processed clockwise or counterclockwise and sorted into an Edge Table using a Bucket Sort, ordered by the smallest y-value of each edge. Each entry contains: The maximum y-value for that edge ($y_{max}$), the x-intercept value at the lower vertex ($x$), and the inverse slope of the edge ($1/m$).
* **Active Edge List:** As scan lines are processed from bottom to top, an active edge list is generated for each line containing only the edges currently crossed by that specific scan line. Iterative coherence calculations ($x_{k}+1/m$) update the intersections horizontally.

![alt text](image-14.png)

## Boundary Fill Algorithm Overview
* The Boundary Fill algorithm is a region-filling approach that begins from a known point inside a region and paints outward towards the boundary.
* This method is mainly implemented within interactive painting packages, where interior points can be easily selected by the user.
* When the boundary consists of a single color, the algorithm proceeds outward, pixel by pixel, until it encounters that specific boundary color.
* The procedure requires three main inputs: the coordinates of an initial interior point (x, y), a designated fill color, and a boundary color.
* Starting from the initial coordinates, it checks neighboring locations to determine whether or not they match the boundary color.
* If a neighboring pixel is not the boundary color, it is painted with the fill color, and its adjacent pixels are subsequently tested against the same condition.
* The algorithm naturally ends when all pixels up until the boundary color for the entire polygon have been thoroughly checked.

---

## Connectivity Approaches
There are two distinct methods for evaluating neighboring pixels when filling a region:

### Four-Connected Approach
* In this approach, only four surrounding pixels are tested: left, right, above, and below.
* The specific order in which pixels are added to the processing stack is: above, below, left, and right.
* The boundary can be checked by evaluating pixels from the left and right first, followed by checking pixels from the top.

### Eight-Connected Approach
* This approach tests eight surrounding pixels: left, right, above, below, and the four diagonal directions.
* The specific order in which pixels are added to the processing stack is: above, below, left, right, above-left, above-right, below-left, and below-right.

---

## Recursive Boundary Fill Logic
The recursive execution of the algorithm follows these standard steps:
* Start the process from an interior point.
* Evaluate if the current pixel is not already filled and is not an edge point.
* If the conditions are met, set the pixel with the fill color.
* Store its neighboring pixels (using either 4-connected or 8-connected logic) into a stack for processing.
* Ensure you only store neighboring pixels that are not already filled and are not edge points.
* Select the next pixel from the stack, and continue the evaluation loop.

---

## 4-Connected Pseudocode Logic

![alt text](image-15.png)

A standard procedural implementation for a 4-connected fill relies on reading the current pixel and making recursive function calls for its direct neighbors.
* Read the current pixel color: `c = getpixel(x, y)`.
* Verify the color is neither the target fill color nor the boundary color.
* Set the current pixel to the target fill color: `setpixel(x, y, fillcolor)`.
* Recursively call the procedure for the right neighbor: `x + 1`.
* Recursively call the procedure for the left neighbor: `x - 1`.
* Recursively call the procedure for the top neighbor: `y + 1`.
* Recursively call the procedure for the bottom neighbor: `y - 1`.

---

## Limitations and Potential Problems
* The algorithm consumes significant time and memory because it relies heavily on recursive calls.
* The algorithm may fail to fill regions correctly if an interior pixel is already colored with the target fill color.
* This error occurs because the algorithm explicitly checks upcoming pixels for both the boundary color and the fill color.
* Encountering a pixel that matches the fill color causes the recursive branch to terminate prematurely, leaving other valid interior pixels unfilled.
* To resolve this, it is necessary to check all pixel colors before applying the algorithm.
* Alternatively, developers can first change the color of any interior pixels that are initially set to the fill color before running the boundary fill procedure.

## Computer Graphics: Flood Fill Algorithm

### Overview and Definition
* The Flood Fill algorithm is utilized when we need to fill or recolor an area that is not bounded by a single defined color.
* It is also commonly known as the "seed fill algorithm".
* Instead of searching outward for a specific boundary color, this algorithm paints areas by targeting and replacing a specified interior color.
* It functions by determining the area connected to a given node within a multi-dimensional array.
* This approach is highly suitable for filling a selected area where the boundary is composed of multiple colors, and the interior needs to be filled with a single color.

---

### How the Algorithm Works
* The process begins by selecting a starting point inside the target region, which is referred to as the "seed point".
* Starting from this specified interior pixel (x, y), the algorithm reassigns all pixel values that are currently set to a given interior color with the new, desired fill color.
* If the target area contains more than one interior color, the pixel values can first be reassigned so that all interior pixels share a uniform color before applying the full fill.
* The algorithm then steps through the pixel positions using either a 4-connected or an 8-connected approach until all the interior pixels have been successfully repainted.

---

### Connectivity Approaches and Logic
Like the boundary fill algorithm, the flood fill utilizes connected approaches to test neighboring pixels.

**1. 4-Connected Flood Fill**
* This approach checks the four immediate neighbors (top, bottom, left, right) of the current pixel.
* **Logic:** The algorithm checks if the current pixel's color matches the defaultColor.
* If it matches, the pixel is painted with the fillColor.
* It then recursively calls the flood fill function for the surrounding pixels: (x+1, y), (x-1, y), (x, y+1), and (x, y-1).

![alt text](image-16.png)



**2. 8-Connected Flood Fill**
* This approach checks all eight surrounding pixels, including the diagonals.
* **Logic:** The algorithm reads the current pixel color and compares it to the old color.
* If they match, it replaces the color with the newcol.
* It then recursively calls the function for all eight directions: (x+1, y), (x-1, y), (x, y+1), (x, y-1), (x+1, y+1), (x-1, y+1), (x+1, y-1), and (x-1, y-1).

![alt text](image-17.png)

---

### Disadvantages of Flood Fill
* It is a very slow algorithm.
* It may fail when processing very large polygons.
* Selecting the initial pixel requires more comprehensive knowledge about the surrounding pixels.

---

### Comparison: Flood Fill vs. Boundary Fill

| Feature | Flood-fill Algorithm | Boundary-fill Algorithm |
| :--- | :--- | :--- |
| **Boundary Colors** | Can process images containing more than one boundary color. | Can only process images containing a single boundary color. |
| **Speed** | Comparatively slower. | Faster than the Flood-fill algorithm. |
| **Painting Method** | A random color can be used to paint the interior, replacing the old color with a new one. | Interior points are painted by continuously searching outward for the boundary color. |
| **Memory Consumption** | Requires a huge amount of memory. | Memory consumption is relatively low. |