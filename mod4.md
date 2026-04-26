### Fundamentals of Digital Images

**1. What is an Image?**
* An image is defined mathematically as a two-dimensional function, $F(x,y)$, where x and y represent spatial coordinates.
* The amplitude of the function F at any specific coordinate pair (x,y) is referred to as the intensity of the image at that location.
* A Digital Image occurs when the spatial coordinates (x, y) and the amplitude values of F are finite.
* Structurally, an image can be conceptualized as a two-dimensional array that is specifically organized into rows and columns.
* A digital image comprises a finite number of individual elements, each possessing a specific value at a designated location.
* These individual components are known by several names: picture elements, image elements, or pixels.
* Pixel is the most widely adopted term to describe the fundamental elements of a Digital Image.

**2. Image as a Matrix**
* An image can be represented mathematically as a matrix of size M $\times$ N. The function $f(x,y)$ maps the coordinates to intensity values from the origin $f(0,0)$ to the bottom-right corner $f(M-1,N-1)$.
* Row 0 begins at $f(0,0)$ and ends at $f(0,N-1)$.
* Row 1 begins at $f(1,0)$ and ends at $f(1,N-1)$.
* The final row (M-1) goes from $f(M-1,0)$ up to $f(M-1,N-1)$.

**3. Image Representation: Color and Bit Depth**

**Binary Image**
* As indicated by the name, a binary image contains only two possible pixel values: 0 and 1.
* A value of 0 corresponds to the color black, while a value of 1 corresponds to the color white.
* This type of image is also referred to as Monochrome.
* Format: The standard format for binary images is PBM (Portable Bit Map).

**8-Bit Color Format (Grayscale Image)**
* This is one of the most widely recognized image formats and is commonly referred to as a Grayscale image.
* It is capable of displaying 256 different shades of color.
* The pixel values range continuously from 0 to 255.
* In this scale, 0 represents black, 255 represents white, and 127 represents a perfect mid-tone gray.
* Historically, this format was utilized by early UNIX operating systems and the first color Macintosh computers.
* Format: These images typically use the PGM (Portable Gray Map) format. Note that this format is not natively supported by Windows by default; viewing it requires specialized image viewers or toolboxes like Matlab.

**16-Bit Color Format (High Color)**
* This is a color image format that can display up to 65,536 distinct colors.
* It is frequently referred to as the High color format.
* Microsoft has historically utilized this format in systems designed to support color depths greater than 8 bits.
* Unlike grayscale images, color representation in 16-bit (and 24-bit) formats is more complex because it relies on the RGB (Red, Green, Blue) model.
* Bit Distribution: The 16 bits are not divided equally. The distribution is 5 bits for Red, 6 bits for Green, and 5 bits for Blue.
* Why 6 bits for Green? If 5 bits are allocated to R, G, and B, one bit remains (since $5+5+5=15$). This extra bit is assigned to the green channel because green is the most soothing color to the human eye among the three primaries.

**24-Bit Color Format (True Color)**
* The 24-bit format is widely known as the True color format.
* Similar to the 16-bit format, the available bits are divided among the Red, Green, and Blue channels.
* Because 24 is perfectly divisible by 3, the bits are distributed equally across the color channels.
* Bit Distribution: 8 bits for Red, 8 bits for Green, and 8 bits for Blue.
* Format: This is the most prevalent image format used today. In Linux operating systems, it is supported as PPM (Portable PixMap). In Windows, it has its own dedicated format known as BMP (Bitmap).


### 1. What is Digital Image Processing?

* **Definition:** Digital Image Processing refers to the processing of digital images using a digital computer.
* **Purpose:** It involves utilizing computer algorithms to either enhance the quality of images or extract useful and specific information from them.

---

### 2. Applications Across the Electromagnetic Spectrum

Image processing spans various bands of the electromagnetic spectrum, each serving distinct scientific, medical, and industrial purposes:

#### 1) Gamma-ray Imaging
* **Nuclear Medicine:** Patients are injected with a radioactive isotope that emits gamma rays as it decays.
* **Data Collection:** Gamma-ray decoders collect emissions to form these images.
* **Medical Diagnostics:** This imaging technique is vital for locating sites of bone pathology, such as infections or tumors.
* **Space Exploration:** It is also utilized for astronomical observations.

#### 2) X-ray Imaging
* **Medical Uses:** Broadly used in medical diagnostics, including Angiography.
* **Advanced Scanning:** Powers Computerized Axial Tomography (CT scans).
* **Manufacturing:** Utilized in various industry applications for non-destructive testing.

#### 3) Ultraviolet (UV) Imaging
Primarily used in specialized technical and scientific fields, including:
* Lithography 
* Industrial inspection 
* Microscopy 
* Lasers 
* Biological imaging 
* Astronomical observations 

#### 4) Imaging in the Visible and Infrared Bands
* **Microscopy:** Standard light microscopy relies on this band.
* **Space and Earth Observation:** Used in astronomy and remote sensing.
* **Commercial and Security:** Applied in various industries and law enforcement, particularly for biometrics.

#### 5) Imaging in the Microwave Band
* **Radar Systems:** Microwave imaging is predominantly used in radar technology.
* **Advantage:** It can collect data over virtually any geographic region at any given time, completely independent of weather or ambient lighting conditions.

#### 6) Imaging in the Radio Band
* **Healthcare:** Highly critical in medicine, specifically for Magnetic Resonance Imaging (MRI).
* **Space Science:** Also used in radio astronomy to observe celestial objects.

## Fundamental Steps in Digital Image Processing

The process of digital image processing involves a sequence of fundamental steps that generally take an image from a problem domain and output either processed images or image attributes. Throughout these stages, a central "Knowledge base" is used, which stores all the information relating to an image for processing.

![alt text](image-31.png)
---

### 1. Image Acquisition
* Image acquisition is the very first step in the digital image processing workflow.
* In this stage, an image is captured and provided in digital form.
* Initial pre-processing tasks, such as scaling the image, are generally performed during this phase.

### 2. Image Enhancement
* Image enhancement involves manipulating an image to make the final result more suitable for a specific application than the original image.
* This step highlights interesting features of an image through adjustments like brightness and contrast tweaking, noise removal, and image sharpening.
* This process is highly subjective in nature, meaning the techniques used will vary greatly from application to application.

### 3. Image Restoration
* Image restoration is the stage focused on improving the overall appearance of an image.
* It deals specifically with recovering an image that has been degraded in some way.
* Unlike enhancement, restoration techniques are objective in nature.

### 4. Color Image Processing
* Color image processing has become a famous and critical area due to the massively increased use of digital images on the internet.
* This stage involves concepts like color modeling and the processing of color data within a digital domain.

### 5. Wavelets and Multi-Resolution Processing
* Wavelets facilitate the wavelet transform, a process that provides both time and frequency information about an image.
* This technique leads to multi-resolution processing, allowing an image to be represented and analyzed in various degrees of resolution.

### 6. Compression
* Compression is a vital technique used for reducing the storage space required to hold an image.
* It is a highly important stage because compressing data is necessary for efficient transmission and use over the internet.

### 7. Morphological Processing
* This stage involves using mathematical tools for extracting specific components of an image.
* These extractions are incredibly useful in the representation and description of object shapes.
* The most basic operations utilized in morphological processing are erosion and dilation.

### 8. Segmentation
* Segmentation is the process where a digital image is partitioned into various subgroups of pixels, known as "Image Objects".
* The goal is to reduce the complexity of the image, making it much simpler to analyze.
* It is widely considered the most difficult task in digital image processing.
* Because it requires identifying individual objects successfully, it is a process that typically takes a lot of time.

### 9. Representation and Description
* Representation and description directly follow the raw output generated by the segmentation stage.
* The segmentation output is raw pixel data containing all the points of a region or the points making up the boundary of a region.
* Representation transforms this raw data into a format that is suitable for computer processing.
* Description is then used to extract specific information to differentiate one class of objects from another.
* This involves feature selection, which extracts specific attributes that result in quantitative information of interest.

### 10. Object Recognition
* In the final fundamental stage, a distinct label is assigned to an object.
* This classification and labeling are based entirely on the descriptors gathered in the previous stage.

## Components of an Image Processing System

![alt text](image-32.png)

An image processing system is structured around several interconnected components that take input from a problem domain and process it for display or storage.

* **Image Sensors:** Acquiring digital images requires two main elements. The first is a physical device sensitive to the radiated energy of the target object. The second element is a digitizer, which is responsible for converting the physical device's output into a digital form.
* **Specialized Image Processing Hardware:** This includes the digitizer along with hardware designed to perform other primitive operations. For example, it might contain an Arithmetic Logic Unit (ALU) for executing parallel arithmetic and logic operations on entire images.
* **Computer:** The core processing unit is typically a general-purpose computer, similar to those used in daily life. Depending on the processing needs, this can range from a standard PC up to a supercomputer. In some cases, custom computers are utilized to achieve specific performance levels.
* **Image Processing Software:** This component encompasses all the algorithms and mechanisms deployed within the image processing system to manipulate the data.
* **Mass Storage:** Storage is required to hold the image pixels during the active processing phase. Providing adequate storage can be challenging. For example, a single uncompressed 1024 x 1024 pixel image with 8-bit intensity requires 1 MB of space. Digital storage in this field is divided into three principal categories: short-term storage for active processing , online storage for relatively fast recall , and archival storage for infrequent access.
* **Image Display:** Processed images are typically viewed on color TV monitors. In some specialized cases, stereo displays are used, which are designed as headgear containing two small displays embedded within goggles worn by the user.
* **Hard Copy Device:** Once an image is fully processed, it is saved to a hard copy device. These can include modern solutions like pen drives or other external ROM devices. Additional hardware options include laser printers, film cameras, optical disks, and CD ROMs.
* **Network:** Because image processing applications inherently involve extremely large amounts of data, bandwidth is the key consideration for image transmission across a network.

## Digital Image Processing: Coordinates, Sampling, and Quantization


### 1. Coordinate Conventions
* An image is mathematically represented as a function $f(x,y)$.
* The size of an image is determined by its dimensions: the number of rows ($M$) multiplied by the number of columns ($N$), often written as $M \times N$.
* The total number of pixels in an image is calculated by multiplying the total number of rows by the total number of columns.
* In the coordinate plane for digital images, the origin $(0,0)$ is located at the top-left corner.
* The x-axis represents the rows, which go downwards from 0 to $M-1$.
* The y-axis represents the columns, which go rightwards from 0 to $N-1$.
* The matrix spans from $f(0,0)$ at the origin to $f(M-1,N-1)$ at the bottom-right corner.

### 2. Conversion of Analog to Digital Signals
* The output generated by most image sensors is initially an analog signal.
* Analog signals cannot be processed digitally or stored in a computer because a signal with continuous (infinite) values would require infinite memory.
* Therefore, to create a digital image, continuous analog data must be converted into a digital form.
* This conversion requires digitizing both the x and y axes of the signal.
* The conversion process relies on two fundamental steps: **Sampling** and **Quantization**.

### 3. Sampling
* Sampling is the process of digitizing the x-axis.
* It is performed on the independent variable of the function.
* For example, in the equation $y=\sin(x)$, sampling is applied to the $x$ variable.
* Practically, sampling involves gathering a large number of discrete values (sample points) along the x-axis at specific intervals (like T, 2T, 3T, etc.) rather than taking a continuous reading.

![alt text](image-33.png)

### 4. Quantization
* Quantization is considered the opposite counterpart to sampling; it focuses on digitizing the y-axis.
* While the x-axis represents coordinate values, the y-axis represents the signal's amplitudes.
* Digitizing these amplitude values is what we call Quantization.
* During quantization, the signal is divided into specific quanta or partitions.
* Essentially, quantization assigns distinct intensity levels to the values gathered during the sampling phase.
* For instance, an analog signal might be quantized into 5 discrete levels, mapping an amplitude to a range like 0 (representing black) to 4 (representing white).

![alt text](image-34.png)
![alt text](image-35.png)

### 5. Gray Levels and Image Quality
* The number of partitions (quanta) used in quantization directly equals the number of gray levels.
* "Number of gray levels" refers to the total number of different shades of gray available in the image.
* To improve the overall quality of a digital image, one must increase the number of gray levels (also known as the gray level resolution).

## Spatial and Gray Level Resolution


### 1. Spatial Resolution
* The clarity of an image is not solely determined by its pixel resolution, which is just the total number of pixels in the image.
* Instead, spatial resolution is properly defined as the number of independent pixel values per inch.
* Different devices use specific metrics to measure this resolution:
  * **Dots per inch (DPI):** This measurement is most commonly used for monitors.
  * **Lines per inch (LPI):** This measurement is typically used for laser printers.
  * **Pixel per inch (PPI):** This metric is used to measure the resolution of devices such as mobile phones and tablets.

### 2. Gray Level Resolution
* Gray level resolution refers to the deterministic or predictable change in the shades or levels of gray present in an image.
* Put simply, the gray-level resolution is equivalent to the number of bits per pixel (BPP).
* The total number of different colors (or shades) in an image is directly dependent on this color depth or bits per pixel.
* The mathematical relationship between gray level resolution and bits per pixel is defined by the formula: $L=2^{k}$.
* In this formula, $L$ represents the number of gray levels, and $k$ represents the bits per pixel.
* As a general rule, the higher the number of bits per pixel in an image, the higher its gray-level resolution will be.

### 3. Practical Examples and Calculations

**Example 1: Grayscale Image of Einstein**
* Consider a standard grayscale image, such as a photograph of Albert Einstein.
* If this image is encoded at 8 bits per pixel (8bpp), we can calculate its resolution.
* Using the formula $L=2^{k}$, where $k=8$, we get $L=2^{8}$, which results in $L=256$.
* This means the image has a gray-level resolution of 256, allowing it to display 256 completely different shades of gray.

**Example 2: Calculating Storage Requirements**
* **Problem:** If the spatial resolution of an image is given as 128 X 128, what are its storage requirements if it is represented by 64 gray levels? 
* **Solution:** First, determine the bits per pixel. Since there are 64 gray levels, and $64=2^{6}$, it requires a 6-bit representation for each individual grey level.
* Next, define the image size, which is $128\times128$.
* Finally, multiply the total number of pixels by the bits per pixel: Storage requirements $= 128\times128\times6$ bits.

## The Basic Relationship Between Pixels


### 1. Neighbors of a Pixel
A pixel $p$ located at coordinates $(x,y)$ has specific neighboring pixels based on their spatial relationship.

* **4-Neighborhood ($N_4(p)$):** These are the four horizontal and vertical neighbors of pixel $p$. Their coordinates are $(x+1,y)$, $(x-1,y)$, $(x,y+1)$, and $(x,y-1)$. Each of these pixels is exactly one unit distance away from $(x,y)$.
* **Diagonal Neighborhood ($N_D(p)$):** These are the four diagonal neighbors of $p$. Their coordinates are $(x+1,y+1)$, $(x+1,y-1)$, $(x-1,y+1)$, and $(x-1,y-1)$.
* **8-Neighborhood ($N_8(p)$):** This set is the combination of the 4-neighbors and the diagonal neighbors ($N_8 = N_4 \cup N_D$).
* **Image Borders:** If the pixel $p$ lies on the border of the digital image, some of these neighbor points (in $N_4$, $N_D$, or $N_8$) will fall outside the image boundaries.

---

### 2. Adjacency
Two pixels are considered "connected" if they are neighbors and their gray levels satisfy a specific criterion of similarity.
This similarity criterion is defined by a set of intensity values, denoted as $v$.

* **Binary Image Example:** In a binary image where $v=\{1\}$, two pixels are connected if they are 4-neighbors and both share the same value of 1.
* **Grayscale Image Example:** The concept remains the same, but the set $v$ typically contains a range of elements. For instance, if possible intensity values range from 0 to 255, $v$ could be a subset like $v=\{180, 181, \dots, 200\}$.

---

### 3. Types of Adjacency
* **4-adjacency:** Two pixels $p$ and $q$ (with values from set $v$) are 4-adjacent if pixel $q$ is found in the set $N_4(p)$.
* **8-adjacency:** Two pixels $p$ and $q$ (with values from set $v$) are 8-adjacent if pixel $q$ is found in the set $N_8(p)$.
* **m-adjacency (mixed adjacency):** Two pixels $p$ and $q$ (with values from $v$) are m-adjacent if:
  * $q$ is in $N_4(p)$, OR
  * $q$ is in $N_D(p)$ AND the set of pixels in both $N_4(p)$ and $N_4(q)$ contains no pixel whose values belong to $v$.
* **Purpose of m-adjacency:** It is a modification of 8-adjacency designed specifically to eliminate ambiguities (such as multiple path connections) that frequently occur when only 8-adjacency is used. If both 4-adjacency and 8-adjacency are simultaneously possible, priority is always given to 4-adjacency to resolve ambiguity.

---

### 4. Digital Paths
A digital path (or curve) from a starting pixel $p$ at $(x,y)$ to an ending pixel $q$ at $(s,t)$ is defined as a sequence of distinct pixels.
The sequence of coordinates is $(x_0,y_0), (x_1,y_1), \dots, (x_n,y_n)$, where the start $(x_0,y_0) = (x,y)$ and the end $(x_n,y_n) = (s,t)$.

* For the path to be valid, adjacent pixels in the sequence, $(x_i,y_i)$ and $(x_{i-1},y_{i-1})$, must be adjacent to each other for $1 \le i \le n$.
* The length of this path is $n$.
* If the starting coordinate equals the ending coordinate ($(x_0,y_0) = (x_n,y_n)$), it is called a closed path.
* Paths are classified as 4-, 8-, or m-paths depending entirely on the type of adjacency rules applied.
* **Pathing Example:** When finding the shortest path between $p$ and $q$ where $V=\{1,2\}$:
  * A 4-path may not be possible if pixel $q$ does not have any 4-adjacent pixels with values of 1 or 2.
  * An 8-path might be possible (e.g., yielding a length of 4).
  * An m-path might also be possible (e.g., yielding a length of 5).

---

### 5. Connected Components and Regions
Let $S$ represent a specific subset of pixels within an image.

* Two pixels $p$ and $q$ are "connected in $S$" if a valid path exists between them that consists entirely of pixels from subset $S$.
* For any pixel $p$ inside $S$, the entire group of pixels connected to $p$ in $S$ is called a "connected component" of $S$.
* If the subset $S$ contains only one connected component, then $S$ is officially called a "connected set".
* Based on adjacency, there are three types of connectivity:
  * **4-connectivity:** Pixels are 4-connected if they are 4-adjacent to each other.
  * **8-connectivity:** Pixels are 8-connected if they are 8-adjacent to each other.
  * **m-connectivity:** Pixels are m-connected if they are m-adjacent to each other.
* **Regions:** A subset of pixels $R$ is called a "region" of the image if $R$ is a connected set.
  * Two regions ($R_i$ and $R_j$) are considered adjacent if combining them (their union) forms a single connected set.
  * Regions that are not adjacent are called "disjoint".
  * **Note:** The type of adjacency used determines if regions connect. Two diagonal regions might only be adjacent if 8-adjacency is used, as a 4-path between them might not exist.

---

### 6. Boundaries
The boundary of a region $R$ consists of the set of pixels inside the region that have at least one neighbor that is not in the region (a background neighbor).

* **Foreground vs. Background:** If an image has $K$ distinct regions ($R_k$) that do not touch the image border, the union of all these regions ($R_u$) is called the "foreground". The complement of this set, denoted as $(R_u)^c$ (points not in $S$), makes up the "background" of the image.
* The rules of connectivity dictate boundary inclusion. For instance, a specific pixel might not be a member of the border under 4-connectivity, but would be considered part of the boundary if 8-adjacency is used between the region and the background.
* An inner border might not form a completely closed path around a region, whereas the outer border of a region does form a closed path.

## Fundamentals of Spatial Domain Filtering


### 1. Mechanics of Spatial Filtering
* Spatial filtering operations involve a defined neighborhood, typically a small rectangle, and a predefined operation that is executed on the image pixels within that neighborhood.
* The filtering process generates a new pixel, assigning it coordinates that correspond precisely to the center of the neighborhood.
* The numerical value of this new pixel is the direct result of the applied filtering operation.
* A filter is classified as a "linear spatial filter" if the operation performed on the pixels is linear; if it is not linear, it is referred to as a nonlinear filter.

### 2. Linear Spatial Filtering Mechanism (**3x3** Neighborhood)

![alt text](image-36.png)

* When utilizing a $3 \times 3$ neighborhood, the output response, denoted as $g(x,y)$, at any specific point $(x,y)$ is calculated as the sum of the products of the filter coefficients and their corresponding image pixel values.
* The center coefficient of the filter mask, designated mathematically as $w(0,0)$, is aligned exactly with the pixel at location $(x,y)$.
* The expanded equation for this $3 \times 3$ operation is: 
  $$g(x,y) = w(-1,-1)f(x-1,y-1) + w(-1,0)f(x-1,y) + \dots + w(0,0)f(x,y) + \dots + w(1,1)f(x+1,y+1)$$

### 3. General Expression for $m \times n$ Filters
* For a generalized filter mask of size $m \times n$, it is assumed that $m = 2a + 1$ and $n = 2b + 1$, where both $a$ and $b$ represent positive integers.
* The general expression for the linear spatial filtering of an image of size $M \times N$ utilizing an $m \times n$ filter is: 
  $$g(x,y) = \sum_{s=-a}^{a} \sum_{t=-b}^{b} w(s,t)f(x+s,y+t)$$
* During this computation, the coordinates $x$ and $y$ are varied sequentially so that every pixel located within the filter mask $w$ visits every pixel located within the image $f$.

### 4. Spatial Correlation vs. Convolution
Both correlation and convolution are fundamental operations defined as functions of displacement.

![alt text](image-37.png)
![alt text](image-38.png)
![alt text](image-39.png)

* **Correlation:** This process involves moving the filter mask over the image and systematically computing the sum of products at each location.
* **Convolution:** This process is identical to correlation, with one crucial exception: the filter mask is first rotated by **180°** before the sliding and multiplication begin.
* Notably, if the filter mask used is perfectly symmetric, both correlation and convolution will yield the exact same output result.
* The mathematical expression for convolution incorporates a minus sign to reflect this **180°** rotation: 
  $$w(x,y) * f(x,y) = \sum_{s=-a}^{a} \sum_{t=-b}^{b} w(s,t)f(x-s,y-t)$$

### 5. Mechanics of 1-D Correlation and Convolution
* When dealing with a 1-D function $f$ and a filter $w$, there are initial parts of the functions that do not physically overlap.
* To resolve this, the function $f$ must be padded with a sufficient number of zeros on both sides to allow every pixel in $w$ to successfully visit every pixel in $f$.
* If the filter size is $m$, the function requires exactly **m-1** zeros padded on either side of $f$.
* At the initial starting position (where displacement $x=0$), the first value computed for correlation is the sum of the products of $f$ and $w$, which is generally zero.
* To find the next value, the filter $w$ is shifted one pixel location to the right (displacement $x=1$), and the sum of products is computed again.
* A "full" correlation result includes all shifts (e.g., producing **12** values), but this array is typically cropped back to the original size of the function $f$.
* Performing correlation with a discrete unit impulse results in a **180°** rotated copy of the function at the impulse location.
* In contrast, performing convolution with a discrete unit impulse results in an exact, unrotated copy of the function at the impulse location.

### 6. Extension to 2-D Images (Padding)
* When applying a filter of size $m \times n$ to a 2-D image, the image must be zero-padded with a minimum of **m-1** rows of zeros at the top and bottom boundaries.
* Similarly, it must be padded with **n-1** columns of zeros on the left and right boundaries.

### 7. Smoothing (Averaging) Filters
* Averaging filters utilize specific masks to achieve spatial smoothing.
* One example is a $3 \times 3$ mask where all coefficients are **1**, requiring a constant multiplier of **1/9** at the front.
* Another common $3 \times 3$ mask uses weighted coefficients (a center value of **4**, edge values of **2**, and corner values of **1**), requiring a constant multiplier of **1/16**.
* As a strict rule, the constant multiplier placed in front of an averaging mask must be equal to **1** divided by the total sum of all its coefficient values.
* This fraction is mathematically required to accurately compute an average.