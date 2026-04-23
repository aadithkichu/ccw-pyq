# **Computer Graphics: Basic Concepts and Applications**

## **1. Introduction to Computer Graphics**
Computer graphics is the art of drawing pictures on computer screens using programming. 
* It primarily involves the computation, creation, and manipulation of data to generate visual outputs.
* **Broad Classification:** Computer graphics can be basically categorized into two main types:
    1. Interactive Computer Graphics
    2. Non-interactive (Passive) Computer Graphics

---

## **2. Types of Computer Graphics**

### **Interactive Computer Graphics**
Interactive computer graphics operate on the principle of **two-way communication** between the user and the computer. 

* **Mechanism:** The computer receives signals or commands from an input device, and the picture on the screen is modified quickly and accordingly.
* **User Control:** The user has significant control over the picture and can actively make changes to the produced image in real-time.
* **Example:** A classic example is a ping-pong video game, where user inputs immediately change the state of the game on screen.
* **Advantages:**
    * Produces higher quality outputs.
    * Yields more precise results and products.
    * Leads to greater productivity.
    * Significantly enhances the human ability to understand complex data and perceive visual trends.

### **Non-Interactive (Passive) Computer Graphics**
Non-interactive graphics involve only **one-way communication** between the computer and the user.

* **Mechanism:** The rendered picture is simply produced and displayed on the monitor. 
* **User Control:** The user acts only as an observer. They have absolutely no control over the image and cannot make any changes to it.
* **Example:** Titles or credits shown on a television broadcast.

---

## **3. Applications of Computer Graphics**

Computer graphics technologies are heavily utilized across a wide variety of fields and industries:

### **Education and Training**
* **Educational Aids:** Computer-generated models of physical, financial, and economic systems are widely used to aid teaching. 
* **System Comprehension:** Models of physiological systems, population trends, or complex equipment help trainees grasp how a system operates safely.
* **Specialized Simulators (e.g., Flight Simulators):** Used extensively to train airplane pilots. Pilots spend a massive portion of their training safely on the ground at the controls of a simulator rather than in a real, expensive aircraft.
* **Educational Software:** Essential in the development of software for computer-aided instruction.

### **Science and Medicine**
* **Biology:** Molecular biologists use computer graphics to display complex pictures of molecules, helping them gain visual insight into their intricate structures.
* **Visualization:** Scientists, engineers, medical personnel, and business analysts use graphics to visually study and interpret massive amounts of complex information and data.

### **Engineering and Architecture**
* **Computer-Generated Maps:** Town planners and transportation engineers utilize specialized graphical maps to display data vital to their infrastructure planning.
* **Architecture:** Architects use interactive graphics terminals to explore alternative solutions to design problems. This allows them to rapidly test many more design iterations than would ever be possible through manual drafting.

### **Business and Communication**
* **Presentation Graphics:** Used to summarize reports (financial, statistical, mathematical, scientific, economic, managerial) and consumer information bulletins. 
* **Visual Formats:** Commonly includes bar charts, line graphs, pie charts, and other visual displays that effectively show relationships between multiple parameters.

### **Media, Arts, and Entertainment**
* **Computer Art:** Widely used in the commercial arts sector, including the generation of television and advertising commercials.
* **Entertainment Industry:** Fundamentally relied upon in the modern creation of motion pictures, television shows, and music videos.
* **Printing Technology:** Crucial for modern printing technologies and textile/fabric design.

---

## **4. Examples of Computer Graphics Packages**
Various software packages and standards are used to create and manage computer graphics. Notable examples include:
* LOGO
* COREL DRAW
* AUTO CAD
* 3D STUDIO
* CORE
* GKS (Graphics Kernel System)
* PHIGS (Programmer's Hierarchical Interactive Graphics System)
* CAM (Computer Graphics Metafile)
* CGI (Computer Graphics Interface)


## **1. Pixels and Light Intensity**
* A pixel is the smallest element of an image.
* If you zoom into an image far enough, you can see these individual pixel divisions, and thousands of them together make up the complete picture.
* Each pixel corresponds to exactly one value, which is proportional to the intensity of light photons striking that particular location.
* **Gray Level:** This pixel value, which denotes the image's intensity at that location, is also known as the gray level.
* In an 8-bit grayscale image, pixel values range from 0 to 255.
* A value of 0 indicates the total absence of light, meaning that specific point will be rendered as black.

## **2. Image Dimensions and Matrices**
* An image is mathematically defined as a two-dimensional signal or matrix.
* To calculate the total number of pixels (PEL) in this matrix, you multiply the number of rows by the number of columns.
* For example, an image with a dimension of 3 rows and 3 columns contains exactly 9 pixels (3 x 3 = 9). If all 9 pixels have a value of 0, the entire resulting 3x3 image will be completely black.

## **3. Aspect Ratio vs. Resolution**
* **Aspect Ratio:** This is the ratio of an image's physical width to its height, expressed in the format of x:y.
    * Common examples include 4:3 and 16:9.
    * The preferred ratio differs depending on the medium, such as photography, television, or computer applications.
* **Resolution:** This is the total number of pixels displayed on your computer or television screen without overlapping.
    * Common monitor resolutions include 640x480, 800x600, and 1024x768.
    * Generally, a higher resolution results in a higher quality image.

## **4. I/O Hardware and The Processing Pipeline**
* **Input Devices:** Hardware used to transfer incoming data—like text, graphics, and sound—into the computer.
* **Output Devices:** Hardware that displays processed data from the computer's memory. Output can be text, numeric data, lines, polygons, and other visual objects.
* Important output devices used in a computer include display devices, graphic plotters, and printers.

**The Data Processing Pipeline**
The flow of data from input to human-readable output happens in this exact sequence:

**Input** $\rightarrow$ **Input Device** $\rightarrow$ **CPU Memory** $\rightarrow$ **Processed Data** $\rightarrow$ **Output Devices** $\rightarrow$ **Result of processing in human acceptable form**



## **1. Introduction to Display Devices**
* A display device is a primary output device used to represent information visually in the form of images.
* These systems are commonly referred to as video monitors or Video Display Units (VDU).
* The fundamental purpose of display technology is to simplify the sharing of information.
* Common types of modern and legacy display devices include:
    * Cathode-Ray Tube (CRT) and Color CRT Monitors.
    * Liquid Crystal Display (LCD).
    * Light Emitting Diode (LED).
    * Direct View Storage Tubes (DVST).
    * Plasma Displays.
    * 3D Displays.

## **2. Cathode-Ray Tube (CRT) Fundamentals**
* The basic operations of most traditional video monitors are based on the standard cathode-ray tube design.
* A CRT is essentially an evacuated glass envelope (an electronic tube) specifically designed to display electrical data.
* The four major components of a basic CRT are:
    * Electron gun.
    * Focusing and accelerating anode.
    * Horizontal and vertical deflection plates.
    * Evacuated glass envelope.

![alt text](image.png)
![alt text](image-1.png)

## **3. How a CRT Works: The Electron Pipeline**
* **Emission:** An electron gun emits a beam of negatively charged electrons, known as cathode rays.
* **Directing the Beam:** This beam passes through a focusing system and deflection plates, which direct the electrons toward very specific target positions on the screen.
* **Illumination:** The inside of the screen is coated with phosphor. When the electron beam strikes the phosphor, it emits a small spot of visible light at that specific point.
* **The Refresh Cycle:** Because the light emitted by the phosphor fades extremely rapidly, the picture must be repeatedly redrawn by quickly directing the electron beam back over the exact same points. This specific type of display methodology is called a "refresh CRT".

## **4. Deep Dive: The Electron Gun & Control Grid**
* The primary components inside the electron gun are a heated metal cathode and a control grid.
* Inside the cathode structure is a wire coil called a filament. When current is directed through this filament, it provides heat to the cathode, causing electrons to effectively "boil off" its surface.
* Because the CRT is a vacuum, a high positive voltage is used to accelerate these free, negatively charged electrons toward the phosphor screen.
* **Controlling Brightness:** The brightness of the display is controlled by adjusting the intensity of the electron beam. This is done by varying the voltage levels on the control grid (a metal cylinder fitting over the cathode).

## **5. Focusing and Deflection Systems**
* **Focusing:** As electrons travel, they naturally repel each other. A focusing system is required to force the beam to converge into a sharp, small spot just as it strikes the phosphor screen. This focusing can be achieved using either electric or magnetic fields. Electrostatic focusing is standard in TV and computer monitors.
* **Deflection:** The actual movement (deflection) of the beam across the screen is also controlled using either electric or magnetic fields.

## **6. Phosphor and Persistence**
* Different types of phosphors dictate not only the color of the screen but also its "persistence".
* **Persistence Defined:** This is the exact amount of time it takes for the emitted light from the phosphor to decay to one-tenth of its original intensity after the electron beam is removed.
* **Low vs. High Persistence:**
    * Low persistence phosphors require higher refresh rates to prevent the screen from flickering. They are highly useful for fluid animation.
    * High persistence phosphors are better suited for displaying highly complex, static pictures.
* Standard graphics monitors are usually built with a persistence ranging from 10 to 60 microseconds.

## **7. Resolution and Aspect Ratio**
* **Resolution:** In a CRT, resolution is defined as the maximum number of points that can be displayed on the screen without overlapping.
    * It relies heavily on the type of phosphor used, the intensity of the beam, and the quality of the focusing and deflection systems.
    * A typical high-quality, high-definition system might have a resolution of 1280 by 1024.
* **Aspect Ratio:** This is the ratio of the width of an image to its height.
    * For example, an aspect ratio of 3/4 indicates that a vertical line plotted with three points will have the exact same physical length on the screen as a horizontal line plotted with four points.

# **Computer Graphics: Display Technologies**

There are two primary ways to display an object on a screen: the raster scan display and the random scan display.

## **1. Raster Scan Display**
The raster scan display is the most common type of graphics monitor and is based on standard television technology. It is widely used in home television sets and printers.

![alt text](image-2.png)

**How It Works:**
* The electron beam sweeps across the screen one row at a time, strictly moving from top to bottom.
* As it moves across each row, the beam's intensity is turned on and off to create a pattern of illuminated spots.
* **Horizontal Retrace:** At the end of each scan line, the beam turns off and returns to the left side of the screen to start the next line.
* **Vertical Retrace:** At the end of the entire frame, the beam returns to the top-left corner to begin drawing the next frame.
* Refreshing is usually carried out at a rate of 60 to 80 frames per second (often expressed as 60 Hz to 80 Hz).

**Memory and Storage (Frame Buffer):**
* The picture definition (intensity values for all screen points) is stored in a memory area called the refresh buffer or frame buffer.
* These stored values are retrieved and "painted" onto the screen one scan line at a time.
* **Bilevel Systems (Black & White):** Each pixel is either on (1) or off (0), requiring only one bit per pixel. In this case, the frame buffer is called a bitmap.
* **Color Systems:** Additional bits are needed for color and intensity. High-quality systems use up to 24 bits per pixel. Here, the frame buffer is called a pixmap.
* *Example:* A 24-bit system with a 1024x1024 resolution requires 3 megabytes of frame buffer storage.

**Architecture:**
* A simple raster graphics system consists of a CPU, System Memory, and a Video Controller, all communicating via a System Bus. 
* The Video Controller drives the final output to the Monitor.

---

## **2. Random Scan Display (Vector Display)**
Random scan displays operate differently and are specifically designed for line-drawing applications. A pen plotter is a physical example of this methodology.

![alt text](image-3.png)

**How It Works:**
* The electron beam is directed only to the specific parts of the screen where a picture needs to be drawn.
* It draws the picture one continuous line at a time, which is why it is often called a vector display.
* The refresh rate depends entirely on the number of lines being displayed, usually cycling 30 to 60 times per second.

**Memory and Storage (Display List):**
* Picture definitions are stored as a set of specific line-drawing commands rather than a grid of pixels.
* This memory area is called the refresh display file, display list, or display program.
* The system loops through these commands, drawing each line in turn, and then cycles back to the first command to refresh.

---

## **3. Raster vs. Random Scan: Key Differences**

| Feature | Raster Scan Display | Random Scan (Vector) Display |
| :--- | :--- | :--- |
| **Electron Beam** | Sweeps the entire screen, top to bottom, one row at a time. | Directed only to where the picture is drawn, one line at a time. |
| **Picture Definition** | Stored as intensity values in a Refresh/Frame Buffer. | Stored as a set of line commands in a Refresh Display File. |
| **Resolution** | Poorer resolution due to discrete pixel storage. | Higher resolution due to mathematical line commands. |
| **Line Quality** | Produces zig-zag (aliased) lines because plotted values are discrete pixels. | Produces perfectly smooth lines because the beam directly follows the line path. |
| **Realism** | Supports shadows, advanced shading, and hidden surfaces for realistic scenes. | Cannot handle shadows or surfaces; cannot display realistic scenes. |
| **Refresh Rate** | Fixed at 60 to 80 frames per second. | Variable; depends on the number of lines (typically 30-60/sec). |
| **Cost** | Less expensive. | Costlier. |


## **1. Raster-Scan System Architecture**
Interactive raster graphics systems rely on multiple processing units to function efficiently.

* **The Video Controller:** Alongside the main CPU, a special-purpose processor called the video controller (or display controller) is used specifically to manage the display device.
* **Frame Buffer Access:** The frame buffer can be located anywhere within the system memory. The video controller is given direct access to this memory area to constantly retrieve data and refresh the screen.
* **Display Processor (Advanced Systems):** Many raster systems also include a separate display processor, sometimes called a graphics controller or display coprocessor.
* **Purpose of the Display Processor:** Its main job is to free the primary CPU from handling heavy graphics computations. These systems may also feature a dedicated display processor memory area, completely separate from the main system memory.

![alt text](image-4.png)
![alt text](image-5.png)

## **2. Operation of a Video Controller**
The video controller uses a Cartesian coordinate system to map memory locations in the frame buffer to physical positions on the screen.

* **Coordinate Mapping:** The coordinate origin (0,0) is typically defined at the lower-left corner of the screen.
* **Screen Quadrant:** The screen represents the first quadrant of a 2D grid: positive x values increase to the right, and positive y values increase from bottom to top.
* **Scan Line Tracking:** Scan lines are counted from the top of the screen ($y_{max}$) down to the bottom (0). Along each individual scan line, pixels are labeled from 0 to $X_{max}$.

## **3. The Basic Refresh Operation (Pixel by Pixel)**
The video controller uses an X register and a Y register to store and track the coordinates of the screen pixels.

* **Initialization:** The process starts at the top-left corner by setting the x register to 0 and the y register to $y_{max}$.
* **Beam Control:** The controller retrieves the intensity value from the frame buffer for that specific pixel and sets the CRT beam accordingly.
* **Horizontal Movement:** The x register is incremented by 1, and the process repeats for the next pixel on that same scan line.
* **Vertical Movement:** Once the final pixel on a line is drawn, the x register resets to 0, and the y register decrements by 1 to drop down to the next scan line.
* **Cycle Reset:** After drawing the absolute bottom scan line (y = 0), the controller resets both registers to the top-left starting position and the entire frame refresh starts over.

## **4. Optimizing Refresh Rates**
Standard RAM chips are fundamentally too slow to handle the simple pixel-by-pixel procedure at the required 60 frames per second.

* **Block Processing:** To speed things up, modern video controllers retrieve multiple pixel values from the refresh buffer simultaneously during a single pass.
* **Register Storage:** These multiple intensities are temporarily stored in a separate, faster register.
* **Execution:** The controller uses this stored block of data to control the CRT beam for a group of adjacent pixels all at once before fetching the next block from the frame buffer.

## **5. Random Scan System Architecture**
Random scan systems, also known as vector systems, use a completely different pipeline designed specifically for drawing continuous lines.

* **Software Pipeline:** An application program and a graphics package are loaded into the system memory. The graphics package translates the program's drawing commands into a dedicated "display file," which is also kept in system memory.
* **Execution:** The display processor (sometimes called a graphics controller) accesses this display file and cycles through every single command in the list once per refresh cycle.
* **Drawing Mechanics:** Lines are defined strictly by the coordinate values of their endpoints. The processor converts these coordinate values directly into x and y deflection voltages.
* **Vector Output:** The electron beam is then positioned to smoothly fill in the line directly between those specified endpoints, rather than scanning empty screen space.

## **6. Sample Calculation: Frame Buffer Size**
**Problem:** A raster system has an 8 inch by 10 inch screen. The resolution is 100 pixels per inch in each direction. If 6 bits are stored per pixel, what is the total frame buffer size required? 

**Step-by-Step Solution:**

* **Calculate Total Pixels:** First, convert the physical dimensions into pixel dimensions.
    * Width: 8 inches x 100 pixels/inch = 800 pixels.
    * Height: 10 inches x 100 pixels/inch = 1000 pixels.
    * Total Pixels: 800 x 1000 = 800,000 pixels.
* **Calculate Total Bits:** Multiply the total pixels by the number of bits each pixel requires (6 bits).
    * 800,000 pixels x 6 bits = 4,800,000 total bits.
* **Convert to Bytes:** Divide the total bits by 8 (since 8 bits = 1 byte).
    * 4,800,000 / 8 = 600,000 bytes.


## **1. Color CRT Monitors**
* A CRT monitor displays color pictures by using a combination of phosphors that emit different colored light.
* By combining the emitted light from these different phosphors, a wide range of colors can be generated.
* There are two basic techniques used for producing color displays with a CRT: the beam-penetration method and the shadow-mask method.

## **2. The Beam Penetration Method**
* This method is primarily used with random scan monitors.
* **How it works:** The inside of the CRT screen is coated with two layers of phosphor, usually red and green. The color displayed depends entirely on how far the electron beam penetrates into these layers.
* A beam of slow-moving electrons only excites the outer red layer, producing red.
* A beam of very fast electrons penetrates through the red layer to excite the inner green layer.
* At intermediate beam speeds, combinations of red and green light are emitted to produce two additional colors: orange and yellow.
* The screen color at any given point is controlled by adjusting the beam acceleration voltage.
* **Pros & Cons:** While beam penetration has been an inexpensive way to produce color in random scan monitors, it is limited to only four colors, and the overall picture quality is not as good as other methods.

## **3. Shadow-Mask Methods**
* This method is commonly used in raster scan systems, including standard color televisions, because it produces a much wider range of colors than the beam penetration method.
* **How it works:** A shadow-mask CRT has three specific phosphor color dots (red, green, and blue) at each pixel position.
* It utilizes three separate electron guns—one for each color dot—and a shadow-mask grid positioned just behind the phosphor-coated screen.
* **Delta-Delta Shadow Mask Method:** The three electron beams are deflected and focused as a group onto the shadow mask, which contains a series of holes perfectly aligned with the phosphor dot patterns.
* When the three beams pass through a hole in the mask, they activate a dot triangle, appearing as a small color spot on the screen. The dots are specifically arranged so that each electron beam can only activate its corresponding color dot when passing through the mask.
* **Creating Color Variations:** Color is varied by changing the intensity levels of the three electron beams.
    * Turning off the red and green guns leaves only the color from the blue phosphor.
    * A pure white area is produced by activating all three dots with equal intensity.
    * Yellow is produced with green and red dots; magenta with blue and red; and cyan with blue and green.
    * Our eyes naturally merge these tiny light spots into one composite color for each pixel position.

![alt text](image-6.png)

## **4. Direct-View Storage Tubes (DVST)**
* Instead of constantly refreshing the screen, a DVST maintains a screen image by storing the picture information directly inside the CRT itself.
* It stores this picture information as a charge distribution located just behind the phosphor-coated screen.
* **Gun System:** A DVST relies on two distinct electron guns:
    * The **primary gun** is used specifically to store the picture pattern.
    * The **flood gun** is used to maintain the active picture display.
* **Advantages:** It can display extremely complex pictures at very high resolutions without any flicker.
* **Disadvantages:** DVST systems cannot display color, and the physical process of erasing and redrawing a complex picture can take several seconds.


## **1. Fundamentals of Points and Lines**
* Line drawing is accomplished by calculating intermediate positions along the line path between two specified endpoint positions.
* The fundamental Cartesian slope-intercept equation for a straight line is $y = m.x + b$.
* Given two endpoints $(x_1, y_1)$ and $(x_2, y_2)$:
    * **Slope ($m$):** $m = (y_2 - y_1) / (x_2 - x_1)$, which can also be written as $m = \Delta y / \Delta x$.
    * **Y-intercept ($b$):** $b = y_1 - m.x_1$.

## **2. Digital Differential Analyzer (DDA)**
* The DDA is a scan conversion line algorithm that works by calculating either $\Delta y$ or $\Delta x$ based on the standard line equations.
* **Core Logic:** The algorithm samples the line at unit intervals in one coordinate and determines the corresponding integer values nearest the line path for the other coordinate.

**Processing Scenarios:**
* **Positive Slope ($m \le 1$), Left to Right:** We sample at unit x intervals ($\Delta x = 1$).
    * The successive x value is: $x_{k+1} = x_k + 1$.
    * The successive y value is computed as: $y_{k+1} = y_k + m$.
    * Because $m$ can be a real number, the calculated y values must be rounded to the nearest integer.
* **Positive Slope ($m > 1$), Left to Right:** The roles of x and y are reversed. We sample at unit y intervals ($\Delta y = 1$).
    * The successive y value is: $y_{k+1} = y_k + 1$.
    * The successive x value is: $x_{k+1} = x_k + 1/m$.
* **Reversed Processing (Right to Left):** If the starting endpoint is on the right, the increments become negative.
    * For $\Delta x = -1$, $y_{k+1} = y_k - m$.
    * For $\Delta y = -1$, $x_{k+1} = x_k - 1/m$.

## **3. The Step-by-Step DDA Algorithm**
* **Step 1:** Start.
* **Step 2:** Enter starting and ending points of a line, $(x_1, y_1)$ and $(x_2, y_2)$ respectively.
* **Step 3:** Calculate $dx = (x_2 - x_1)$ and $dy = (y_2 - y_1)$. Declare variables step, k, x_inc, y_inc, and initialize $x = x_1$ and $y = y_1$.
* **Step 4:** Check if abs(dx) > abs(dy).
    * If true, calculate step = abs(dx).
    * Else, calculate step = abs(dy).
* **Step 5:** Determine increments:
    * x_inc = dx / step.
    * y_inc = dy / step.
    * Assign $x = x_1$ and $y = y_1$.
* **Step 6:** Plot the starting pixel SetPixel(x,y).
* **Step 7:** Loop from k = 0 to k < step:
    * $x = x + x_{inc}$.
    * $y = y + y_{inc}$.
    * Plot the points $(x,y)$ until k = step, ensuring to plot the nearest integer value.
* **Step 8:** Stop.

## **4. Advantages and Disadvantages of DDA**
**Advantages:**
* It is a faster method than directly using the line equation $y = m.x + b$.
* It eliminates complex multiplication by making use of raster characteristics, applying appropriate increments in the x or y direction.
* It is conceptually easy because each step involves just two simple additions.

**Disadvantages:**
* It involves floating-point additions which must be rounded off.
* Accumulation of round-off errors causes the line to drift or become inaccurate over a long distance.
* Floating-point operations and rounding consume a lot of processing time.
* It is more suitable for software-based generation but less suited for direct hardware implementation.

## **2. Introduction to Bresenham's Line Algorithm**
* Developed by Bresenham, this algorithm is widely used for scan-converting a line.
* It is highly efficient because it relies strictly on integer addition, subtraction, and multiplication operations.
* Because it avoids floating-point math, these operations can be performed very rapidly, allowing lines to be generated quickly.

## **3. Bresenham's Scan Conversion Process (For $0 < m < 1$)**
* Starting from the left endpoint $(x_0, y_0)$, the algorithm steps to each successive column (x position) and plots the pixel whose scan line y value is closest to the mathematical line path.
* At a given plotted pixel $(x_k, y_k)$, there are two choices for the next pixel in column $x_{k+1}$: the lower pixel $(x_k+1, y_k)$ or the upper pixel $(x_k+1, y_k+1)$.
* The algorithm determines the closest pixel using a decision parameter ($p_k$), which calculates the difference between the physical pixel locations and the actual mathematical line.
* If $p_k$ is negative, it means the lower pixel is closer to the line path, so we plot the lower pixel. Otherwise, we plot the upper pixel.  

![alt text](image-7.png)

## **4. Algorithm Steps for Bresenham ($|m| < 1$)**
1. Input the two line endpoints and store the left endpoint in $(x_0, y_0)$.
2. Load $(x_0, y_0)$ into the frame buffer, effectively plotting the first point.
3. Calculate the constants $\Delta x$, $\Delta y$, $2\Delta y$, and $2\Delta y - 2\Delta x$, and obtain the starting value for the decision parameter: $p_0 = 2\Delta y - \Delta x$.
4. At each $x_k$ along the line, starting at $k=0$, perform the following test:
    * If $p_k < 0$, the next point to plot is $(x_k+1, y_k)$ and $p_{k+1} = p_k + 2\Delta y$.
    * Otherwise, the next point to plot is $(x_k+1, y_k+1)$ and $p_{k+1} = p_k + 2\Delta y - 2\Delta x$.
5. Repeat step 4 exactly $\Delta x$ times.
*(Note: For lines with a positive slope greater than 1, we interchange the roles of the x and y directions, stepping along y in unit steps and calculating successive x values nearest the line path).*

# **Derivation of Bresenham's Decision Parameter ($p_k$)**

**1. Identifying the Pixels**  
Consider the scan conversion process for a line with a positive slope less than 1 ($0 < m < 1$). 
Assuming we have just plotted the pixel at $(x_k, y_k)$, we need to decide which pixel to plot in the next column $x_{k+1}$. 
* The exact mathematical y-value on the line at this next step is: $y = m(x_k + 1) + b$
* We have two choices for the next pixel to plot: 
  * The lower pixel: $(x_k + 1, y_k)$
  * The upper pixel: $(x_k + 1, y_k + 1)$

**2. Calculating the Distances ($d_1$ and $d_2$)**  
We calculate the vertical distance from the mathematical line to both of our pixel choices:  
* Distance to the lower pixel ($d_1$):  
  $d_1 = y - y_k$
  $d_1 = [m(x_k + 1) + b] - y_k$

* Distance to the upper pixel ($d_2$):  
  $d_2 = (y_k + 1) - y$
  $d_2 = (y_k + 1) - [m(x_k + 1) + b]$

**3. Finding the Difference ($d_1 - d_2$)**  
To see which pixel is closer, we find the difference between these two distances:  
$d_1 - d_2 = [m(x_k + 1) + b - y_k] - [(y_k + 1) - (m(x_k + 1) + b)]$  
$d_1 - d_2 = 2m(x_k + 1) - 2y_k + 2b - 1$ *(This is Equation 1)*

**4. Introducing the Decision Parameter ($p_k$)**  
Since the slope $m = \Delta y / \Delta x$, we can substitute $m$ in our equation. To remove the fractional division and work only with integers, we multiply the entire equation by $\Delta x$. This gives us our decision parameter, $p_k$:  
$p_k = \Delta x (d_1 - d_2)$  
$p_k = \Delta x [2(\Delta y / \Delta x)(x_k + 1) - 2y_k + 2b - 1]$  
$p_k = 2\Delta y(x_k) - 2\Delta x(y_k) + c$  

*(Where $c$ is a constant equal to $2\Delta y + \Delta x(2b - 1)$)*

**5. Finding the Next Decision Parameter ($p_{k+1}$)**  
To find the parameter for the next step, we evaluate the equation at $k + 1$:  
$p_{k+1} = 2\Delta y(x_{k+1}) - 2\Delta x(y_{k+1}) + c$

Now, we subtract $p_k$ from $p_{k+1}$ to find the incremental difference:  
$p_{k+1} - p_k = 2\Delta y(x_{k+1} - x_k) - 2\Delta x(y_{k+1} - y_k)$

Since we always increment x by 1 ($x_{k+1} = x_k + 1$), the term $(x_{k+1} - x_k)$ is simply 1. This simplifies our equation to:
$p_{k+1} = p_k + 2\Delta y - 2\Delta x(y_{k+1} - y_k)$  
*(Note: $(y_{k+1} - y_k)$ will either be 0 or 1, depending on whether we chose the lower or upper pixel in the previous step).*

**6. Calculating the Initial Decision Parameter ($p_0$)**  
To start the algorithm, we need the very first decision parameter evaluated at the starting endpoint $(x_0, y_0)$. Substituting $(x_0, y_0)$ into our earlier equation and applying the line equation $b = y_0 - m \cdot x_0$, it simplifies entirely down to:  
**$p_0 = 2\Delta y - \Delta x$**

## **5. Bresenham Example Calculation**
* **Problem:** Calculate the intermediate points between coordinates (9, 18) and (14, 22).
* **Initial Values:** $\Delta y = 4$, $\Delta x = 5$, $m = 0.8$.
* **Constants:** $2\Delta y = 8$, $2\Delta x = 10$, $p_0 = 2\Delta y - \Delta x = 3$.
* **Iterations:**
    * $k=0$: $p = 3$, plot (10, 19).
    * $k=1$: $p_1 = 3 + 8 - 10 = 1$, plot (11, 20).
    * $k=2$: $p_2 = 1 + 8 - 10 = -1$, plot (12, 20).
    * $k=3$: $p_3 = -1 + 8 = 7$, plot (13, 21).
    * $k=4$: $p_4 = 7 + 8 - 10 = 5$, plot (14, 22).

## **6. Advantages and Disadvantages of Bresenham's Algorithm**
**Advantages:**
* It is easy to implement, fast, and highly incremental.
* The points generated by this algorithm are considerably more accurate than the DDA algorithm.
* It uses fixed points (integers) only, completely eliminating floating-point math.

**Disadvantages:**
* While it executes quickly, it is generally considered slightly less fast than the DDA algorithm.
* Although it improves the accuracy of generated points, the resulting line will still not be perfectly smooth due to the discrete nature of pixels.
* This specific algorithm is strictly meant for basic line drawing.


## **1. Properties of Circles and Basic Generation Methods**
A circle is defined as the set of points that are all at a given distance $r$ from a center position $(x_c, y_c)$.

* **Cartesian Method:** This distance relationship is expressed by the Pythagorean theorem in Cartesian coordinates as $(x - x_c)^2 + (y - y_c)^2 = r^2$. We can calculate points by stepping along the x-axis and calculating $y = y_c \pm \sqrt{r^2 - (x - x_c)^2}$.
    * **Drawback:** This approach involves considerable computation at each step.
* **Polar Coordinates Method:** Points can be calculated using polar coordinates $r$ and $\theta$ with the parametric equations $x = x_c + r \cos \theta$ and $y = y_c + r \sin \theta$.
    * **Drawback:** This equation requires significant computing time because it involves multiplication and trigonometric calculations, while the Cartesian method requires square root calculations.

Due to these inefficiencies, two primary algorithms are used: the Midpoint Circle Algorithm and Bresenham's Algorithm.

![alt text](image-8.png)

## **2. Midpoint Circle Drawing Algorithm: Principles**
* **Symmetry:** Computation can be heavily reduced by considering the symmetry of circles. The shape is similar in each quadrant, and circle sections in adjacent octants within one quadrant are symmetric with respect to the 45-degree line dividing the two octants. By calculating points within just one sector (from $x=0$ to $x=y$), we can find the remaining octants by symmetry and then translate them to the actual center $(x_c, y_c)$.
* **The Circle Function:** We define a circle function: $f_{circle}(x,y) = x^2 + y^2 - r^2$.
    * If $< 0$, the point $(x,y)$ is inside the circle boundary.
    * If $= 0$, the point $(x,y)$ is exactly on the circle boundary.
    * If $> 0$, the point $(x,y)$ is outside the circle boundary.  
    
![alt text](image-9.png)  
![alt text](image-10.png)

## **3. Mathematical Derivation of the Decision Parameter (From Handwritten Notes)**
Assuming we have just plotted the pixel at $(x_k, y_k)$, our next step is to determine if the pixel at position $(x_k+1, y_k)$ or the one at position $(x_k+1, y_k-1)$ is closer to the true circle. Our decision parameter ($p_k$) is the circle function evaluated at the exact midpoint between these two candidate pixels.

* **Midpoint Calculation:**  
$Midpoint = (\frac{(x_k+1) + (x_k+1)}{2}, \frac{y_k + (y_k-1)}{2}) = (x_k+1, y_k - \frac{1}{2})$.
* **Setting up $p_k$:**  
    * $p_k = f_{circle}(x_k+1, y_k - \frac{1}{2})$.
    * $p_k = (x_k+1)^2 + (y_k - \frac{1}{2})^2 - r^2$.
* **Setting up the next parameter $p_{k+1}$:**
    * $p_{k+1} = f_{circle}(x_{k+1}+1, y_{k+1} - \frac{1}{2})$.
    * $p_{k+1} = (x_{k+1}+1)^2 + (y_{k+1} - \frac{1}{2})^2 - r^2$.
* **Finding the Difference ($p_{k+1} - p_k$):**
    * $p_{k+1} - p_k = [(x_{k+1}+1)^2 + (y_{k+1} - \frac{1}{2})^2 - r^2] - [(x_k+1)^2 + (y_k - \frac{1}{2})^2 - r^2]$.
    * Since $x_{k+1} = x_k + 1$, the equation simplifies to:
    * $p_{k+1} = p_k + 2(x_{k+1}) + (y_{k+1}^2 - y_k^2) - (y_{k+1} - y_k) + 1$.
* **Conditional Updates:**
    * **If $p_k < 0$:** The midpoint is inside the circle, meaning $y_k$ is closer. We select $y_k$ (so $y_{k+1} = y_k$). The parameter updates to: $p_{k+1} = p_k + 2x_{k+1} + 1$.
    * **If $p_k \ge 0$:** The midpoint is outside or on the circle, meaning $y_k-1$ is closer. We select $y_k-1$ (so $y_{k+1} = y_k - 1$). The parameter updates to: $p_{k+1} = p_k + 2x_{k+1} + 1 - 2y_{k+1}$.
* **Initial Decision Parameter ($p_0$):**
    * Evaluated at the starting point $(0, r)$, where $x_0 = 0$ and $y_0 = r$.
    * $p_0 = f_{circle}(0+1, r - \frac{1}{2})$.
    * $p_0 = (1)^2 + (r - \frac{1}{2})^2 - r^2 = 1 + r^2 - r + \frac{1}{4} - r^2 = \frac{5}{4} - r$.
    * If the radius is an integer, this can be safely approximated to $1 - r$.

## **4. Midpoint Circle Algorithm Steps**
1. Input radius $r$ and circle center $(x_c, y_c)$, then set the coordinates for the first point on the circumference of an origin-centered circle as $(x_0, y_0) = (0, r)$.
2. Calculate the initial decision parameter as $p_0 = 5/4 - r$ (or $1-r$).
3. At each $X_k$, starting from $k=0$, perform the following tests:
    * If $p_k < 0$, the next point is $(x_k+1, y_k)$ and $p_{k+1} = p_k + 2x_{k+1} + 1$.
    * Otherwise, the next point is $(x_k+1, y_k-1)$ and $p_{k+1} = p_k + 2x_{k+1} + 1 - 2y_{k+1}$.
4. Determine symmetry points in the other seven octants.
5. Move each calculated pixel position $(x,y)$ onto the true circular path by calculating: $X = x + x_c$ and $Y = y + y_c$.
6. Repeat steps 3 through 5 until $x \ge y$.

## **5. Advantages and Disadvantages of Midpoint Algorithm**
* **Advantages:** It is a powerful and efficient algorithm based entirely on the simple equation $X^2 + Y^2 = R^2$. It is easy to implement and is standard for generating curves on raster displays.
* **Disadvantages:** The accuracy of the generated points can be an issue, the resulting circle is not perfectly smooth, and the algorithm is time-consuming.

## **6. Bresenham's Circle Drawing Algorithm Steps**
1. Input radius $r$ and circle center $(x_c, y_c)$, then set the first coordinate for the origin-centered circle as $(x_0, y_0) = (0, r)$.
2. Calculate the initial decision parameter: $p_0 = 3 - 2r$.
3. At each $X_k$, starting from $k=0$, test:
    * If $p_k < 0$, the next point is $(x_k+1, y_k)$ and $p_{k+1} = p_k + 4x_k + 6$.
    * Otherwise, the next point is $(x_k+1, y_k-1)$ and $p_{k+1} = p_k + 4(x_k - y_k) + 10$.
4. Determine symmetry points in the other seven octants.
5. Move each pixel onto the true path: $X = x + X_c$ and $Y = y + y_c$.
6. Repeat steps 3 through 5 until $x \ge y$.

---

## **7. University & Sample Questions Bank**

**Sample Practical Problems:**
1. The center coordinates are (0, 0), and the radius of the circle is 10. Find all points of the circle by using the midpoint circle drawing algorithm?
2. Given the center point coordinates (4, 4) and radius as 10, generate all the points to form a circle.
3. Use mid-point circle drawing algorithm to plot a circle whose radius =20 units and center at (50,30) (5M).
4. Using both DDA and Bresenham's line drawing algorithm, plot the line with endpoints (20,15) and (34,20).
5. Rasterize the line segment from pixel coordinate (1,1) to (8,5) using Bresenham's line drawing algorithm.
6. Describe the DDA line drawing algorithm. Use the algorithm to find the coordinate along the line joining the pixel positions (5,12) and (15,20).
7. Explain the midpoint circle drawing algorithm. Find the pixel locations approximately the first octant of a circle having centre (10,13) and radius of 5 units using this algorithm.
8. Rasterize the line with end points(2,3) and (5,8) using Bresenham's line drawing algorithm.
9. Using the midpoint circle drawing algorithm find out the first quadrant point of a circle from x=0 to x=y where r=10. Also draw the complete circle using the same.

**Theoretical & Hardware Questions:**  

10. Distinguish between raster scan display and random scan display.  
11. What do you understand about the aspect ratio and resolution of a display screen in a raster scan display?  
12. Explain the working of a random scan display system with a suitable diagram.  
13. Explain the working of a beam penetration CRT.  
14. Explain the working of direct view storage tubes (DVST).  
15. Consider a raster system with a resolution of 2560x2048. Determine the frame buffer size (in bytes) needed for the system to store 12-bits per pixel. How much storage is required if 24-bits per pixel are to be stored?  
16. Explain the working of a delta-delta shadow mask CRT.  
17. What is the use of computer graphics? List out and explain any 5 applications of computer graphics.  
18. Draw and explain the architecture of simple raster graphics systems.  
19. Define the following: Persistence, Resolution, Aspect ratio, Frame buffer.  
20. Describe in detail the basic video controller refresh operation used in interactive raster graphics systems.  
21. Explain the working of the cathode ray tube in detail.  
22. What is the role of a display controller in a raster scan display system? Explain.  
23. Explain the functioning of a random scan display system.  
24. With a neat diagram describe the working of a cathode ray display device.  
25. Write the methods used to plot a dashed line segment.  
26. How 8-way symmetric points if (x,y) is a point on the circle with centre at origin.  
27. Write the DDA line drawing algorithm.  
28. Write the midpoint circle drawing algorithm.  
29. What are the advantages and disadvantages of the DDA algorithm?  
30. Explain DDA line drawing algorithm with examples.  
31. Describe simple random scan display system and draw its architecture.  
32. With a suitable figure, describe the shadow masking techniques.  
33. Compare the working principle of raster scan systems and random scan systems.  
34. How much time is spent scanning across each row of pixels during screen refresh on a raster system with resolution of 1280x1024 and a refresh rate of 60 frames per second?