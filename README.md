# Human Emotion Recognition by a CNN (TensorFlow)

## Introduction
In this project, the aim is to implement a CNN to achieve the task of human emotion recognition from facial images. The architecture of the implemented Neural Network is as follows:<br>

| Layer  | Kernel | Activation | Output Shape
| :------------: |:---------------:|:---------------:|:---------------:|
| **Input** | - | - | 48x48x1
| **Conv2D** | 3x3x32 | ReLU | 46x46x32
| **BN** | - | - | 46x46x32
| **Conv2D** | 3x3x32 | ReLU | 44x44x32
| **BN** | - | - | 44x44x32
| **Conv2D** | 3x3x32 | ReLU | 42x42x32
| **BN** | - | - | 42x42x32
| **Conv2D** | 3x3x64 | ReLU | 40x40x64
| **BN** | - | - | 40x40x64
| **MaxPooling** | 2x2 | ReLU | 20x20x64
| **Conv2D** | 3x3x32 | ReLU | 18x18x64
| **BN** | - | - | 18x18x64
| **Conv2D** | 3x3x32 | ReLU | 16x16x64
| **BN** | - | - | 16x16x64
| **MaxPooling** | 2x2 | ReLU | 8x8x64
| **Conv2D** | 3x3x32 | ReLU | 6x6x128
| **BN** | - | - | 6x6x128
| **MaxPooling** | 2x2 | ReLU | 3x3x128
| **Conv2D** | 3x3x32 | ReLU | 1x1x128
| **Flatten** | - | - | 128
| **Dense** | - | ReLU | 7


<br>

Dataset: [FER-2013](https://www.kaggle.com/datasets/msambare/fer2013)

This dataset contains 35887 images and their corresponding labels. The images are in bytes, rather a conventional image file. Therefore, images are first read using the BytesIO method of the io library and then converted to an image using PIL. Then, they are turned into numpy arrays for easier manipulation and convenience.

There 7 classes in this dataset, each represented by a number (0-6): 0=Angry, 1=Disgust, 2=Fear, 3=Happy, 4=Sad, 5=Surprise, 6=Neutral.

All the data points are first split into 2 segments of training and test data, where test data contains 15% of the whole.
Also, during the training (fitting) phase, 5% of the training data is considered as the validation data.
## Installation

First, you'll need to clone this repository to your local drive via the following command:

```shell
$ git clone https://github.com/aylinghsr/Human_Emotion_Recognition.git
$ cd Human_Emotion_Recognition
```

Alternatively, if `git` package is not installed, you can download the zip file for this repository and then extract it.
## Requirements

This project is written in Python3 and requires Pillow, IO, Numpy, Scikit-learn, and TensorFlow.

All the required libraries can be installed by running the following command:

```shell
$ pip install -r requirements.txt
```

If the command above results in an error, you can also try:

```shell
$ python -m pip install -r requirements.txt
```
Also, the code will download the dataset automaticly on your computer.
## Results
The designed and implemented CNN gets trained on the training data on 15 epochs. After this, it achieves an accuracy of 0.9313 on the training data, 0.5773 on the validation data, and 0.5804 on the test data.
