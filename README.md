# brain tumor vision
Brain_Tumor_Vision  is an end-to-end deep learning project for brain tumor detection and segmentation from MRI images. The project combines CNN-based classification, U-Net segmentation, and an advanced hybrid model that integrates patient clinical metadata to improve tumor localization accuracy

# Project Overview
This repository contains three main components:

- Tumor Detection (Classification): Binary classification to determine whether a brain MRI contains a tumor or not.

- Tumor Segmentation : Pixel-level segmentation using a U-Net architecture to precisely localize tumor regions.

- Hybrid Segmentation with Patient Metadata : An enhanced U-Net model that integrates MRI images with clinical patient data using FiLM conditioning for improved segmentation performance.

## 1. Tumor Detection (CNN)

### Description
CNN model built with TensorFlow/Keras to classify brain MRI images into Tumor or No Tumor.

### Key Points
- Image resizing (128×128) and normalization  
- CNN with Convolution + MaxPooling layers  
- Dropout for regularization  
- Sigmoid output for binary classification  
- Early stopping at 99% training accuracy  

### Performance
- Test Accuracy: ~88%  
- Loss Function: Binary Cross-Entropy  
- Optimizer: Adam

----

## 2. Tumor Segmentation (U-Net)

### Description
Pixel-wise tumor segmentation using a U-Net model implemented in PyTorch.

### Dataset
- LGG Brain MRI dataset  
- MRI images with corresponding ground-truth segmentation masks  

### Key Points
- Custom PyTorch Dataset class  
- Albumentations data augmentation  
- Encoder–decoder U-Net with skip connections  

### Training
- Loss: Binary Cross-Entropy  
- Optimizer: Adam  
- Epochs: 15  

----

## 3. Hybrid MRI + Clinical Metadata Model

### Description
Hybrid U-Net combining MRI images and patient clinical metadata to enhance segmentation quality.

### Techniques
- Missing value imputation  
- Feature normalization (MinMaxScaler)  
- FiLM conditioning for metadata-guided feature modulation  
- Metadata fusion at the bottleneck layer  

### Advantages
- Improved segmentation accuracy  
- Clinically informed predictions

----

## Technologies Used

### Detection
- Python  
- TensorFlow / Keras  
- OpenCV  
- NumPy, Pandas  
- Matplotlib, Seaborn  

### Segmentation
- PyTorch  
- Albumentations  
- Torchvision  
- TorchMetrics  
- OpenCV  
- Scikit-learn  
