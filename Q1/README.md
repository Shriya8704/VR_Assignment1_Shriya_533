# **Coin Segmentation Using Watershed Algorithm**
### **Introduction**
This project demonstrates the use of the Watershed Algorithm for segmenting and counting coins in an image. The script performs image preprocessing, applies morphological transformations, and utilizes the Watershed algorithm to identify and count the number of coins.

### **Requirements**
Ensure you have the following dependencies installed before running the script:
```bash
pip install opencv-python numpy matplotlib
```
Alternatively, if you are running the code in Google Colab, you can use:
```bash
!pip install opencv-python numpy matplotlib
```
### **Running the Code**

1. Place the image file (coins.png) in the working directory.

2. Run the script in a Jupyter Notebook or Google Colab.

3. The script will display intermediate steps and final results, including:

   - Original image
    
    * Grayscale image
    
    * Binary thresholding
    
    * Morphological transformations
    
    * Background and foreground detection
    
    * Watershed segmentation
  
    * Final image with contours drawn around detected coins

### **Code Explanation**

1. **Image Preprocessing**
   * Loading the Image: The script reads coins.png using OpenCV.
   * Displaying the Image: A helper function imshow() is used to display images within a Jupyter Notebook.
   * Grayscale Conversion: Converts the image to grayscale for processing.
     
2. **Image Segmentation**
   * Thresholding: Uses Otsu’s Binarization to create a binary image.
  
   * Morphological Transformations: Applies an opening operation to remove noise.
  
   * Background & Foreground Detection:
  
     * Sure Background: Dilation is applied to get the sure background.
    
     * Sure Foreground: Distance Transform is used to identify the sure foreground.
    
     * Unknown Region: The difference between background and foreground.
  
   * Connected Components Analysis: Labels different regions of the segmented image.
  
   * Watershed Algorithm: Applies OpenCV’s watershed() function to perform segmentation.

3. **Contour Extraction and Counting**

   * Extracts contours of the detected objects (coins) and draws them on the original image.
  
   * The script prints the total number of coins detected.
