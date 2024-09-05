# Anti-Spoofing-System
This Repository Contains the Implementation of my Final Project for the Course Fundamentals of Computer Vision taken during the Spring 2024 Semester at the School of Computer Engineering at Iran University of Science and Technology.

## Project Description
The purpose of this project is to develop an anti-spoofing algorithm to detect the liveness of a face in a video, in which a frame of the video is taken and it is determined whether the image belongs to a live person or not. For example, the picture has makeup on the person or is a printed picture of him or maybe the picture is playing from another device or not. For this purpose, I was asked to use two approaches: 
1. Using the old-fashioned ML by extracting features from the vidoe frames(features such as frequency, texture, person's liveliness signs, et cetera)
2. Using Deep Learning-based approaches and architectures
For each of the approaches a model was trained and then tested on the corresponding dataset.

## Used Datasets
- [CelebA-Spoof Dataset](https://github.com/ZhangYuanhan-AI/CelebA-Spoof): Consists of images, containing both real and spoofed faces.

## Libraries and Tools
- **Python**: `PyTorch`, `scipy`, `tensorflow`, `opencv`, `numpy`, `pandas`, `matplotlib`
- **Deep Learning Architecture**: MobileNet used for feature extraction and classification tasks.

### 1. Deep Learning Model
- **Model Architecture**: Images are fed into a MobileNet model with pre-trained weights of ImageNet, which is used for classification. Also there is another block defined as the Fourier Transform block containing Linear, Convolutional, Residual and Depthwise Convolution block that tries to extract hidden features related to the Fourier Transformation of the image.
- **Training and Testing**: The model is trained on the CelebA-Spoof training part dataset.

### 2. Feature Engineering
- **Face Detection**: The face in the input video or image is detected using the Cascade classifier.
- **Texture Analysis**: Techniques like LBP are applied to analyze the texture of the detected face.
- **Model Architecture**: The extracted features are then passed into the mobileNet but this time there is no FTGenerator Block.
- **Training and Testing**: The model is trained on the CelebA-Spoof dataset.
- **Classification**: Trained model outputs a prediction, indicating whether the face is real or spoofed.

## Document and Files
To view the project's document click [here](https://github.com/iMahdiGhazavi/Anti-Spoofing-System/blob/main/CV_Final_Project_Document.pdf). *This ducument is in Persian.*

## References
- [CelebA-Spoof Dataset](https://github.com/ZhangYuanhan-AI/CelebA-Spoof)
- [Anti-Spoofing Documentation](https://antispoofing.org/face-recognition-methods-complete-overview/)
