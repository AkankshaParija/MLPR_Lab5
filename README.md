# MLPR_Lab5

# Aim: 
The objective of this project is to build an automated pipeline to detect human faces from a group photograph and perform unsupervised machine learning to cluster them based on their color profiles (Hue and Saturation). This project demonstrates the integration of classical Computer Vision (Haar-Cascades) with statistical clustering (K-Means).

# Methodology  
1. Image Preprocessing: 
The input image Plaksha_Faculty.jpg was loaded using the OpenCV library.
<img width="1166" height="776" alt="Screenshot 2026-02-14 at 9 57 52 PM" src="https://github.com/user-attachments/assets/2b425e2c-9ec7-4390-b5e7-018bcb92aa31" />

The image was converted from BGR to Grayscale to simplify the data for the face detection algorithm.

3. Face Detection: 
A Haar-Cascade classifier (haarcascade_frontalface_default.xml) was utilized to identify facial regions.
The detectMultiScale method was tuned with specific parameters (scaleFactor=1.05, minNeighbors=4) to accurately detect 30 faces in the group setting.

5. Feature Extraction: 
The detected facial regions were converted into the HSV (Hue, Saturation, Value) color space.
Mean Hue and Saturation values were extracted for each face to represent their unique color signatures, avoiding the influence of varying light intensity (Value).

6. K-Means Clustering: 
The K-Means algorithm was applied to the extracted features to group the faces into distinct clusters (e.g., K=3).
Centroids for each cluster were calculated to represent the "average" color profile of that group.

7. Template Matching: 
A template image of Dr. Shashi Tharoor(Dr_Shashi_Tharoor.jpg) was processed through the same pipeline.
<img width="396" height="390" alt="Screenshot 2026-02-14 at 9 58 33 PM" src="https://github.com/user-attachments/assets/31c2c6dd-c069-440e-84c7-54059d602dfa" />

The model predicted the template's cluster based on its Euclidean distance to the established centroids.

# KEY FINDINGS
(A) Detector Performance: The Haar-cascade successfully identified 30 faces in a complex group environment, though it required precise parameter tuning for scale and neighbor density.
<img width="1005" height="672" alt="Screenshot 2026-02-14 at 9 45 01 PM" src="https://github.com/user-attachments/assets/f716fe66-1a29-4cbf-9614-ca8aec7b3881" />

(B) Color Grouping: The K-Means algorithm effectively separated faces into clusters that reflect different lighting conditions and skin tones.

<img width="832" height="454" alt="Screenshot 2026-02-14 at 9 45 32 PM" src="https://github.com/user-attachments/assets/a50f29c6-041d-4004-a4b0-2f4c272c3b2f" />


(C) Template Prediction: The template image was mathematically assigned to Cluster 0 , confirming its color similarity to that specific faculty subgroup.

<img width="836" height="453" alt="Screenshot 2026-02-14 at 9 51 47 PM" src="https://github.com/user-attachments/assets/7e1d2095-96f5-4ec5-929c-d1421ce95d6c" />



# CONCLUSION
This project highlights the power of combining traditional Computer Vision with machine learning. By transforming images into the HSV space, we achieved a more robust color analysis that is less sensitive to lighting variations. This pipeline has significant real-world applications in facial recognition, image organization, and automated biometric systems.
