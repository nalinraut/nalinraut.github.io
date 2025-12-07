---
title: "Traffic Sign Classifier"
excerpt: "Computer Vision - Deep Learning - July 2018"
collection: portfolio
---

![Traffic Sign Classifier]({{ '/assets/img/trafficsignclassifier/intro.jpg' | relative_url }}){:style="max-width: 500px; height: auto;"}

## Description

It is extremely necessary for a self-driving car to perceive all the traffic indications, mostly conveyed through traffic signs and act/ drive accordingly. In this project, I develop an algorithm to classify traffic signs. The project uses German Traffic Sign dataset.

Programming platform and Libraries: Python, OpenCV, Tensorflow, Pandas, Pickle.

## Methodology and Results

### Dataset

For this project, I used the German Traffic Sign dataset for classification. Following table illustrates the dataset.

![Dataset]({{ '/assets/img/trafficsignclassifier/1.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

Following are randomly picked images with their labels each from a different class.

![Random Images]({{ '/assets/img/trafficsignclassifier/output_8_0.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

#### Training Set

The figure below illustrates number of image samples per class in the training set.

![Training Samples]({{ '/assets/img/trafficsignclassifier/output_9_0.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

#### Validation Set

The figure below illustrates number of image samples per class in the validation set.

![Validation Samples]({{ '/assets/img/trafficsignclassifier/output_9_1.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

#### Testing Set

The figure below illustrates number of image samples per class in the testing set.

![Testing Samples]({{ '/assets/img/trafficsignclassifier/output_9_2.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

### Image Pre-processing

The image is first normalized to have pixel values between -1.0 to 1.0 and also have zero mean. The images are trained relatively faster with the normalization. Further, the image is converted to a grayscale color space from RGB color space. This reduces the breadth of the layering. The images are trained in batches and each batch consists of images shuffled to eliminate any bias.

### Model Architecture

#### Design

LeNet is a popular classification architecture for digits, traffic signs, etc. My design consists of layers as tabulated below.

![Architecture]({{ '/assets/img/trafficsignclassifier/2.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

#### Training and Validation

As mentioned earlier the images are trained in batches. EPOCHS or episodes are run with a single batch trained in it. Following are the parameters used for training.

* EPOCHS = 17 - After running 17 epochs there is no significant or no improvement in the accuracy.
* BATCH_SIZE = 128 - I trained the network model on a local CPU and hence preferred a low batch size of 128 images per batch.
* LEARNING RATE = 0.001 - Since Adam optimizer was used, a learning rate of 0.001 is suggested.

Following are the accuracies each for the training set, the last validation set and the testing set.

![Accuracies]({{ '/assets/img/trafficsignclassifier/3.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

The graph below shows a trade off between the training and validation accuracies considering the number of episodes run.

![Trade-off]({{ '/assets/img/trafficsignclassifier/trade.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

### Testing on Unknown Images

I picked the following 5 unknown images for testing.

![Unknown Images]({{ '/assets/img/trafficsignclassifier/web.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

The prediction for the images are tabulated as follows:

![Predictions]({{ '/assets/img/trafficsignclassifier/4.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

The probabilities for individual labels for each image are as follows:

#### 1. Image 1 - Keep Right

![Keep Right]({{ '/assets/img/trafficsignclassifier/5.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

#### 2. Image 2 - Stop

![Stop]({{ '/assets/img/trafficsignclassifier/6.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

#### 3. Image 3 - Speed limit (30km/h)

![Speed Limit]({{ '/assets/img/trafficsignclassifier/7.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

#### 4. Image 4 - Pedestrians

![Pedestrians]({{ '/assets/img/trafficsignclassifier/8.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

#### 5. Image 5 - No entry

![No Entry]({{ '/assets/img/trafficsignclassifier/9.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

## Conclusion

This project uses an architecture similar to LeNet for training purpose. An accuracy of 92.90% is obtained for the test set. The accuracy can be improved using batch normalization after every convolutional layer in the neural network model.

**Code Repository:** [GitHub](https://github.com/nalinraut/CarND-Traffic_Sign_Classifier)

