# MLND Capstone - Number Translator Android App. 

## Overview 

<img src="img1_readme.png" alt="eample phone image" width="300" height="500">

This is an android application which can translate images of multi-digit numbers taken from phone camera into word form as shown above. 

The project had the following parts.

1) Computer vision techniques using OpenCV for Android (thresholding, canny edge detection, contour selection etc) to properly segment each digit. The application was robust to various lighting conditions and also to numbers written in different colors and orientation. 

2) Trained a Deep Convolutional Neural Network using Tensorflow on the MNIST dataset. Got an accuracy of 99.2%. 

3) Integrated the Tensorflow model with the Android application using Java Native Interface. 

4) Pass the segmented digits to the model for recognition. 

This app will currently only work with images taken on a light background (like a whiteboard)

## Report 
Due to formatting issues while converting to PDF format, please go to the following link to access the report for this project. 

https://docs.google.com/document/d/1qpQmtVZ_7zrX1p2IG9v8KHbXRqBmGPrC-Hn8zdmBjZU/edit?usp=sharing

## Source Code
Trainer script written in Python using Tensorflow APIs to create the deep model. Located in trainer/
- `Trainer.ipynb`

The Java code for the app is located in
app/src/main/java/com/udacity/mlndcapstone/numtrans/
- `DigitDetector.java`
- `IOUtils.java`
- `ImageProcessor.java`
- `MainActivity.java`
- `NumberToWordConv.java`
- `RoiObject.java`


## Requirements

This project requires **Python 2.7** and the following installed:

- [TensorFlow](http://www.tensorflow.org/)
- [NumPy](http://www.numpy.org/)
- [matplotlib](http://matplotlib.org/)
- [scikit-learn](http://scikit-learn.org/stable/)
- [SciPy library](http://www.scipy.org/scipylib/index.html)
- [Pillow](http://pypi.python.org/pypi/Pillow/)
- [Jupyter Notebook](http://ipython.org/notebook.html)
- Android Studio to install the APK of the app into the device.

In addition to this, you would need an android mobile phone with minimum SDK > 22. 


## Run

Open `Ipython Notebook` in the trainer folder. Then open Trainer.ipynb and run it for performing the training. This takes a long time depending on the speed of the computer.  

You can directly run the app on an android phone by downloading the APK and using adb to install it onto the phone.

- [NumTrans.apk](https://drive.google.com/open?id=0B9YEn7soJLyVVGt0dDh1MFdhdms)

Enable USB Debugging on the android device and then use ADB to install  the apk

adb install -r NumTrans.apk

The app will be loaded initially with two buttons. Click the Take Photo button. This should redirect to the Camera App of the phone.
Since the App was tested on only numbers written on a WhiteBoard, I recommend trying it on that first.  

Once the photo is clicked, it will return to the app. Click on the next photo button which will show you the original, pre-processed image and the final
image with segmented digits and the word translation. 

