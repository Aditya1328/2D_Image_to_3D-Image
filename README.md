# 2D_Image_to_3D-Image

## Libraries used:

1. Numpy
2. Matplotlib
3. Torch
4. PIL ,Image
5. Transformers (GLPNImageProcessor,GLPNForDepthEstimation)
6. Open3d

## Steps

Step 1: Load Pretrained Depth Estimation Model

GLPNImageProcessor prepares input images into the required format (tensor, normalization, etc.)
GLPNForDepthEstimation performs the actual inference to produce a depth map.

Step 2: Image Loading and Resizing

Open the image using the Python Imaging Library (PIL). Since GLPN expects input sizes to be divisible by 32 (due to convolution operations), we resize the image accordingly.

Step 3: Depth Prediction

The preprocessed image is passed to the model, and the predicted depth map is retrieved. The output is scaled and padded.
Then visualized the input image and the depth prediction side-by-side using Matplotlib.

Step 4: Convert Depth to RGB-D

The depth map is normalized and converted to an 8-bit image. It is combined with the RGB image to create an Open3D RGBDImage. Then, using a pinhole camera model with intrinsic parameters, a 3D point cloud is created.

Step 5: Visualize in 3D

Step 6: Mesh Reconstruction

Step 7: Saving image as .OBJ File

The thought process behind this program is to convert a single 2D image into a realistic 3D mesh by using deep learning and 3D reconstruction techniques.The image is resized to meet model requirements, and the predicted depth map is combined with the RGB image to form a structured RGB-D image.This is then transformed into a 3D point cloud using virtual camera intrinsics.The point cloud is cleaned, normals are estimated, and a 3D mesh is reconstructed using Poisson surface reconstruction.
I thought this would generate clear image but background of image has lot of noise and I am unable to clear that noise. The focused part is clear. Then download as .obj file.


![3D image](https://github.com/user-attachments/assets/9c40c8c5-af09-45c5-8556-174525ea1fd7)

