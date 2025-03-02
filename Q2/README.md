# **Image Stitching with SIFT and Homography**

## Introduction
This project demonstrates how to use SIFT (Scale-Invariant Feature Transform) and Homography Estimation to stitch two images together into a panorama. The approach involves detecting keypoints, finding matches, computing homography, and warping images for alignment.

## Running the Code

1. Upload two images (1.jpg and 2.jpg) to your working directory.

2. Run the script in Google Colab or a Python environment.

3. The script will:

   * Load and display the images.
  
   * Convert them to grayscale.
  
   * Detect keypoints and descriptors using SIFT.
  
   * Match keypoints using BFMatcher.
   * Compute Homography for perspective transformation.
  
   * Warp and align the images to create a stitched output.
  
   * Save and display the final stitched image (output.jpg).
   

### **Code Explanation**

1. **Image Processing**

   * Loading Images: Reads 1.jpg and 2.jpg using OpenCV.
  
   * Grayscale Conversion: Converts both images to grayscale for feature detection.

2. **Feature Matching**

   * SIFT Keypoint Detection: Extracts key points and descriptors.
   * BFMatcher: Finds the best feature matches based on descriptor distances.
   * Sorting Matches: Keeps the best matches based on distance for accuracy.
     


3. **Homography Estimation**

   * Extracts matched key points.

   * Computes the transformation matrix using cv2.findHomography with RANSAC.
    ![Greyscale Image](https://github.com/Shriya8704/VR_Assignment1_Shriya_533/blob/main/Q2/img_matches.jpg)

4. **Image Warping & Blending**

   * Applies the perspective transformation to align img1 with img2.

   * Computes the bounding box for the stitched image.

   * Uses a translation matrix to align both images properly.

   * Creates a blended output by selecting non-zero pixels from the warped images.
     ![Greyscale Image](https://github.com/Shriya8704/VR_Assignment1_Shriya_533/blob/main/Q2/output.jpg)

## **Results and Observations**

   * The script successfully aligns and stitches images to form a panorama.

   * SIFT + Homography works well for overlapping images but may struggle with large perspective differences.

   * Some seams may be visible; blending techniques like multi-band blending could improve the result.

## **Sample Output**

   * The final output (output.jpg) will contain the stitched panorama.

