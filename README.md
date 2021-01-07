# Landscape Classification
<h3> Transfer Learning on VGG16 model using Keras </h3>

I had a dataset of 6 types of landscape: <b>Buildings, Forest, Glacier, Mountains, Sea, Street</b>

Instead of training a custom model from scratch, I used one of pretrained models available in keras, namely VGG16, pretrained on Imagenet.

<h4><p align="center">Some training samples</p></h4>

<p align="center">
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/0.jpg'/>
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/10.jpg'/>
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/16.jpg'/>
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/7.jpg'/>
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/8.jpg'/>
  <img width="150" height="175" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Images/9.jpg'/>
</p>


<hr>
After loading the pretrained model I attached 2 fully connected layers on top of it before the final classification layer. The activations for the fully connected layers were ReLu and the activation for classification layer was softmax. Categorical Cross Entropy loss was used as this was a multi-class classification problem. Stochastic gradient descent optimizer was used with a learning rate of 0.001, decay of 1e-7 and momentum of 0.9. The model was trained for 10 epochs with 64 batch size and the maximum training accuracy achieved on these settings was 98.8% while maximum validation accuracy was 91.4%. After training was finished, upon testing on previously unseen samples, test accuracy came out to be 89.6%. The results and a few of correctly classified samples are listed below.


<hr>
<p align="center">
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20ResNet50.png'/>
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20VGG16.png'/>
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20Inception.png'/>
</p>
<p align = "center">Validation and training loss progress graphs for training of models when all models were trained for 30 epochs</p>

<p align="center">
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20Inception.png'/>
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20ES%20VGG16.png'/>
  <b VGG16 based model /b>
  <img width="400" height="230" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Plot%20Inception.png'/>
</p>
<p align = "center">Validation and training loss progress graphs for training of models when all models were trained until early stopping</p>
<hr>

<hr>
<p align = "center">Tables with quantitative comparison of base models on differnt training settings are shown below</p>
<p align="center">
  <img width="700" height="300" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Training%2030%20Epochs.png'/>
  <img width="700" height="300" src='https://github.com/mhassan93/landscape-classification-TL/blob/main/Results/Training%2030%20Epochs.png'/>
</p>
<hr>
