---
layout: single
title:  "Traffic Sign Classifier"
duration:  "July 2018" 
excerpt: "Computer Vision - Deep Learning"
project: true
---

[//]: # (Image References)

[image0]: /assets/img/trafficsignclassifier/intro.jpg
[image1]: /assets/img/trafficsignclassifier/output_8_0.png
[image2]: /assets/img/trafficsignclassifier/output_9_0.png
[image3]: /assets/img/trafficsignclassifier/output_9_1.png
[image4]: /assets/img/trafficsignclassifier/output_9_2.png
[image5]: /assets/img/trafficsignclassifier/trade.png
[image6]: /assets/img/trafficsignclassifier/web.png
[image7]: /assets/img/trafficsignclassifier/1.png
[image8]: /assets/img/trafficsignclassifier/2.png
[image9]: /assets/img/trafficsignclassifier/3.png
[image10]: /assets/img/trafficsignclassifier/4.png
[image11]: /assets/img/trafficsignclassifier/5.png
[image12]: /assets/img/trafficsignclassifier/6.png
[image13]: /assets/img/trafficsignclassifier/7.png
[image14]: /assets/img/trafficsignclassifier/8.png
[image15]: /assets/img/trafficsignclassifier/9.png
---
![Intro][image0]
<br/>
<center><h3>Description</h3></center>
<hr class="star-primary">
<p style="text-align: justify"> It is extremely necessary for a self-driving car to perceive all the traffic indications, mostly conveyed through traffic signs and act/ drive accordingly. In this project, I develop an algorithm to classify traffic signs.The project uses German Traffic Sign dataset. <br/>
Programming platform and Libraries: Python, OpenCV, Tensorflow, Pandas, Pickle.</p>


<center><h3>Methodology and Results </h3></center>
<hr class="star-primary">


### Dataset

For this project, I used the German Traffic Sign dataset for classification. Following table illustrates the dataset.
![Intro][image7]



Following are randomly picked images with their labels each from a different class.
![Intro][image1]

#### Training Set

The figure below illustrates number of image samples per class in the training set.
![Training Samples][image2]

#### Validation Set

The figure below illustrates number of image samples per class in the validation set.
![Validation Samples][image3]

#### Testing Set

The figure below illustrates number of image samples per class in the testing set.
![Testing Samples][image4]



### Image Pre-processing

The image is first normalized to have pixel values between -1.0 to 1.0 and also have zero mean. The images are trained relatively faster with the normalization.  Further, the image is converted to a grayscale color space from RGB color space. This reduces the breadth of the layering. The images are trained in batches and each batch consists of images shuffled to eliminate any bias. 


### Model Architecture

#### Design

LeNet is a popular classification architecture for digits, traffic signs, etc. My design consists of layers as tabulated below.

![Intro][image8]

#### Training and Validation 

As mentioned earlier the images are trained in batches. EPOCHS or episodes are run with asingle batch trained in it. Following are the parameters used for training.

EPOCHS = 17 
After running 17 epochs there is no significant or no improvement in the accuracy.

<br/> 
BATCH_SIZE    = 128
I trained the network model on a local CPU and hence preferred a low batch size of 128 images per batch.

<br/>
LEARNING RATE = 0.001 
Since Adam optimizer was used, a learning rate of 0.001 is suggested.

<br/>

Following are the accuracies each for the training set, the last validation set and the testing set.

![Intro][image9]

The graph below shows a trade off between the training and validation accuracies considering the number of episodes run.

![Testing Samples][image5]

### Testing on Unknown Images

I picked the following 5 unknown images for testing.

![Testing Samples][image6]

The prediction for the images are tabulated as follows :

![Intro][image10]


The probabilities for individual labels for each image are as follows :

#### 1. Image 1 - Keep Right

![Intro][image11]

#### 2. Image 2 - Stop

![Intro][image12]

#### 3. Image 3 - Speed limit (30km/h)

![Intro][image13]

#### 4. Image 4 - Pedestrians

![Intro][image14]

#### 5. Image 5 - No entry

![Intro][image15]





<center><h3>Conclusion</h3></center>
<hr class="star-primary">

<p style="text-align: justify"> This project uses an architecture similar to LeNet for training purpose. An accuracy of 92.90% is obtained for the test set. The accuracy can be improved using batch normalization after every convolutional layer in the neural network model.  </p>

<hr class="star-primary">
                            
<ul id ="horizontal-list">
<li class="display: inline">
<strong><a target="_blank"  href="https://github.com/nalinraut/CarND-Traffic_Sign_Classifier">Code Repository Link <i class="fa fa-fw fa-github"></i></a>
</strong>
</li>
                                
                                
<!-- <li>
<strong><a href="javascript:void(0);">Project-Report</a>
</strong>
</li> -->
                                
</ul>
     

