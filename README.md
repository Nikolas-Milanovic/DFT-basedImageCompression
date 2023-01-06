# The Problem

Storing data is expensive. Data such as images are very expensive. So what if we could compress the image data (i.e. decrease the required date to store the image), without losing much detail from the orignal? Luckily, thanks to our boy Fourier we can!

# DFT-basedImageCompression

This program uses Discrete Fourier Transform (DFT) to compress a grayscale image.

# Implementation

1) Convert the inputed grayscale image to a 2D array of floating point values
2) We then iterate over every 32 x 32 pixel block, and do the following:
  * Compute the DFT for the 32 x 32 block
  * Compute F_max = maximum of frequency value {F_k,l} within a given 32 x 32 block 
  * Input a tol(erance) - a specided drop tolerance 
  * Then for any Frequency, {F_k,l} which satisfies the following condition, we drop (i.e set {F_k,l} = 0 ):
  
  <img width="174" alt="image" src="https://user-images.githubusercontent.com/59632554/211053446-b29835ec-07f7-4969-830e-4e04c20d3d2a.png">

3) Perform an Inverse Discrete Fourier Transform (IDFT) on the mutated Frequencies, to get the resulting compressed image.

# Results

Original Inputed Image (Full Resolution)

![operahall](https://user-images.githubusercontent.com/59632554/211055278-4d6b26be-4473-4752-bcb8-935ab234b515.png)

The following results include the Tol value and the Drop Ratio (i.e. % of frequencies set to zero/ ~compression %) 

<img width="589" alt="image" src="https://user-images.githubusercontent.com/59632554/211055698-576cd5d3-97e6-4f35-8443-8fb5fd65b4fd.png">

![image](https://user-images.githubusercontent.com/59632554/211055488-d8efb2ff-1a75-4ab9-82af-0ab89f8303e5.png)

![image](https://user-images.githubusercontent.com/59632554/211055532-7926c50e-fcfc-41c0-a5f2-0048aa4eb39c.png)

![image](https://user-images.githubusercontent.com/59632554/211055912-dc57b6c8-4121-45cf-a309-3850520a440d.png)

![image](https://user-images.githubusercontent.com/59632554/211055946-0f00e5d4-4313-4fc9-84e0-7d95206b0d83.png)
