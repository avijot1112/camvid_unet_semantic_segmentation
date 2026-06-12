# Multiclass semantic segmentation of CamVid dataset using U-Net
<div>
<img src="https://github.com/yumouwei/camvid_unet_semantic_segmentation/raw/main/animations/u-net_0001TP_2.gif" width="800" >
</div>

**_Test sequence 0001TP_2. Left to right: input image sequence, true masks, and predicted masks overlaid onto the images_**

I treated this project as an opportunity to learn the image segmentation task, including how to prepare the data, what are some of the popular models, and how to evaluate their performances. For this reason I chose a simple algorithm (i.e. U-Net) and a small enough dataset so that I can run these on my own hardware. My final model still have lots of scope of improvement but I'm still impressed by how well they work given their simple implementations. I also chose not to include the trained models in this repo (even though I kept the `./models` folder) because of their sizes (between 300~600 MB) and how easy they can be trained on basic hardwares or on Colab.

Some of the useful papers and links I referred to include:
- The original U-Net paper: https://arxiv.org/abs/1505.04597

## 1. Semantic segmentation using U-Net

The goal of semantic segmentation is to assign a label to every pixel in a image. It differs from object detection, which tries to find a bounding box for each of the detected object, and instance segmentation, which tries to assign both the semantic class and the specific object instance to each pixel. The class labels can either be binary or multiclass . For this project I focused on multiclass semantic segmentation.

One of the simpliest models for semantic segmentation is the U-Net. This network basically consists of a symmetric fully convolutional encoder-decoder network with skip connections between each encoder-decoder stage. It was originally created for segmenting biomedical images but has been applied to many other areas (probably because how easy it can be implemented). The model is trained to reproduce the given segmented masks using the input images.

## 2. Use cases-
   Biomedical Image Segmentation
   
   Autonomous Driving

## 3. Dataset
<div>
<img src="https://user-images.githubusercontent.com/46117079/235361740-4f6a6607-d2a7-48ff-893d-ed5c5226bdb9.png" width="600" >
</div>
Dataset - 12 classes including void-
CamVid -is a database for understanding road or driving scenes. It consists of 701 images and hand-annotated masks captured from 5 driving video sequences. 

## 4. Hyperparameters-
CamVid is a database for understanding road or driving scenes. It consists of 701 images and hand-annotated masks captured from 5 driving video sequences. The original dataset contains 32 semantic classes, although a 11-category classification (which combines several similar classes) is more often used in the literatures. The 701 image-mask pairs are split into 367 for training, 101 for validation, and 233 for testing.

## 5. U-Net Model Architecture-

## 6. Results
<div>
<img src="https://user-images.githubusercontent.com/46117079/235374354-f75ce977-163b-4cd6-929e-6f0700f44a55.png" width="1000" >
</div>

**_Image, true mask, predicted mask using the vanilla U-Net_**

The Model achieved remarkable accuracy of 80.38%.
