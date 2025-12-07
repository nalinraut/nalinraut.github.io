---
layout: post
title:  "Scene Recognition using Transfer Learning"
excerpt: "Computer Vision"
project: true
duration: "October 2017 - December 2017"
---

![image-title-here](/assets/img/cv1.jpeg){:class="img-responsive width=176 height=71"}   
<br/>
<center><h3>Description</h3></center>
<hr class="star-primary">
<p style="text-align: justify">The project includes scene recognition including different scene categories such as: Kitchen, Bedroom, and Corridor. Furthermore, implementing different classification techniques and comparing them is also part of our study. The project attempts to solve this problem using Convolutional Neural Networks. This project also utilizes and compares various approaches such as Transfer Learning and the bag-of-words model for the purpose of indoor scene recognition.</p>


<center><h3>Methodology</h3></center>
<hr class="star-primary">
<p style="text-align: justify">- Implemented Transfer Learning using a pre-trained Convolutional Neural Network. <br/> 
- Additionally, designed a Convolutional Neural Network model from scratch in MATLAB <br/>
- Compared the above mentioned approaches, earlier implemented Nearest Neighbour and SVM classifier approaches.</p>


<center><h3>Results</h3></center>
<hr class="star-primary">
<p style="text-align: justify"> The results of the study are listed in the table below. </p>

![image-title-here](/assets/img/tabular_CV.png){:class="img-responsive width=176 height=71"}  <br/><br/>


<p style="text-align: justify">I. Confusion Matrix (Bag of Features with Nearest Neighbor Classifier). The figure below shows confusion matrix for scene classification using Bag of Features with Nearest Neighbor Classifier: </p> 
![image-title-here](/assets/img/BoW_NN.png){:class="img-responsive width=176 height=71"}  <br/><br/>

<br/><br/>

<p style="text-align: justify">II. Confusion Matrix (Bag of Features with SVM Classifier). The figure below shows confusion matrix for scene classification using Bag of Features with SVM Classifier: </p> 
![image-title-here](/assets/img/BoW_SVM.png){:class="img-responsive width=176 height=71"}  

<br/><br/>

<p style="text-align: justify">III. Confusion Matrix (CNN built from scratch). The figure below shows confusion matrix for scene classification using CNN designed from scratch : </p> 
![image-title-here](/assets/img/CNN_scratch.png){:class="img-responsive width=176 height=71"}  

<br/><br/>

<p style="text-align: justify">IV. Confusion Matrix (Transfer Learning with a Pre-Trained CNN). The figure below shows confusion matrix for scene classification using Transfer Learning with a pre-trained network.: </p> 
![image-title-here](/assets/img/CNN_TL.png){:class="img-responsive width=176 height=71"}  



<center><h3>Conclusion</h3></center>
<hr class="star-primary">

<p style="text-align: justify">Through this project, we learned all about the intricacies of convolutional neural networks and their use in image recognition tasks. Based on the comparative results, we concluded that Neural Networks perform better than other classification methods used in this project for the purpose of indoor scene recognition. We also saw that the bag-of-words model was more confident in classifying images from the kitchen, whereas the CNNs were most confident about classifying corridors. Another important observation was that to improve the accuracy of CNNs, a huge dataset of objects or scenes is required.</p>

<hr class="star-primary">
                            
<ul id ="horizontal-list">
<li class="display: inline">
<strong><a target="_blank"  href="https://github.com/nalinraut/Indoor-Scene-Recognition">Code Repository Link <i class="fa fa-fw fa-github"></i></a>
</strong>
</li>
                                
                                
<li>
<strong><a href="javascript:void(0);">Project-Report</a>
</strong>
</li>
                                
</ul>
     

