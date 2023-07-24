
# Real-Time Emotion Detection iOS App with Machine Learning

![App Demo](images/cover-image.png)

This repo contains a real-time facial emotion detection iOS application developed as a personal project. The app utilizes CoreML with SwiftUI to provide an intuitive and interactive user experience.

This project builds a convolutional neural network (CNN) model to classify facial expressions from pixel images of faces. The model is trained and evaluated on the [ICML 2013 Face Expression Recognition Challenge](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge) dataset.


## Data

The dataset contains 35,887 grayscale 48x48 pixel face images with 7 emotions (angry, disgust, fear, happy, sad, surprise, neutral). The data is split into train, validation, and test sets. 

## Model

A CNN model with the following architecture is defined:

- Conv2D layers
- MaxPooling
- Dropout 
- Batch normalization
- Dense layers
- Softmax output layer

The model is trained for 50 epochs using the Adam optimizer and categorical cross-entropy loss.

## Results 

The model achieves the following accuracy on the test set:

[](images/accuracy.png)
This indicates some overfitting on the training data. 

Analysis of individual test image predictions shows the model is generally able to predict the correct expression, but struggles with some subtle/ambiguous expressions.  The model performs very well for the "happy" class and reasonably well for other expressions, but commonly confuses "disgust", "fear", and "sadness".

[](images/accuracy2.png)
[](images/accuracy3.png)
[](images/accuracy4.png)

Overall the model achieves decent but not excellent performance on this dataset. Some ways to potentially improve accuracy include tuning hyperparameters, training on more data, and exploring different model architectures.

## Installation

To run the iOS application, follow these steps:

1. Clone the repository to your local machine.

```bash
$ git clone https://github.com/andr3wV/CoreMLEmotionDetect.git
```

2. Open the project in Xcode.

3. Ensure you have the necessary dependencies installed. If any are missing, use CocoaPods or Swift Package Manager to install them.

4. Build and run the app on a connected iOS device or simulator.

To train the model, follow these steps:

1. Install the notebook dependencies
```bash
$ pip install -r requirements.txt
```
2. Download the training data from [this dataset](https://www.kaggle.com/competitions/challenges-in-representation-learning-facial-expression-recognition-challenge/overview)
4. Open the Jupyter Notebook 
	> facial_expression_recognition.ipynb
	
5. Run the notebook

## How to Use

1. Launch the application on your iOS device.

2. Grant necessary permissions for camera access.

3. Point the front camera at a human face.

## Contributing

Contributions to this project are welcome! If you find any bugs or have suggestions for improvements, please feel free to open an issue or submit a pull request. Also, if someone want to work on the UI, that would be greatly appreciated!

---
